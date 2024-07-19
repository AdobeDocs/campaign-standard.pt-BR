---
title: Compartilhamento de públicos com o Audience Manager ou o Serviço principal de pessoas
description: Saiba como importar ou exportar seu público-alvo nas diferentes soluções da Adobe Experience Cloud.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
exl-id: b0d063de-863c-42e7-98dd-c4c86da3281e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 26%

---

# Compartilhamento de públicos com o Audience Manager ou o Serviço principal de pessoas{#sharing-audiences-with-audience-manager-or-people-core-service}

## Importação de um público-alvo {#importing-an-audience}

A integração do serviço principal Pessoas permite importar diretamente um público para o Adobe Campaign por meio de um fluxo de trabalho técnico para enriquecer seu banco de dados. Para obter mais informações sobre compartilhamento de público no serviço principal People, consulte esta [documentação](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=pt-BR).

A importação de públicos/segmentos do serviço principal Pessoas na Adobe Campaign pode ser realizada pelo menu **[!UICONTROL Audiences]** somente por usuários conectados pelo IMS (autenticação via Adobe ID).

1. Vá para o menu **[!UICONTROL Audiences]**.
1. Na barra de ações, selecione **[!UICONTROL Create]** a ser levado à tela para criar um público-alvo.
1. Especifique o rótulo do novo público-alvo.
1. Defina o público-alvo **[!UICONTROL Type]** como **[!UICONTROL Experience Cloud]** para indicar que o público-alvo que está sendo criado é um público importado do serviço principal Pessoas.
1. No campo **[!UICONTROL Name of the shared audience]**, selecione o público-alvo a ser importado. Apenas segmentos podem ser importados. Dados granulares, incluindo pares chave-valor, traços e regras não são compatíveis.

   ![](assets/aam_import_audience.png)

1. Selecione o **[!UICONTROL Shared Data Source]** correspondente.

   Se a fonte de dados selecionada estiver configurada para usar um algoritmo de criptografia, uma opção adicional oferecerá a possibilidade de **[!UICONTROL Force reconciliation with a profile]**. Marque esta opção se o campo **[!UICONTROL Channel]** da fonte de dados estiver definido como Email ou Mobile (SMS) e se você deseja aproveitar os dados do perfil.

   Se você não selecionar o **[!UICONTROL Force reconciliation with a profile]** e se **[!UICONTROL Channel]** estiver definido na fonte de dados da AMC como Email ou Mobile (SMS), todas as IDs declaradas criptografadas serão descriptografadas. Um público-alvo do tipo **Arquivo** com uma lista de todos os endereços de email/números de celular foi criado/atualizado. Dessa forma, nenhum endereço de email/número de celular é perdido durante a importação de um público-alvo compartilhado por meio dessa integração, mesmo que esse perfil não exista no Campaign. Observe que esse tipo de público-alvo não pode ser usado diretamente, pois precisa ser reconciliado manualmente usando workflows.

1. Confirme para criar o público-alvo.

   O público é importado por meio de um workflow técnico. É composto de registros dos quais a ID (&quot;ID do visitante&quot; ou &quot;ID declarada&quot;) pôde ser reconciliada com a dimensão de perfil. Os IDs dos segmentos de Serviço principal de pessoas que não são reconhecidos pelo Adobe Campaign não são importados.

Seu público-alvo foi importado para o banco de dados do Adobe Campaign. O processo de importação leva de 24 a 36 horas para sincronizar, quando os segmentos são importados diretamente do Serviço principal de pessoas ou do Audience Manager. Após esse período, é possível encontrar e usar seu novo público no Adobe Campaign.

>[!NOTE]
>
>Se você estiver importando públicos do Adobe Analytics para o Adobe Campaign, esses públicos precisam primeiro ser compartilhados no Serviço Principal de Pessoas ou no Audience Manager. Esse processo leva de 12 a 24 horas, e deve ser adicionado ao tempo de sincronização de 24 a 36 horas com o Campaign. Nesse caso específico, o período de compartilhamento de público pode durar até 60 horas. Para obter mais informações sobre o compartilhamento de público do Adobe Analytics no Serviço Principal de Pessoas e no Audience Manager, consulte esta [documentação](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=pt-BR).

## Exportação de um público-alvo {#exporting-an-audience}

Um público pode ser exportado do Adobe Campaign para o Audience Manager ou do Serviço principal de pessoas usando um fluxo de trabalho e a atividade **[!UICONTROL Save audience]**.

Ele pode ser executado em um novo fluxo de trabalho e somente por usuários conectados pelo IMS (autenticação via Adobe ID).

1. Crie um novo workflow a partir de um programa, de uma campanha ou da lista de atividades de marketing.
1. Usando as diferentes atividades disponíveis, direcione a um conjunto de perfis.
1. Após o direcionamento, arraste e solte uma atividade **[!UICONTROL Save audience]** no fluxo de trabalho e depois a abra.
1. Selecione **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. Especifique o público usando o campo **[!UICONTROL Shared audience]**. Na janela que abre, você tem a opção de selecionar um público existente ou criar um novo público:

   * Se você selecionar um público existente, somente os novos registros serão adicionados ao público.
   * Para exportar sua lista de perfis para um novo público, preencha o campo **[!UICONTROL Segment name]** e depois clique em **[!UICONTROL Create]** antes de selecionar o público recém-criado.

   ![](assets/aam_save_audience_segment_picker.png)

   Para serem reconciliados e trocados, os registros devem ter uma ID do Adobe Experience Cloud (&quot;ID do visitante&quot; ou &quot;ID declarada&quot;). Os registros não reconciliados são ignorados ao importar e exportar públicos.

1. Para concluir, clique na marca de seleção localizada na parte superior direita da tela.
1. Selecione o **[!UICONTROL Shared Data Source]** correspondente.
1. Se desejar, marque a caixa **[!UICONTROL Generate an outbound transition]** para usar os perfis que foram exportados. Somente os perfis que podem ser reconciliados são exportados.
1. Confirme a configuração da atividade e salve o workflow.
1. Inicie o fluxo de trabalho para exportar o público. A sincronização entre o Adobe Campaign e o serviço principal Pessoas pode levar várias horas

A sincronização entre o Adobe Campaign e o Serviço principal de pessoas leva de 24 a 36 horas. Após esse período, é possível encontrar seu novo público no Serviço principal de pessoas e reutilizá-lo em outras soluções da Adobe Experience Cloud. Para obter mais informações sobre como usar um público compartilhado do Adobe Campaign no Serviço principal de pessoas da Adobe, consulte esta [documentação](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/t-audience-create.html?lang=pt-BR).

**Tópicos relacionados:**

* [Fluxos de trabalho](../../automating/using/get-started-workflows.md)
* [Públicos-alvo](../../audiences/using/about-audiences.md)
