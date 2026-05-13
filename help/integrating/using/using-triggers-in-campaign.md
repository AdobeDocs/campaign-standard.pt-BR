---
title: Utilização do Triggers no Campaign
description: Crie um evento de acionador no Adobe Campaign com base em um acionador existente do Adobe Experience Cloud.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 6b8d5118-89ed-49c2-b601-0aff472fcadd
TQID: https://experienceleague.adobe.com/JS2nl6HlwWPj9JFhWgNPeWV2cNNiAjvCdczoYH5AhtE
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 743
ht-degree: 76%

---

# Utilização do Triggers no Campaign{#using-triggers-in-campaign}

## Criação de um acionador mapeado no Campaign {#creating-a-mapped-trigger-in-campaign}

>[!NOTE]
>
>Para criar Triggers, você precisará da função **[!UICONTROL Administration]** ou estar no grupo de segurança **[!UICONTROL Administrators]**. Para obter mais informações sobre essas operações, consulte esta [página](../../administration/using/list-of-roles.md).

É recomendável definir os comportamentos que deseja monitorar antecipadamente no Adobe Experience Cloud (**[!UICONTROL Triggers]** serviço principal). Para obter mais informações, consulte a [documentação da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/experience-cloud/triggers/create.html?lang=pt-BR). Observe que, ao definir o acionador, é necessário habilitar os aliases. Para cada comportamento (navegação/abandono de formulário, adição/exclusão de produtos, sessão expirada etc.), um novo acionador deve ser adicionado na Adobe Experience Cloud.

Agora é necessário criar um evento de acionador no Adobe Campaign com base em um acionador existente da Adobe Experience Cloud.

Estas são as etapas para colocar o acionador em prática:

1. Clique no logotipo **Adobe**, no canto superior esquerdo, e selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Experience Cloud Triggers]**.

   ![](assets/remarketing_1.png)

1. Clique no botão **[!UICONTROL Create]**. O assistente de criação que é aberto exibe a lista de todos os acionadores definidos na Adobe Experience Cloud. A coluna **[!UICONTROL Fired by Analytics]** exibe o número de eventos enviados pelo acionador da Adobe Experience Cloud para o Campaign. Esse é o mapeamento de acionadores criados na interface da Experience Cloud.

   ![](assets/remarketing_2.png)

1. Selecione o acionador da Adobe Experience Cloud que deseja usar e clique em **[!UICONTROL Next]**.
1. Configure as propriedades gerais do acionador. Nesta etapa do assistente, especifique também o canal e a dimensão de direcionamento a serem usados para o acionador (consulte [Dimensões de direcionamento e recursos](../../automating/using/query.md#targeting-dimensions-and-resources)). Em seguida, confirme a criação do acionador.
1. Clique no botão à direita do campo **[!UICONTROL Event content and enrichment]** para visualizar o conteúdo do payload. Essa tela também permite enriquecer os dados do evento com os dados do perfil armazenados no banco de dados do Adobe Campaign. O enriquecimento é executado da mesma maneira que é executado para uma mensagem transacional padrão.

   ![](assets/remarketing_3.png)

1. No campo **[!UICONTROL Transactional message validity duration]**, defina a duração para a qual a mensagem permanecerá válida após o evento ser enviado pelo Analytics. Se uma duração de 2 dias for definida, a mensagem não será mais enviada depois que essa duração tiver expirado. Se você colocar várias mensagens em espera, elas não serão enviadas se você retomá-las após um determinado período.

   ![](assets/remarketing_4.png)

1. Agora você pode publicar seus acionadores. Para obter mais informações, consulte [Publicar um acionador no Campaign](../../integrating/using/using-triggers-in-campaign.md#publishing-trigger-in-campaign).

## Publicação de um acionador no Campaign {#publishing-trigger-in-campaign}

Depois de criar um evento de acionador no Adobe Campaign com base em um acionador existente do Adobe Experience Cloud, agora é necessário publicá-lo.

1. No acionador criado anteriormente, clique no botão **[!UICONTROL Publish]** para iniciar a publicação do evento do acionador.

   ![](assets/trigger_publish_1.png)

1. Você pode verificar o progresso da sua publicação de acionador em **[!UICONTROL Publication]**.

   ![](assets/trigger_publish_2.png)

1. Quando a publicação for concluída, a seguinte mensagem aparecerá em **[!UICONTROL Publication]**.

   ![](assets/trigger_publish_3.png)

1. Se precisar fazer uma alteração no esquema do acionador, mesmo depois de publicar o evento do acionador, clique no botão **[!UICONTROL Update schema]** para recuperar as alterações mais recentes.

   Observe que essa ação cancelará a publicação do acionador e a mensagem transacional. Você precisará publicá-los novamente depois.

   ![](assets/trigger_publish_4.png)

1. O botão **[!UICONTROL Show Trigger in Experience Cloud]** permite exibir a definição do acionador no Adobe Experience Cloud.

Depois que o evento for publicado, um modelo transacional vinculado ao novo evento é criado automaticamente. Depois é necessário modificar e publicar o modelo que acabou de ser criado. Para obter mais informações, consulte a seção [Edição do modelo](../../start/using/marketing-activity-templates.md).

## Edição do modelo de mensagem transacional {#editing-the-transactional-message-template}

Depois de criar e publicar o evento de acionador, o modelo transacional correspondente é criado automaticamente. Para obter mais informações, consulte a seção [Criação de um acionador mapeado no Campaign](#creating-a-mapped-trigger-in-campaign).

Para que o evento acione o envio de uma mensagem transacional, é necessário personalizar o modelo, testá-lo e publicá-lo. Essas etapas são as mesmas de uma mensagem transacional padrão. Para obter mais informações, consulte a seção [Edição de mensagem transacional](../../channels/using/editing-transactional-message.md).

>[!NOTE]
>
>Se você cancelar a publicação do modelo, a publicação do evento de acionador será automaticamente cancelada.

Ao editar o conteúdo, você pode adicionar um campo de personalização com base nas informações enviadas pelo acionador do Analytics. Se você enriquecer os dados do evento com os dados de perfil do Adobe Campaign, será possível personalizar a mensagem com base nessas informações. Para personalizar a mensagem, selecione **[!UICONTROL Transactional event]** > **[!UICONTROL Event context]** e selecione um campo.

![](assets/remarketing_8.png)

## Acesso aos relatórios {#accessing-the-reports}

Para exibir o relatório de acionador dedicado no Adobe Campaign, abra o evento de acionador, criado anteriormente, e clique em **[!UICONTROL Show trigger report]**.

![](assets/remarketing_9.png)

O relatório mostra o número de eventos processados em comparação ao número de eventos enviados pelo Analytics. Ele também exibe uma lista de todos os acionadores recentes.

![](assets/trigger_uc_browse_14.png)
