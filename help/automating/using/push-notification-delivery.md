---
title: Entrega por notificação por push
description: A atividade de entrega de notificação por push permite configurar o envio de uma única notificação por push de envio ou de uma notificação por push recorrente em um fluxo de trabalho.
page-status-flag: never-activated
uuid: 994d8fe3-29f0-4b5c-89ee-c6be7c60a31b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: e61bdaee-4b48-4845-a2a5-574b577ea796
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: accc382ca1543d648e60d53cab338537fd9ea3ef

---


# Entrega por notificação por push{#push-notification-delivery}

## Descrição {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

A **[!UICONTROL Push notification]**atividade permite configurar o envio de uma notificação por push em um fluxo de trabalho. Esta pode ser uma**&#x200B;única notificação de envio **e enviada apenas uma vez, ou pode ser uma notificação** recorrente **.

As notificações de envio único são entregas de notificação por push de aplicativo móvel padrão, enviadas uma vez.

Notificações recorrentes permitem enviar a mesma entrega de notificação por push do aplicativo móvel várias vezes para diferentes destinos em um período definido. Você pode agregar as entregas por período para obter relatórios que correspondam às suas necessidades.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Push notification]**atividade é geralmente usada para automatizar o envio de uma notificação para um destino calculado no mesmo fluxo de trabalho.

Quando vinculado a um programador, você pode definir notificações por push recorrentes.

Os destinatários são definidos como upstream da atividade no mesmo fluxo de trabalho, por meio de atividades de definição de metas, como consultas, interseções etc.

A preparação da mensagem é acionada de acordo com os parâmetros de execução do fluxo de trabalho. No painel de mensagens, você pode selecionar se deseja solicitar ou não uma confirmação manual para enviar a mensagem (obrigatório por padrão). Você pode iniciar o fluxo de trabalho manualmente ou colocar uma atividade do programador no fluxo de trabalho para automatizar a execução.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Push notification]**atividade em seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.

   >[!NOTE]
   >
   >Você pode acessar as propriedades gerais e as opções avançadas da atividade (e não da entrega em si) por meio do ![](assets/dlv_activity_params-24px.png) botão das ações rápidas da atividade. Esse botão é específico para a **[!UICONTROL Push notification]**atividade. As propriedades da notificação por push podem ser acessadas pela barra de ação no painel de push.

1. Selecione o modo de envio de notificação por push:

   * **[!UICONTROL Single notification]**: a notificação por push é enviada uma única vez. Você pode especificar aqui se deseja ou não adicionar uma transição de saída à atividade. Os diferentes tipos de transição estão detalhados na etapa 7 deste procedimento.
   * **[!UICONTROL Recurring notification]**: a notificação por push é enviada várias vezes, de acordo com a frequência definida em uma**[!UICONTROL Scheduler]** atividade. Selecione o período de agregação dos envios. Isso permite agrupar todos os envios que ocorrem durante o período definido em uma única notificação por push, também chamada de execução **** recorrente e que podem ser acessados da lista de atividades de marketing do aplicativo.

      Por exemplo, para uma notificação de aniversário recorrente, que é enviada diariamente, você pode escolher agregar os envios por mês. Isso permite que você receba relatórios sobre sua entrega mensalmente, embora a notificação seja enviada todos os dias.

