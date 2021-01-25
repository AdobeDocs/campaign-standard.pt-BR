---
solution: Campaign Standard
product: campaign
title: Notas de versão anteriores
description: Notas de versão anteriores
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
hide: true
hidefromtoc: true
translation-type: tm+mt
source-git-commit: a1a670f32201ba6b8fa4488a5ab3dd881aece097
workflow-type: tm+mt
source-wordcount: '2618'
ht-degree: 4%

---


# Nova versão {#new-release}

[Planejamento](../../rn/using/release-planning.md)  de lançamento| Versões [ de ](https://docs.adobe.com/content/help/pt-BR/control-panel/using/release-notes.html) Painel de controle do Campaign| Atualizações [ de ](../../rn/using/documentation-updates.md) documentação| Notas [ de versão ](../../rn/using/release-notes.md) mais recentes| Recursos  [obsoletos](../../rn/using/deprecated-features.md)

Esta página descreve novos recursos, melhorias e correções incluídos na próxima versão do Campaign Standard.

>[!CAUTION]
>
> Este conteúdo está sujeito a alterações sem aviso prévio até a data de atualização dos ambientes de estágio. Saiba mais na [página de planejamento de versão](../../rn/using/release-planning.md).


## Versão 21.1 - fevereiro de 2021 {#release-21-1---febuary-2021}

**Novidades**

<table> 
<thead> 
<tr> 
<th> <strong>Serviço de feedback por email</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>O EFS (Email Feedback Service) é um serviço escalável que captura o feedback do MTA aprimorado diretamente, melhorando assim a precisão do relatórios. Esse recurso é lançado como um beta privado e estará progressivamente disponível para todos os clientes em versões futuras.</p>
<ul>
<li>Todas as categorias de eventos são capturadas: Atrasos, Entregues, Enviados, Cancelados A Assinatura (Link, Lista), Comentários (Reclamações De Spam, eventos Assíncronos).</li>
<li>O cálculo dos indicadores Enviados/Entregues agora se baseia no feedback em tempo real do MTA aprimorado para melhorar a precisão e a reatividade.</li>
<li>O EFS soluciona o problema de rejeições síncronas de atrasos de relatórios e retira 80% da carga do processo inMail.</li>
</ul>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Melhorias na integração ao Adobe Experience Manager</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>A integração com a Adobe Experience Manager foi aprimorada: agora você pode importar conteúdo multilíngue mais facilmente do Adobe Experience Manager. A Adobe Campaign Standard agora detecta automaticamente as variantes de idioma do conteúdo da Adobe Experience Manager e permite a importação e criação de variantes em massa, simplificando significativamente o número de etapas que um profissional precisa seguir para criar uma campanha multilíngue com base no conteúdo da Adobe Experience Manager.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Interface de Experience Cloud unificada</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>A barra de cabeçalho do Adobe Campaign foi alterada para unificar e melhorar sua experiência em todos os produtos e serviços do Experience Cloud. Essas alterações foram projetadas para facilitar sua vida, incluindo:</p>
<ul>
<li>É mais fácil alternar entre suas organizações ou para um aplicativo diferente.</li>
<li>Ajuda do usuário aprimorada - inserir o Experience League no produto, os resultados da pesquisa também incluem resultados de fóruns da comunidade e mais conteúdo de vídeo, facilitando o acesso a mais conteúdo para ajudar a aproveitar ao máximo o aplicativo. Também adicionamos um mecanismo de feedback diretamente no menu Ajuda, facilitando o relatório de problemas ou o compartilhamento de suas ideias.</li>
<li>Notificações aprimoradas - o menu suspenso Notificações agora tem duas guias: uma para suas próprias notificações de produtos e uma para anúncios de produtos mais globais.</li>
</ul>
</td> 
</tr> 
</tbody> 
</table>

**Aprimoramentos**

* A integração do Microsoft Dynamics 365 foi aprimorada com um aplicativo dedicado de integração de autoatendimento e um processo de implementação aprimorado. [Saiba mais](../../integrating/using/d365-acs-get-started.md)

* Correção de um problema que fazia com que os delivery fossem executados muito lentamente devido a determinados processos. Isso se deve a unidades incorretas definidas para vários parâmetros (milissegundos em vez de segundos, por exemplo).

* Corrigido um problema quando o SDK móvel enviava uma solicitação de rastreamento aberta com base na condição de que deliveryId/MessageID não fosse nulo. Isso resultaria em 404 erros para delivery com rastreamento desativado. Uma variável adicional (acsDeliveryTracking) com informações sobre o status de rastreamento do delivery agora é enviada na carga. Essa variável pode ter dois valores ativados ou desativados dependendo do status de rastreamento definido.

* Foi feito um aprimoramento para facilitar a solução de problemas ao encontrar problemas com o processo de mensagens transacionais. Os administradores técnicos do Adobe agora podem usar o rastreamento em qualquer processo sem reiniciá-lo.

* A lista Perfis agora permite que você pesquise por registros com base em um desses campos: email, nome, sobrenome ou campos personalizados que foram adicionados na filtragem avançada ao estender o recurso de perfil. Esse recurso também está disponível em APIs de Campaign Standard usando o parâmetro filterType.

* Um parâmetro foi ajustado para o número de container que executam o processo de pooling do banco de dados de mensagens transacionais. Isso permite que a carga seja distribuída uniformemente em todos os container usados e alcance o desempenho ideal.

* Uma nova função (GetOption) agora está disponível no atividade usando variáveis de evento após chamar um fluxo de trabalho com parâmetros externos. Permite retornar o valor de uma função especificada.

* Uma nova opção técnica foi adicionada. Ele permite que o Campaign Standard verifique se há memória física suficiente disponível no sistema antes de iniciar um fluxo de trabalho. Se a quantidade de memória for muito baixa, a execução do fluxo de trabalho será atrasada até que a memória do sistema atinja esse limite. Isso é feito para evitar uma maior degradação do desempenho e mitigar o risco de uma interrupção. Tente reagendar este fluxo de trabalho para um tempo de menos atividade e tente novamente. O fluxo de trabalho será retomado automaticamente assim que a tensão do servidor for relaxada. Observe que essa opção é somente leitura e não pode ser modificada.

**Outras alterações**

* Alteração de um erro para um aviso durante a preparação da mensagem, quando o limite de 100 downloads de conteúdo por hora de rolagem é atingido. Um aviso agora é exibido quando o limite é atingido, o que permite continuar com o delivery.

* Um novo mapeamento de delivery (mapRtEventAppSubRcp) agora está disponível para perfis de definição de metas de mensagens de push transacionais. O delivery, a exclusão e os logs de rastreamento desses deliveries agora estarão disponíveis nas tabelas broadLogAppSubRcp, excludeLogAppSubRcp e trackingLogAppSubRcp. Isso resolve um problema que causava a falha da análise do delivery ao enviar uma mensagem de push transacional usando a dimensão do público-alvo do perfil.

* Ao enriquecer um conteúdo de mensagen transacional, os links não são mais recuperados ao buscar dados da tabela do Perfil, o que reduz a latência durante a preparação da mensagem e evita dados vazios do perfil devido a uma relação incorreta definida com a tabela do perfil.

* A configuração técnica da instância foi otimizada para garantir a estabilidade. (CAMP-45681)

* O gerenciamento de sessões foi aprimorado para otimizar a memória. (CAMP-45901, CAMP-46767)

* A atividade **Transferir arquivo** agora gera uma variável adicional (filesCount) que contém o número de arquivos carregados ou baixados. (CAMP-45842)

* O conector SMS agora pode enviar vários parâmetros opcionais com cada mensagem.

* Correção de um problema que impedia que usuários com a função MODELO DE DADOS publicassem extensões de log de delivery. Esta operação agora estará disponível para a função MODELO DE DADOS. (CAMP-46604)

* Correção de um problema em workflows que ocorria ao copiar e colar uma atividade **Desduplicação-duplicada** executada uma vez e que aproveitava um recurso temporário. Depois de duplicado, o recurso de atividade foi automaticamente definido como vazio, resultando em problemas em outras atividades do fluxo de trabalho. Depois de colado, o recurso de atividade permanecerá o mesmo, para que o erro seja acionado o mais rápido possível, em vez de posteriormente, no fluxo de trabalho. (CAMP-46903)

* A mensagem de erro exibida ao tentar publicar um recurso direcionando um recurso personalizado que não existe mais foi tornada mais clara. (CAMP-46893)

* Os seguintes idiomas foram adicionados à lista de idioma preferencial: Indonésia - Indonésia (in-id), Inglês - Suécia (en-se), Inglês - Pacífico Asiático (en-ap), Inglês - Japão (en-jp), Espanhol - América Latina (es-la). (CAMP-46351)

* O seletor de perfis ao testar uma landing page agora usará o recurso profilBase em vez do perfil para evitar o tempo limite.

* O formato de registro SMPP foi aprimorado.

* Parâmetros opcionais para as funções CryptString e descriptografptString JS foram adicionados para corresponder às APIs da Adobe Campaign Classic.

* Mensagens de aviso ou erro aprimoradas nos registros de preparação de delivery.

* Registros de erros aprimorados ao tentar se conectar ao IMS.

* Agora é possível filtrar ainda mais as dimensões de Delivery e Campanha usando a barra de pesquisa no relatórios dinâmico.

* A data de validade da mensagem SMS transacional agora pode ser definida pelo valor definido para o parâmetro de expiração na API de Mensagens transacionais. (CAMP-36600)

* No relatórios dinâmico, o relatório **resumo do Delivery** integrado estava mostrando dados incorretos para a métrica de taxa não subscrita. Uma nova métrica chamada **unsubscription exclusiva** foi adicionada para corrigir isso. (CAMP-46445)

**Correções**

* Correção de um problema que impedia a execução de relatórios do delivery quando 5000 linhas eram exibidas.
* Correção de um problema com o teste A/B que impedia que o conteúdo da variante B fosse atualizado após a modificação do template do delivery. (CAMP-45235)
* Correção de um problema que causava a interrupção do processo de mensagens transacionais, impedindo o envio de mensagens.
* Correção de um problema que resultava em problemas de navegação após clicar em um link interno (por exemplo, ao acessar o delivery pai de uma tela de resumo de prova).
* Correção de um problema que impedia que todos os modelos de conteúdo de Experience Manager disponíveis fossem exibidos ao criar um delivery. (CAMP-45990)
* Correção de um problema em workflows que impedia a exibição de mensagens de falha nos logs do delivery após a adição da coluna **Razão** à guia de dados adicional. (CAMP-45139)
* Correção de um problema que ocorria quando duas chamadas de subscrição do aplicativo tinham a mesma ID do Marketing Cloud (&#39;valor da chave do duplicado viola o erro de restrição exclusiva&#39;).
* Correção de um problema que resultava em problemas de lentidão ao arrastar e soltar atividades em um fluxo de trabalho contendo uma grande quantidade de atividades **Query** e **Ler audiência**. (CAMP-44511)
* Corrigido um erro que ocorria ao final da preparação do mensagen transacional, impedindo que as informações de redirecionamento fossem carregadas nos servidores de rastreamento.
* Correção de um problema que podia exibir mensagens de erro ao tentar abrir templates de importação ou trabalhos de importação anteriores após a personalização do recurso de fluxo de trabalho. (CAMP-46183)
* Correção de um problema que impedia a execução de uma atividade **audiência de leitura** se ela estivesse configurada com um nome de audiência dinâmico. (CAMP-46047)
* Correção de um problema que impedia a exibição do botão **Exportar lista**
* Correção de um problema que resultava na falha do fluxo de trabalho **do agregação** do Relatórios. (CAMP-45979)
* Correção de um problema ao criar um recurso personalizado com uma chave composta personalizada (conteúdo dinâmico de texto/data).
* Correção de um problema que impedia a exibição dos dados de transição do query. (CAMP-45669)
* Correção de problemas de consumo de memória relacionados à publicação de recursos personalizados.
* Correção de um problema que ocorria ao configurar um delivery a ser enviado em uma data específica. Se o delivery tiver sido definido para ser enviado imediatamente depois de confirmado, a preparação do delivery falhou e a data inicialmente especificada ainda foi tomada em consideração. (CAMP-44107)
* Correção de um problema que impedia a abertura de modelos transacionais. (CAMP-47181)
* Correção de um problema no processo de publicação de mensagens transacionais que resultava em tipologias de duplicados e regras de tipologia com nomes que excediam o tamanho de sequência permitido. (CAMP-47104)
* Correção de um problema na atividade **API externa** que ocorria quando um parâmetro de entrada retornava um registro que não existia. (CAMP-47023)
* Correção de um problema que impedia a reconexão do conector SMPP.
* Correção de um problema que ocorria na atividade **Transferência de arquivo** ao baixar um arquivo contendo um ponto em seu nome. Os caracteres que seguem o ponto foram considerados como a extensão do arquivo. (CAMP-46624)
* Correção de um problema que impedia a execução do pool do banco de dados, o que fazia com que mensagens transacionais ficassem presos na fila do roteador.
* Correção de um erro que não impedia o envio dos logs do delivery cancelados.
* Correção de um problema que causava a falha de um fluxo de trabalho ao usar uma atividade **AND-join**. A atividade alterou automaticamente o Conjunto primário para a última transição com fio, mesmo se ele mostrasse visualmente a primeira transição com fio. (CAMP-46900)
* Correção de um problema que fazia com que endereços colocados em quarentena com êxito tivessem seu status definido incorretamente como Válido, removendo-os da quarentena.
* Corrigido um problema que impedia que campos personalizados fossem exibidos se contivessem caracteres especiais. (CAMP-46805)
* Correção de um problema que impedia a exibição de uma visualização detalhada específica para um perfil. Isso ocorria se o recurso de perfil tivesse sido estendido com campos personalizados com a opção **Adicionar uma seção de campos personalizados** ativada.
* Correção de um problema que retornava um código de erro 500 ao enviar eventos transacionais. (CAMP-46811)
* Correção de um problema que poderia impedir o recebimento de relatórios agendados por email. (CAMP-46891)
* Correção de um problema que ocorria ao vincular um recurso personalizado ao recurso do perfil com um link simples de cardinalidade 1. Ao acessar um perfil com o campo de recurso personalizado vazio, uma mensagem de erro agora é exibida em vez de uma lista vazia.
* Correção de um problema ao usar substituição de perfil em um fluxo de trabalho em que a página não carregava os perfis de delivery ao selecionar o perfil a ser substituído. (CAMP-46522)
* Correção de uma regressão em que o fluxo de trabalho técnico **Limpeza de Banco de Dados** tentava soltar as tabelas de trabalho de delivery expiradas, resultando nos seguintes erros: (CAMP-46536)

```
   PGS-220000 PostgreSQL error: ERROR: table ""wkdlv_24439460_data"" does not exist and WDB-200001 SQL statement 'DROP TABLE wkdlv_24448131_data' could not be executed.
```

* Correção do seguinte erro que ocorria em alguns casos ao usar o filtro personalizado em recursos personalizados: (CAMP-46509)

```
   The 'profile/xxxx' field used in the filter 'xxxxx' does not exist in custom resource 'xxx'
```

* Correção de um problema em que a preparação da notificação por push demorava muito para ser concluída. Isso foi causado pela falta de um índice nas tabelas de trabalho transitórias.
* Correção de um erro que poderia ocorrer ao usar a opção **Dimension para reconciliar** em uma atividade **Reconciliação** em um fluxo de trabalho se uma relação já estivesse definida entre um recurso personalizado e um recurso de perfil.
* Correção de um problema que ocorria ao adicionar links por meio de uma atividade **Reconciliação** ou **Enriquecimento**. Os links selecionados não eram exibidos na transição de saída.
* Correção de um problema ao usar uma atividade **Segmentation** com delivery recorrentes em um fluxo de trabalho que fazia com que o delivery fosse enviado para a audiência errada. (CAMP-46275, CAMP-46470)
* Correção de um erro em que a publicação de recursos personalizados falhava ao tentar estender o recurso de Perfil para criar dimensões de perfil personalizadas para o relatórios dinâmico. (CAMP-46266)
* Correção de um erro que ocorria ao adicionar um link a uma tabela de importação de Arquivo. Depois de adicionar uma atividade **Enriquecimento** à atividade **Importação de arquivos**, o link configurado anteriormente desapareceu. (CAMP-46557)
* Correção de um problema ao usar recursos personalizados vinculados aos dados do Perfil em que a ordem de exibição na tela de configuração Detalhe era alterada ao salvar. (CAMP-46312)
* Correção de um problema que impedia a exibição de dados no relatórios dinâmico devido a delivery com base em um mapeamento de delivery personalizado.
* Correção de um erro que poderia impedir a seleção de uma coleção com um público alvo de recurso incorreto em uma atividade de query de fluxo de trabalho.
* Corrigido um problema que fazia com que o processo do InMail validasse as rejeições em disco incorretamente.
* Correção de um erro que ocorria ao abrir uma tela de perfil devido a um erro de link.
* Correção de um problema que impedia a exclusão de dados do RGPD do fluxo de trabalho de limpeza.
* Correção de um erro que ocorria quando a configuração de agendamento era atualizada manualmente com teclado tipo nos parâmetros de agendamento do delivery de email.
* Correção de um problema que poderia impedir a edição de um perfil devido a parâmetros incorretos na unidade Organizacional.
* Correção de um problema que deixava o campo Extensão de serviço vazio e impossível de ser definido nas propriedades de Email, mesmo se ele estivesse definido no template do delivery.
* Correção de um problema que resultava em provas demorando mais para serem processadas. (CAMP-45048)
* Correção de um problema que impedia a classificação de colunas em uma tela de visão geral do perfil.
* Correção de um problema de geração de miniaturas que poderia ocorrer no Azure em variantes de email contendo caracteres chineses. (CAMP-47152)
* Corrigida uma regressão introduzida na versão 20.4 que poderia levar a taxas de abertura incorretas para o Gmail devido à filtragem de eventos de rastreamento recebidos das contas do Gmail. (CAMP-46504)
* Correção de um problema que impedia a importação de conteúdo HTML em um template de mensagem transacional. (CAMP-47318)
* Correção de um problema que poderia retardar a exibição das renderizações no relatório de renderização por email. (CAMP-46226)
* Correção de um problema que poderia impedir a publicação de recursos personalizados configurados com um elemento do tipo Lista na definição da tela. (CAMP-47217)
* Correção de um problema no Designer de email que impedia que os divisores de linha fossem renderizados corretamente no Microsoft Outlook quando colocados na parte superior do conteúdo de email. (CAMP-46294)
* Correção de um problema que causava a paralisação da reconciliação de KPIs com o fluxo de trabalho técnico da Adobe Analytics. (CAMP-46576)
* Correção de um problema no Designer de email que impedia a exibição automática de fragmentos em caixas de pesquisa ao inserir blocos de conteúdo. (CAMP-44205)
* Correção de um problema no Designer de email que fazia com que caracteres indesejados fossem exibidos em emails enviados ao usar emojis em fragmentos. (CAMP-46621)
* Corrigida a regressão introduzida na versão 20.4 no Email Designer que afetava o componente Divider, o que resultava em mais alturas de linha e distorções de imagem no conteúdo. (CAMP-46663)
* Correção de um problema que fazia com que os botões prontos para uso permanecessem centralizados quando a mensagem era enviada para uma caixa de correio do Outlook, mesmo que esses botões estivessem alinhados à direita ou à esquerda no Designer de email. (CAMP-46466)
* Correção de um problema que impedia que a lista de perfis de teste fosse atualizada ao pesquisar perfis na pré-visualização do Designer de email. (CAMP-45265)
* Correção de um problema que impedia que perfis de teste personalizados fossem exibidos na lista ao pesquisar perfis na pré-visualização do Designer de email. (CAMP-45589)
* Correção de um problema que fazia com que datas incorretas fossem exibidas ao gerar gráficos de tendência do relatório de resumo do delivery. (CAMP-45521)
