---
solution: Campaign Standard
product: campaign
title: Rastreamento de mensagens
description: Saiba como rastrear o comportamento dos recipients do seu delivery.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: Performance Monitoring
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 38%

---


# Rastreamento de mensagens{#tracking-messages}

## Sobre o rastreamento {#about-tracking}

Graças às suas funcionalidades de rastreamento, o Adobe Campaign permite rastrear o comportamento dos recipients do seu delivery. Para fazer isso, o Adobe Campaign usa cookies de sessão e cookies permanentes.

Você pode informar aos usuários que seus sites estão equipados com ferramentas de rastreamento Web por meio de uma solicitação de autorização (que aparece sobre a página, por exemplo) com uma caixa de seleção para autorizar o uso de cookies ou adicionar um banner na parte superior da primeira página, etc. As janelas pop-up devem ser evitadas, pois geralmente são bloqueadas pelos navegadores.

As informações de rastreamento estão disponíveis para cada contato do banco de dados em **[!UICONTROL integrated customer profiles]**. Para obter mais informações, consulte [esta seção](../../audiences/using/integrated-customer-profile.md).

O Adobe Campaign usa dois tipos de cookies:

* Um cookie de sessão (nlid). Ele contém o identificador do email enviado ao contato (broadlogId) e o identificador do modelo de mensagem (deliveryId). Ele é adicionado quando o contato clica em um URL incluído em um email enviado pelo Adobe Campaign e permite que você acompanhe seu comportamento na Web. Esse cookie de sessão é apagado automaticamente quando o navegador é fechado. O contato pode configurar o navegador para recusar cookies.
* Um cookie compartilhado entre as soluções da Adobe Experience Cloud. Ele permite identificar os usuários que interagem com as soluções da Experience Cloud quando visitam um site. A descrição deste cookie está disponível [aqui](https://docs.adobe.com/content/help/pt-BR/core-services/interface/ec-cookies/cookies-mc.html).

O rastreamento com a Adobe Campaign Standard permite acessar as seguintes funcionalidades:

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
<td>Acompanhamento de email</td>
<td>Rastreamento de push</td>
<td>URLs rastreados</td>
<td>Logs de rastreamento</td>
<td>Relatório de rastreamento</td>
</tr>
</table>

## Logs de rastreamento {#tracking-logs}

A guia **[!UICONTROL Tracking logs]** lista o histórico de rastreamento desse delivery. Essa guia exibe as informações de rastreamento das mensagens enviadas, como todos os URLs que foram rastreados pelo Adobe Campaign. As informações de rastreamento nesta guia são atualizadas a cada 10 minutos.

>[!NOTE]
>
>Se o rastreamento não estiver ativado para um delivery, essa guia não será exibida. Os logs de rastreamento estão disponíveis somente para os canais **email** e **notificação por push** .

![](assets/tracking_logs.png)

No exemplo acima, o recipient:

* Aberta a mensagem.
* Clicado no link da mirror page.
* Clicado no link personalizado &quot;SAIBA MAIS&quot;.

Na coluna **[!UICONTROL Type]**, os valores possíveis são:

* **[!UICONTROL Email click]**: os recipients clicaram em um link personalizado.
* **[!UICONTROL Mirror page]**: o recipient clicou em um link para a mirror page.
* **[!UICONTROL Open]**: o recipient abriu o email.
* **[!UICONTROL Opt-out]**: o recipient clicou em um link de unsubscription.

>[!NOTE]
>
>Para o canal **notificação por push**, somente os cliques nas notificações móveis são rastreados. Nesse caso, o valor será **[!UICONTROL Click on mobile notification]**.

Para obter mais informações sobre como inserir links de rastreamento, consulte [esta página](../../designing/using/links.md#inserting-a-link).

O relatório **[!UICONTROL Tracking indicators]** contém os indicadores-chave para rastrear o comportamento após o recebimento de mensagens de email. Para obter mais informações, consulte esta [página](../../reporting/using/tracking-indicators.md).

## URLs rastreados {#tracked-urls}

A guia **[!UICONTROL Tracked URLs]** agrupa os URLs contidos na mensagem enviada, incluindo o tipo de URL e o URL de origem.

![](assets/sending_delivery6.png)

Para obter mais informações sobre links de rastreamento, consulte [esta seção](../../designing/using/links.md#about-tracked-urls).
