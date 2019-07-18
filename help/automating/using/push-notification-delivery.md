---
title: Entrega de notificação por push
seo-title: Entrega de notificação por push
description: Entrega de notificação por push
seo-description: A atividade de entrega de notificação por push permite configurar o envio de uma notificação por push única ou uma notificação por push recorrente em um fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 994 d 8 fe 3-29 f 0-4 b 5 c -89 ee-c 6 be 7 c 60 a 31 b
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: channel-activities
discoiquuid: e 61 bdaee -4 b 48-4845-a 2 a 5-574 b 577 ea 796
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Push notification delivery{#push-notification-delivery}

## Description {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

The **[!UICONTROL Push notification]** activity allows you to configure sending a push notification in a workflow. This can be a **single send** notification and sent just once, or it can be a **recurring** notification.

Notificações de envio único são entregas padrão de notificação por push de aplicativos móveis, enviadas uma vez.

As notificações recorrentes permitem enviar diversas vezes a mesma entrega de notificação por push de aplicativo móvel para diferentes metas durante um período definido. Você pode agregar as entregas por período para obter relatórios que correspondam às suas necessidades.

## Context of use {#context-of-use}

The **[!UICONTROL Push notification]** activity is generally used to automate sending a notification to a target calculated in the same workflow.

Quando vinculada a um agendador, você pode definir notificações por push recorrentes.

Os destinatários são definidos como upstream da atividade no mesmo fluxo de trabalho, por atividades de definição de metas como consultas, interseções etc.

A preparação de mensagens é acionada de acordo com os parâmetros de execução do fluxo de trabalho. No painel de mensagens, você pode selecionar se deseja ou não solicitar ou não uma confirmação manual para enviar a mensagem (obrigatório por padrão). Você pode iniciar o fluxo de trabalho manualmente ou colocar uma atividade de agendamento no fluxo de trabalho para automatizar a execução.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Push notification]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button from the activity's quick actions. This button is specific to the **[!UICONTROL Push notification]** activity. As propriedades da notificação por push podem ser acessadas por meio da barra de ações no painel de push.

1. Selecione o modo de envio de notificação por push:

   * **[!UICONTROL Single notification]**: a notificação por push é enviada uma única vez. Você pode especificar aqui se deseja adicionar uma transição de saída à atividade. Os diferentes tipos de transição são detalhados na etapa 7 desse procedimento.
   * **[!UICONTROL Recurring notification]**: a notificação por push é enviada várias vezes, de acordo com a frequência definida em uma **[!UICONTROL Scheduler]** atividade. Selecione o período de agregação dos envios. This allows you to regroup all the sends that occur during the defined period in one single push notification that is also called **recurring execution** and can be accessed from the application's marketing activity list.

      Por exemplo, para uma notificação de aniversário recorrente, que é enviada diariamente, você pode optar por agregar os envios por mês. Isso permite que você receba relatórios mensalmente, embora a notificação seja enviada diariamente.

1. Selecione um tipo de notificação. These types come from push notifications templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. Insira as propriedades gerais da notificação por push. Você também pode anexá-lo a uma campanha existente. O rótulo da atividade de entrega do fluxo de trabalho é atualizado com o rótulo de notificação por push.
1. Defina o conteúdo de notificação por push. See [Creating a push notification](../../channels/using/preparing-and-sending-a-push-notification.md)
1. By default, the **[!UICONTROL Push notification]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL Push Notification]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**: isso permite gerar uma transição de saída que contenha exatamente a mesma população que a transição de entrada.
   * **[!UICONTROL Add outbound transition with the population]**: isso permite gerar uma transição de saída contendo a população para a qual a notificação foi enviada. Os membros da meta excluída durante a preparação de entrega são excluídos desta transição.

1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

Ao reabrir a atividade, você será direcionado diretamente para o painel de notificação por push. Somente seu conteúdo pode ser editado.

Por padrão, iniciar um fluxo de trabalho de entrega apenas aciona a preparação de mensagens. O envio de mensagens criadas a partir de um fluxo de trabalho ainda precisa ser confirmado após a inicialização do fluxo de trabalho. But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. Ao desmarcar essa opção, as mensagens são enviadas sem aviso prévio após a conclusão da preparação.

## Remarks {#remarks}

As entregas criadas em um fluxo de trabalho podem ser acessadas na lista de atividades de marketing do aplicativo. Você pode visualizar o status de execução do fluxo de trabalho usando o painel. Os links no painel de resumo de notificações por push permitem acessar diretamente os elementos vinculados (fluxo de trabalho, campanha etc.).

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL Push notification]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).

## Sending a recurring push notification with a workflow {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

Neste exemplo, uma notificação por push personalizada é enviada a cada primeiro dia do mês, às 8 pm horas, para os assinantes do aplicativo móvel, dependendo dos fusos horários. Para fazer isso:

1. The **[!UICONTROL Scheduler]** activity allows you to start the workflow days before the start of the delivery to be able to send the notification to every subscriber at 8 pm in any given time zone:

   * In the **[!UICONTROL Execution frequency]** field, select Monthly.
   * Select 8 pm in the **[!UICONTROL Time]** field.
   * Escolha em qual dia a entrega será enviada todos os meses.
   * Selecione uma data de início para seu fluxo de trabalho, pelo menos um dia antes do início da entrega. Caso contrário, alguns destinatários poderão receber a mensagem um dia depois se o tempo selecionado já tiver passado em seus fusos horários.
   * In the **[!UICONTROL Execution options]** tab, select at which time zone your workflow will start in the **[!UICONTROL Time zone]** field. Aqui, por exemplo, o fluxo de trabalho começará às 8 pm horas do Pacífico, uma semana antes do primeiro dia do mês para permitir que as entregas sejam criadas para todos os fusos horários aplicáveis.
   ![](assets/wkf_push_example_5.png)

1. The **Query** activity allows you to target your VIP customers aged between 20-30, who have subscribed to your mobile application and who did not open the email you sent:

   * Selecione um público-alvo (seus clientes VIP) e filtre suas idades.
   * Drag and drop the **Subscriptions to an application** element into the workspace. Select **Exists** and select the mobile application that you want to use.
   * Selecione o email enviado aos seus clientes.
   * Drag and drop the **Delivery logs (logs)** element into the workspace and select **Exists** to target all of the customers who received the email.
   * Drag and drop the **Tracking logs (tracking)** element into the workspace and select **Does not exist** to target all of the customers who did not open the email.

      ![](assets/wkf_push_example_2.png)

1. The **Push notification** activity allows you to enter the content of your message and to select the personalization fields that you want to use:

   * Select the **[!UICONTROL Recurring notification]** option.
   * Defina o conteúdo de notificação por push. For more information on push notification content, refer to this [section](../../channels/using/preparing-and-sending-a-push-notification.md).
   * In the **[!UICONTROL Schedule]** block, select **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Here, we chose the **[!UICONTROL Time zone of the contact date]** Pacific as in the workflow **[!UICONTROL Scheduler]**.
   * In the **[!UICONTROL Optimize the sending time per recipient]** field, select **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Click the **[!UICONTROL Start]** button to start your recurring workflow.

   ![](assets/wkf_push_example_3.png)

Seu fluxo de trabalho está em execução. It will start at the chosen start date of the **[!UICONTROL Scheduler]** at 8 pm Pacific time, the recurring push will then be sent every first day of the month at 8 pm depending on the customers time zone.
