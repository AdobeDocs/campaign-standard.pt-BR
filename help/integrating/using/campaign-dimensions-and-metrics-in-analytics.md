---
title: Dimensões e métricas do Campaign no Analytics
description: Saiba mais sobre as diferentes dimensões que você pode encontrar no Adobe Analytics para começar a rastrear seus deliveries de email do Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 6516c71a-efa8-4778-82bb-10615378f985
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 4%

---

# Dimensões e métricas do Campaign no Analytics{#campaign-dimensions-and-metrics-in-analytics}

A integração do Adobe Campaign e do Adobe Analytics permite rastrear o sucesso de suas entregas de email diretamente no Adobe Analytics.

A campanha **[!UICONTROL dimensions]** encontrada no Analytics está listada abaixo:

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> Definição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> ID da campanha<br /> </td> 
   <td> Nome interno da campanha conforme visto na Campanha<br /> </td> 
  </tr> 
  <tr> 
   <td> Rótulo da campanha<br /> </td> 
   <td> Rótulo da campanha como visto na Campanha <br /> </td> 
  </tr> 
  <tr> 
   <td> ID de Entrega<br /> </td> 
   <td> Nome interno do delivery conforme visto no Campaign.<br /> Por exemplo, DM1 é uma entrega recorrente programada para enviar entregas secundárias toda semana. DM2, DM3 e DM4 são enviados nas primeiras três semanas. A dimensão ID de Entrega exibirá os resultados para cada entrega, especificamente DM1 a DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Rótulo de entrega<br /> </td> 
   <td> Rótulo de entrega como visto na Campanha <br /> </td> 
  </tr> 
  <tr> 
   <td> ID de entrega executada<br /> </td> 
   <td> Nome interno do delivery conforme visto no Campaign. Isso só afeta a entrega em execução no Campaign.<br /> Por exemplo, DM1 é uma entrega recorrente programada para enviar entregas secundárias toda semana. DM2, DM3 e DM4 são enviados nas primeiras três semanas. A dimensão ID de entrega executada exibirá os resultados das entregas executadas, especificamente as entregas secundárias DM2, DM3 e DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Rótulo de entrega executado <br /> </td> 
   <td> Rótulo de delivery conforme visto no Campaign. Isso só afeta a entrega em execução no Campaign.<br /> </td> 
  </tr> 
 </tbody> 
</table>

A campanha **[!UICONTROL metrics]** encontrada no Analytics está listada abaixo:

<table> 
 <thead> 
  <tr> 
   <th> Métrica<br /> </th> 
   <th> Definição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Clicou<br /> </td> 
   <td> Número de vezes que um conteúdo foi clicado em uma entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregue<br /> </td> 
   <td> Número de mensagens enviadas com êxito, em relação ao número total de mensagens enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aberto<br /> </td> 
   <td> Número de vezes que uma mensagem foi aberta em uma entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Sent<br /> </td> 
   <td> Número total de envios para a entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Total de Rejeições<br /> </td> 
   <td> Total de erros acumulados durante o processamento de entrega e retorno automático em relação ao número total de mensagens enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abertura única<br /> </td> 
   <td> Número de destinatários que abriram a entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clique Único<br /> </td> 
   <td> Número de destinatários que clicaram em um conteúdo em uma entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Assinatura cancelada<br /> </td> 
   <td> Número de cliques no link de cancelamento de assinatura.<br /> </td> 
  </tr> 
 </tbody> 
</table>