1. Selecione um tipo de notificação. Esses tipos vêm de modelos de notificações por push definidos no menu **[!UICONTROL Resources]**>**[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Insira as propriedades gerais para a notificação por push. Você também pode anexá-la a uma campanha existente. A etiqueta da atividade de entrega do fluxo de trabalho é atualizada com a etiqueta de notificação por push.
1. Defina o conteúdo da notificação por push. Consulte [Criação de uma notificação por push](../../channels/using/preparing-and-sending-a-push-notification.md)
1. Por padrão, a **[!UICONTROL Push notification]**atividade não inclui nenhuma transição de saída. Se você deseja adicionar uma transição de saída à sua**[!UICONTROL Push Notification]** atividade, vá para a **[!UICONTROL General]**guia das opções de atividade avançada (![](assets/dlv_activity_params-24px.png)botão nas ações rápidas da atividade) e verifique uma das seguintes opções:

   * **[!UICONTROL Add outbound transition without the population]**: isso permite gerar uma transição de saída que contém exatamente a mesma população da transição de entrada.
   * **[!UICONTROL Add outbound transition with the population]**: isso permite gerar uma transição de saída contendo a população para a qual a notificação foi enviada. Os membros do alvo excluídos durante a preparação de entrega são excluídos desta transição.

1. Confirme a configuração da atividade e salve o fluxo de trabalho.

Ao reabrir a atividade, você é levado diretamente para o painel de notificação por push. Somente seu conteúdo pode ser editado.

Por padrão, iniciar um fluxo de trabalho de entrega aciona somente a preparação da mensagem. O envio de mensagens criadas a partir de um fluxo de trabalho ainda precisa ser confirmado depois que o fluxo de trabalho for iniciado. Mas no painel de mensagens, e somente se a mensagem foi criada a partir de um fluxo de trabalho, você pode desativar a **[!UICONTROL Request confirmation before sending messages]**opção. Ao desmarcar essa opção, as mensagens são enviadas sem aviso prévio após a preparação.

## Observações {#remarks}

As entregas criadas em um fluxo de trabalho podem ser acessadas na lista de atividades de marketing do aplicativo. Você pode exibir o status de execução do fluxo de trabalho usando o painel. Os links no painel de resumo da notificação por push permitem acessar diretamente os elementos vinculados (fluxo de trabalho, campanha etc.).

Nas entregas principais, que podem ser acessadas na lista de atividades de marketing, você pode exibir o número total de envios que foram processados (de acordo com o período de agregação especificado quando a **[!UICONTROL Push notification]**atividade foi configurada). Para fazer isso, abra a exibição detalhada do**[!UICONTROL Deployment]** bloco da entrega pai selecionando ![](assets/wkf_dlv_detail_button.png).

## Envio de uma notificação por push recorrente com um fluxo de trabalho {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

Neste exemplo, uma notificação por push personalizada é enviada todos os primeiros dias do mês, às 20 horas, aos assinantes do aplicativo móvel, dependendo de seus fusos horários. Para fazer isso:

1. A **[!UICONTROL Scheduler]**atividade permite que você inicie o fluxo de trabalho dias antes do início da entrega para poder enviar a notificação a cada assinante às 20 horas em um determinado fuso horário:

   * No **[!UICONTROL Execution frequency]**campo, selecione Mensal.
   * Selecione 20 horas no **[!UICONTROL Time]**campo.
   * Escolha em que dia a entrega será enviada todos os meses.
   * Selecione uma data de início para o fluxo de trabalho, pelo menos um dia antes do início da entrega. Caso contrário, alguns destinatários poderão receber a mensagem um dia depois se a hora selecionada já tiver passado em seus fusos horários.
   * Na **[!UICONTROL Execution options]**guia, selecione em qual fuso horário seu fluxo de trabalho será iniciado no**[!UICONTROL Time zone]** campo. Aqui, por exemplo, o fluxo de trabalho começará às 20 horas, hora do Pacífico, uma semana antes do primeiro dia do mês para permitir que as entregas sejam criadas para todos os fusos horários aplicáveis.
   >[!NOTE]
   >
   >Por padrão, o fuso horário selecionado é o definido nas propriedades do fluxo de trabalho (consulte [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. A atividade de **Consulta** permite direcionar seus clientes VIP com idades entre 20 e 30 anos, que se inscreveram no aplicativo móvel e que não abriram o email enviado:

   * Selecione um público-alvo (seus clientes VIP) e filtre na idade.
   * Arraste e solte as **Assinaturas em um elemento de aplicativo** na área de trabalho. Selecione **Existe** e selecione o aplicativo móvel que deseja usar.
   * Selecione o email que você enviou aos seus clientes.
   * Arraste e solte o elemento Registros de **entrega (logs)** na área de trabalho e selecione **Existe** para direcionar todos os clientes que receberam o email.
   * Arraste e solte o elemento **Rastreamento de logs (rastreamento)** no espaço de trabalho e selecione **Não existe** para direcionar todos os clientes que não abriram o email.

      ![](assets/wkf_push_example_2.png)

1. A atividade de notificação **por** push permite que você insira o conteúdo de sua mensagem e selecione os campos de personalização que deseja usar:

   * Selecione a **[!UICONTROL Recurring notification]**opção.
   * Defina o conteúdo da notificação por push. Para obter mais informações sobre o conteúdo da notificação por push, consulte esta [seção](../../channels/using/preparing-and-sending-a-push-notification.md).
   * No **[!UICONTROL Schedule]**bloco, selecione**[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Aqui, escolhemos o **[!UICONTROL Time zone of the contact date]**Pacífico como no fluxo de trabalho**[!UICONTROL Scheduler]**.
   * No **[!UICONTROL Optimize the sending time per recipient]**campo, selecione**[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Clique no **[!UICONTROL Start]**botão para iniciar seu fluxo de trabalho recorrente.

   ![](assets/wkf_push_example_3.png)

Seu fluxo de trabalho está em execução. Ele começará na data inicial escolhida para as 18h00 (horário do Pacífico), o envio recorrente será enviado todos os primeiros dias do mês, às 20h00, dependendo do fuso horário do cliente. **[!UICONTROL Scheduler]**
