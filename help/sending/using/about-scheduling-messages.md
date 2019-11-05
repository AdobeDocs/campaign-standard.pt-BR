---
title: Sobre o agendamento de mensagens
description: Saiba como agendar suas mensagens.
page-status-flag: nunca ativado
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: envio
content-type: referência
topic-tags: mensagens de agendamento
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: entrega,agendamento,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Sobre o agendamento de mensagens{#about-scheduling-messages}

>[!CAUTION]
>
>Sempre que fizer alterações no agendamento de uma entrega, você deverá preparar novamente a entrega clicando no botão **Preparar** antes de clicar em **Confirmar**.

No painel de mensagens, o **[!UICONTROL Schedule]** bloco permite definir quando as mensagens (email, SMS ou notificações por push) serão enviadas.

![](assets/delivery_dashboard.png)

As **[!UICONTROL Schedule]** propriedades permitem definir opções de envio para seus emails, SMS ou notificações por push:

* **[!UICONTROL Messages to be sent once confirmed]**: são enviadas assim que o envio é confirmado. See [Confirming the send](../../sending/using/confirming-the-send.md).

   ![](assets/delivery_planning_1.png)

* **[!UICONTROL Messages to be sent automatically on the date specified below]**: as mensagens serão enviadas em data e hora posteriores. Especifique a data **do** contato no campo **Começar a enviar** .

   Você pode preparar e confirmar o envio, mas as mensagens só serão enviadas a partir da data e hora selecionadas. A preparação e a confirmação do envio são apresentadas nas seções [Preparando o envio](../../sending/using/preparing-the-send.md) e [Confirmando o envio](../../sending/using/confirming-the-send.md) .

   A lista **[!UICONTROL Time zone of the contact date]** suspensa permite modificar o fuso horário que será considerado para o horário de envio. Por exemplo, se você digitar 9:00 AM no **[!UICONTROL Start sending from]** campo e selecionar Bruxelas, Copenhague, Madrid, Paris (GMT+1) na lista **[!UICONTROL Time zone of the contact date]** suspensa, todos os destinatários receberão a mensagem às 9:00 AM, horário de Paris. Portanto, um destinatário localizado em Moscou (GMT+3) receberá a mensagem às 11h00, horário de Moscou.

   Se você deseja confirmar manualmente o envio, marque a **[!UICONTROL Request confirmation before sending messages]** opção. Essa opção é ativada por padrão.

   ![](assets/delivery_planning.png)

>[!CAUTION]
>
>Ao duplicar uma entrega, todas as configurações de agendamento são excluídas. A menos que você agende uma nova data de contato, a entrega duplicada será enviada assim que o envio for confirmado.

**Tópicos relacionados**:

* [Otimização do tempo de envio](../../sending/using/optimizing-the-sending-time.md)
* [Enviar mensagens no fuso horário do destinatário](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [Calcular a data de envio](../../sending/using/computing-the-sending-date.md)

