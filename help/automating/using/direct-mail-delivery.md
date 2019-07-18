---
title: Entrega de mala direta
seo-title: Entrega de mala direta
description: Entrega de mala direta
seo-description: A atividade de entrega de mala direta permite configurar o envio de um único email direto enviado ou uma mala direta recorrente em um fluxo de trabalho.
page-status-flag: nunca ativado
uuid: bfa 7 b 176-a 17 c -4079-a 073-64 b 8 ce 4788 ed
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: channel-activities
discoiquuid: b 9 ddb 2 a 0-54 ff -4 ada-be 6 f -8109 fa 06 d 461
context-tags: Directmail, fluxo de trabalho, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Direct mail delivery{#direct-mail-delivery}

## Description {#description}

![](assets/paper.png)

![](assets/recurrentpaper.png)

The **[!UICONTROL Direct mail delivery]** activity allows you to configure and prepare a file containing profile data that you want to use for a direct mail campaign. This can be a direct mail that is used just once, or it can be a **recurring** direct mail.

Os emails diretos padrão são enviados uma vez.

Os emails recorrentes permitem enviar o mesmo email direto várias vezes para diferentes metas durante um período definido. Você pode agregar as entregas por período para obter relatórios que correspondam às suas necessidades.

## Context of use {#context-of-use}

The **[!UICONTROL Direct mail delivery]** activity is generally used to automate preparing a file that contains profile data. Esse arquivo pode ser enviado a um parceiro/provedor responsável pela correspondência.

Quando vinculados a um agendador, você pode definir os emails diretos recorrentes.

Os destinatários de mala direta são definidos como upstream da atividade no mesmo fluxo de trabalho, por atividades de definição de metas como consultas, interseções etc. Os perfis cujo endereço de correspondência não é especificado são excluídos automaticamente quando o mala direta está preparado.

A preparação de mensagens é acionada de acordo com os parâmetros de execução do fluxo de trabalho. No painel de mensagens, você pode selecionar se deseja ou não solicitar ou não uma confirmação manual para enviar a mensagem (obrigatório por padrão). Você pode iniciar o fluxo de trabalho manualmente ou colocar uma atividade de agendamento no fluxo de trabalho para automatizar a execução.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Direct mail delivery]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button from the activity's quick actions. Esse botão é específico das atividades do canal. As propriedades do mala direta podem ser acessadas por meio da barra de ações no painel de mala direta.

1. Selecione o modo de envio de mala direta:

   * **[!UICONTROL Direct mail]**: o mala direta é enviado uma única vez. Você pode especificar aqui se deseja adicionar uma transição de saída à atividade. Os diferentes tipos de transição são detalhados na etapa 7 desse procedimento.
   * **[!UICONTROL Recurring direct mail]**: o mala direta é enviado várias vezes, de acordo com a frequência definida em uma **[!UICONTROL Scheduler]** atividade. Selecione o período de agregação dos envios. This allows you to regroup all the sends that occur during the defined period in one single direct mail that is also called **Recurring execution** and can be accessed from the application's marketing activity list.

      Por exemplo, para um email de aniversário recorrente, que é processado diariamente, você pode optar por agregar os envios por mês. Isso permite que você receba relatórios mensalmente, embora o email seja processado diariamente.

      >[!NOTE]
      >
      >Para os emails diretos recorrentes, um novo arquivo é gerado em cada execução do fluxo de trabalho. O período de agregação selecionado não afeta esse comportamento.

1. Selecione um tipo de mala direta. The direct mail types come from templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. Insira as propriedades gerais do mala direta. Você também pode anexá-lo a uma campanha existente. O rótulo da atividade de entrega do fluxo de trabalho é atualizado com o rótulo de mala direta.
1. Definir o conteúdo de mala direta. Refer to the section concerning [content editing](../../designing/using/about-personalization.md).
1. By default, the **[!UICONTROL Direct mail delivery]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL Direct mail delivery]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**: isso permite gerar uma transição de saída que contenha exatamente a mesma população que a transição de entrada. Esta transição contém o arquivo gerado pela atividade de mala direta e pela população bruta recebida pela atividade de mala direta.
   * **[!UICONTROL Add outbound transition with the population]**: isso permite gerar uma transição de saída contendo a população para a qual o mala direta será enviado. Os membros do destino excluído durante a preparação de mala direta (quarentena, endereço inválido etc.) são excluídos desta transição. A transição também contém o arquivo gerado pelo mala direta.

1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

Ao reabrir a atividade, você será direcionado diretamente para o painel de mala direta. Somente seu conteúdo pode ser editado.

Por padrão, iniciar um fluxo de trabalho de entrega apenas aciona a preparação de mensagens. O envio de mensagens criadas a partir de um fluxo de trabalho ainda precisa ser confirmado após a inicialização do fluxo de trabalho. But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. Ao desmarcar essa opção, as mensagens são enviadas sem aviso prévio após a conclusão da preparação.

## Remarks {#remarks}

As entregas criadas em um fluxo de trabalho podem ser acessadas na lista de atividades de marketing do aplicativo. Você pode visualizar o status de execução do fluxo de trabalho usando o painel. Os links no painel de resumo de mala direta permitem acessar diretamente os elementos vinculados (fluxo de trabalho, campanha, entrega pai no caso de uma mala direta recorrente).

![](assets/wkf_display_parent_elements_direct_mail.png)

As execuções de entregas recorrentes são mascaradas por padrão. To view them, check the **[!UICONTROL Show recurring executions]** option in the marketing activities' search panel.

![](assets/wkf_display_recurrent_executions_direct_mail.png)

In the parent deliveries, which can be accessed from the marketing activity list or directly via the associated recurring executions, you can view the total number of mails that have been processed (according to the aggregation period specified when the **[!UICONTROL Direct mail delivery]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3_direct_mail.png)

## Example {#example}

An example of **[!UICONTROL Direct mail delivery]** is available in the [Direct Mail](../../channels/using/example-of-direct-mail-in-a-workflow.md) chapter.
