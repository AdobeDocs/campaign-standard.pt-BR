---
title: Compartilhamento de públicos-alvo com o Audience Manager ou o serviço principal do People
description: Saiba como importar ou exportar seu público-alvo nas diferentes soluções da Adobe Experience Cloud.
page-status-flag: nunca ativado
uuid: a3701e72-5846-4241-afee-d713b499a27a
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: integrando
content-type: referência
topic-tags: trabalhar com campanha e público-gerente-ou-público-principal-serviço
discoiquuid: 77af0772-52b5-46bc-a964-675b45965524
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Compartilhamento de públicos-alvo com o Audience Manager ou o serviço principal do People{#sharing-audiences-with-audience-manager-or-people-core-service}

## Importação de um público {#importing-an-audience}

A integração do serviço principal de pessoas permite importar diretamente um público-alvo para o Adobe Campaign por meio de um fluxo de trabalho técnico para aprimorar seu banco de dados. For more information on audience sharing in People core service, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

A importação de públicos-alvo/segmentos do serviço principal de Pessoas no Adobe Campaign pode ser realizada a partir do **[!UICONTROL Audiences]** menu somente por usuários conectados via IMS (autenticação via Adobe ID).

1. Vá para o **[!UICONTROL Audiences]** menu.
1. Na barra de ações, selecione **[!UICONTROL Create]** a ser levado para a tela para criar um público-alvo.
1. Especifique o rótulo do novo público-alvo.
1. Defina o público-alvo **[!UICONTROL Type]** para indicar **[!UICONTROL Experience Cloud]** que o público-alvo que está sendo criado é um público-alvo importado do serviço principal de Pessoas.
1. No **[!UICONTROL Name of the shared audience]** campo, selecione o público-alvo a ser importado. Apenas segmentos podem ser importados. Dados granulares, incluindo pares chave-valor, características e regras não são compatíveis.

   ![](assets/aam_import_audience.png)

1. Selecione o correspondente **[!UICONTROL Shared Data Source]**.

   Se a fonte de dados selecionada estiver configurada para usar um algoritmo de criptografia, uma opção adicional oferecerá a você a possibilidade de **[!UICONTROL Force reconciliation with a profile]**. Marque essa opção se o **[!UICONTROL Channel]** campo da fonte de dados estiver definido como Email ou Móvel (SMS) e se você quiser aproveitar os dados do perfil.

   Se você não selecionar o e se **[!UICONTROL Force reconciliation with a profile]** **[!UICONTROL Channel]** estiver definido na fonte de dados AMC como Email ou Móvel (SMS), todas as IDs declaradas criptografadas serão descriptografadas. Um público-alvo do tipo **Arquivo** com uma lista de todos os endereços de email/números de telefone móvel é criado/atualizado. Dessa forma, nenhum endereço de email/número de telefone móvel é perdido ao importar um público compartilhado por meio dessa integração, mesmo que esse perfil não exista no Campaign. Observe que esse tipo de público-alvo não pode ser usado diretamente, pois eles precisam ser reconciliados manualmente usando fluxos de trabalho.

1. Confirme para criar o público-alvo.

   O público-alvo é importado por meio de um fluxo de trabalho técnico. Ele é composto de registros dos quais a ID ("ID do visitante" ou "ID declarada") pode ser reconciliada com a dimensão do perfil. Os IDs dos segmentos de Serviço principal de pessoas que não são reconhecidos pelo Adobe Campaign não são importados.

Seu público-alvo agora é importado no banco de dados do Adobe Campaign. O processo de importação leva de 24 a 36 horas para sincronizar, quando os segmentos são importados diretamente do Serviço principal de pessoas ou do Audience Manager. Após esse período, é possível encontrar e usar seu novo público no Adobe Campaign.

>[!NOTE]
>
>Se você estiver importando públicos-alvo do Adobe Analytics para o Adobe Campaign, esses públicos-alvo devem primeiro ser compartilhados no People Core Service ou no Audience Manager. Esse processo leva de 12 a 24 horas, e deve ser adicionado ao tempo de sincronização de 24 a 36 horas com o Campaign. Nesse caso específico, o período de compartilhamento de público pode durar até 60 horas. Para obter mais informações sobre o compartilhamento de público do Adobe Analytics no Serviço Principal de Pessoas e no Audience Manager, consulte esta [documentação](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

## Exportação de um público {#exporting-an-audience}

Um público-alvo pode ser exportado do Adobe Campaign para o Audience Manager ou o serviço principal de Pessoas usando um fluxo de trabalho e a **[!UICONTROL Save audience]** atividade.

Ele pode ser executado em um novo fluxo de trabalho e somente por usuários conectados via IMS (autenticação via Adobe ID).

1. Crie um novo fluxo de trabalho a partir de um programa, campanha ou lista de atividades de marketing.
1. Usando as diferentes atividades disponíveis, direcione um conjunto de perfis.
1. Depois da definição de metas, arraste e solte uma **[!UICONTROL Save audience]** atividade no fluxo de trabalho e, em seguida, abra-a.
1. Select **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. Especifique o público-alvo usando o **[!UICONTROL Shared audience]** campo. Na janela que é aberta, você tem a opção de selecionar um público existente ou criar um novo público-alvo:

   * Se você selecionar um público existente, somente os novos registros serão adicionados ao público.
   * Para exportar sua lista de perfis para um novo público-alvo, preencha o **[!UICONTROL Segment name]** campo e clique **[!UICONTROL Create]** antes de selecionar o público-alvo recém-criado.
   ![](assets/aam_save_audience_segment_picker.png)

   Para ser reconciliado e trocado, os registros devem ter uma Adobe Experience Cloud ID ("ID do visitante" ou "ID declarada"). Os registros não reconciliados são ignorados ao importar e exportar públicos.

1. Para finalizar, clique na marca de seleção localizada na parte superior direita da tela.
1. Selecione o correspondente **[!UICONTROL Shared Data Source]**.
1. Se desejar, marque a **[!UICONTROL Generate an outbound transition]** caixa para usar os perfis que foram exportados. Somente os perfis que podem ser reconciliados são exportados.
1. Confirme a configuração da atividade e salve seu fluxo de trabalho.
1. Inicie seu fluxo de trabalho para exportar seu público-alvo. A sincronização entre o Adobe Campaign e o serviço principal de Pessoas pode levar várias horas

A sincronização entre o Adobe Campaign e o Serviço principal de pessoas leva de 24 a 36 horas. Após esse período, é possível encontrar seu novo público no Serviço principal de pessoas e reutilizá-lo em outras soluções da Adobe Experience Cloud. Para obter mais informações sobre como usar um público compartilhado do Adobe Campaign no Serviço principal de pessoas da Adobe, consulte esta [documentação](https://marketing.adobe.com/resources/help/en_US/mcloud/t_audience_create.html).

**Tópicos relacionados:**

* [Fluxos de trabalho](../../automating/using/workflow-data-and-processes.md)
* [Públicos](../../audiences/using/about-audiences.md)

