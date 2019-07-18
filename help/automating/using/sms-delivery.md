---
title: entrega SMS
seo-title: entrega SMS
description: entrega SMS
seo-description: A atividade de entrega SMS permite configurar o envio de um SMS único ou um SMS recorrente em um fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 736078 c 6-ac 91-4440-825 b -4 a 6 ae 31894 ef
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: channel-activities
discoiquuid: 978592 b 8-989 a -446 a -8 a 84-12 b 7 fecfc 130
context-tags: sms, main; entrega, smscontent, voltar
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# SMS delivery{#sms-delivery}

## Description {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

The **[!UICONTROL SMS delivery]** activity allows you to configure sending an SMS in a workflow. This can be a **single send** SMS and sent just once, or it can be a **recurring** SMS.

Mensagens SMS de envio único são SMS padrão, enviadas uma vez.

Mensagens SMS recorrentes permitem enviar o mesmo SMS várias vezes para diferentes metas durante um período definido. Você pode agregar as entregas por período para obter relatórios que correspondam às suas necessidades.

## Context of use {#context-of-use}

The **[!UICONTROL SMS delivery]** activity is generally used to automate sending an SMS to a target calculated in the same workflow.

Quando vinculados a um agendador, você pode definir mensagens SMS recorrentes.

Os destinatários de SMS são definidos como upstream da atividade no mesmo fluxo de trabalho, por atividades de definição de metas como consultas, interseções etc.

A preparação de mensagens é acionada de acordo com os parâmetros de execução do fluxo de trabalho. No painel de mensagens, você pode selecionar se deseja ou não solicitar ou não uma confirmação manual para enviar a mensagem (obrigatório por padrão). Você pode iniciar o fluxo de trabalho manualmente ou colocar uma atividade de agendamento no fluxo de trabalho para automatizar a execução.

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL SMS delivery]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button in the workflow's action bar. This button is specific to the **[!UICONTROL SMS delivery]** activity. As propriedades SMS podem ser acessadas por meio da barra de ações no painel SMS.

1. Selecione o modo de envio de SMS:

   * **[!UICONTROL SMS]**: o SMS é enviado uma única vez. Você pode especificar aqui se deseja adicionar uma transição de saída à atividade. Os diferentes tipos de transição são detalhados na etapa 7 desse procedimento.
   * **[!UICONTROL Recurring SMS]**: o SMS é enviado várias vezes, de acordo com a frequência definida em uma **[!UICONTROL Scheduler]** atividade. Selecione o período de agregação dos envios. This allows you to regroup all the sends that occur during the defined period into one single view that is also called **Recurring execution** and can be accessed from the application's marketing activity list.

      Por exemplo, para um SMS de aniversário recorrente, que é enviado diariamente, você pode optar por agregar os envios por mês. Isso permite que você receba relatórios mensalmente, embora o SMS seja enviado diariamente.

1. Selecione um tipo de SMS. The SMS types come from SMS templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. Insira as propriedades gerais do SMS. Você também pode anexá-lo a uma campanha existente. O rótulo da atividade de entrega do fluxo de trabalho é atualizado com o rótulo SMS.
1. Defina o conteúdo SMS. Refer to the section concerning [Creating an SMS message](../../channels/using/creating-an-sms-message.md).
1. By default, the **[!UICONTROL SMS delivery]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL SMS delivery]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**: isso permite gerar uma transição de saída que contenha exatamente a mesma população que a transição de entrada.
   * **[!UICONTROL Add outbound transition with the population]**: isso permite gerar uma transição de saída contendo a população para a qual o SMS foi enviado. Os membros do alvo excluídos durante a preparação de entrega (quarentena, número inválido etc.) são excluídos desta transição.

1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

Ao reabrir a atividade, você será direcionado diretamente para o painel SMS. Somente seu conteúdo pode ser editado.

Por padrão, iniciar um fluxo de trabalho de entrega apenas aciona a preparação de mensagens. O envio de mensagens criadas a partir de um fluxo de trabalho ainda precisa ser confirmado após a inicialização do fluxo de trabalho. But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. Ao desmarcar essa opção, as mensagens são enviadas sem aviso prévio após a conclusão da preparação.

## Remarks {#remarks}

As entregas criadas em um fluxo de trabalho podem ser acessadas na lista de atividades de marketing do aplicativo. Você pode visualizar o status de execução do fluxo de trabalho usando o painel. Os links no painel de resumo SMS permitem acessar diretamente os elementos vinculados (fluxo de trabalho, campanha, entrega pai no caso de um SMS recorrente).

Entretanto, as execuções de entregas recorrentes são mascaradas por padrão. To view them, check the **[!UICONTROL Show recurring executions]** option in the marketing activities' search panel.

In the parent deliveries, which can be accessed from the marketing activity list or directly via the associated recurring executions, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL SMS delivery]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).

## Example {#example}

![](assets/wkf_sms_example_1.png)

Este exemplo é um fluxo de trabalho de aniversário. Todo dia um SMS é enviado para perfis cujo aniversário está no dia. Para fazer isso:

* The **[!UICONTROL Scheduler]** allows you to start the workflow every day at 8am.

   ![](assets/wkf_delivery_example_2.png)

* **[!UICONTROL Query]** A atividade permite calcular os perfis que forneceram um número de telefone móvel e cujo aniversário está no dia atual, toda vez que o fluxo de trabalho é executado. O cálculo de aniversário é executado usando um filtro predefinido disponível na paleta na ferramenta de edição de consulta.

   ![](assets/wkf_delivery_example_3.png)

* The **[!UICONTROL SMS]** is recurring. Os envios são agregados por mês. Assim, todas as mensagens SMS enviadas em um mês são agregadas a uma única exibição. In one year, 365 deliveries are therefore executed but they are regrouped into 12 views (also called **recurring executions**) in the Adobe Campaign interface. Os detalhes do histórico e do relatório são exibidos todo mês e não para cada envio.

   ![](assets/wkf_sms_example_4.png)

