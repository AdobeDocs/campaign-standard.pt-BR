---
title: Otimizar o tempo de envio
seo-title: Otimizar o tempo de envio
description: Otimizar o tempo de envio
seo-description: Saiba como configurar o tempo de envio e melhorar a taxa de abertura de suas mensagens.
page-status-flag: nunca ativado
uuid: c 2 c 13934-9819-4 e 18-b 5 c 7-60915 c 907 f 37
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviando
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 609355 f 6-9003-41 b 9-9981-ea 787419 fbf 5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Optimizing the sending time{#optimizing-the-sending-time}

Para melhorar a taxa de abertura de suas mensagens, você pode definir manualmente um tempo de envio por destinatário. Cada perfil receberá a mensagem na data e hora especificadas, sempre que possível.

A definição de um tempo de envio pode ser feita no nível de entrega ou usando um fluxo de trabalho.

Para emails, dependendo do carregamento do servidor e da quantidade de tentativas, o melhor esforço será o envio da mensagem na data e hora programadas para cada destinatário.

* As tentativas dependem do provedor de Internet e da sua reputação. A mensagem pode não ser aceita na primeira tentativa e várias tentativas podem ser realizadas. See [List of email channel parameters](../../administration/using/configuring-email-channel.md).
* Atrasos no recebimento do email podem ocorrer devido a uma largura de banda insuficiente.

You can view when the message was sent to each recipient in the [sending logs](../../sending/using/monitoring-a-delivery.md#sending-logs).

Várias opções estão disponíveis:

* **[!UICONTROL No optimization]**: As mensagens são enviadas no horário do usuário.

   For example, if your time zone is GMT+1 and if you enter 9:00 AM in the **[!UICONTROL Start sending from]** field, a recipient located in the GMT+3 time zone will receive the message at 11:00 AM local time for that recipient.

* **[!UICONTROL Send at the recipient's time zone]**: Todos os destinatários receberão a mensagem com o fuso horário tomado em consideração.

   For example, if you enter 9:00 AM in the **[!UICONTROL Start sending from]** field, a recipient located in the GMT+3 time zone will receive the message at 9:00 AM local time for that recipient.

   See [Sending messages at the recipient's time zone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**: Cada destinatário receberá a mensagem na data e hora configuradas pela fórmula especificada.

   See [Computing the sending date](../../sending/using/computing-the-sending-date.md).

