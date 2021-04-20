---
solution: Campaign Standard
product: campaign
title: Atualização da estrutura do banco de dados
description: Descubra como atualizar o banco de dados do Adobe Campaign.
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
context-tags: deploy,main;eventCusResource,overview
feature: Data Model
role: Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 98%

---


# Atualização da estrutura do banco de dados{#updating-the-database-structure}

Para que as modificações no modelo de dados sejam eficazes, e para que elas possam ser usadas, a estrutura do banco de dados precisa ser atualizada.

>[!NOTE]
>
>Os recursos personalizados são atualizados automaticamente durante atualizações automáticas executadas pela Adobe.

## Publicação de um recurso personalizado {#publishing-a-custom-resource}

Para aplicar as alterações feitas nos recursos, é necessário executar uma atualização do banco de dados.

>[!NOTE]
>
>Se um campo de um recurso personalizado usado em um evento for modificado ou excluído, a publicação do evento correspondente será automaticamente cancelada. Consulte [Cancelar a publicação de um evento transacional](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Development]** e **[!UICONTROL Publishing]** pelo logotipo do Adobe Campaign.
1. Por padrão, a opção **[!UICONTROL Determine modifications since the last publication]** está marcada, o que significa que somente as alterações feitas desde a última atualização serão aplicadas.

   >[!NOTE]
   >
   >O **[!UICONTROL Repair database structure]** restabelecerá uma configuração correta se a publicação falhar antes de concluir. Qualquer modificação que tenha sido feita diretamente no banco de dados e que não use recursos personalizados será excluída.

   ![](assets/schema_extension_12.png)

1. Clique no botão **[!UICONTROL Prepare publication]** para iniciar a análise. Observe que as grandes atualizações de tabela devem ser feitas quando a instância não estiver intensivamente ocupada por fluxos de trabalho.

   Para saber mais sobre a ação a ser executada na API de Perfis e serviços, consulte [Publicação de um recurso com extensão de API](#publishing-a-resource-with-api-extension).

   ![](assets/schema_extension_13.png)

1. Depois que a publicação for feita, clique no botão **[!UICONTROL Publish]** para aplicar as novas configurações.
1. Depois de publicado, o painel de **[!UICONTROL Summary]** de cada recurso indica que o status está agora **[!UICONTROL Published]** e especifica a data da última publicação.

   >[!NOTE]
   >
   >Se você fizer novas alterações em um recurso, deverá repetir essa operação para que as alterações sejam aplicadas.

   Se os recursos tiverem o status de **[!UICONTROL Pending re-draft]** antes da publicação, será exibida uma mensagem adicional convidando você a verificar as ações, pois a publicação resultará em alterações definitivas (exclusão de colunas, tabelas...). Para ajudar você a fazer essa última alteração, uma guia de **[!UICONTROL SQL Script]** está disponível. Ele fornece o comando SQL que será executado durante a publicação.

   ![](assets/schema_extension_scriptsql.png)

   >[!NOTE]
   >
   >Você pode interromper o processo de recriação de rascunho clicando no botão **[!UICONTROL Cancel re-draft]**. Essa ação reverterá o status do recurso para o status original.

1. Se a publicação falhar, você pode voltar para a publicação anterior clicando em **[!UICONTROL Back to latest successful publication]**.

   Observe que, se você deixar a publicação com um status de falha, uma janela pop-up será aberta assim que você fizer logon em sua instância para lembrá-lo de corrigir essa publicação. A instância não será atualizada com novas versões de produtos até que a publicação seja corrigida.

   ![](assets/schema_extension_31.png)

## Publicação de recurso com extensão de API {#publishing-a-resource-with-api-extension}

Você pode criar a API de Perfis e Serviços nos seguintes casos:

* Ao estender os recursos personalizados **[!UICONTROL Profiles]** ou **[!UICONTROL Services]**, você pode executar uma atualização da API de Perfis e Serviços para integrar os campos declarados na extensão de recursos personalizados.
* Ao definir um recurso personalizado e criar um link entre os recursos **[!UICONTROL Profiles]** ou **[!UICONTROL Services]** e o recurso personalizado, você pode fazer uma atualização para incluir o novo recurso na API.

Você pode selecionar essa opção na tela da publicação.

* Se a API ainda não tiver sido publicada (ou seja, se você nunca tiver estendido o recurso ou se ainda não tiver verificado essa opção para esse recurso ou outro recurso), você terá a opção de criá-la ou não.

   ![](assets/create-profile-and-services-api.png)

* Se a API já tiver sido publicada (ou seja, se você já tiver estendido o recurso e verificado essa opção uma vez), a atualização da API será forçada.

   Na verdade, uma vez criada, a API é atualizada automaticamente cada vez que você a publica novamente. Isso evita quebrar o perfil ou o recurso de serviço dessa API e prejudicar a instância.

Observe que, por padrão, o recurso personalizado é integrado, mas, para um comportamento específico, se você não quiser publicar esse recurso, poderá selecionar a opção **[!UICONTROL Hide this resource from APIs]**, disponível nas **[!UICONTROL Resource Properties]**.

![](assets/removefromextoption.png)

Após a etapa **[!UICONTROL Prepare Publication]**, o Adobe Campaign exibe o delta entre a versão atual da API e a versão futura, após a publicação na guia **[!UICONTROL Profiles & Services API Preview]**. Se você estender a API pela primeira vez, o delta compara a definição de recurso personalizado pronta para uso com a sua extensão.

As informações exibidas na guia são divididas em três seções: elementos adicionados, excluídos e modificados.

![](assets/extendpandsapi_diff.png)

A análise do delta é uma etapa obrigatória, já que a etapa de publicação modificará o comportamento da API e provavelmente afetará o desenvolvimento ao redor em um efeito dominó.

>[!NOTE]
>
>Essa publicação atualiza a API **[!UICONTROL profilesAndServicesExt]**. A API **[!UICONTROL profilesAndServices]** não é atualizada.

Para obter mais informações sobre a API do Adobe Campaign, consulte a documentação dedicada do Adobe Campaign sobre [Adobe IO](https://docs.campaign.adobe.com/doc/standard/en/adobeio.html).
