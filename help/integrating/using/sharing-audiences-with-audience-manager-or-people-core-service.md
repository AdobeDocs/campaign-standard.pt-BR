---
title: Compartilhar públicos-alvo com o Audience Manager ou o serviço principal de pessoas
seo-title: Compartilhar públicos-alvo com o Audience Manager ou o serviço principal de pessoas
description: Compartilhar públicos-alvo com o Audience Manager ou o serviço principal de pessoas
seo-description: Saiba como importar ou exportar seu público-alvo dentro das diferentes soluções da Adobe Experience Cloud.
page-status-flag: nunca ativado
uuid: a 3701 e 72-5846-4241-afee-d 713 b 499 a 27 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: 77 af 0772-52 b 5-46 bc-a 964-675 b 45965524
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Sharing audiences with Audience Manager or People core service{#sharing-audiences-with-audience-manager-or-people-core-service}

## Importing an audience {#importing-an-audience}

A integração de serviço principal das pessoas permite importar diretamente um público-alvo para o Adobe Campaign por meio de um fluxo de trabalho técnico para aprimorar o banco de dados. For more information on audience sharing in People core service, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

Importing audiences/segments from People core service in Adobe Campaign can be carried out from the **[!UICONTROL Audiences]** menu only by users connected via IMS (authentication via Adobe ID).

1. Go to the **[!UICONTROL Audiences]** menu.
1. In the action bar, select **[!UICONTROL Create]** to be taken to the screen to create an audience.
1. Especifique o rótulo do novo público.
1. Set the audience **[!UICONTROL Type]** to **[!UICONTROL Experience Cloud]** to indicate that the audience being created is an audience that was imported from People core service.
1. From the **[!UICONTROL Name of the shared audience]** field, select the audience to import. Somente os segmentos podem ser importados. Dados granulares, incluindo pares de valores chave, características e regras não são suportados.

   ![](assets/aam_import_audience.png)

1. Select the corresponding **[!UICONTROL Shared Data Source]**.

   If the selected data source is configured to use an encryption algorithm, an additional option offers you the possibility to **[!UICONTROL Force reconciliation with a profile]**. Check this option if the **[!UICONTROL Channel]** field of the data source is set to Email or Mobile (SMS) and if you want to leverage profile data.

   If you do not select the **[!UICONTROL Force reconciliation with a profile]** and if **[!UICONTROL Channel]** is set in AMC Data source to Email or Mobile (SMS) then all the encrypted declared IDs are decrypted. An audience of type **File** with a list of all the email addresses/mobile phone numbers is created/updated. Dessa forma, nenhum endereço de email/telefone é perdido ao importar um público-alvo compartilhado por meio dessa integração, mesmo que esse perfil não exista no Campaign. Observe que esse tipo de público-alvo não pode ser usado diretamente, pois precisa ser conciliado manualmente usando fluxos de trabalho.

1. Confirme para criar o público-alvo.

   O público-alvo é então importado por um fluxo de trabalho técnico. É composto por registros de onde a ID (' ID do visitante'ou'ID declarada ') foi capaz de se reconciliar com a dimensão do perfil. As IDs dos segmentos de serviços principais de Pessoas não reconhecidas pelo Adobe Campaign não são importadas.

Seu público-alvo agora é importado em seu banco de dados do Adobe Campaign. O processo de importação leva 24-36 horas para sincronizar, quando os segmentos são importados diretamente do serviço principal Pessoas ou do Audience Manager. Após esse período, você poderá encontrar e usar seu novo público-alvo no Adobe Campaign.

>[!NOTE]
>
>Se você estiver importando públicos-alvo do Adobe Analytics para o Adobe Campaign, esses públicos precisam primeiro ser compartilhados no Serviço principal de Pessoas ou no Audience Manager. Esse processo leva 12a 24 horas, que deve ser adicionado à sincronização de 24a 36 horas com a Campanha. Nesse caso específico, o período de compartilhamento de público-alvo pode ser de até 60 horas. For more information on Adobe Analytics audience sharing in People Core service and Audience manager, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

## Exporting an audience {#exporting-an-audience}

An audience can be exported from Adobe Campaign to Audience Manager or People core service using a workflow and the **[!UICONTROL Save audience]** activity.

Ele pode ser realizado em um novo fluxo de trabalho e apenas por usuários conectados via IMS (autenticação pela Adobe ID).

1. Crie um novo fluxo de trabalho a partir de um programa, uma campanha ou uma lista de atividades de marketing.
1. Usando as diferentes atividades disponíveis, direcione um conjunto de perfis.
1. After the targeting, drag and drop a **[!UICONTROL Save audience]** activity into the workflow, then open it.
1. Select **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. Specify the audience using the **[!UICONTROL Shared audience]** field. Na janela aberta, você tem a opção de selecionar um público existente ou criar um novo público-alvo:

   * Se você selecionar um público-alvo existente, apenas os novos registros serão adicionados ao público-alvo.
   * To export your profile list into a new audience, complete the **[!UICONTROL Segment name]** field then click **[!UICONTROL Create]** before selecting the newly created audience.
   ![](assets/aam_save_audience_segment_picker.png)

   Para ser conciliado e trocado, os registros devem ter uma Adobe Experience Cloud ID (' ID do visitante'ou'ID declarada '). Os registros não sincronizados são ignorados ao importar e exportar públicos-alvo.

1. Para concluir, clique na marca de seleção localizada na parte superior direita da tela.
1. Select the corresponding **[!UICONTROL Shared Data Source]**.
1. If you like, check the **[!UICONTROL Generate an outbound transition]** box to use the profiles that were exported. Somente os perfis que podem ser conciliados são exportados.
1. Confirme a configuração da atividade e salve seu fluxo de trabalho.
1. Inicie o fluxo de trabalho para exportar seu público. A sincronização entre o Adobe Campaign e o serviço principal de pessoas pode levar várias horas

A sincronização entre o Adobe Campaign e o serviço principal de pessoas leva 24a 36 horas. Após esse período, você poderá encontrar o novo público-alvo no serviço principal das Pessoas e reutilizá-lo em outras soluções da Adobe Experience Cloud. For more information on using an Adobe Campaign shared audience in Adobe People core service, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_audience_create.html).

**Tópicos relacionados:**

* [Fluxos de trabalho](../../automating/using/workflow-data-and-processes.md)
* [Públicos-alvo](../../audiences/using/about-audiences.md)

