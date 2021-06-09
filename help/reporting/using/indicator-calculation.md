---
solution: Campaign Standard
product: campaign
title: Cálculo do indicador
description: Entenda os resultados de seus relatórios com uma lista de todas as fórmulas de métricas.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Relatórios
role: Leader
level: Intermediate
exl-id: 47cc11d7-89e8-4d1c-9638-5f66a53cef7e
source-git-commit: a9a91df349b107b06f229db33812a27addfb5c27
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 8%

---

# Cálculo do indicador{#indicator-calculation}

>[!NOTE]
>
>Para processar e gerenciar melhor volumes altos e análises em tempo real, os relatórios dinâmicos usam agregações aproximadas para estimativas de contagem distintas. Agregações aproximadas oferecem uso limitado de memória e geralmente são mais rápidas que computações exatas.

As tabelas abaixo fornecem a lista de indicadores usados nos diferentes relatórios e suas fórmulas de cálculo, dependendo do tipo de delivery.

## Delivery por email {#email-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Label</strong> <br /> </th> 
   <th> <strong>Nome do campo</strong> <br /> </th> 
   <th> <strong>Fórmula do cálculo de indicador</strong> <br /> </th> 
   <th> <strong>Comentários</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Conta desabilitada<br /> </td> 
   <td> @disabled<br /> </td> 
   <td> count(@failureReason=4)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Em lista de bloqueios<br /> </td> 
   <td> @blacklist<br /> </td> 
   <td> count(@failureReason=8, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de  Lista de bloqueios<br /> </td> 
   <td> @rateBlacklisted<br /> </td> 
   <td> @blacklist/@sent<br /> </td> 
   <td> O denominador para cálculo de taxa é baseado na contagem de Enviados (Entregues + Devoluções).<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeições + Erros<br /> </td> 
   <td> @bounces<br /> </td> 
   <td> count(@status=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Rejeição + Taxa de erro<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> @bounces/@sent<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Clique em<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> count(@trackingUrlType=1 ou 10 ou 11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Índice de click-through<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @uniqueclicks/@delivery<br /> </td> 
   <td> O denominador para cálculo de taxa é baseado apenas em Delivered.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregue<br /> </td> 
   <td> @delivery<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa entregue<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @delivery/@sent<br /> </td> 
   <td> O denominador para cálculo de taxa é baseado na contagem de Enviados (Entregues + Devoluções).<br /> </td> 
  </tr> 
  <tr> 
   <td> Devoluções permanentes<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failureType=2 AND @failureReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de devoluções permanentes<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> O denominador para cálculo de taxa é baseado na contagem de Enviados (Entregues + Devoluções).<br /> </td> 
  </tr> 
  <tr> 
   <td> Domínio inválido<br /> </td> 
   <td> @invalidDomain<br /> </td> 
   <td> count(@failureReason=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Caixa de entrada cheia<br /> </td> 
   <td> @mailBoxFull<br /> </td> 
   <td> count(@failureReason=5)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Mirror page<br /> </td> 
   <td> @mirrorPage<br /> </td> 
   <td> count(@trackingUrlType=6)<br /> </td> 
   <td> O denominador para cálculo de taxa é baseado apenas em Delivered.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de mirror page<br /> </td> 
   <td> @rateMirrorPage<br /> </td> 
   <td> @mirrorPage/@delivery<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Não conectado<br /> </td> 
   <td> @notConnected<br /> </td> 
   <td> count(@failureReason=6)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Abertura<br /> </td> 
   <td> @uniqueOpens<br /> </td> 
   <td> count(@trackingUrlType=2 + unique(@trackingUrlType=1,2,3,6,10,11) - unique(@trackingUrlType=2))<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de abertura<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> @opens/@delivery<br /> </td> 
   <td> O denominador para cálculo de taxa é baseado apenas em Delivered.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarentena<br /> </td> 
   <td> @quarantine<br /> </td> 
   <td> isQuarantine=true<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de quarentena<br /> </td> 
   <td> @rateQuarantine<br /> </td> 
   <td> @quarantine/@sent<br /> </td> 
   <td> O denominador para cálculo de taxa é baseado na contagem de Enviados (Entregues + Devoluções).<br /> </td> 
  </tr>
  <tr> 
   <td> Rejeitada<br /> </td> 
   <td> @rejected<br /> </td> 
   <td> count(@failureReason=20, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa rejeitada<br /> </td> 
   <td> @rateRejected<br /> </td> 
   <td> @rejected/@sent<br /> </td> 
   <td> O denominador para cálculo de taxa é baseado na contagem de Enviados (Entregues + Devoluções).<br /> </td> 
  </tr> 
  <tr> 
   <td> Processado/enviado<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @delivery + @bounces<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Rejeição suave<br /> </td> 
   <td> @softBounces<br /> </td> 
   <td> count(@failureType=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de rejeição suave<br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> O denominador para cálculo de taxa é baseado na contagem de Enviados (Entregues + Devoluções).<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques exclusivos<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> Cliques exclusivos são calculados usando os conceitos do ThetaSketch. Para obter mais informações, consulte este <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">exemplo</a>.<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Aberturas exclusivas<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> unique(@trackingUrlType=1,2,3,6,10,11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Inacessível <br /> </td> 
   <td> @unreachable<br /> </td> 
   <td> count(@failureReason=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Cancelar inscrição<br /> </td> 
   <td> @unsubscribes<br /> </td> 
   <td> count(@trackingUrlType=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cancelamento de inscrição<br /> </td> 
   <td> @rateUnsubscribes<br /> </td> 
   <td> @unsubscribes/@delivery<br /> </td> 
   <td> O denominador para cálculo de taxa é baseado apenas em Delivered.<br /> </td> 
  </tr> 
  <tr> 
   <td> Usuário desconhecido<br /> </td> 
   <td> @unknownUser<br /> </td> 
   <td> count(@failureReason=1)<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

## Entrega por notificação por push {#push-notification-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Rótulo</strong> <br /> </th> 
   <th> <strong>Nome do campo</strong> <br /> </th> 
   <th> <strong>Fórmula do cálculo de indicador</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Processado/enviado<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregue<br /> </td> 
   <td> @delivery<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa entregue<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> (@delivery/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeição + Taxa de erro<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> (@delivery/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Abertura<br /> </td> 
   <td> @opens<br /> </td> 
   <td> @count(status=open)<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de abertura<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> (@opens/@delivery)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Aberturas exclusivas<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> As aberturas exclusivas são calculadas usando os conceitos de ThetaSketch de RecipientIds exclusivos. Para obter mais informações, consulte este <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">exemplo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões<br /> </td> 
   <td> @impressões<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões exclusivas<br /> </td> 
   <td> @uniqueimpressões<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
  </tr> 
  <tr> 
   <td> Clique em<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> @count(status=interact)<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques exclusivos<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> Cliques exclusivos são calculados usando os conceitos do ThetaSketch. Para obter mais informações, consulte este <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">exemplo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Índice de click-through<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> (@interact/@delivery)*100<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Entrega no aplicativo {#in-app-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Rótulo</strong> <br /> </th> 
   <th> <strong>Nome do campo</strong> <br /> </th> 
   <th> <strong>Fórmula do cálculo de indicador</strong> <br /> </th> 
   <th> <strong>Comentários</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Processado/enviado<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
   <td> sent=delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregue<br /> </td> 
   <td> @delivery<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
   <td> delivery=enviado<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões<br /> </td> 
   <td> @impressões<br /> </td> 
   <td> @count(status=view) ou @count(status=button 1 clique + botão 2 clique + demissões)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Impressões exclusivas<br /> </td> 
   <td> @uniqueimpressões<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
   <td> Para usuários do <span class="uicontrol">Target com base no modelo do perfil da campanha (inAppProfile)</span>, usuário = Id do destinatário.<br /> Para  <span class="uicontrol">direcionar todos os usuários de um aplicativo móvel (inAppBroadcast)</span> e usuários do  <span class="uicontrol">Target com base em seus modelos de perfil móvel (inApp)</span> , usuário = MC Id ou equivalente que representa uma combinação exclusiva de usuário, aplicativo móvel e dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques no aplicativo <br /> </td> 
   <td> @inappclicks<br /> </td> 
   <td> @count (status=click)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Cliques únicos no aplicativo<br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @unique(@count (status=clicks))<br /> </td> 
   <td> Para usuários do <span class="uicontrol">Target com base no modelo do perfil da campanha (inAppProfile)</span>, usuário = Id do destinatário.<br /> Para  <span class="uicontrol">direcionar todos os usuários de um aplicativo móvel (inAppBroadcast)</span> e usuários do  <span class="uicontrol">Target com base em seus modelos de perfil móvel (inApp)</span> , usuário = MC Id ou equivalente que representa uma combinação exclusiva de usuário, aplicativo móvel e dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Índice de click-through no aplicativo<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> Total de cliques no Botão 1 ou no Botão 2/total de impressões*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Demissão no aplicativo<br /> </td> 
   <td> @dismiss<br /> </td> 
   <td> @count (status=close)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Despedimentos únicos no aplicativo<br /> </td> 
   <td> @uniquedismiss<br /> </td> 
   <td> @unique(@count (status=close))<br /> </td> 
   <td> Para usuários do <span class="uicontrol">Target com base no modelo do perfil da campanha (inAppProfile)</span>, usuário = Id do destinatário.<br /> Para  <span class="uicontrol">direcionar todos os usuários de um aplicativo móvel (inAppBroadcast)</span> e usuários do  <span class="uicontrol">Target com base em seus modelos de perfil móvel (inApp)</span> , usuário = MC Id ou equivalente que representa uma combinação exclusiva de usuário, aplicativo móvel e dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de desativação no aplicativo<br /> </td> 
   <td> @dismissalrate<br /> </td> 
   <td> Total de impressões de fechamento/total*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>
