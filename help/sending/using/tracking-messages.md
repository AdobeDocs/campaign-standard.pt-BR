---
title: Rastreamento de mensagens
seo-title: Rastreamento de mensagens
description: Rastreamento de mensagens
seo-description: Saiba como rastrear o comportamento dos destinatários da entrega.
page-status-flag: nunca ativado
uuid: c3721647-0663-4614-a9c9-3b3a40af328a
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: envio
content-type: referência
topic-tags: enviar e rastrear mensagens
discoiquuid: 6fa50f0d-3dcf-4a9e-bcc-1ecda2bfb449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# Rastreamento de mensagens{#tracking-messages}

## Sobre o rastreamento {#about-tracking}

Graças às suas funcionalidades de rastreamento, o Adobe Campaign permite que você rastreie o comportamento dos destinatários da entrega. Para fazer isso, o Adobe Campaign usa cookies de sessão e cookies permanentes.

Você pode informar aos usuários que seus sites estão equipados com ferramentas de rastreamento da Web por meio de uma solicitação de autorização (que aparece na página, por exemplo) com uma caixa de seleção para autorizar o uso de cookies ou adicionar um banner na parte superior da primeira página em que eles chegam, etc. As janelas pop-up devem ser evitadas, pois geralmente são bloqueadas pelos navegadores.

O Adobe Campaign usa dois tipos de cookies:

* Um cookie de sessão (nlid). Ele contém o identificador do email enviado ao contato (BroadlogId) e o identificador do modelo de mensagem (deliveryId). Ele é adicionado quando o contato clica em um URL incluído em um email enviado pelo Adobe Campaign e permite que você rastreie seu comportamento na Web. Este cookie de sessão é apagado automaticamente quando o navegador é fechado. O contato pode configurar seu navegador para recusar cookies.
* Um cookie compartilhado entre as soluções da Adobe Experience Cloud. Isso permite identificar os usuários que interagem com as soluções da Experience Cloud ao visitar um site. A descrição deste cookie está disponível aqui: [https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html).

As informações de rastreamento estão disponíveis para cada contato do banco de dados no **[!UICONTROL integrated customer profiles]**. For more on this, refer to [this section](../../audiences/using/integrated-customer-profile.md).

## Registros de rastreamento {#tracking-logs}

A **[!UICONTROL Tracking logs]** guia lista o histórico de rastreamento desta entrega. Essa guia exibe as informações de rastreamento das mensagens enviadas, como todos os URLs que foram rastreados pelo Adobe Campaign. As informações de rastreamento nesta guia são atualizadas a cada 10 minutos.

>[!NOTE]
>
>Se o rastreamento não estiver ativado para uma entrega, essa guia não será exibida. Os registros de rastreamento estão disponíveis somente para canais de notificação **por** email **e** push.

![](assets/tracking_logs.png)

No exemplo acima, o destinatário:

* A mensagem foi aberta.
* Clicado no link personalizado "APRENDER MAIS".
* Clicado no link de cancelamento de assinatura e página espelhada.

Na **[!UICONTROL Type]** coluna, os valores possíveis são:

* **[!UICONTROL Email click]**: os destinatários clicaram em um link personalizado.
* **[!UICONTROL Mirror page]**: o destinatário clicou em um link para a página espelhada.
* **[!UICONTROL Open]**: o destinatário abriu o email.
* **[!UICONTROL Opt-out]**: o destinatário clicou em um link para cancelar a assinatura.

>[!NOTE]
>
>Para o canal de notificação **por** push, somente cliques em notificações móveis são rastreados. Nesse caso, o valor será **[!UICONTROL Click on mobile notification]**.

Para obter mais informações sobre como inserir links de rastreamento, consulte [esta página](../../designing/using/links.md#inserting-a-link).

## URLs acompanhados {#tracked-urls}

A **[!UICONTROL Tracked URLs]** guia agrupa os URLs contidos na mensagem enviada, incluindo o tipo de URL e o URL de origem.

![](assets/sending_delivery6.png)

For more on tracking links, refer to [this section](../../designing/using/links.md#about-tracked-urls).
