---
solution: Campaign Standard
product: campaign
title: Solução de problemas de SMS
description: Solução de problemas de SMS
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Configurações de instância
role: Administrador
level: Experienciado
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '2700'
ht-degree: 90%

---


# Solução de problemas de SMS {#sms-troubleshooting}

## Conflito entre contas externas diferentes {#external-account-conflict}

Se a instância tiver várias contas externas de SMS, verifique se os problemas não são causados por um conflito entre contas externas.

O Adobe Campaign trata as contas externas como entidades não relacionadas.

Se você tiver várias contas, siga este procedimento para isolar a conta externa que está causando problemas:

1. Desative todas as contas externas.
1. Ative uma conta externa.
1. Tente reproduzir o problema.
1. Se o problema inicial nem sempre ocorrer, faça uma quantidade razoável de tentativas antes de concluir.
1. Se o problema não ocorrer com essa única conta, desative-a e a reinicie na etapa 2 na próxima conta.

Depois de verificar cada conta individualmente, há dois cenários possíveis:

* **O problema ocorreu em uma ou em várias contas**

   Nesse caso, você pode aplicar outros procedimentos de solução de problemas a cada conta individualmente. É melhor desativar outras contas ao diagnosticar uma conta para reduzir o tráfego de rede e o número de logs.

* **O problema não ocorreu quando apenas uma conta estava ativa a qualquer momento**

   Você tem um conflito entre contas. Como mencionado anteriormente, o Adobe Campaign trata as contas individualmente, mas o provedor pode tratá-las como uma única conta.

   * Você está usando diferentes combinações de logon/senha em todas as suas contas.
Você terá que entrar em contato com o provedor para diagnosticar possíveis conflitos referentes a ele.

   * Algumas contas externas têm a mesma combinação de logon/senha.
