---
title: Rastreamento de mensagens
description: Saiba como rastrear o comportamento de seus recipient de delivery.
page-status-flag: never-activated
uuid: c3721647-0663-4614-a9c9-3b3a40af328a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
discoiquuid: 6fa50f0d-3dcf-4a9e-bccc-1ecda2bfb449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2926b916ac8e8a2605694758407c48b1db359c60

---


# Rastreamento de mensagens{#tracking-messages}

## Sobre o rastreamento {#about-tracking}

Graças às suas funcionalidades de rastreamento, o Adobe Campaign permite rastrear o comportamento dos recipient do delivery. Para fazer isso, o Adobe Campaign usa cookies de sessão e cookies permanentes.

Você pode informar aos usuários que seus sites estão equipados com ferramentas de rastreamento da Web por meio de uma solicitação de autorização (que aparece na página, por exemplo) com uma caixa de seleção para autorizar o uso de cookies ou adicionar um banner na parte superior da primeira página em que eles chegam, etc. As janelas pop-up devem ser evitadas, pois geralmente são bloqueadas pelos navegadores.

As informações de rastreamento estão disponíveis para cada contato do banco de dados no **[!UICONTROL integrated customer profiles]**. Para obter mais informações, consulte [esta seção](../../audiences/using/integrated-customer-profile.md).

O Adobe Campaign usa dois tipos de cookies:

* Um cookie de sessão (nlid). Ele contém o identificador do email enviado ao contato (BroadlogId) e o identificador do modelo de mensagem (deliveryId). Ele é adicionado quando o contato clica em uma URL incluída em um e-mail enviado pelo Adobe Campaign e permite que você acompanhe seu comportamento na Web. Esse cookie de sessão é apagado automaticamente quando o navegador é fechado. O contato pode configurar o navegador para recusar cookies.
* Um cookie compartilhado entre as soluções da Adobe Experience Cloud. Isso permite identificar os usuários que interagem com as soluções da Experience Cloud ao visitar um site. A descrição deste cookie está disponível aqui: [https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html).

O rastreamento com o Adobe Campaign Standard permite acessar as seguintes funcionalidades:

<table>
<tr>
    <td valign="top">
        <a href="../../administration/using/configuring-email-channel.md#tracking-parameters"><img width="60px" alt="condições" src="assets/icon_email_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="https://helpx.adobe.com/campaign/kb/push-tracking.html"><img width="60px" alt="condições" src="assets/icon_push_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="../../designing/using/links.md#about-tracked-urls"><img width="60px" alt="condições" src="assets/icon_url.png"/></a>
    </td>
        <td valign="top">
          <a href="../../sending/using/tracking-messages.md#tracking-logs"><img width="60px" alt="condições" src="assets/icon_log.png"/></a>
    </td>
    </td>
    <td valign="top">
          <a href="../../reporting/using/tracking-indicators.md"><img width="60px" alt="condições" src="assets/icon_report.png"/></a>

</tr>
<tr>
<td>Tracking de email</td>
<td>Rastreamento de push</td>
<td>URLs acompanhados</td>
<td>Logs de rastreamento</td>
<td>Relatório de rastreamento</td>
</tr>

</table>

## Logs de rastreamento {#tracking-logs}

A guia **[!UICONTROL Tracking logs]** lista o histórico de rastreamento desse delivery. Esta guia exibe as informações de rastreamento das mensagens enviadas, como todos os URLs que foram rastreados pelo Adobe Campaign. As informações de rastreamento nesta guia são atualizadas a cada 10 minutos.

>[!NOTE]
>
>Se o rastreamento não estiver ativado para um delivery, essa guia não será exibida. Logs de rastreamento estão disponíveis somente para canais de notificação por **email** e **push** .

![](assets/tracking_logs.png)

No exemplo acima, o recipient:

* A mensagem foi aberta.
* Clicado no link personalizado &quot;APRENDER MAIS&quot;.
* Clicado no link unsubscription e mirror page.

Na **[!UICONTROL Type]** coluna, os valores possíveis são:

* **[!UICONTROL Email click]**: os recipient clicaram em um link personalizado.
* **[!UICONTROL Mirror page]**: o recipient clicou em um link para o mirror page.
* **[!UICONTROL Open]**: o recipient abriu o email.
* **[!UICONTROL Opt-out]**: o recipient clicou em um link de unsubscription.

>[!NOTE]
>
>Para o canal de notificação **por** push, somente cliques em notificações móveis são rastreados. Nesse caso, o valor será **[!UICONTROL Click on mobile notification]**.

Para obter mais informações sobre como inserir links de rastreamento, consulte [esta página](../../designing/using/links.md#inserting-a-link).

## URLs acompanhados {#tracked-urls}

A **[!UICONTROL Tracked URLs]** guia agrupa os URLs contidos na mensagem enviada, incluindo o tipo de URL e o URL de origem.

![](assets/sending_delivery6.png)

For more on tracking links, refer to [this section](../../designing/using/links.md#about-tracked-urls).
