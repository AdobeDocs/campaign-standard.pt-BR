---
title: Uso de acionadores no Campaign
seo-title: Uso de acionadores no Campaign
description: Uso de acionadores no Campaign
seo-description: null
page-status-flag: nunca ativado
uuid: d 844 d 013-b 38 a -4 e 69-9 df 5-0 edc 01 fa 9 c 6 e
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: a 524 c 700-bad 6-4 fcf -857 a-c 31 bfae 4 d 30 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Using Triggers in Campaign{#using-triggers-in-campaign}

## Creating a mapped trigger in Campaign {#creating-a-mapped-trigger-in-campaign}

You should make sure to define the behaviors that you want to monitor beforehand in Adobe Experience Cloud ( **[!UICONTROL Triggers]** core service). For more on this, refer to the [Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html). Observe que ao definir o acionador, você precisa ativar os alias. Para cada comportamento (navegação/abandono de formulário, adição/exclusão de produtos, sessão expirada etc.), é necessário adicionar um novo disparador na Adobe Experience Cloud.

Agora você precisa criar um evento de acionamento no Adobe Campaign com base em um disparador existente da Adobe Experience Cloud.

You can watch this [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) to help you understand how triggers are set up in Adobe Campaign.

As etapas para colocar isso em vigor são:

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Experience Cloud Triggers]**.

   ![](assets/remarketing_1.png)

1. Click the **[!UICONTROL Create]** button. O assistente de criação que é aberto exibe a lista de todos os acionadores definidos na Adobe Experience Cloud. **[!UICONTROL Fired by Analytics]** A coluna exibe o número de eventos enviados pelo acionador da Adobe Experience Cloud para Campanha. Isso é o mapeamento de disparadores criados na interface da Experience Cloud.

   ![](assets/remarketing_2.png)

1. Select the Adobe Experience Cloud trigger that you want to use and click **[!UICONTROL Next]**.
1. Configure as propriedades gerais do acionador. At this step of the wizard, also specify the channel and the targeting dimension to use for the trigger (see [targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)). Em seguida, confirme a criação do acionador.
1. Click the button to the right of the **[!UICONTROL Event content and enrichment]** field to view the content of the payload. Essa tela também permite aprimorar os dados do evento com dados de perfil armazenados no banco de dados do Adobe Campaign. O enriquecimento é realizado da mesma forma que para uma mensagem transacional padrão.

   ![](assets/remarketing_3.png)

1. In the **[!UICONTROL Transactional message validity duration]** field, define the duration for which the message will stay valid after the event is sent by Analytics. Se uma duração de 2 dias for definida, a mensagem não será mais enviada após o passado da duração. Se várias mensagens forem mantidas em espera, isso garante que as mensagens não serão enviadas se você as retomar após um determinado período.

   ![](assets/remarketing_4.png)

1. If a propensity scoring is defined in Analytics (see the [Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/insight/client/c_visitor_propensity.html)), you can choose not to send the message if the customer has a high probability of coming back to the website in the near future. O conteúdo da pontuação e o limite estão disponíveis no conteúdo da carga para que você possa usar esses valores para personalizar a mensagem. Para usar essa opção, marque a caixa na parte inferior da tela. Os clientes com uma forte probabilidade de retornar para o site em breve não receberão uma mensagem.
1. Click the **[!UICONTROL Publish]** button to start publishing the trigger event.
1. If you need to make a change in your trigger schema even after publishing your trigger event, click the **[!UICONTROL Update schema]** button to retrieve the latest changes.

   Observe que esta ação cancelará a publicação de sua mensagem transacional e acionadora, você será obrigada a publicá-las novamente depois.

   ![](assets/remarketing_11.png)

The **[!UICONTROL Show Trigger in Experience Cloud]** button allows you to view the trigger definition in Adobe Experience Cloud.

Depois que o evento é publicado, um modelo transacional vinculado ao novo evento é criado automaticamente. Você precisa modificar e publicar o modelo que acabou de ser criado. For more on this, refer to the [Editing the template](../../start/using/about-templates.md) section.

## Editing the transactional message template {#editing-the-transactional-message-template}

Após criar e publicar o evento de acionamento, o modelo transacional correspondente é criado automaticamente. For more on this, refer to the [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) section.

Para que o evento dispare uma mensagem transacional, você deve personalizar o modelo e depois testá-lo e publicá-lo. Essas etapas são as mesmas de uma mensagem transacional padrão. For more on this, refer to the [Transactional template](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message) section.

>[!NOTE]
>
>Se você cancelar a publicação do modelo, a publicação do evento acionará automaticamente.

Ao editar o conteúdo, você pode adicionar um campo de personalização com base nas informações enviadas pelo acionador do Analytics. Se você aprimora os dados do evento com os dados de perfil do Adobe Campaign, é possível personalizar a mensagem com base nessas informações. To personalize your message, select **[!UICONTROL Transactional event]** &gt; **[!UICONTROL Event context]** and select a field.

![](assets/remarketing_8.png)

## Accessing the reports {#accessing-the-reports}

To view the dedicated trigger report in Adobe Campaign, open the trigger event that you previously created, and click **[!UICONTROL Show trigger report]**.

![](assets/remarketing_9.png)

O relatório mostra o número de eventos processados em comparação com o número de eventos enviados pelo Analytics. Também exibe uma lista de todos os acionadores recentes.

![](assets/trigger_uc_browse_14.png)

