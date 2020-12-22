---
solution: Campaign Standard
product: campaign
title: Solução de problemas de SMS
description: Solução de problemas de SMS
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 80e4f752a1b9b6c8b0125a502c05c19796e98104
workflow-type: tm+mt
source-wordcount: '2696'
ht-degree: 0%

---


# Solução de problemas de SMS {#sms-troubleshooting}

## Conflito entre contas externas diferentes {#external-account-conflict}

Se a instância tiver várias contas externas SMS, verifique se os problemas não são causados por um conflito entre contas externas.

A Adobe Campaign trata as contas externas como entidades independentes.

Se você tiver várias contas, siga este procedimento para isolar a conta externa que está causando problemas:

1. Desative todas as contas externas.
1. Habilite uma conta externa.
1. Tente reproduzir o problema.
1. Se o problema inicial nem sempre aparecer, faça uma quantidade razoável de tentativas antes de concluir.
1. Se o problema não aparecer com essa única conta, desative-a e reinicie para a etapa 2 na próxima conta.

Depois de marcar cada conta individualmente, há 2 cenários possíveis:

* **O problema apareceu em uma ou várias contas**

   Nesse caso, você pode aplicar outros procedimentos de solução de problemas em cada conta individualmente. É melhor desativar outras contas ao diagnosticar uma conta para reduzir o tráfego de rede e o número de registros.

* **O problema não era exibido quando apenas uma conta estava ativa a qualquer momento**

   Você tem um conflito entre contas. Como mencionado anteriormente, a Adobe Campaign trata as contas individualmente, mas o provedor pode tratá-las como uma única conta.

   * Você está usando diferentes combinações de logon/senha entre todas as suas contas.
Você terá que entrar em contato com o provedor para diagnosticar possíveis conflitos do lado deles.

   * Algumas contas externas compartilham a mesma combinação de logon/senha.
