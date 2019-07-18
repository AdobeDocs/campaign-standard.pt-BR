---
title: Atualização da estrutura do banco de dados
seo-title: Atualização da estrutura do banco de dados
description: Atualização da estrutura do banco de dados
seo-description: Descobrir como atualizar o banco de dados do Adobe Campaign.
page-status-flag: nunca ativado
uuid: 6 c 802 f 4 f-d 298-4 ca 4-acdb -09 f 2 ad 3865 b 9
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adição ou extensão-a-resource
discoiquuid: 2448 b 126-66 b 8-4608-aa 6 c -8028 fb 1902 a 4
context-tags: implantar, principal; Eventcusresource, visão geral
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Updating the database structure{#updating-the-database-structure}

Para que as modificações no modelo de dados sejam eficazes e possam usá-las, a estrutura do banco de dados precisa ser atualizada.

>[!NOTE]
>
>Os recursos personalizados são atualizados automaticamente durante as atualizações automáticas realizadas pela Adobe.

## Publishing a custom resource {#publishing-a-custom-resource}

Para aplicar as alterações realizadas nos recursos, é necessário executar uma atualização de banco de dados.

>[!NOTE]
>
>Se um campo de um recurso personalizado usado em um evento for modificado ou excluído, o evento correspondente será despublicado automaticamente. See [Configuring Transactional messaging](../../administration/using/configuring-transactional-messaging.md).

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]**, then **[!UICONTROL Publishing]**.
1. By default, the option **[!UICONTROL Determine modifications since the last publication]** is checked, which means that only the changes carried out since the last update will be applied.

   >[!NOTE]
   >
   >The **[!UICONTROL Repair database structure]** reestablishes a correct configuration if the publication failed before completing. Qualquer modificação realizada diretamente no banco de dados e sem uso de recursos personalizados será excluída.

   ![](assets/schema_extension_12.png)

1. Click the **[!UICONTROL Prepare publication]** button to start the analysis. Observe que as grandes atualizações da tabela devem ser feitas quando a instância não estiver amplamente ocupada por fluxos de trabalho.

   To learn more on the action to perform on the Profiles &amp; Services API, refer to [Publishing a resource with API extension](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).

   ![](assets/schema_extension_13.png)

1. Once the publication has been carried out, click the **[!UICONTROL Publish]** button to apply your new configurations.
1. Once published, the **[!UICONTROL Summary]** pane of each resource indicates that the status is now **[!UICONTROL Published]** and specifies the date of the last publication.

   >[!NOTE]
   >
   >Se você efetuar novas alterações em um recurso, repita esta operação para que as alterações sejam aplicadas.

   If resources have the **[!UICONTROL Pending re-draft]** status before publishing, then an additional message will appear inviting you to check your actions because publishing will result in definitive changes (deleting columns, tables...). To help you carry out this last change, an **[!UICONTROL SQL Script]** tab is available. Fornece o comando SQL que será executado durante a publicação.

   ![](assets/schema_extension_scriptsql.png)

   >[!NOTE]
   >
   >You can stop the Re-draft process by clicking the **[!UICONTROL Cancel re-draft]** button. Essa ação reverterá o status do recurso de volta para a original.

1. If your publication failed, you can always go back to the previous publication by clicking **[!UICONTROL Back to latest successful publication]**.

   Observe que, se você deixar sua publicação em um status de falha, uma janela pop-up será aberta assim que você fizer logon na sua instância para lembrá-la de corrigir essa publicação. Sua instância não será atualizada com novas versões de produto até que sua publicação seja fixa.

   ![](assets/schema_extension_31.png)

## Publishing a resource with API extension {#publishing-a-resource-with-api-extension}

Você pode criar a API de perfil e de serviços nos seguintes casos:

* When you extend the custom resources **[!UICONTROL Profiles]** or **[!UICONTROL Services]**, you can perform an update of the Profiles and Services API to integrate the fields declared in the custom resources extension.
* When you define a custom resource and you create a link between the resources **[!UICONTROL Profiles]** or **[!UICONTROL Services]** and the custom resource, you can perform an update to include the new resource in the API.

Você pode selecionar essa opção na tela de publicação.

* Se a API ainda não tiver sido publicada (ou seja, se você nunca tiver estendido o recurso ou se nunca tiver selecionado essa opção ainda para esse recurso ou outro recurso), você terá a opção de criá-la ou não.

   ![](assets/create-profile-and-services-api.png)

* Se a API já tiver sido publicada (ou seja, se você já tiver estendido o recurso e selecionado essa opção uma vez), a atualização da API será forçada.

   Na verdade, após a criação, a API será automaticamente atualizada toda vez que você a publicar novamente. Isso deve evitar quebrar o perfil ou o recurso de serviço dessa API e aprimorar sua instância.

Note that by default, the custom resource is integrated, but, for a specific behavior, if you don't want to publish this resource, you can select the option **[!UICONTROL Hide this resource from APIs]** available in the **[!UICONTROL Resource Properties]**.

![](assets/removefromextoption.png)

After the **[!UICONTROL Prepare Publication]** step, Adobe Campaign displays the delta between the current version of the API and the future version after the publication in the tab **[!UICONTROL Profiles & Services API Preview]**. Se você estender a API pela primeira vez, o delta compara a definição de recurso personalizada predefinida com sua extensão.

As informações exibidas na guia são divididas em três seções: adicionados, excluídos e modificados.

![](assets/extendpandsapi_diff.png)

A análise do delta é uma etapa obrigatória, já que a etapa da publicação modificará o comportamento da API e provavelmente afetará o desenvolvimento circundante em um efeito domino.

>[!NOTE]
>
>This publication updates the **[!UICONTROL profilesAndServicesExt]** API. The **[!UICONTROL profilesAndServices]** API is not updated.

For more information on the Adobe Campaign API, consult the dedicated Adobe Campaign documentation on [Adobe IO](https://docs.campaign.adobe.com/doc/standard/en/adobeio.html).
