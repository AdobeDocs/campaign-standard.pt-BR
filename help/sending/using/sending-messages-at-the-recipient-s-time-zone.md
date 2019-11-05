---
title: Enviar mensagens no fuso horário do destinatário
description: Saiba como enviar mensagens no fuso horário do destinatário.
page-status-flag: nunca ativado
uuid: 70228c07-451f-4ddb-8d26-92a5a4814e3a
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: envio
content-type: referência
topic-tags: mensagens de agendamento
discoiquuid: daa980ba-8c7c-4673-a68f-379d63e4b8bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Enviar mensagens no fuso horário do destinatário{#sending-messages-at-the-recipient-s-time-zone}

Ao gerenciar uma campanha na qual a data e a hora são importantes, você pode programar uma entrega que leve em conta a hora local de cada destinatário: eles receberão notificações por email, SMS ou push no momento agendado, em seu próprio fuso horário.

>[!NOTE]
>
>Para usar essa funcionalidade, verifique se todos os perfis direcionados pela entrega têm um fuso horário especificado na **[!UICONTROL Address]** seção de suas propriedades. Para obter mais informações sobre como acessar as propriedades do perfil, consulte esta [seção](../../audiences/using/editing-profiles.md).

Para enviar uma entrega no fuso horário do destinatário, você também pode usar a **[!UICONTROL Scheduler]** atividade em um fluxo de trabalho. Para obter mais informações, consulte esta [página](../../automating/using/scheduler.md).

No exemplo a seguir, queremos enviar um código promocional válido apenas no Dia dos Namorados para todos os clientes em todo o mundo. Para fornecer tempo suficiente para usá-lo durante o dia, todos os clientes devem receber sua mensagem em 14 de fevereiro às 8:00, dependendo de seus fusos horários.

1. Na **[!UICONTROL Marketing activities]** guia, comece a criar sua entrega, no nosso caso, um email. Para saber mais sobre a criação da entrega, consulte esta [seção](../../channels/using/creating-an-email.md).
1. Depois de criar o email Dia dos namorados, clique em **[!UICONTROL Create]** para acessar o painel de entrega. For more on email designing, refer to this [page](../../designing/using/personalization.md#example-email-personalization).

   ![](assets/send-time_opt_valentine_1.png)

1. No painel de entrega, selecione o **[!UICONTROL Schedule]** bloco.

   ![](assets/send-time_opt_valentine_2.png)

1. Selecione a **[!UICONTROL Messages to be sent automatically on the date]** opção especificada abaixo. Em seguida, no **[!UICONTROL Start sending from]** campo, defina a data do contato, no nosso caso 14 de fevereiro às 8:00 da manhã para que todos os destinatários a recebam no Dia dos Namorados.

   ![](assets/send-time_opt_valentine.png)

1. No **[!UICONTROL Time zone of the contact date]** campo, selecione em qual fuso horário a entrega deve ser enviada por padrão.

   Se um perfil **[!UICONTROL Time zone]** for deixado como **[!UICONTROL Default]**, os destinatários receberão a entrega dependendo do fuso horário escolhido aqui.

1. No menu **[!UICONTROL Optimize the sending time per recipient]** suspenso, escolha **[!UICONTROL Send at the recipient's time zone]**. Isso permite que os destinatários recebam o email do dia dos namorados no dia 14 de fevereiro, dependendo do fuso horário.

   ![](assets/send-time_opt_valentine_3.png)

1. Depois de confirmar seu cronograma de entrega, clique no **[!UICONTROL Prepare]** botão e depois **[!UICONTROL Confirm]** na entrega.

   Certifique-se de confirmar o envio com pelo menos 24 horas de antecedência. Caso contrário, dependendo da sua localização, alguns destinatários poderão receber a entrega antes do evento de dia dos namorados.

   ![](assets/send-time_opt_valentine_4.png)

Não importa onde eles estejam localizados, todos os destinatários receberão a mensagem em 14 de fevereiro às 8:00 da manhã, horário local.
