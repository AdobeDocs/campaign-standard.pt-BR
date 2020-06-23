---
title: Usar acionadores no Campaign
description: null
page-status-flag: never-activated
uuid: d844d013-b38a-4e69-9df5-0edc01fa9c6e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: a524c700-bad6-4fcf-857a-c31bfae4d30c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 2%

---


# Usar acionadores no Campaign{#using-triggers-in-campaign}

## Criação de um acionador mapeado na Campanha {#creating-a-mapped-trigger-in-campaign}

Você deve definir os comportamentos que deseja monitorar antecipadamente na Adobe Experience Cloud (serviço **[!UICONTROL Triggers]** principal). Para obter mais informações, consulte a documentação [da](https://docs.adobe.com/content/help/en/core-services/interface/activation/triggers.html)Adobe Experience Cloud. Observe que, ao definir o acionador, é necessário ativar os aliases. Para cada comportamento (navegação/abandono de formulário, adição/exclusão de produtos, sessão expirada etc.), um novo acionador deve ser adicionado na Adobe Experience Cloud.

Agora é necessário criar um evento de disparo no Adobe Campaign com base em um acionador da Adobe Experience Cloud existente.

Você pode assistir a este [vídeo](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) para ajudá-lo a entender como os acionadores são configurados no Adobe Campaign.

As etapas para colocar isso em prática são:

1. Clique no **[!UICONTROL Adobe Campaign]** logotipo, no canto superior esquerdo, em seguida selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Experience Cloud Triggers]**.

   ![](assets/remarketing_1.png)

1. Clique no botão **[!UICONTROL Create]**. O assistente de criação que é aberto exibe a lista de todos os acionadores definidos na Adobe Experience Cloud. A **[!UICONTROL Fired by Analytics]** coluna exibe o número de eventos enviados pelo acionador da Adobe Experience Cloud para a Campanha. Este é o mapeamento de acionadores criados na interface do Experience Cloud.

   ![](assets/remarketing_2.png)

1. Selecione o acionador da Adobe Experience Cloud que deseja usar e clique em **[!UICONTROL Next]**.
1. Configure as propriedades gerais do acionador. Nesta etapa do assistente, especifique também o canal e o targeting dimension a serem usados para o acionador (consulte [targeting dimension e recursos](../../automating/using/query.md#targeting-dimensions-and-resources)). Em seguida, confirme a criação do acionador.
1. Clique no botão à direita do **[!UICONTROL Event content and enrichment]** campo para visualização o conteúdo da carga. Essa tela também permite que você aprimore os dados do evento com os dados do perfil armazenados no banco de dados do Adobe Campaign. O enriquecimento é executado da mesma forma que para um mensagen transacional padrão.

   ![](assets/remarketing_3.png)

1. No **[!UICONTROL Transactional message validity duration]** campo, defina a duração para a qual a mensagem permanecerá válida após o evento ser enviado pela Analytics. Se uma duração de 2 dias for definida, a mensagem não será mais enviada após essa duração ter expirado. Se você colocar várias mensagens em espera, isso garante que elas não serão enviadas se você as retomar após um determinado período de tempo.

   ![](assets/remarketing_4.png)

1. Clique no **[!UICONTROL Publish]** botão para start de publicar o evento de disparo.
1. Se precisar fazer uma alteração no schema do acionador mesmo depois de publicar o evento do acionador, clique no **[!UICONTROL Update schema]** botão para recuperar as alterações mais recentes.

   Observe que essa ação cancelará a publicação do seu acionador e mensagen transacional, você precisará republicá-los depois.

   ![](assets/remarketing_11.png)

O **[!UICONTROL Show Trigger in Experience Cloud]** botão permite que você visualização a definição do acionador na Adobe Experience Cloud.

Depois que o evento é publicado, um modelo transacional vinculado ao novo evento é criado automaticamente. Em seguida, é necessário modificar e publicar o modelo que acabou de ser criado. For more on this, refer to the [Editing the template](../../start/using/marketing-activity-templates.md) section.

## Edição do template de mensagem transacional {#editing-the-transactional-message-template}

Depois de criar e publicar o evento de disparo, o modelo transacional correspondente é criado automaticamente. Para obter mais informações, consulte a seção [Criação de um acionador mapeado na Campanha](#creating-a-mapped-trigger-in-campaign) .

Para que o evento acione o envio de um mensagen transacional, é necessário personalizar o modelo, testá-lo e publicá-lo. Essas etapas são as mesmas de um mensagen transacional padrão. For more on this, refer to the [Transactional template](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message) section.

>[!NOTE]
>
>Se você cancelar a publicação do modelo, ele cancelará automaticamente a publicação do evento acionador.

Ao editar o conteúdo, você pode adicionar um campo de personalização com base nas informações enviadas pelo acionador do Analytics. Se você enriquecer os dados do evento, poderá personalizar a mensagem com base nessas informações. Para personalizar sua mensagem, selecione **[!UICONTROL Transactional event]** > **[!UICONTROL Event context]** e selecione um campo.

![](assets/remarketing_8.png)

## Acesso aos relatórios {#accessing-the-reports}

Para visualização do relatório de disparo dedicado no Adobe Campaign, abra o evento de disparo criado anteriormente e clique em **[!UICONTROL Show trigger report]**.

![](assets/remarketing_9.png)

O relatório mostra o número de eventos processados em comparação ao número de eventos enviados pela Analytics. Também exibe uma lista de todos os acionadores recentes.

![](assets/trigger_uc_browse_14.png)

