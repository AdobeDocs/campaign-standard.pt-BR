---
solution: Campaign Standard
product: campaign
title: Cálculo do indicador
description: Entenda os resultados de seus relatórios com uma lista da fórmula de cada métrica.
audience: reporting
content-type: reference
topic-tags: about-reporting
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 8%

---


# Cálculo do indicador{#indicator-calculation}

>[!NOTE]
>
>Para processar e gerenciar melhor volumes altos e análises em tempo real, o relatórios dinâmico usa agregações aproximadas para estimativas de contagem distintas. Agregações aproximadas Uso de memória limitada por oferta e geralmente são mais rápidas que computações exatas.

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
   <td> Na lista de bloqueios<br /> </td> 
   <td> @incluído na blacklist<br /> </td> 
   <td> count(@failureReason=8, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> lista de bloqueios taxa de <br /> </td> 
   <td> @rateBlacklisted<br /> </td> 
   <td> @incluído na blacklist/@send<br /> </td> 
   <td> O denominador para cálculo de taxa baseia-se na contagem de Enviados (Entregues + Rejeições).<br /> </td> 
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
   <td> @bounces/@send<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Clique em<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> count(@trackingUrlType=1 ou 10 ou 11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Clique na taxa<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @uniqueclicks/@entregue<br /> </td> 
   <td> O denominador para cálculo de taxa se baseia somente em Entregue.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregue<br /> </td> 
   <td> @entregue<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa entregue<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @entregue/@send<br /> </td> 
   <td> O denominador para cálculo de taxa baseia-se na contagem de Enviados (Entregues + Rejeições).<br /> </td> 
  </tr> 
  <tr> 
   <td> Devoluções permanentes<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failureType=2 AND @failureReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de rejeição em disco rígido<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@send<br /> </td> 
   <td> O denominador para cálculo de taxa baseia-se na contagem de Enviados (Entregues + Rejeições).<br /> </td> 
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
   <td> O denominador para cálculo de taxa se baseia somente em Entregue.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de mirror page<br /> </td> 
   <td> @rateMirrorPage<br /> </td> 
   <td> @mirrorPage/@entregue<br /> </td> 
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
   <td> @abertos/@entregue<br /> </td> 
   <td> O denominador para cálculo de taxa se baseia somente em Entregue.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarentena<br /> </td> 
   <td> @quarentena<br /> </td> 
   <td> isQuarantine=true<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa de quarentena<br /> </td> 
   <td> @rateQuarantine<br /> </td> 
   <td> @quarentena/@send<br /> </td> 
   <td> O denominador para cálculo de taxa baseia-se na contagem de Enviados (Entregues + Rejeições).<br /> </td> 
  </tr>
  <tr> 
   <td> Rejeitada<br /> </td> 
   <td> @rejeitada<br /> </td> 
   <td> count(@failureReason=20, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taxa rejeitada<br /> </td> 
   <td> @rateReject<br /> </td> 
   <td> @supported/@send<br /> </td> 
   <td> O denominador para cálculo de taxa baseia-se na contagem de Enviados (Entregues + Rejeições).<br /> </td> 
  </tr> 
  <tr> 
   <td> Processado/enviado<br /> </td> 
   <td> @send<br /> </td> 
   <td> @entregue + @bounces<br /> </td> 
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
   <td> @softBounces/@send<br /> </td> 
   <td> O denominador para cálculo de taxa baseia-se na contagem de Enviados (Entregues + Rejeições).<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques únicos<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> Cliques únicos são calculados usando conceitos de ThetaSketch. Para obter mais informações, consulte este <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">exemplo</a>.<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Aberturas exclusivas<br /> </td> 
   <td> @uniqueopen<br /> </td> 
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
   <td> Cancelar assinatura<br /> </td> 
   <td> @unsubscribes<br /> </td> 
   <td> count(@trackingUrlType=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Cancelar assinatura da taxa<br /> </td> 
   <td> @rateUnsubscribes<br /> </td> 
   <td> @unsubscribes/@entregue<br /> </td> 
   <td> O denominador para cálculo de taxa se baseia somente em Entregue.<br /> </td> 
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
   <td> @send<br /> </td> 
   <td> @count(status=enviado)<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregue<br /> </td> 
   <td> @entregue<br /> </td> 
   <td> @count(status=entregue)<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa entregue<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> (@entregue/@enviado)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeição + Taxa de erro<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> (@entregue/@enviado)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Abertura<br /> </td> 
   <td> @opens<br /> </td> 
   <td> @count(status=open)<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de abertura<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> (@open/@entregue)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Aberturas exclusivas<br /> </td> 
   <td> @uniqueopen<br /> </td> 
   <td> As aberturas exclusivas são calculadas usando conceitos ThetaSketch de RecipientIds exclusivos. Para obter mais informações, consulte este <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">exemplo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões<br /> </td> 
   <td> @impressões<br /> </td> 
   <td> @count(status=entregue)<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões exclusivas<br /> </td> 
   <td> @uniqueimpressões<br /> </td> 
   <td> @unique(@count(status=visualização))<br /> </td> 
  </tr> 
  <tr> 
   <td> Clique em<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> @count(status=interact)<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques únicos<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> Cliques únicos são calculados usando conceitos de ThetaSketch. Para obter mais informações, consulte este <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">exemplo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clique na taxa<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> (@interact/@entregue)*100<br /> </td> 
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
   <td> @send<br /> </td> 
   <td> @count(status=enviado)<br /> </td> 
   <td> send=delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregue<br /> </td> 
   <td> @entregue<br /> </td> 
   <td> @count(status=entregue)<br /> </td> 
   <td> delivery=send<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões<br /> </td> 
   <td> @impressões<br /> </td> 
   <td> @count(status=visualização) ou @count(status=botão 1 clique + botão 2 clique + demissões)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Impressões exclusivas<br /> </td> 
   <td> @uniqueimpressões<br /> </td> 
   <td> @unique(@count(status=visualização))<br /> </td> 
   <td> Para os usuários do Público alvo <span class="uicontrol">com base em seu perfil de Campanha (inAppProfile)</span> modelo, usuário = Id do Recipient.<br /> Para  <span class="uicontrol">Público alvo, todos os usuários de um aplicativo móvel (inAppBroadcast) </span> e usuários de  <span class="uicontrol">Públicos alvos com base em seus </span> modelos de perfil móvel (inApp)usuário = MC Id ou equivalente que representa uma combinação exclusiva de usuário, aplicativo móvel e dispositivo.<br /> </td> 
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
   <td> Para os usuários do Público alvo <span class="uicontrol">com base em seu perfil de Campanha (inAppProfile)</span> modelo, usuário = Id do Recipient.<br /> Para  <span class="uicontrol">Público alvo, todos os usuários de um aplicativo móvel (inAppBroadcast) </span> e usuários de  <span class="uicontrol">Públicos alvos com base em seus </span> modelos de perfil móvel (inApp)usuário = MC Id ou equivalente que representa uma combinação exclusiva de usuário, aplicativo móvel e dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clique no aplicativo na taxa<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> Total de cliques no Botão 1 ou no Botão 2/total de impressões*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Demissão no aplicativo<br /> </td> 
   <td> @demissão<br /> </td> 
   <td> @count (status=close)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Despedimentos únicos no aplicativo<br /> </td> 
   <td> @uniquedismissal<br /> </td> 
   <td> @unique(@count (status=close))<br /> </td> 
   <td> Para os usuários do Público alvo <span class="uicontrol">com base em seu perfil de Campanha (inAppProfile)</span> modelo, usuário = Id do Recipient.<br /> Para  <span class="uicontrol">Público alvo, todos os usuários de um aplicativo móvel (inAppBroadcast) </span> e usuários de  <span class="uicontrol">Públicos alvos com base em seus </span> modelos de perfil móvel (inApp)usuário = MC Id ou equivalente que representa uma combinação exclusiva de usuário, aplicativo móvel e dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de demissão no aplicativo<br /> </td> 
   <td> @dismissalrate<br /> </td> 
   <td> Total de impressões de fechamento/total*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

