---
title: Cálculo do indicador
description: Entenda os resultados de seus relatórios com uma lista de todas as fórmulas de métrica.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 47cc11d7-89e8-4d1c-9638-5f66a53cef7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 9%

---

# Cálculo do indicador{#indicator-calculation}

>[!NOTE]
>
>Para processar e gerenciar melhor grandes volumes e análises em tempo real, os Relatórios dinâmicos usam agregações aproximadas para estimativas de contagem distintas. Agregações aproximadas oferecem uso de memória limitado e geralmente são mais rápidas que cálculos exatos.

As tabelas abaixo fornecem a lista de indicadores usados nos diferentes relatórios e suas fórmulas de cálculo, dependendo do tipo de delivery.

## Entrega por email {#email-delivery}

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
   <td> Na inclui na lista de bloqueios<br /> </td> 
   <td> @blacklisted<br /> </td> 
   <td> count(@failureReason=8, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> taxa de Inclui na lista de bloqueios<br /> </td> 
   <td> @rateBlacklisted<br /> </td> 
   <td> @blacklisted/@sent<br /> </td> 
   <td> O denominador para cálculo de taxa é baseado na contagem Enviada (Entregue + Rejeições).<br /> </td> 
  </tr> 
  <tr> 
   <td> Devoluções + Erros<br /> </td> 
   <td> @bounces<br /> </td> 
   <td> count(@status=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Rejeição + taxa de erro<br /> </td> 
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
   <td> Taxa de cliques<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @uniqueclicks/@delivered<br /> </td> 
   <td> O denominador para o cálculo da taxa baseia-se em Delivered only.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregue<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de entregas<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @delivered/@sent<br /> </td> 
   <td> O denominador para cálculo de taxa é baseado na contagem Enviada (Entregue + Rejeições).<br /> </td> 
  </tr> 
  <tr> 
   <td> Devoluções permanentes<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failureType=2 E @failureReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de devoluções permanentes<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> O denominador para cálculo de taxa é baseado na contagem Enviada (Entregue + Rejeições).<br /> </td> 
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
   <td> O denominador para o cálculo da taxa baseia-se em Delivered only.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de mirror pages<br /> </td> 
   <td> @rateMirrorPage<br /> </td> 
   <td> @mirrorPage/@delivered<br /> </td> 
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
   <td> Taxa de aberturas<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> @opens/@delivered<br /> </td> 
   <td> O denominador para o cálculo da taxa baseia-se em Delivered only.<br /> </td> 
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
   <td> O denominador para cálculo de taxa é baseado na contagem Enviada (Entregue + Rejeições).<br /> </td> 
  </tr>
  <tr> 
   <td> Rejeitada<br /> </td> 
   <td> @rejected<br /> </td> 
   <td> count(@failureReason=20, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de rejeições<br /> </td> 
   <td> @rateRejected<br /> </td> 
   <td> @rejected/@sent<br /> </td> 
   <td> O denominador para cálculo de taxa é baseado na contagem Enviada (Entregue + Rejeições).<br /> </td> 
  </tr> 
  <tr> 
   <td> Processado/enviado<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @delivered + @bounces<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Rejeição leve<br /> </td> 
   <td> @softBounces<br /> </td> 
   <td> count(@failureType=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de rejeição temporária<br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> O denominador para cálculo de taxa é baseado na contagem Enviada (Entregue + Rejeições).<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques únicos<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> Cliques únicos são calculados usando conceitos ThetaSketch. Para obter mais informações, consulte <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">exemplo</a>.<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Aberturas únicas<br /> </td> 
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
   <td> @unsubscribes/@delivered<br /> </td> 
   <td> O denominador para o cálculo da taxa baseia-se em Delivered only.<br /> </td> 
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
   <th> <strong>Label</strong> <br /> </th> 
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
   <td> @delivered<br /> </td> 
   <td> @count(status=delivery)<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de entregas<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeição + taxa de erro<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Abertura<br /> </td> 
   <td> @opens<br /> </td> 
   <td> @count(status=open)<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de aberturas<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> (@opens/@delivered)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Aberturas únicas<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> Aberturas únicas são calculadas usando conceitos ThetaSketch de RecipientIds exclusivos. Para obter mais informações, consulte <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">exemplo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=delivery)<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões exclusivas<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
  </tr> 
  <tr> 
   <td> Clique em<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> @count(status=interagir)<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques únicos<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> Cliques únicos são calculados usando conceitos ThetaSketch. Para obter mais informações, consulte <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">exemplo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cliques<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> (@interact/@delivered)*100<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Entrega no aplicativo {#in-app-delivery}

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
   <td> Processado/enviado<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
   <td> sent=delivered<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregue<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delivery)<br /> </td> 
   <td> delivery=sent<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=view) ou @count(status=botão 1 clique + botão 2 clique + rejeições)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Impressões exclusivas<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
   <td> Para <span class="uicontrol">Direcionar usuários com base em seus perfis do Campaign (inAppProfile)</span> modelo, usuário = ID do destinatário.<br /> Para <span class="uicontrol">Direcionar todos os usuários de um aplicativo móvel (inAppBroadcast)</span> e <span class="uicontrol">Direcionar usuários com base em seus perfis móveis (inApp)</span> modelos, usuário = MC Id ou equivalente que representa uma combinação exclusiva de usuário, aplicativo móvel e dispositivo.<br /> </td> 
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
   <td> @unique(@count (status=cliques))<br /> </td> 
   <td> Para <span class="uicontrol">Direcionar usuários com base em seus perfis do Campaign (inAppProfile)</span> modelo, usuário = ID do destinatário.<br /> Para <span class="uicontrol">Direcionar todos os usuários de um aplicativo móvel (inAppBroadcast)</span> e <span class="uicontrol">Direcionar usuários com base em seus perfis móveis (inApp)</span> modelos, usuário = MC Id ou equivalente que representa uma combinação exclusiva de usuário, aplicativo móvel e dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cliques no aplicativo<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> Total de cliques no Botão 1 ou Botão 2/total de impressões*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Descarte no aplicativo<br /> </td> 
   <td> @dismissal<br /> </td> 
   <td> @count (status=close)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Descartes únicos no aplicativo<br /> </td> 
   <td> @uniquedismissal<br /> </td> 
   <td> @unique(@count (status=close))<br /> </td> 
   <td> Para <span class="uicontrol">Direcionar usuários com base em seus perfis do Campaign (inAppProfile)</span> modelo, usuário = ID do destinatário.<br /> Para <span class="uicontrol">Direcionar todos os usuários de um aplicativo móvel (inAppBroadcast)</span> e <span class="uicontrol">Direcionar usuários com base em seus perfis móveis (inApp)</span> modelos, usuário = MC Id ou equivalente que representa uma combinação exclusiva de usuário, aplicativo móvel e dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de demissão no aplicativo<br /> </td> 
   <td> @dismissalrate<br /> </td> 
   <td> Total de impressões de fechamento/total*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>
