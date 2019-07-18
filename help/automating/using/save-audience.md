---
title: Salvar público-alvo
seo-title: Salvar público-alvo
description: Salvar público-alvo
seo-description: A atividade Salvar público-alvo permite atualizar um público existente ou criar um novo público-alvo da população calculada para um fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 8 babb 173-fa 59-44 a 7-a 2 a 5-49 f 45 ba 6 bf 99
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: atividades de definição de metas
discoiquuid: 1 f 6 bb 048-7 abd -499 b-a 4 b 0-187 f 9492 dc 47
context-tags: Saveaudience, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Save audience{#save-audience}

## Description {#description}

![](assets/save_audience.png)

The **[!UICONTROL Save audience]** activity allows you to update an existing audience or create a new audience from the population computed upstream in a workflow. The audiences created or updated from this activity are **List** or **File** audiences. They are added to the list of application audiences, and are made available via the **[!UICONTROL Audiences]** menu.

>[!NOTE]
>
>If the audience created through the **[!UICONTROL Save audience]** activity has been enriched with additional data, you will not be able to use these data to personalize a standalone delivery. Eles só podem ser usados a partir de uma entrega executada em um fluxo de trabalho.

Essa atividade também permite exportar perfis como públicos-alvo/segmentos da Adobe Experience Cloud. Isso permite que você explore esses públicos-alvo em outras soluções da Adobe Experience Cloud. For more information about shared audiences, refer to [Working with Campaign and People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).

## Context of use {#context-of-use}

**[!UICONTROL Save audience]** A atividade é usada principalmente para manter grupos de população calculados no mesmo fluxo de trabalho, convertendo-os em públicos-alvo reutilizáveis.

## Configuration {#configuration}

1. Drop a **[!UICONTROL Save audience]** activity into your workflow.
1. Conecte-o depois das outras atividades de direcionamento, como uma consulta, uma interseção, uma união ou uma exclusão.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Selecione a ação que deseja executar:

   * **[!UICONTROL Update an existing audience]**: Selecione um público existente e escolha o tipo de atualização:

      * **[!UICONTROL Replace audience content with new data]**: Todo o conteúdo do público-alvo é substituído. Os dados antigos são perdidos. Somente os dados da transição de entrada do público-alvo salvo serão mantidos.
      * **[!UICONTROL Complete audience with new data]**: Os dados antigos do público-alvo são mantidos e os dados da transição de entrada do público-alvo salvo são adicionados a ele.
   * **[!UICONTROL Create then update an audience]**: Digite o nome do público-alvo e selecione o tipo de atualização. Se o público-alvo ainda não existir, então será criado. Se ele já existir, será atualizado de acordo com o modo selecionado:

      * **[!UICONTROL Replace audience content with new data]**: Todo o conteúdo do público-alvo é substituído. Os dados antigos são perdidos. Somente os dados da transição de entrada do público-alvo salvo serão mantidos.

         Aviso, esta opção apaga o tipo de público-alvo e a dimensão de definição de metas do público-alvo atualizado.

      * **[!UICONTROL Complete audience with new data]**: Os dados antigos do público-alvo são mantidos e os dados da transição de entrada do público-alvo salvo são adicionados a ele.

         Aviso, essa opção causa um erro se o tipo de público-alvo ou a dimensão de definição de metas do público-alvo atualizado não forem compatíveis com a configuração atual do fluxo de trabalho. Por exemplo, você não pode concluir um tipo de arquivo de tipo de arquivo com perfis que vêm de uma consulta.
   * **[!UICONTROL Create a new audience]**: Insira o nome do público-alvo a ser criado. A hora e a data em que o público-alvo é criado automaticamente serão adicionadas ao nome do público-alvo. Isso torna o público-alvo único sempre que o fluxo de trabalho é executado.
   * **[!UICONTROL Share in Adobe Experience Cloud]**: Se você tiver perfis direcionados e quiser exportar seu público para a Adobe Experience Cloud, selecione esta opção, depois selecione um público compartilhado existente ou crie um novo público-alvo.

      Also select a **[!UICONTROL Shared Data source]** that corresponds to the resource of the data contained in the audience so that the data is correctly reconciled in Adobe Experience Cloud.

      Using this option, the shared audience is not added to the list of Adobe Campaign audiences available via the **[!UICONTROL Audiences]** menu.

      >[!NOTE]
      >
      >Essa opção estará disponível somente se a funcionalidade de públicos-alvo compartilhados com a Adobe Experience Cloud tiver sido configurada pelo seu administrador. For more information, refer to [Working with Campaign and People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).
   O tipo de público-alvo salvo ou disponível durante uma atualização depende das atividades inseridas no fluxo de trabalho.

   If the targeting dimension of the audience is unknown when it is saved (for example if it is from an imported file), the audience is created or updated as a **[!UICONTROL File]** type audience.

   If the targeting dimension of the saved audience is already defined when it is saved (for example, if it comes from a targeting, after a query, etc.), then the audience is saved or updated as a **[!UICONTROL List]** type audience.

   The content of the saved audience is then available in the detail view of the audience, which can be accessed from the **[!UICONTROL Audiences]** menu. As colunas disponíveis nessa exibição correspondem às colunas da transição de entrada do fluxo de trabalho salva do fluxo de trabalho. Por exemplo: as colunas do arquivo importado, os dados adicionais adicionados a partir de uma consulta.

1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

## Example {#example}

O fluxo de trabalho definido neste exemplo mostra uma atualização de público-alvo regular da definição de metas:

* It is automatically executed once a month using a **[!UICONTROL Scheduler]**.
* You can use a **[!UICONTROL Query]** to recover all the profiles subscribed to the different application services available.
* The **[!UICONTROL Save audience]** activity updates the audience by deleting profiles that have unsubscribed from the service since the last workflow execution and by adding the newly subscribed profiles.

![](assets/save_audience_example_1.png)

**[!UICONTROL Save audience]** A atividade é configurada da seguinte maneira:

![](assets/save_audience_example_2.png)

