---
title: Rastreamento de mensagens
description: Saiba como rastrear o comportamento dos recipients do seu delivery.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: fac29bc2-57fa-40f9-a160-cd75f695b91e
source-git-commit: affd4f9716235a283df20de5539e43c4832762f7
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 35%

---

# Rastreamento de mensagens{#tracking-messages}

## Sobre o rastreamento {#about-tracking}

Graças às suas funcionalidades de rastreamento, o Adobe Campaign permite que você acompanhe o comportamento dos seus recipients de delivery. Para fazer isso, o Adobe Campaign usa cookies de sessão e cookies permanentes.

Você pode informar aos usuários que seus sites estão equipados com ferramentas de rastreamento web por meio de uma solicitação de autorização (que aparece, por exemplo, sobre a página) com uma caixa de seleção que autoriza a utilização de cookies ou adicionando um banner na parte superior da primeira página, etc. As janelas pop-up devem ser evitadas, pois geralmente são bloqueadas pelos navegadores.

As informações de rastreamento estão disponíveis para cada contato do banco de dados no **[!UICONTROL integrated customer profiles]**. Para obter mais informações, consulte [esta seção](../../audiences/using/integrated-customer-profile.md).

O Adobe Campaign usa dois tipos de cookies:

* Um cookie de sessão (nlid). Ele contém o identificador do email enviado ao contato (broadlogId) e o identificador do modelo de mensagem (deliveryId). Ele é adicionado quando o contato clica em um URL incluído em um email enviado pelo Adobe Campaign e permite que você acompanhe seu comportamento na Web. Esse cookie de sessão é apagado automaticamente quando o navegador é fechado. O contato pode configurar o navegador para recusar cookies.
* Um cookie compartilhado entre as soluções da Adobe Experience Cloud. Ele permite identificar os usuários que interagem com as soluções da Experience Cloud quando visitam um site. A descrição deste cookie está disponível [aqui](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-mc.html?lang=pt-BR).

O rastreamento com o Adobe Campaign Standard permite acessar as seguintes funcionalidades:

<table>
<tr>
    <td valign="top">
        <a href="../../administration/using/configuring-email-channel.md#tracking-parameters"><img width="60px" alt="condições" src="assets/icon_email_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="../../administration/using/push-tracking.md"><img width="60px" alt="condições" src="assets/icon_push_parameters.png"/></a>
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
<td>Rastreamento de emails</td>
<td>Rastreamento por push</td>
<td>URLs rastreados</td>
<td>Logs de rastreamento</td>
<td>Relatório de rastreamento</td>
</tr>
</table>

## Logs de rastreamento {#tracking-logs}

A guia **[!UICONTROL Tracking logs]** lista o histórico de rastreamento dessa entrega. Essa guia exibe as informações de rastreamento das mensagens enviadas, como todos os URLs que foram rastreados pelo Adobe Campaign. As informações de rastreamento nesta guia são atualizadas a cada 10 minutos.

>[!NOTE]
>
>Se o rastreamento não estiver ativado para um delivery, essa guia não será exibida. Os logs de rastreamento estão disponíveis somente para os canais **email** e **notificação por push**.

![](assets/tracking_logs.png)

No exemplo acima, o recipient:

* Aberto a mensagem.
* Clicou no link da mirror page.
* Clicou no link personalizado &quot;SAIBA MAIS&quot;.

Na coluna **[!UICONTROL Type]**, os valores possíveis são:

* **[!UICONTROL Email click]**: os destinatários clicaram em um link personalizado.
* **[!UICONTROL Mirror page]**: o destinatário clicou em um link para a mirror page.
* **[!UICONTROL Open]**: o destinatário abriu o email.
* **[!UICONTROL Opt-out]**: o destinatário clicou em um link de cancelamento de assinatura.

>[!NOTE]
>
>Para o canal de **notificação por push**, somente os cliques nas notificações móveis são rastreados. Nesse caso, o valor será **[!UICONTROL Click on mobile notification]**.

Para obter mais informações sobre como inserir links de rastreamento, consulte [esta página](../../designing/using/links.md#inserting-a-link).

O relatório **[!UICONTROL Tracking indicators]** contém os indicadores principais para o comportamento de rastreamento após o recebimento de mensagens de email. Para obter mais informações, consulte esta [página](../../reporting/using/tracking-indicators.md).

## URLs rastreados {#tracked-urls}

A guia **[!UICONTROL Tracked URLs]** reagrupa as URLs contidas na mensagem enviada, incluindo seu tipo de URL e sua URL de origem.

![](assets/sending_delivery6.png)

Para obter mais informações sobre links de rastreamento, consulte [esta seção](../../designing/using/links.md#about-tracked-urls).
