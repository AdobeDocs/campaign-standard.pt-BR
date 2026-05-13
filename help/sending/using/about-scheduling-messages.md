---
title: Sobre a programação de mensagens
description: Saiba como programar as mensagens.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Send Time Optimization
role: User
exl-id: 6b26615b-4aa6-401d-a12d-25cef4cd0524
TQID: https://experienceleague.adobe.com/N0t5qvKiceoZEekhToXAk1PfNe1HE22vAaobLr32oME
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 276
ht-degree: 80%

---

# Sobre a programação de mensagens{#about-scheduling-messages}

>[!IMPORTANT]
>
>Sempre que você fizer alterações no cronograma de uma entrega, prepare novamente a entrega clicando no botão **Prepare** antes de clicar em **Confirm**.

No painel de mensagens, o bloco **[!UICONTROL Schedule]** permite definir quando as mensagens (email, SMS ou notificações por push) serão enviadas.

![](assets/delivery_dashboard.png)

As propriedades **[!UICONTROL Schedule]** permitem definir as opções de envio para emails, SMS ou notificações por push:

* **[!UICONTROL Messages to be sent once confirmed]**: as mensagens são enviadas assim que o envio é confirmado. Consulte [Confirmação do envio](../../sending/using/confirming-the-send.md).

  ![](assets/delivery_planning_1.png)

* **[!UICONTROL Messages to be sent automatically on the date specified below]**: as mensagens serão enviadas em data e hora posteriores. Especifique a **data de contato** no campo **Start sending from**.

  Você pode preparar e confirmar o envio, mas as mensagens só serão enviadas a partir da data e hora selecionadas. A preparação e a confirmação do envio são apresentadas nas seções [Preparação do envio](../../sending/using/preparing-the-send.md) e [Confirmação do envio](../../sending/using/confirming-the-send.md).

  A lista suspensa **[!UICONTROL Time zone of the contact date]** permite modificar o fuso horário que será considerado para o horário de envio. Por exemplo, se você inserir 9:00 AM no campo **[!UICONTROL Start sending from]** e selecionar Brussels, Copenhagen, Madrid, Paris (GMT+1) na lista suspensa de **[!UICONTROL Time zone of the contact date]**, todos os recipients receberão a mensagem às 9:00 AM, horário de Paris. Portanto, um recipient localizado em Moscou (GMT+3) receberá a mensagem às 11:00, horário de Moscou.

  Se você quiser confirmar o envio manualmente, marque a opção **[!UICONTROL Request confirmation before sending messages]**. Essa opção está habilitada por padrão.

  ![](assets/delivery_planning.png)

>[!IMPORTANT]
>
>Ao duplicar uma entrega, todas as configurações de programação são excluídas. A menos que você programe uma nova data de contato, a entrega duplicada será enviada assim que o envio for confirmado.

**Tópicos relacionados**:

* [Otimização do tempo de envio](../../sending/using/optimizing-the-sending-time.md)
* [Envio de mensagens no fuso horário do destinatário](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [Cálculo da data de envio](../../sending/using/computing-the-sending-date.md)
