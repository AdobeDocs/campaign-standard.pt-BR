---
title: Mensagens de rastreamento
seo-title: Mensagens de rastreamento
description: Mensagens de rastreamento
seo-description: Saiba como rastrear o comportamento dos destinatários de entrega.
page-status-flag: nunca ativado
uuid: c 3721647-0663-4614-a 9 c 9-3 b 3 a 40 af 328 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviando
content-type: reference
topic-tags: enviar e rastrear mensagens
discoiquuid: 6 fa 50 f 0 d -3 dcf -4 a 9 e-bccc -1 ecda 2 bfb 449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Tracking messages{#tracking-messages}

## About tracking {#about-tracking}

Graças às suas funcionalidades de rastreamento, o Adobe Campaign permite que você rastreie o comportamento dos destinatários de entrega. Para fazer isso, o Adobe Campaign usa cookies de sessão e cookies permanentes.

Você pode informar aos usuários que seus sites estão equipados com ferramentas de rastreamento da Web por meio de uma solicitação de autorização (que aparece sobre a página, por exemplo) com uma caixa de seleção para autorizar o uso de cookies, ou adicionar um banner na parte superior da primeira página em que eles chegam, etc. Janelas pop-up devem ser evitadas, pois frequentemente são bloqueadas pelos navegadores.

O Adobe Campaign usa dois tipos de cookies:

* Um cookie de sessão (nlid). Contém o identificador do email enviado para o contato (broadlogid) e o identificador do modelo de mensagem (deliveryid). É adicionado quando o contato clica em um URL incluído em um email enviado pelo Adobe Campaign e permite que você rastreie seu comportamento na Web. Este cookie de sessão é apagado automaticamente quando o navegador é fechado. O contato pode configurar o navegador para recusar cookies.
* Um cookie compartilhado entre as soluções da Adobe Experience Cloud. Isso permite identificar os usuários que interagem com as soluções da Experience Cloud quando visitam um site. The description of this cookie is available here: [https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html).

Tracking information are available for each contact of your database into **[!UICONTROL integrated customer profiles]**. For more on this, refer to [this section](../../audiences/using/integrated-customer-profile.md).

## Tracking logs {#tracking-logs}

**[!UICONTROL Tracking logs]** A guia lista o histórico de rastreamento para esta entrega. Esta guia exibe as informações de rastreamento das mensagens enviadas, como todos os urls que foram rastreados pelo Adobe Campaign. As informações de rastreamento nesta guia são atualizadas a cada 10 minutos.

>[!NOTE]
>
>Se o rastreamento não estiver ativado para uma entrega, esta guia não será exibida. Tracking logs are available for the **email** and **push notification** channels only.

![](assets/tracking_logs.png)

No exemplo acima, o destinatário:

* Abra a mensagem.
* Clicou no link personalizado "SAIBA MAIS".
* Clicou na cancelação da assinatura e no link da página espelhada.

In the **[!UICONTROL Type]** column, the possible values are:

* **[!UICONTROL Email click]**: os destinatários clicavam em um link personalizado.
* **[!UICONTROL Mirror page]**: o destinatário clicou em um link para a página espelhada.
* **[!UICONTROL Open]**: o destinatário abriu o email.
* **[!UICONTROL Opt-out]**: o destinatário clicou em um link de cancelamento de assinatura.

>[!NOTE]
>
>For the **push notification** channel, only clicks on mobile notifications are tracked. In that case, the value will be **[!UICONTROL Click on mobile notification]**.

For more on how to insert tracking links, refer to [this page](../../designing/using/inserting-a-link.md).

## Tracked URLs {#tracked-urls}

**[!UICONTROL Tracked URLs]** A guia reúne os urls contidos na mensagem enviada, incluindo o tipo de URL e o URL de origem.

![](assets/sending_delivery6.png)

For more on tracking links, refer to [this section](../../designing/using/about-tracked-urls.md).
