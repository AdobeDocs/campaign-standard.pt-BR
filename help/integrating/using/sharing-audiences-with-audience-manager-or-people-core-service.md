---
title: Compartilhamento de públicos-alvo com o Audience Manager ou o serviço principal do People
description: Saiba como importar ou exportar sua audiência nas diferentes soluções da Adobe Experience Cloud.
page-status-flag: never-activated
uuid: a3701e72-5846-4241-afee-d713b499a27a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: 77af0772-52b5-46bc-a964-675b45965524
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 26%

---


# Compartilhamento de públicos-alvo com o Audience Manager ou o serviço principal do People{#sharing-audiences-with-audience-manager-or-people-core-service}

## Importação de um público {#importing-an-audience}

A integração do serviço principal de pessoas permite importar diretamente uma audiência por meio de um fluxo de trabalho técnico para enriquecer seu banco de dados. For more information on audience sharing in People core service, refer to this [documentation](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-publish.html).

A importação de audiências/segmentos do serviço principal de Pessoas no Adobe Campaign pode ser realizada a partir do **[!UICONTROL Audiences]** menu somente por usuários conectados via IMS (autenticação via Adobe ID).

1. Go to the **[!UICONTROL Audiences]** menu.
1. Na barra de ações, selecione **[!UICONTROL Create]** a ser levado para a tela para criar uma audiência.
1. Especifique o rótulo da nova audiência.
1. Configure a audiência **[!UICONTROL Type]** para **[!UICONTROL Experience Cloud]** indicar que a audiência que está sendo criada é uma audiência importada do serviço principal de Pessoas.
1. No **[!UICONTROL Name of the shared audience]** campo, selecione a audiência a ser importada. Apenas segmentos podem ser importados. Dados granulares, incluindo pares chave-valor, características e regras não são compatíveis.

   ![](assets/aam_import_audience.png)

1. Selecione o correspondente **[!UICONTROL Shared Data Source]**.

   Se a fonte de dados selecionada estiver configurada para usar um algoritmo de criptografia, uma opção adicional oferta a possibilidade de **[!UICONTROL Force reconciliation with a profile]**. Marque essa opção se o **[!UICONTROL Channel]** campo da fonte de dados estiver definido como Email ou Móvel (SMS) e se você quiser aproveitar os dados do perfil.

   Se você não selecionar o e se **[!UICONTROL Force reconciliation with a profile]** **[!UICONTROL Channel]** estiver definido na fonte de dados AMC como Email ou Móvel (SMS), todas as IDs declaradas criptografadas serão descriptografadas. Uma audiência do tipo **Arquivo** com uma lista de todos os endereços de email/números de telefone móvel é criada/atualizada. Dessa forma, nenhum endereço de email/número de telefone móvel é perdido ao importar uma audiência compartilhada por meio dessa integração, mesmo que esse perfil não exista na Campanha. Observe que esse tipo de audiência não pode ser usado diretamente, pois precisa ser reconciliado manualmente usando workflows.

1. Confirme para criar a audiência.

   A audiência é então importada por meio de um fluxo de trabalho técnico. Ele é composto de registros dos quais a ID (&#39;ID do Visitante&#39; ou &#39;ID declarada&#39;) pode ser reconciliada com a dimensão do perfil. Os IDs dos segmentos de Serviço principal de pessoas que não são reconhecidos pelo Adobe Campaign não são importados.

Sua audiência agora é importada no banco de dados do Adobe Campaign. O processo de importação leva de 24 a 36 horas para sincronizar, quando os segmentos são importados diretamente do Serviço principal de pessoas ou do Audience Manager. Após esse período, é possível encontrar e usar seu novo público no Adobe Campaign.

>[!NOTE]
>
>Se você estiver importando o audiência do Adobe Analytics para o Adobe Campaign, essas audiências devem ser compartilhadas primeiro no People Core Service ou no Audience Manager. Esse processo leva de 12 a 24 horas, e deve ser adicionado ao tempo de sincronização de 24 a 36 horas com o Campaign. Nesse caso específico, o período de compartilhamento de público pode durar até 60 horas. Para obter mais informações sobre o compartilhamento de público do Adobe Analytics no Serviço Principal de Pessoas e no Audience Manager, consulte esta [documentação](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-publish.html).

## Exportação de um público {#exporting-an-audience}

Uma audiência pode ser exportada de Adobe Campaign para Audience Manager ou serviço principal de Pessoas usando um fluxo de trabalho e a **[!UICONTROL Save audience]** atividade.

Pode ser executado em um novo fluxo de trabalho e somente por usuários conectados via IMS (autenticação via Adobe ID).

1. Crie um novo fluxo de trabalho a partir de um programa, uma campanha ou a lista de atividades de marketing.
1. Usando as diferentes atividades disponíveis, público alvo um conjunto de perfis.
1. Depois da definição de metas, arraste e solte uma **[!UICONTROL Save audience]** atividade no fluxo de trabalho e, em seguida, abra-a.
1. Selecione **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. Especifique a audiência usando o **[!UICONTROL Shared audience]** campo. Na janela que é aberta, você tem a opção de selecionar uma audiência existente ou criar uma nova audiência:

   * Se você selecionar um público existente, somente os novos registros serão adicionados ao público.
   * To export your profile list into a new audience, complete the **[!UICONTROL Segment name]** field then click **[!UICONTROL Create]** before selecting the newly created audience.
   ![](assets/aam_save_audience_segment_picker.png)

   Para ser reconciliado e trocado, os registros devem ter uma Adobe Experience Cloud ID (&#39;ID do Visitante&#39; ou &#39;ID declarada&#39;). Os registros não reconciliados são ignorados ao importar e exportar audiências.

1. Para finalizar, clique na marca de seleção localizada na parte superior direita da tela.
1. Selecione o correspondente **[!UICONTROL Shared Data Source]**.
1. Se desejar, marque a **[!UICONTROL Generate an outbound transition]** caixa para usar os perfis que foram exportados. Somente os perfis que podem ser reconciliados são exportados.
1. Confirme a configuração do atividade e salve seu fluxo de trabalho.
1. Start seu fluxo de trabalho para exportar sua audiência. A sincronização entre o Adobe Campaign e o serviço principal de Pessoas pode levar várias horas

A sincronização entre o Adobe Campaign e o Serviço principal de pessoas leva de 24 a 36 horas. Após esse período, é possível encontrar seu novo público no Serviço principal de pessoas e reutilizá-lo em outras soluções da Adobe Experience Cloud. Para obter mais informações sobre como usar um público compartilhado do Adobe Campaign no Serviço principal de pessoas da Adobe, consulte esta [documentação](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-audience-create.html).

**Tópicos relacionados:**

* [Workflows](../../automating/using/get-started-workflows.md)
* [Públicos](../../audiences/using/about-audiences.md)

