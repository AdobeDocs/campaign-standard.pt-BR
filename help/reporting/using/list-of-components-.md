---
title: Lista de componentes
description: Encontre aqui a lista de todos os componentes disponíveis em Relatórios dinâmicos, bem como suas definições.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: 8980bf05-60a8-4360-a354-445e1faeb5b2
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1269'
ht-degree: 7%

---

# Lista de componentes {#list-of-components}

Para saber mais sobre a compatibilidade entre dimensões e métricas, consulte este [tabela](/help/reporting/using/assets/dynamic_report_compatibility.pdf). Se dois componentes não forem compatíveis, a célula exibirá o valor **Nenhum**.

[![imagem](assets/dynamic_report_compatibility.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf)

## Dimensões {#dimensions}

A tabela abaixo fornece a lista de dimensões usadas em relatórios e suas definições.

<table> 
 <thead> 
  <tr> 
   <th> Dimensão<br /> </th> 
   <th> Definição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Navegador<br /> </td> 
   <td> Navegador no qual a mensagem foi aberta ou clicada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Campanha<br /> </td> 
   <td> Rótulo e ID da sua campanha.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cidade<br /> </td> 
   <td> Cidade registrada no perfil do destinatário.<br /> </td> 
  </tr> 
  <tr> 
   <td> País/região<br /> </td> 
   <td> País registrado no perfil do destinatário.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery<br /> </td> 
   <td> Etiqueta e ID da entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dispositivo<br /> </td> 
   <td> Dispositivo no qual o email/SMS/notificação por push foi aberto/exibido/clicado.<br /> </td> 
  </tr> 
  <tr> 
   <td> Motivo da falha<br /> </td> 
   <td> Tipos de erros que causaram rejeições para cada delivery, por exemplo, usuário desconhecido, domínio inválido ou caixa de correio cheia.<br /> </td> 
  </tr> 
  <tr> 
   <td> Sexo<br /> </td> 
   <td> Sexo do destinatário, como masculino ou feminino. Se o campo de gênero estiver vazio no perfil do recipient, o valor será nenhum.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ações de mensagem no aplicativo<br /> </td> 
   <td> Ações na mensagem no aplicativo entregue, por exemplo, ações no botão 1 ou 2 ou rejeições.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tipo de mensagem<br /> </td> 
   <td> Canal usado para a entrega, como email, SMS, notificação por push ou no aplicativo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nome do aplicativo móvel<br /> </td> 
   <td> Nome do aplicativo móvel<br /> </td> 
  </tr> 
  <tr> 
   <td> Plataforma<br /> </td> 
   <td> Plataforma do dispositivo do qual a mensagem foi aberta/exibida/clicada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Perfil<br /> </td> 
   <td> Reagrupa campos de perfil prontos para uso e personalizados criados durante a extensão de recurso de perfil. Para obter mais informações, consulte este <a href="../../developing/using/key-steps-to-add-a-resource.md">página</a> ou esta <a href="../../reporting/using/creating-a-custom-profile-dimension.md">exemplo</a>.<br /> Observe que os dados dessa dimensão são recuperados assim que o recurso personalizado vinculado ao campo de perfil é publicado.<br /> </td> 
  </tr> 
  <tr> 
   <td> Plataforma de push<br /> </td> 
   <td> Plataforma do dispositivo do qual a notificação por push foi aberta, como iOS ou Android.<br /> </td> 
  </tr> 
  <tr> 
   <td> Domínio do destinatário<br /> </td> 
   <td> Domínio usado para abrir o email.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery recorrente<br /> </td> 
   <td> Rótulo e ID da entrega recorrente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Domínio do remetente<br /> </td> 
   <td> Domínio usado para enviar o email.<br /> </td> 
  </tr> 
  <tr> 
   <td> IP do remetente<br /> </td> 
   <td> IP usado para enviar o email.<br /> </td> 
  </tr> 
  <tr> 
   <td> Estado<br /> </td> 
   <td> Estado registrado no perfil do destinatário.<br /> </td> 
  </tr> 
  <tr> 
   <td> URL de rastreamento<br /> </td> 
   <td> URL no qual o usuário clicou a partir da mensagem.<br /> </td> 
  </tr> 
  <tr> 
   <td> Categoria de URL de rastreamento<br /> </td> 
   <td> Categoria atribuída ao URL de rastreamento.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rótulo do URL de rastreamento<br /> </td> 
   <td> Rótulo fornecido ao URL, como mirror page, entre em contato conosco ou abra.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega transacional<br /> </td> 
   <td> Rótulo e ID da entrega transacional.<br /> </td> 
  </tr> 
  <tr> 
   <td> Variante<br /> </td> 
   <td> Variante do email em caso de teste A/B.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Métricas {#metrics}

As tabelas abaixo fornecem a lista de métricas usadas em relatórios e suas definições, dependendo do tipo de delivery.

### Métricas de email e SMS {#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Métrica<br /> </th> 
   <th> Definição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Na inclui na lista de bloqueios<br /> </td> 
   <td> Número de destinatários que declararam um email como spam ou lixo eletrônico.<br /> </td> 
  </tr> 
  <tr> 
   <td> taxa de Inclui na lista de bloqueios<br /> </td> 
   <td> Porcentagem de entregas marcadas na inclui na lista de bloqueios.<br /> </td> 
  </tr> 
  <tr> 
   <td> Devoluções + Erros<br /> </td> 
   <td> Total de erros acumulados durante o processamento de entrega e retorno automático em relação ao número total de mensagens enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeição + taxa de erro<br /> </td> 
   <td> Porcentagem de emails enviados em comparação ao email enviado.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clique em<br /> </td> 
   <td> Número de vezes que um conteúdo foi clicado em um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cliques<br /> </td> 
   <td> Porcentagem de cliques em uma entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregue<br /> </td> 
   <td> Número de mensagens enviadas com êxito em relação ao número total de mensagens enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de entregas<br /> </td> 
   <td> Porcentagem de mensagens enviadas com êxito.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeição permanente<br /> </td> 
   <td> Número total de erros permanentes, como um endereço de email incorreto.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de rejeição permanente<br /> </td> 
   <td> Porcentagem de entregas que falharam devido a erros permanentes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mirror page<br /> </td> 
   <td> Número de destinatários que clicaram no link da mirror page.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de mirror pages<br /> </td> 
   <td> Porcentagem de cliques no link da mirror page em comparação ao total de mensagens de delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques de oferta<br /> </td> 
   <td> Número de vezes que uma oferta foi clicada em um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cliques da oferta<br /> </td> 
   <td> Porcentagem de cliques em uma oferta.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abertura<br /> </td> 
   <td> Número de vezes que uma mensagem foi aberta em um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de aberturas<br /> </td> 
   <td> Porcentagem de mensagens abertas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Processado/enviado<br /> </td> 
   <td> Número total de envios para a entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarentena<br /> </td> 
   <td> Número de mensagens que foram rejeitadas e resultaram na quarentena do endereço.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de quarentena<br /> </td> 
   <td> Porcentagem de quarentenas em comparação às mensagens enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeitada<br /> </td> 
   <td> Número de mensagens classificadas como spam pelos servidores SMTP.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de rejeições<br /> </td> 
   <td> Porcentagem de mensagens marcadas como rejeitadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeição leve<br /> </td> 
   <td> Número total de erros temporários, como uma caixa de entrada cheia.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de rejeição temporária<br /> </td> 
   <td> Porcentagem de entregas que falharam devido a um motivo temporário.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques únicos<br /> </td> 
   <td> Número de recipients que clicaram em um conteúdo em um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aberturas únicas<br /> </td> 
   <td> Número de destinatários que abriram o delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cancelamento de assinatura exclusivo<br /> </td> 
   <td> Número de recipients que clicaram no link unsubscription.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cancelamento de inscrição<br /> </td> 
   <td> Número de cancelamentos de subscrição exclusivos em comparação às mensagens entregues.<br /> </td> 
  </tr> 
  <tr> 
   <td> Assinatura cancelada<br /> </td> 
   <td> Número de cliques no link unsubscription.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Métricas de notificação por push {#push-notification-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Métrica<br /> </th> 
   <th> Definição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Devoluções + Erros<br /> </td> 
   <td> Total de erros acumulados durante o delivery em relação ao número total de mensagens enviadas, por exemplo, erros do MCPNS ou do provedor.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeição + taxa de erro<br /> </td> 
   <td> Porcentagem de notificações por push que foram rejeitadas em comparação às notificações por push enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clique em<br /> </td> 
   <td> Número de vezes que uma notificação por push foi entregue ao dispositivo e clicada pelo usuário. O usuário queria visualizar a notificação, que será movida para o rastreamento de Abertura por push ou a descartará.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cliques<br /> </td> 
   <td> Porcentagem de usuários que interagiram com a notificação por push.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregue<br /> </td> 
   <td> Número de notificações por push enviadas com êxito, em relação ao número total de notificações por push enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de entregas<br /> </td> 
   <td> Porcentagem de notificações por push enviadas com êxito.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões<br /> </td> 
   <td> Número de vezes que uma notificação por push foi entregue ao dispositivo e deixada intocada na central de notificações. Na maioria dos casos, o número de impressões deve ser semelhante ao número entregue. Isso garante que o dispositivo recebeu a mensagem e transmitiu essas informações de volta ao servidor.<br /> </td> 
  </tr> 
  <tr> 
   <td> Processado/enviado<br /> </td> 
   <td> Número total de notificações por push enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abertura<br /> </td> 
   <td> Número total de notificações por push entregues ao dispositivo e clicadas pelos usuários, abrindo o aplicativo. Isso é semelhante ao clique por push, exceto que uma abertura por push não será acionada se a notificação tiver sido descartada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de aberturas<br /> </td> 
   <td> Porcentagem de notificações por push abertas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques únicos<br /> </td> 
   <td> Número de vezes que um usuário único interage com a notificação por push, por exemplo, cliques na notificação ou no botão.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões exclusivas<br /> </td> 
   <td> Número de impressões por recipient.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aberturas únicas<br /> </td> 
   <td> Número de destinatários que abriram o delivery.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Métricas no aplicativo {#in-app-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Métrica<br /> </th> 
   <th> Definição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Entregue<br /> </td> 
   <td> Número total de mensagens no aplicativo entregues ao dispositivo pelo provedor de serviços.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões<br /> </td> 
   <td> Total de mensagens no aplicativo vistas pelos destinatários dependendo se o critério do acionador foi atendido.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques no aplicativo <br /> </td> 
   <td> Número total de destinatários que clicaram no Botão 1 ou Botão 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cliques no aplicativo<br /> </td> 
   <td> Porcentagem de usuários que clicaram no Botão 1 ou Botão 2 em comparação aos usuários que viram a mensagem.<br /> </td> 
  </tr> 
  <tr> 
   <td> Descarte no aplicativo<br /> </td> 
   <td> Número total de mensagens que os destinatários rejeitaram clicando no botão Fechar ou descartando automaticamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de demissão no aplicativo<br /> </td> 
   <td> Porcentagem de mensagens no aplicativo que os destinatários rejeitaram.<br /> </td> 
  </tr> 
  <tr> 
   <td> Processado/enviado<br /> </td> 
   <td> Número total de mensagens no aplicativo enviadas do Adobe Campaign como parte do processo de envio do delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões exclusivas<br /> </td> 
   <td> Número de impressões por um recipient exclusivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques únicos no aplicativo<br /> </td> 
   <td> Número de vezes que os recipients clicaram no Botão 1 ou Botão 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Descartes únicos no aplicativo<br /> </td> 
   <td> Número de vezes que os destinatários rejeitaram uma mensagem no aplicativo.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Segmentos {#segments}

A tabela abaixo fornece a lista de segmentos usados em relatórios e suas definições.

<table> 
 <thead> 
  <tr> 
   <th> Segmento<br /> </th> 
   <th> Definição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Idade: Boomers 1<br /> </td> 
   <td> Recipients nascidos de 1946 a 1954.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Boomers 2<br /> </td> 
   <td> Recipients nascidos de 1955 a 1965.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: de 18 a 25<br /> </td> 
   <td> Recipients de 18 a 25 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: de 26 a 30<br /> </td> 
   <td> Recipients de 26 a 30 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: de 31 a 40<br /> </td> 
   <td> Recipients de 31 a 40 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: de 41 a 50<br /> </td> 
   <td> Recipients de 41 a 50 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Geração X<br /> </td> 
   <td> Recipients nascidos de 1966 a 1976.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: geração Y (Millennials)<br /> </td> 
   <td> Recipients nascidos de 1977 a 1994.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: geração Z<br /> </td> 
   <td> Recipients nascidos de 1995 a hoje.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: maior que 50<br /> </td> 
   <td> Recipients com idade superior a 50 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: menos de 25<br /> </td> 
   <td> Recipients com menos de 25 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: menos de 30<br /> </td> 
   <td> Recipients com menos de 30 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: menos de 40<br /> </td> 
   <td> Recipients com menos de 40 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: menos de 50<br /> </td> 
   <td> Recipients com menos de 50 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: geração silenciosa<br /> </td> 
   <td> Recipients nascidos em 1945 ou antes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Todas as visitas<br /> </td> 
   <td> Todos os recipients<br /> </td> 
  </tr>
 </tbody> 
</table>
