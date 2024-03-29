---
title: Envio de mensagens no fuso horário do destinatário
description: Saiba como enviar mensagens no fuso horário do destinatário.
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Proofs
role: User
level: Intermediate
exl-id: 48f222bd-9c2f-4eeb-a12b-bbfc62119024
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 88%

---

# Envio de mensagens no fuso horário do destinatário{#sending-messages-at-the-recipient-s-time-zone}

Ao gerenciar uma campanha na qual a data e a hora são importantes, você pode agendar um delivery que considere a hora local de cada recipient: eles receberão notificações por email, SMS ou por push na hora agendada, em seu próprio fuso horário.

>[!NOTE]
>
>Para usar essa funcionalidade, verifique se todos os perfis direcionados pela entrega têm um fuso horário especificado na seção **[!UICONTROL Address]** de suas propriedades. Para obter mais informações sobre o acesso às propriedades dos perfis, consulte esta [seção](../../audiences/using/editing-profiles.md).

Para enviar uma entrega no fuso horário do destinatário, você também pode usar a atividade **[!UICONTROL Scheduler]** em um fluxo de trabalho. Para obter mais informações, consulte esta [página](../../automating/using/scheduler.md).

No exemplo a seguir, queremos enviar um código promocional válido somente no Dia dos namorados para todos os clientes no mundo todo. Para que haja tempo suficiente para usá-lo durante o dia, todos os clientes devem receber a mensagem em 14 de fevereiro, às 8h, dependendo de seus fusos horários.

1. Na guia **[!UICONTROL Marketing activities]**, comece criando a entrega, no nosso caso, um email. Para saber mais sobre a criação de email, consulte esta [seção](../../channels/using/creating-an-email.md).
1. Depois de criar o email Dia dos namorados, clique em **[!UICONTROL Create]** para acessar o painel da entrega. Para obter mais informações sobre design de email, consulte esta [página](../../designing/using/personalization.md#example-email-personalization).

   ![](assets/send-time_opt_valentine_1.png)

1. No painel da entrega, selecione o bloco **[!UICONTROL Schedule]**.

   ![](assets/send-time_opt_valentine_2.png)

1. Selecione a opção **[!UICONTROL Messages to be sent automatically on the date]** especificada abaixo. Em seguida, no campo **[!UICONTROL Start sending from]**, defina a data do contato, no nosso caso, 14 de fevereiro às 8h, para que todos os destinatários recebam no Dia dos namorados.

   ![](assets/send-time_opt_valentine.png)

1. No campo **[!UICONTROL Time zone of the contact date]**, selecione em qual fuso horário a entrega deve ser enviada por padrão.

   Se um **[!UICONTROL Time zone]** do perfil for deixado como **[!UICONTROL Default]**, os destinatários receberão a entrega dependendo do fuso horário escolhido aqui.

1. No menu suspenso **[!UICONTROL Optimize the sending time per recipient]**, escolha **[!UICONTROL Send at the recipient's time zone]**. Assim, os destinatários receberão o email do Dia dos namorados no dia 14 de fevereiro, dependendo do fuso horário.

   ![](assets/send-time_opt_valentine_3.png)

1. Depois de confirmar a programação da entrega, clique no botão **[!UICONTROL Prepare]** e depois **[!UICONTROL Confirm]** sua entrega.

   Confirme o envio com pelo menos 24 horas de antecedência. Caso contrário, dependendo da sua localização, alguns destinatários poderão receber a entrega antes do evento Dia dos namorados.

   ![](assets/send-time_opt_valentine_4.png)

Não importa onde eles estejam localizados, todos os destinatários receberão a mensagem em 14 de fevereiro, às 8h, no horário local.
