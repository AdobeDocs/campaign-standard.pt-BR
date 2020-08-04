---
title: Sobre a programação de mensagens
description: Saiba como programar as mensagens.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e
workflow-type: ht
source-wordcount: '268'
ht-degree: 100%

---


# Sobre a programação de mensagens{#about-scheduling-messages}

>[!CAUTION]
>
>Sempre que você fizer alterações na programação de um delivery, prepare novamente o delivery clicando no botão **Prepare** antes de clicar em **Confirm**.

No painel de mensagens, o bloco **[!UICONTROL Schedule]** permite definir quando as mensagens (email, SMS ou notificações por push) serão enviadas.

![](assets/delivery_dashboard.png)

As propriedades **[!UICONTROL Schedule]** permitem definir as opções de envio para emails, SMS ou notificações por push:

* **[!UICONTROL Messages to be sent once confirmed]**: as mensagens são enviadas assim que o envio é confirmado. Consulte [Confirmação do envio](../../sending/using/confirming-the-send.md).

   ![](assets/delivery_planning_1.png)

* **[!UICONTROL Messages to be sent automatically on the date specified below]**: as mensagens serão enviadas em data e hora posteriores. Especifique a **data de contato** no campo **Start sending from**.

   Você pode preparar e confirmar o envio, mas as mensagens só serão enviadas a partir da data e hora selecionadas. A preparação e a confirmação do envio são apresentadas nas seções [Preparação do envio](../../sending/using/preparing-the-send.md) e [Confirmação do envio](../../sending/using/confirming-the-send.md).

   A lista suspensa **[!UICONTROL Time zone of the contact date]** permite modificar o fuso horário que será considerado para o horário de envio. Por exemplo, se você inserir 9:00 AM no campo **[!UICONTROL Start sending from]** e selecionar Brussels, Copenhagen, Madrid, Paris (GMT+1) na lista suspensa de **[!UICONTROL Time zone of the contact date]**, todos os recipients receberão a mensagem às 9:00, horário de Paris. Portanto, um recipient localizado em Moscou (GMT+3) receberá a mensagem às 11:00, horário de Moscou.

   Se você quiser confirmar o envio manualmente, marque a opção **[!UICONTROL Request confirmation before sending messages]**. Essa opção está ativada por padrão.

   ![](assets/delivery_planning.png)

>[!CAUTION]
>
>Ao duplicar um delivery, todas as configurações de programação são excluídas. A menos que você programe uma nova data de contato, o delivery duplicado será enviado assim que o envio for confirmado.

**Tópicos relacionados**:

* [Otimização do tempo de envio](../../sending/using/optimizing-the-sending-time.md)
* [Envio de mensagens no fuso horário do recipient](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [Calcular a data de envio](../../sending/using/computing-the-sending-date.md)

