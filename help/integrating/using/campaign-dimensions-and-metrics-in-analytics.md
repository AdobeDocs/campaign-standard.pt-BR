---
title: Dimensões e métricas do Campaign no Analytics
description: Saiba mais sobre as diferentes dimensões que você pode encontrar no Adobe Analytics para começar a rastrear suas entregas de email pelo Adobe Campaign.
page-status-flag: nunca ativado
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: integrando
content-type: referência
topic-tags: trabalhar com campanha e análise
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Dimensões e métricas do Campaign no Analytics{#campaign-dimensions-and-metrics-in-analytics}

A integração entre o Adobe Campaign e o Adobe Analytics permite rastrear o sucesso das entregas de email diretamente no Adobe Analytics.

A campanha **[!UICONTROL dimensions]** encontrada no Analytics está listada abaixo:

<table> 
 <thead> 
  <tr> 
   <th> Dimensão<br /> </th> 
   <th> Definição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> ID da campanha<br /> </td> 
   <td> Nome interno da campanha, como visto no Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Rótulo da campanha<br /> </td> 
   <td> Rótulo da campanha como visto no Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> ID de entrega<br /> </td> 
   <td> O nome interno da entrega como visto no Campaign.<br /> Por exemplo, DM1 é uma entrega recorrente programada para enviar entregas secundárias toda semana. DM2, DM3 e DM4 são enviados nas três primeiras semanas. A dimensão da ID de entrega exibirá os resultados de cada entrega, a saber, DM1 para DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Rótulo de entrega<br /> </td> 
   <td> Rótulo da entrega como visto no Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> ID de entrega executada<br /> </td> 
   <td> O nome interno da entrega como visto no Campaign. Isso só diz respeito à execução no Campaign.<br /> Por exemplo, DM1 é uma entrega recorrente programada para enviar entregas secundárias toda semana. DM2, DM3 e DM4 são enviados nas três primeiras semanas. A dimensão ID de entrega Executada exibirá os resultados das entregas executadas, a saber, as entregas secundárias DM2, DM3 e DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Rótulo de entrega executado<br /> </td> 
   <td> Rótulo da entrega como visto no Campaign. Isso só diz respeito à execução no Campaign.<br /> </td> 
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
   <td> Clicado<br /> </td> 
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
   <td> O número total de envios para a entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Total de rejeições<br /> </td> 
   <td> Total de erros acumulados durante a entrega e o processamento automático de retorno em relação ao número total de mensagens enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abertura exclusiva<br /> </td> 
   <td> Número de destinatários que abriram a entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clique único<br /> </td> 
   <td> Número de destinatários que clicaram em um conteúdo em uma entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Inscrito<br /> </td> 
   <td> Número de cliques no link unsubscription.<br /> </td> 
  </tr> 
 </tbody> 
</table>

