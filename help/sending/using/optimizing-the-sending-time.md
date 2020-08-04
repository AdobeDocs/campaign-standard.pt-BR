---
title: Otimização do tempo de envio
description: Saiba como configurar o tempo de envio e melhorar a taxa de abertura das suas mensagens.
page-status-flag: never-activated
uuid: c2c13934-9819-4e18-b5c7-60915c907f37
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 609355f6-9003-41b9-9981-ea787419fbf5
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e
workflow-type: ht
source-wordcount: '272'
ht-degree: 100%

---


# Otimização do tempo de envio{#optimizing-the-sending-time}

Para melhorar a taxa de abertura das mensagens, é possível definir manualmente uma hora de envio por recipient. Cada perfil receberá a mensagem na data e hora especificadas, sempre que possível.

A definição de um tempo de envio pode ser feita em nível de delivery ou usando um workflow.

Para emails, dependendo da carga do servidor e da quantidade de tentativas, será feito o melhor esforço para enviar a mensagem na data e hora agendadas para cada recipient.

* As tentativas dependem do provedor de Internet e da sua reputação. A mensagem pode não ser aceita na primeira tentativa e várias outras tentativas podem ser realizadas. Consulte [Lista de parâmetros de canal de email](../../administration/using/configuring-email-channel.md).
* Atrasos no recebimento do email podem ocorrer devido à falta de largura de banda.

Você pode visualizar quando a mensagem foi enviada a cada recipient nos [registros de envio](../../sending/using/monitoring-a-delivery.md#sending-logs).

Várias opções estão disponíveis:

* **[!UICONTROL No optimization]**: as mensagens são enviadas no horário do usuário.

   Por exemplo, se o fuso horário for GMT+1 e você inserir 9:00 AM no campo **[!UICONTROL Start sending from]**, um recipient localizado no fuso horário GMT+3 receberá a mensagem às 11:00 da hora local desse recipient.

* **[!UICONTROL Send at the recipient's time zone]**: todos os recipients receberão a mensagem levando em conta o fuso horário.

   Por exemplo, se você digitar 9:00 AM no campo **[!UICONTROL Start sending from]**, um recipient localizado no fuso horário GMT+3 receberá a mensagem às 9:00 AM, horário local desse recipient.

   Consulte [Enviar mensagens no fuso horário do recipient](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**: cada recipient receberá a mensagem na data e hora configuradas pela fórmula especificada.

   Consulte [Calcular a data de envio](../../sending/using/computing-the-sending-date.md).