O provedor não tem como saber de qual conta externa o `BIND PDU` vem. Portanto, ele trata todas as conexões de várias contas como uma única. Ele pode ter roteado MO e SR aleatoriamente nas duas contas, causando problemas.
Se o provedor der suporte a vários códigos curtos para a mesma combinação de logon/senha, você terá que perguntar a ele onde colocar esse código curto no `BIND PDU`. Observe que essa parte das informações deve ser colocada em `BIND PDU`, não em `SUBMIT_SM`, já que `BIND PDU` é o único local que permitirá o roteamento correto de MOs.
Consulte a seção [Informações em cada tipo de PDU](../../administration/using/sms-protocol.md#information-pdu) acima para saber qual campo está disponível em `BIND PDU`. Normalmente, você adiciona o código curto a `address_range`, mas isso requer suporte especial do provedor. Entre em contato com ele para saber como espera rotear vários códigos curtos independentemente.
O Adobe Campaign dá suporte à manipulação de vários códigos curtos na mesma conta externa.

## Problema com a conta externa em geral {#external-account-issues}

* Verifique se o conector foi alterado recentemente e por quem (verifique as Contas externas como um grupo).

   ```
   select saccount, (sserver ||':'||sport) as serverPort, iextaccountid, CASE WHEN N0.iactive=1 THEN 'Yes' ELSE 'No' END as "(x) Enabled",
   
   (select X1.sname from xtkoperator X1 where N0.icreatedbyid = X1.ioperatorid) as "Created By",
   
   (select X1.sname from xtkoperator X1 where N0.imodifiedbyid = X1.ioperatorid) as "Last Modified By",
   
   N0.slabel as "External Account", N0.tslastmodified as "LastModifiedDate"
   
   from nmsextaccount N0 LEFT JOIN xtkoperator X0 ON (N0.icreatedbyid=X0.ioperatorid) order by 8 DESC LIMIT 50;
   ```

* Verifique (no diretório /postupgrade) se o sistema foi atualizado e quando
* Verifique se algum pacote que afeta o SMS pode ter sido atualizado recentemente (/var/log/dpkg.log).

## Problema ao conectar-se ao provedor {#issue-provider}

* Se `BIND PDU` retornar um código diferente de zero `command_status`, peça mais informações ao provedor.

* Verifique se a rede está configurada corretamente para que a conexão TCP possa ser estabelecida com o provedor.

* Peça ao provedor que verifique se incluiu corretamente os IPs na lista de permissões da instância do Adobe Campaign.

* Verifique as configurações de **Conta externa**. Pergunte ao provedor o valor dos campos.

* Se a conexão for bem-sucedida, mas instável, verifique a seção [Problema com conexões instáveis](../../administration/using/troubleshooting-sms.md#issues-unstable-connection).

* Se problemas de conexão forem difíceis de diagnosticar, uma captura de rede poderá fornecer informações. Verifique se a captura de rede é executada simultaneamente enquanto o problema ocorre para que ele seja analisado com eficiência. Você também deve observar a hora exata em que o problema ocorre.

## Problemas de conexão instável {#issues-unstable-connection}

Uma conexão será considerada instável se qualquer uma das seguintes situações ocorrer:

* Reiniciar o MTA corrigirá os problemas temporariamente. Isso significa que uma conexão instável aciona o controle de MTA no Adobe Campaign Standard, reiniciando o MTA limpa o controle. Isso acontecerá novamente até que a causa raiz seja encontrada.

* O provedor envia `UNBIND PDU`s.

* `enquire_link` expira, no Adobe Campaign ou no provedor. Nesse caso, você pode ver `ENQUIRE_LINK_RESP` com um código de erro diferente de zero.

* Há muitos `BIND PDU`s. Não deve haver mais do que alguns durante um dia, dependendo do número de conexões. Mais de 1 BIND PDU por hora deve gerar um alerta.

Como corrigir problemas de estabilidade de conexão:

* Conexões instáveis raramente são a causa principal. Muitas vezes, é o resultado de outro problema que aciona uma desconexão. Encontrar a causa raiz é a prioridade.

* Ative rastreamentos SMPP detalhados. Você precisará deles para ver o que está acontecendo quando a conexão for reiniciada.

* Se o provedor envia `BIND PDU`s, algo pode estar errado. Pergunte ao provedor por que `UNBING` é enviado.

* Fazer uma captura de rede às vezes é a única maneira de ver como a conexão é fechada.

* Se o provedor fechar as conexões enviando um pacote `TCP FIN` ou `TCP RST`, pergunte ao provedor mais informações.

* Se o provedor fechar a conexão depois de enviar um erro limpo, como`DELIVER_SM_RESP`, com um código de erro, ele deverá corrigir o conector. Caso contrário, isso impedirá que outros tipos de mensagens sejam transmitidas e acionará a limitação do MTA. Isso é especialmente importante no modo transceptor, em que o fechamento da conexão afeta tanto o MT quanto o SR.

## Problema ao enviar um MT (SMS normal enviado para um usuário final){#issue-MT}

* Verifique se a conexão está estável. Uma conexão SMPP deve permanecer ativa por pelo menos 1 hora continuamente. Consulte a seção [Problema com conexões instáveis](../../administration/using/troubleshooting-sms.md#issues-unstable-connection).

* Se o reinício do MTA fizer com que o envio do MT funcione novamente por um breve período, provavelmente você terá uma limitação devido a uma conexão instável. Consulte a seção [Problema com conexões instáveis](../../administration/using/troubleshooting-sms.md#issues-unstable-connection).

* Verifique se o log amplo está presente e com o status e as datas corretas. Se não for o caso, poderá ser um problema de delivery ou de preparação de delivery.

* Verifique se o MTA realmente processa a mensagem. Se não for o caso, talvez não seja um problema de SMS.

* Verifique se o conector de SMS está associado ao equipamento do provedor. Solicite feedback ao provedor para garantir que todos os sistemas estejam se comunicando corretamente. Consulte `BIND_TRANSMITTER` e `BIND_TRANSCEIVER PDU`s para obter informações sobre o processo de associação. Talvez seja necessário ativar os rastreamentos SMPP para solucionar problemas corretamente.

* Com os rastreamentos SMPP ativados, verifique se `SUBMIT_SM PDU` contém as informações certas.

* Verifique se o provedor responde com um `SUBMIT_SM_RESP PDU` com um valor &quot;OK&quot; (código 0). Verifique se a PDU chega com um atraso razoável: qualquer tempo superior a 1 segundo deve ser discutido com o provedor. Geralmente, chega em menos de 100 ms.

* Se todas essas etapas funcionarem, você poderá ter certeza de que o problema se refere ao provedor. Ele terá que solucionar problemas na respectiva plataforma.

* Se isso funcionar, mas o tráfego for inconsistente, tente ajustar a janela de envio e diminuir o rendimento do MT. Você precisará trabalhar com o provedor para ajustar isso. O Adobe Campaign pode enviar mensagens muito rapidamente. Portanto, problemas de desempenho podem surgir no equipamento do provedor.

## Os MTs são duplicados (o mesmo SMS é enviado várias vezes seguidas){#duplicated-MT}

Duplicatas frequentemente são causadas por tentativas. É normal haver duplicatas ao tentar enviar mensagens novamente. Você deve tentar remover a causa raiz das tentativas.

* Se duplicatas forem enviadas com um intervalo de exatamente 60 segundos, provavelmente será um problema referente ao provedor, que não envia um `SUBMIT_SM_RESP` com rapidez suficiente.

* Se há muitos `BIND/UNBIND`, você tem uma conexão instável. Consulte a seção [Problema com conexões instáveis](../../administration/using/troubleshooting-sms.md#issues-unstable-connection) para obter soluções antes de tentar resolver problemas de mensagens duplicadas.

Diminuição na quantidade de duplicatas quando há uma nova tentativa:

* Diminua a janela de envio. A janela de envio deve ser grande o suficiente para abranger a latência `SUBMIT_SM_RESP`. Seu valor representa o número máximo de mensagens que poderão ser duplicadas se ocorrer um erro enquanto a janela estiver cheia.

## Problema ao processar SR (recibos de delivery) {#issue-process-SR}

* Você precisará de rastreamentos SMPP ativados para realizar qualquer tipo de solução de problemas de SR.

* Verifique se `DELIVER_SM PDU` vem do provedor e se está corretamente formado.

* Verifique se o Adobe Campaign responde com um `DELIVER_SM_RESP PDU` bem-sucedido em tempo hábil. No Adobe Campaign Standard, isso garante que toda a lógica de processamento tenha sido aplicada, se esse não for o caso, é garantido que haja uma mensagem de erro nos logs informando por que o processamento falhou.

Se `DELIVER_SM PDU` não for confirmado com êxito, verifique o seguinte:

* Verifique o regex relacionado à extração de id e ao processamento de erros na **Conta externa**. Talvez seja necessário validá-los em relação ao conteúdo de `DELIVER_SM PDU`.

* Verifique se os erros foram devidamente provisionados na tabela `broadLogMsg`.

* Para o Adobe Campaign Standard, verifique se as tabelas `broadLog` e `broadLogExec` estão sincronizadas corretamente.

Se você corrigiu tudo, menos alguns SR inválidos, ainda estão nos buffers do provedor, é possível ignorá-los usando a opção **ID confirm count** inválida. Isso deverá ser usado com cuidado e redefinido como 0 o mais rápido possível depois que os buffers estiverem limpos.

## Problema ao processar o MO (e lista de bloqueio/resposta automática){#issue-process-MO}

* Ativar rastreamentos SMPP durante testes. Se você não ativar o TLS, deverá fazer uma captura de rede ao solucionar problemas do MO para verificar se as PDUs contêm as informações corretas e estão formatadas adequadamente.

* Ao capturar tráfego de rede ou analisar rastreamentos SMPP, capture toda a conversa com o MO e seu MT de resposta se uma resposta estiver configurada.

* Se o MO (`DELIVER_SM PDU`) não aparece nos rastreamentos, o problema se refere ao provedor. Ele terá que solucionar problemas em sua plataforma.

* Se `DELIVER_SM PDU` for exibido, verifique se ele foi confirmado pelo Adobe Campaign com um `DELIVER_SM_RESP PDU` bem-sucedido (código 0). Esse RESP garante que toda a lógica de processamento foi aplicada pelo Adobe Campaign (resposta automática e lista de permissão/bloqueio). Se não for o caso, procure por uma mensagem de erro nos logs MTA.

* Se as respostas automáticas estiverem ativadas, verifique se `SUBMIT_SM` foi enviado ao provedor. Caso contrário, é garantido encontrar uma mensagem de erro nos logs MTA.

* Se o `SUBMIT_SM MT PDU` que contém a resposta for encontrado nos rastreamentos, mas o SMS não chegar ao telefone celular, você terá que entrar em contato com o provedor para obter assistência na solução de problemas.

## Problema durante a preparação do delivery sem a exclusão de recipient em quarentena (em quarentena pelo recurso de resposta automática) {#issue-delivery-preparation}

* Verifique se o formato do número de telefone é exatamente o mesmo na tabela de quarentena e no log de delivery.  Caso contrário, consulte esta [seção](../../administration/using/sms-protocol.md#automatic-reply) se tiver problemas com o prefixo &quot;+&quot; do formato de número de telefone internacional.

* Verifique os códigos curtos. Poderão correr exclusões se o código curto do recipient for igual ao definido na conta externa ou se estiver vazio (vazio = qualquer código curto). Se apenas um código curto for usado para toda a instância do Adobe Campaign, será mais fácil deixar todos os campos de **código curto** vazios.

## Problemas de codificação {#encoding-issues}

**Etapa 1: entrar em contato com o provedor**

Entre em contato com ele e veja o que há de errado. Ele deve ser capaz de dizer se o problema se refere a ele ou ao Adobe Campaign. Se o problema estiver no Adobe Campaign, ele deverá saber exatamente qual campo está incorreto.

**Etapa 2: saiba o que está em sua mensagem**

O Unicode permite muitas variantes para caracteres semelhantes, e o Adobe Campaign não pode lidar com todas elas.

A origem de problemas mais comum é a cópia e colagem por meio de um processador de texto, o que altera os caracteres comuns para versões tipograficamente corretas: espaços alterados para espaços não separáveis, aspas duplas alteradas para aspas de abertura e fechamento, sinais de menos alterados para vários tipos de hifens etc.

Não copie e cole a mensagem ao testar. Sempre digite-a diretamente na interface.

Com o hexadecimal, é possível diferenciar entre caracteres semelhantes. Um L minúsculo, um I maiúsculo, O, 0, todos os diferentes tipos de aspas, codificações não latinas ou até mesmo tipos diferentes de espaços podem parecer iguais ou não ser exibidos.

Para converter o unicode em hexadecimal, você pode usar ferramentas online, como o site do [conversor de código Unicode](https://r12a.github.io/app-conversion/). Digite o texto, verifique se não há informações de identificação pessoal, como números de telefone, e clique em **Converter**. Você verá os valores hexadecimais na parte inferior (zona UTF-32).

Ao abrir tíquetes sobre problemas de codificação, para o provedor ou o suporte do Adobe Campaign, sempre inclua uma versão hexadecimal do que você digita e do que vê.

**Etapa 3: saiba o que você deve enviar**

Determine a codificação que você espera que seja usada e pesquise online a tabela de caracteres dela. Verifique se os caracteres que você deseja enviar estão disponíveis na página de código de destino. Verifique se o campo `data_coding` está correto e corresponde ao que você e o provedor esperam.

**Etapa 4: saiba o que você realmente enviou**

Você precisará da saída de depuração do conector para ver exatamente quais bytes enviou ao provedor. Problemas de codificação aparecem em `SUBMIT_SM PDU`s, portanto, capture-os. Envie mensagens muito distintas, que sejam fáceis de encontrar no log.

Envie diferentes tipos de caracteres especiais ao testar. Por exemplo, a codificação GSM7 tem caracteres estendidos que são muito distintos em sua forma hexadecimal. Eles são fáceis de identificar, já que não aparecem em nenhuma outra codificação.

## Elementos a serem incluídos ao se comunicar sobre um problema de SMS {#element-include}

Sempre que buscar assistência para um problema de SMS, seja para abrir um tíquete de suporte para o Adobe Campaign, para o provedor de SMS ou qualquer tipo de comunicação sobre o problema, você precisará incluir as informações a seguir para ter certeza de que ele será qualificado corretamente. A qualificação correta dos problemas é fundamental para resolvê-los mais rapidamente.

* **Ative as mensagens SMPP detalhadas** quando o problema surgir. A maioria dos problemas de SMS é impossível de resolver sem isso.

* Se o problema estiver relacionado ao tráfego de SMS, entre em contato primeiro com o provedor. A plataforma dele é mais adequada para o diagnóstico eficiente dos problemas de tráfego de SMS em tempo real.

* Inclua uma descrição breve e concreta do problema.

* Inclua uma descrição do resultado esperado.

* Inclua o feedback do provedor.

* Inclua logs e/ou capturas de rede relevantes. Ao fazer capturas, reproduza o problema durante a captura.

* Se você incluir logs, rastreamentos ou capturas, aponte o local exato no arquivo quando o problema ocorrer.

* Se você mencionar mensagens, PDUs ou logs, indique claramente a data e a hora para facilitar a localização.

* Tente reproduzir o problema em um ambiente de teste. Se não tiver certeza sobre uma configuração, experimente-a no ambiente de teste e verifique o resultado com os rastreamentos SMPP. Geralmente, é melhor relatar problemas replicados em ambientes de teste do que problemas em ambientes de produção.

* Inclua qualquer alteração ou ajuste feito na plataforma. Além disso, inclua qualquer alteração que o provedor possa ter feito.

### Captura de rede {#network-capture}

Nem sempre é necessária uma captura de rede. Geralmente, as mensagens SMPP detalhadas são suficientes. Estas são algumas diretrizes que ajudarão você a determinar se uma captura de rede é necessária:

* Problemas de conexão, mas as mensagens detalhadas não mostram nenhum `BIND_RESP PDU`.

* Desconexões inexplicáveis sem mensagem de erro, o comportamento normal do conector quando detecta um erro de protocolo de baixo nível.

* O provedor reclama sobre o processo de desconexão/desassociação.

* Problemas de codificação em campos TLV opcionais.

* Há suspeita de que o tráfego esteja misturado entre conexões diferentes.

Em todas as outras situações, tente analisar primeiro mensagens SMPP completas e solicitar uma captura de rede somente se estiver claro que as informações estão ausentes nos logs detalhados.

Em alguns casos, a captura do tráfego de rede não é necessária. As situações mais comuns são:

* TLS ativado: por definição, o tráfego TLS é criptografado para que não possa ser capturado.

* Problemas de desempenho: os logs contêm todas as informações necessárias para rastrear problemas de desempenho.

* Problemas de tempo (`retry timing`, `enquire_link` duração, limite de rendimento etc.)

* Análise e processamento SR: os registros detalhados dão muito mais contexto e uma apresentação melhor.

* Processamento de MO (respostas automáticas, quarentena).

* Erros que não envolvem o tráfego SMPP real: preparação de delivery, problemas da API do centro de mensagens, problemas de fluxo de trabalho etc.

## Habilitar rastreamentos SMPP {#enabling-smpp-traces}

O novo conector dá suporte a logs estendidos por meio de rastreamentos: SMPP. Os rastreamentos são enviados no log MTA, não na saída padrão.

**Ativação por conta externa (método preferencial)**

1. Na **External account**, selecione **Enable verbose SMPP traces in the log file**.
1. Salve, o conector se reconectará com os rastreamentos ativados.

**Ativação em tempo real**

O MTA do Adobe Campaign Standard tem uma interface de controle HTTP que permite alterar o filtro de rastreamento em tempo real.
Uma chamada de POST pode ativar/desativar rastreamentos. Exemplo de URL para ativar rastreamentos SMPP:

```
POST http://host:7780/mta/trace?filter=SMPP
```

Para desativar rastreamentos, defina um filtro vazio:

```
POST http://host:7780/mta/trace?filter=
```

**Ativação na configuração**

No arquivo `config-instance.xml`, defina os seguintes parâmetros:

```
<mta args="-tracefilter:SMPP"/>
```

## Verificação do número de conexões abertas em um container {#open-connections}

Para verificar o número de conexões abertas em um container, você pode usar este comando:

```
(for pid in $(ss -neopts  | sed -n ‘s/^.*:3600[ \t].*users:(([0-9A-Za-z”]*,pid=\([0-9]*\),.*$/\1/p’ | sort ); do  cat /proc/$pid/cmdline; echo  ” $pid” ;done;) | uniq --count
```

Ele lista o número de conexões abertas para determinada porta. Aqui estamos usando a porta 3600.

O resultado deve ser o seguinte:

```
4 nlserversms -noconsole -tracefile:sms@INSTANCE_NAME -instance:INSTANCE_NAME -detach 15180
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 1838
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 24025
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 24029
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 29088
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 30390
```

Quatro conexões abertas para o processo SMS e duas por filho mta com cinco filhos.
