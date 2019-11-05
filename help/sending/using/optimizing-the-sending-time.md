---
title: Otimização do tempo de envio
description: Saiba como configurar o tempo de envio e melhorar a taxa de abertura de suas mensagens.
page-status-flag: nunca ativado
uuid: c2c13934-9819-4e18-b5c7-60915c907f37
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: envio
content-type: referência
topic-tags: mensagens de agendamento
discoiquuid: 609355f6-9003-41b9-9981-ea787419fbf5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Otimização do tempo de envio{#optimizing-the-sending-time}

Para melhorar a taxa de abertura das mensagens, é possível definir manualmente uma hora de envio por destinatário. Cada perfil receberá a mensagem na data e hora especificadas, sempre que possível.

A definição de uma hora de envio pode ser feita no nível de entrega ou usando um fluxo de trabalho.

Para emails, dependendo da carga do servidor e da quantidade de tentativas, será feito o melhor esforço para enviar a mensagem na data e hora programadas para cada destinatário.

* As tentativas dependem do provedor de Internet e da sua reputação. A mensagem pode não ser aceite na primeira tentativa e podem ser efetuadas várias tentativas. Consulte [Lista de parâmetros](../../administration/using/configuring-email-channel.md)de canal de email.
* Os atrasos no recebimento do email podem ocorrer devido à falta de largura de banda.

Você pode exibir quando a mensagem foi enviada a cada destinatário nos registros [de](../../sending/using/monitoring-a-delivery.md#sending-logs)envio.

Várias opções estão disponíveis:

* **[!UICONTROL No optimization]**: As mensagens são enviadas no momento do usuário.

   Por exemplo, se o fuso horário for GMT+1 e você digitar 9:00 AM no **[!UICONTROL Start sending from]** campo, um destinatário localizado no fuso horário GMT+3 receberá a mensagem às 11:00 da hora local para esse destinatário.

* **[!UICONTROL Send at the recipient's time zone]**: Todos os destinatários receberão a mensagem levando em conta o fuso horário.

   Por exemplo, se você digitar 9:00 AM no **[!UICONTROL Start sending from]** campo, um destinatário localizado no fuso horário GMT+3 receberá a mensagem às 9:00 AM, horário local, para esse destinatário.

   See [Sending messages at the recipient's time zone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**: Cada destinatário receberá a mensagem na data e hora configuradas pela fórmula especificada.

   See [Computing the sending date](../../sending/using/computing-the-sending-date.md).

