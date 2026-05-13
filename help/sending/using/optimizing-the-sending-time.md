---
title: Otimização do tempo de envio
description: Saiba como configurar o tempo de envio e melhorar a taxa de abertura das suas mensagens.
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: f35b46c6-de88-4efa-b3b7-8bb9024e40a8
TQID: https://experienceleague.adobe.com/FjL5t1ohvrgDdqLiCr03z1Nbq6IukIBysKkmXJ7561c
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 279
ht-degree: 74%

---

# Otimização do tempo de envio{#optimizing-the-sending-time}

Para melhorar a taxa de abertura das mensagens, é possível definir manualmente uma hora de envio por destinatário. Cada perfil receberá a mensagem na data e hora especificadas, sempre que possível.

A definição de um tempo de envio pode ser feita em nível de entrega ou usando um fluxo de trabalho.

Para emails, dependendo da carga do servidor e da quantidade de tentativas, será feito o melhor esforço para enviar a mensagem na data e hora agendadas para cada destinatário.

* As tentativas dependem do provedor de Internet e da sua reputação. A mensagem pode não ser aceita na primeira tentativa e várias outras tentativas podem ser realizadas. Consulte [Lista de parâmetros de canal de email](../../administration/using/configuring-email-channel.md).
* Atrasos no recebimento do email podem ocorrer devido à falta de largura de banda.

Você pode visualizar quando a mensagem foi enviada a cada destinatário nos [registros de envio](../../sending/using/monitoring-a-delivery.md#sending-logs).

Várias opções estão disponíveis:

* **[!UICONTROL No optimization]**: as mensagens são enviadas no horário do usuário.

  Por exemplo, se o fuso horário for GMT+1 e você inserir 9:00 AM no campo **[!UICONTROL Start sending from]**, um recipient localizado no fuso horário GMT+3 receberá a mensagem às 11:00 AM, horário local desse recipient.

* **[!UICONTROL Send at the recipient's time zone]**: todos os destinatários receberão a mensagem levando em conta o fuso horário.

  Por exemplo, se você inserir 9:00 AM no campo **[!UICONTROL Start sending from]**, um recipient localizado no fuso horário GMT+3 receberá a mensagem às 9:00 AM, hora local desse recipient.

  Consulte [Enviar mensagens no fuso horário do destinatário](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**: cada destinatário receberá a mensagem na data e hora configuradas pela fórmula especificada.

  Consulte [Calcular a data de envio](../../sending/using/computing-the-sending-date.md).