O provedor não tem como saber de qual conta externa o `BIND PDU` vem, então eles tratam todas as conexões de várias contas como uma única. Eles podem ter roteado MO e SR aleatoriamente nas duas contas, causando problemas.
Se o provedor suportar vários códigos curtos para a mesma combinação de logon/senha, você terá que perguntar a eles onde colocar esse código curto no `BIND PDU`. Observe que essa parte das informações deve ser colocada dentro de `BIND PDU`, e não em `SUBMIT_SM`, já que `BIND PDU` é o único local que permitirá aos roteamentos MOs corretamente.
Consulte a seção [Informações em cada tipo de PDU](../../administration/using/sms-protocol.md#information-pdu) acima para saber qual campo está disponível em `BIND PDU`, normalmente você adiciona o código curto em `address_range`, mas isso requer suporte especial do provedor. Entre em contato com eles para saber como eles esperam rotear vários códigos curtos independentemente.
A Adobe Campaign suporta a manipulação de vários códigos curtos na mesma conta externa.

## Problema com a conta externa em geral {#external-account-issues}

* Verifique se o conector foi alterado recentemente e por quem (verifique as Contas externas como um grupo).

   ```
   select saccount, (sserver ||':'||sport) as serverPort, iextaccountid, CASE WHEN N0.iactive=1 THEN 'Yes' ELSE 'No' END as "(x) Enabled",
   
   (select X1.sname from xtkoperator X1 where N0.icreatedbyid = X1.ioperatorid) as "Created By",
   
   (select X1.sname from xtkoperator X1 where N0.imodifiedbyid = X1.ioperatorid) as "Last Modified By",
   
   N0.slabel as "External Account", N0.tslastmodified as "LastModifiedDate"
   
   from nmsextaccount N0 LEFT JOIN xtkoperator X0 ON (N0.icreatedbyid=X0.ioperatorid) order by 8 DESC LIMIT 50;
   ```

* Investigue (no diretório /postupgrade) se o sistema foi atualizado e quando
* Verifique se algum pacote que afete o SMS pode ter sido atualizado recentemente (/var/log/dpkg.log).

## Problema ao conectar-se ao provedor {#issue-provider}

* Se `BIND PDU` retornar um código diferente de zero `command_status`, peça mais informações ao provedor.

* Verifique se a rede está configurada corretamente para que a conexão TCP possa ser feita com o provedor.

* Peça ao provedor para verificar se eles adicionaram corretamente os IPs à lista de permissões da instância do Adobe Campaign.

* Verifique as configurações de **Conta externa**. Pergunte ao provedor o valor dos campos.

* Se a conexão for bem-sucedida, mas instável, verifique a seção [Problema com conexões instáveis](../../administration/using/troubleshooting-sms.md#issues-unstable-connection).

* Se problemas de conexão forem difíceis de diagnosticar, uma captura de rede pode fornecer informações. Verifique se a captura de rede é executada simultaneamente enquanto o problema aparece para ela pode ser analisado com eficiência. Você também deve observar a hora exata em que o problema aparece.

## Problemas com conexão instável {#issues-unstable-connection}

Uma conexão é considerada instável se qualquer uma das seguintes situações ocorrer:

* Reiniciar o MTA corrigirá os problemas temporariamente. Isso significa que uma conexão instável aciona o controle MTA no Adobe Campaign Standard, reiniciando o MTA para limpar o controle. Acontecerá novamente até que a causa raiz seja encontrada.

* O provedor envia `UNBIND PDU`s.

* `enquire_link` expira, no Adobe Campaign ou no provedor. Nesse caso, você pode ver `ENQUIRE_LINK_RESP` com um código de erro diferente de zero.

* Há muitos `BIND PDU`s. Não deve haver mais do que alguns durante um dia, dependendo do número de conexões. Mais de 1 PDU BIND por hora deve estar alertando.

Como corrigir problemas de estabilidade de conexão:

* Conexões instáveis raramente são a causa principal, muitas vezes são o resultado de outro problema que aciona uma desconexão. Encontrar a causa raiz é a prioridade.

* Ative rastreamentos SMPP detalhados. Você precisará que eles vejam o que está acontecendo quando a conexão for reiniciada.

* Se o provedor enviar `BIND PDU`s, algo pode estar errado. Pergunte ao seu provedor por que `UNBING` é enviado.

* Fazer uma captura de rede às vezes é a única maneira de ver como a conexão é fechada.

* Se o provedor fechar as conexões enviando um pacote `TCP FIN` ou `TCP RST`, pergunte ao provedor mais informações.

* Se o provedor fechar a conexão depois de enviar um erro limpo, como `DELIVER_SM_RESP`, com um código de erro, ele deverá corrigir o conector, caso contrário isso impedirá que outros tipos de mensagens sejam transmitidas e acionará a limitação MTA. Isso é especialmente importante no modo transceptor, onde o fechamento da conexão afeta tanto o MT quanto o SR.

## Problema ao enviar um MT (SMS normal enviado para um usuário final){#issue-MT}

* Verifique se a conexão está estável. Uma conexão SMPP deve permanecer ativa por pelo menos 1 hora continuamente. Consulte a seção [Problema com conexões instáveis](../../administration/using/troubleshooting-sms.md#issues-unstable-connection).

* Se reiniciar o MTA fizer com que o envio do MT funcione novamente por um pequeno período de tempo, provavelmente você terá uma limitação devido a uma conexão instável. Consulte a seção [Problema com conexões instáveis](../../administration/using/troubleshooting-sms.md#issues-unstable-connection).

* Verifique se o log amplo está presente e no status correto com as datas corretas. Se não for, pode ser um problema de preparação de delivery ou delivery.

* Verifique se o MTA realmente processa a mensagem. Se não for o caso, isso pode não ser um problema de SMS.

* Verifique se o conector SMS está ligado ao equipamento do fornecedor. Solicite feedback ao provedor para garantir que todos os sistemas estejam se comunicando corretamente. Consulte `BIND_TRANSMITTER` e `BIND_TRANSCEIVER PDU`s para obter informações sobre o processo de vinculação. Talvez seja necessário ativar os rastreamentos SMPP para solucionar problemas corretamente.

* Com os rastreamentos SMPP ativados, verifique se `SUBMIT_SM PDU` contém as informações certas.

* Verifique se o provedor responde com um `SUBMIT_SM_RESP PDU` com um valor &quot;OK&quot; (código 0). Verifique se a PDU chega com um atraso razoável: qualquer coisa superior a 1 segundo deve ser discutida com o provedor, geralmente chega em menos de 100 ms.

* Se todas essas etapas funcionarem, você pode ter certeza de que o problema está no lado do provedor. Eles terão que solucionar problemas em sua plataforma.

* Se funcionar, mas o throughput for inconsistente, tente ajustar a janela de envio e diminuir o throughput do MT. Você precisará trabalhar com o provedor para ajustar isso. A Adobe Campaign pode enviar mensagens muito rapidamente para que problemas de desempenho possam surgir no equipamento do provedor.

## MT são duplicados (o mesmo SMS é enviado várias vezes seguidas){#duplicated-MT}

Duplicados são frequentemente causados por tentativas. É normal ter duplicados ao tentar novamente mensagens, você deve tentar remover a causa raiz do tentativas.

* Se você vir duplicados enviados com um intervalo de exatamente 60 segundos, provavelmente é um problema do lado do provedor, eles não enviam um `SUBMIT_SM_RESP` com rapidez suficiente.

* Se vir muitos `BIND/UNBIND`, você tem uma conexão instável. Consulte a seção [Problema com conexões instáveis](../../administration/using/troubleshooting-sms.md#issues-unstable-connection) para obter soluções antes de tentar resolver problemas de mensagens de duplicado.

Diminuindo a quantidade de duplicados quando há uma nova tentativa:

* Abaixe a janela de envio. A janela de envio deve ser grande o suficiente para cobrir a latência `SUBMIT_SM_RESP`. Seu valor representa o número máximo de mensagens que podem ser duplicadas se ocorrer um erro enquanto a janela estiver cheia.

## Problema ao processar SR (recebimentos de delivery) {#issue-process-SR}

* Você precisará de rastreamentos SMPP ativados para fazer qualquer tipo de solução de problemas SR.

* Verifique se `DELIVER_SM PDU` provém do provedor e se ele está bem formado.

* Verifique se a Adobe Campaign responde com êxito `DELIVER_SM_RESP PDU` em tempo hábil. No Adobe Campaign Standard, isso garante que toda a lógica de processamento tenha sido aplicada, se esse não for o caso, é garantido que haja uma mensagem de erro nos logs explicando por que o processamento falhou.

Se `DELIVER_SM PDU` não for confirmado com êxito, verifique o seguinte:

* Verifique o regex relacionado à extração de ID e ao processamento de erros na Conta externa ****. Talvez seja necessário validá-los em relação ao conteúdo de `DELIVER_SM PDU`.

* Verifique se os erros foram devidamente provisionados na tabela `broadLogMsg`.

* Para Adobe Campaign Standard, verifique se as tabelas `broadLog` e `broadLogExec` estão sincronizadas corretamente.

Se você corrigiu tudo, mas alguns SR inválidos ainda estão nos buffers do provedor, é possível ignorá-los usando a opção **ID inválida reconhecendo count**. Isso deve ser usado com cuidado e redefinido para 0 o mais rápido possível depois que os buffers estiverem limpos.

## Problema ao processar o MO (e lista negra/resposta automática){#issue-process-MO}

* Habilitar rastreamentos SMPP durante testes. Se você não ativar o TLS, deverá fazer uma captura de rede ao solucionar problemas do MO para verificar se as PDUs contêm as informações corretas e estão formatadas corretamente.

* Ao capturar tráfego de rede ou analisar rastreamentos SMPP, certifique-se de capturar toda a conversa com o MO e seu MT de resposta se uma resposta estiver configurada.

* Se o MO (`DELIVER_SM PDU`) não aparecer nos rastreamentos, o problema está no lado do provedor. Eles terão que solucionar problemas em suas plataformas.

* Se `DELIVER_SM PDU` for exibido, verifique se ele foi confirmado pela Adobe Campaign com um `DELIVER_SM_RESP PDU` bem-sucedido (código 0). Esse RESP garante que toda a lógica de processamento foi aplicada pela Adobe Campaign (resposta automática e permitir/lista de bloqueios). Se esse não for o caso, procure uma mensagem de erro nos registros MTA.

* Se as respostas automáticas estiverem ativadas, verifique se `SUBMIT_SM` foi enviado para o provedor. Caso contrário, é garantido encontrar uma mensagem de erro nos registros MTA.

* Se o `SUBMIT_SM MT PDU` que contém a resposta for encontrado nos rastreamentos, mas o SMS não chegar ao telefone celular, você terá que entrar em contato com o provedor para obter assistência na solução de problemas.

## Problema durante a preparação do delivery não excluindo recipient em quarentena (em quarentena pelo recurso de resposta automática) {#issue-delivery-preparation}

* Verifique se o formato do número de telefone é exatamente o mesmo na tabela quarentena e no registro de delivery.  Caso contrário, consulte esta [seção](../../administration/using/sms-protocol.md#automatic-reply) se tiver problemas com o prefixo plus do formato de número de telefone internacional.

* Verifique os códigos curtos. As exclusões podem ocorrer se o código curto do recipient for igual ao definido na conta externa ou se estiver vazio (vazio = qualquer código de atalho). Se apenas um código curto for usado para a instância inteira do Adobe Campaign, será mais fácil deixar todos os campos **código curto** vazios.

## Problemas de codificação {#encoding-issues}

**Etapa 1: Entre em contato com o provedor**

Entre em contato com eles e veja o que há de errado com eles. Eles devem ser capazes de dizer se o problema está do lado deles ou do lado do Adobe Campaign. Se o problema estiver no Adobe Campaign, eles devem saber exatamente qual campo está incorreto.

**Etapa 2: Saiba o que está em sua mensagem**

O Unicode permite muitas variantes para caracteres semelhantes e o Adobe Campaign não pode lidar com todos eles.

A fonte de problemas mais comum é uma colagem de cópia de um processador de texto, que altera os caracteres comuns para versões tipograficamente corretas: espaços alterados para espaços não separáveis, aspas de duplo alteradas para aspas de abertura e fechamento, sinais de menos alterados para vários tipos de hífens etc.

Não copie e cole sua mensagem ao testar, sempre digite-a diretamente na interface.

Com o hexadecimal, é possível diferenciar entre caracteres semelhantes. Um L minúsculo, um I maiúsculo, O, 0, todos os tipos diferentes de aspas, codificações não latinas ou até mesmo tipos diferentes de espaços podem parecer iguais ou mesmo não ser exibidos.

Para converter o unicode em hexadecimal, você pode usar ferramentas online, como o [site do conversor de código Unicode](https://r12a.github.io/app-conversion/). Digite o texto, verifique se não há PII, como números de telefone, e clique em **Converter**. Você verá os valores hexadecimais na parte inferior (zona UTF-32).

Ao abrir tíquetes sobre problemas de codificação, com o provedor ou com o suporte da Adobe Campaign, sempre inclua uma versão hexadecimal do que você digita e do que você vê.

**Etapa 3: Saiba o que você deve enviar**

Determine a codificação que você espera que seja usada e pesquise online por sua tabela de caracteres. Verifique se os caracteres que você deseja enviar estão disponíveis na página de código do público alvo. Verifique se o campo `data_coding` está correto e corresponde ao que você e o provedor esperam.

**Etapa 4: Saiba o que você realmente enviou**

Você precisará da saída de depuração do conector para ver exatamente quais bytes você enviou ao provedor. Problemas de codificação aparecem em `SUBMIT_SM PDU`s, portanto, certifique-se de capturá-los. Envie mensagens muito distintas, fáceis de encontrar no registro.

Envie diferentes tipos de caracteres especiais ao testar. Por exemplo, a codificação GSM7 tem caracteres estendidos que são muito distintos em sua forma hexadecimal, eles são fáceis de identificar, já que não aparecem em nenhuma outra codificação.

## Elementos a serem incluídos ao se comunicar sobre um problema de SMS {#element-include}

Sempre que você buscar assistência em um problema de SMS, quer esteja abrindo um ticket de suporte para a Adobe Campaign, para o provedor de SMS, ou qualquer tipo de comunicação sobre o problema, você precisará incluir as seguintes informações para ter certeza de que ele será qualificado corretamente. Problemas devidamente qualificados são fundamentais para resolver problemas mais rapidamente.

* **Ative** mensagens SMPP detalhadas quando o problema for exibido. A maioria dos problemas de SMS é impossível de resolver sem isso.

* Se o problema estiver relacionado ao tráfego SMS, entre em contato primeiro com o provedor. A plataforma deles é mais adequada para o diagnóstico eficiente dos problemas de tráfego do SMS em tempo real.

* Inclua uma descrição breve, mas fatual, do problema.

* Incluir uma descrição do resultado esperado.

* Inclua o feedback do provedor.

* Incluir registros relevantes e/ou capturas de rede. Ao fazer capturas, reproduza o problema durante a captura.

* Se você incluir registros, rastreamentos ou capturas, aponte o local exato no arquivo quando o problema for exibido.

* Se você fizer referência a mensagens, PDUs ou logs, indique claramente seu carimbo de data e hora para facilitar sua localização.

* Tente reproduzir o problema em um ambiente de teste. Se não tiver certeza sobre uma configuração, experimente-a no ambiente de teste e verifique o resultado com os rastreamentos SMPP. Geralmente, é melhor reportar problemas replicados em ambientes de teste do que problemas de relatórios direto em ambientes de produção.

* Inclua qualquer alteração ou ajuste feito na plataforma. Além disso, inclua qualquer alteração que o provedor possa ter feito de seu lado.

### Captura de rede {#network-capture}

Nem sempre é necessária uma captura de rede, geralmente as mensagens SMPP detalhadas são suficientes. Estas são algumas diretrizes que ajudarão você a determinar se uma captura de rede é necessária:

* Problemas de conexão, mas as mensagens detalhadas não mostram nenhum `BIND_RESP PDU`.

* Desconexões inexplicáveis sem mensagem de erro, o comportamento normal do conector quando detecta um erro de protocolo de baixo nível.

* O provedor reclama sobre o processo de desconexão/desassociação.

* Problemas de codificação em campos TLV opcionais.

* Suspeita-se que o tráfego seja misturado entre conexões diferentes.

Em todas as outras situações, tente analisar as mensagens SMPP detalhadas primeiro e solicitar uma captura de rede somente se estiver claro que as informações estão ausentes nos registros detalhados.

Em alguns casos, a captura do tráfego de rede não é necessária. Estas são as situações mais comuns:

* TLS ativado: Por definição, o tráfego TLS é criptografado para que não possa ser capturado.

* Problemas de desempenho: Os registros contêm todas as informações necessárias para rastrear problemas de desempenho.

* Problemas de tempo (`retry timing`, `enquire_link` ponto, limite de throughput etc.)

* Análise e processamento SR: os registros detalhados dão muito mais contexto e uma apresentação melhor.

* Processamento de MO (respostas automáticas, quarentena).

* Erros que não envolvem o tráfego SMPP real: Preparação de delivery, problemas com a API do centro de mensagens, problemas de fluxo de trabalho etc.

## Habilitar rastreamentos SMPP {#enabling-smpp-traces}

O novo conector suporta registro estendido através de rastreamentos: SMPP. Os rastreamentos são enviados no registro MTA, não na saída padrão.

**Ativação por conta externa (método preferencial)**

1. Na Conta externa ****, selecione **Ativar rastreamentos SMPP detalhados no arquivo de log**.
1. Salvar, o conector se reconectará com rastreamentos ativados.

**Ativando dinamicamente**

O Adobe Campaign Standard MTA tem uma interface de controle HTTP que permite alterar o filtro de rastreamento dinamicamente.
Uma chamada de POST pode ativar/desativar rastreamentos. Exemplo de URL para ativar rastreamentos SMPP:

```
POST http://host:7780/mta/trace?filter=SMPP
```

Para desativar os rastreamentos, defina um filtro vazio:

```
POST http://host:7780/mta/trace?filter=
```

**Ativação na configuração**

No arquivo `config-instance.xml`, defina os seguintes parâmetros:

```
<mta args="-tracefilter:SMPP"/>
```

## Verificando o número de conexões abertas em um container {#open-connections}

Para verificar o número de conexões abertas em um container, você pode usar este comando:

```
(for pid in $(ss -neopts  | sed -n ‘s/^.*:3600[ \t].*users:(([0-9A-Za-z”]*,pid=\([0-9]*\),.*$/\1/p’ | sort ); do  cat /proc/$pid/cmdline; echo  ” $pid” ;done;) | uniq --count
```

Isso lista o número de conexões abertas para uma determinada porta. Aqui estamos usando a porta 3600.

O resultado deve ser o seguinte:

```
4 nlserversms -noconsole -tracefile:sms@INSTANCE_NAME -instance:INSTANCE_NAME -detach 15180
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 1838
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 24025
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 24029
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 29088
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 30390
```

4 conexões abertas para o processo sms e 2 por filho mta com 5 filhos.
