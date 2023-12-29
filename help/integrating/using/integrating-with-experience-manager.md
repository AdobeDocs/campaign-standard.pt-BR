---
title: Sobre a integração do Campaign com o Experience Manager
description: Com a integração do Adobe Experience Manager, é possível criar conteúdo diretamente no AEM e usá-lo posteriormente no Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: ff94f69b-3036-4103-a841-6b85feb0eb7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 1%

---

# Sobre a integração do Campaign com o Experience Manager{#integrating-with-experience-manager}

Essa integração entre o Adobe Campaign Standard e o Adobe Experience Manager permite usar o conteúdo criado no Adobe Experience Manager em seus emails do Adobe Campaign.

Portanto, você pode aproveitar ao máximo as funcionalidades de edição de conteúdo do Adobe Experience Manager, bem como os recursos de entrega e gestão de dados do Adobe Campaign. Observe que você não pode executar testes A/B para o conteúdo importado do Adobe Experience Manager.

O Adobe Campaign Standard é compatível com o Adobe Experience Manager 6.1, 6.2, 6.3, 6.4 e 6.5. As seções a seguir apresentam uma visão geral das ações que podem ser executadas. Para obter mais informações, consulte as seções dedicadas a [configuração](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html) e a variável [use](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) da integração.

>[!NOTE]
>
> Os modelos do Adobe Campaign Standard não estão mais disponíveis com o Adobe Experience Manager 6.5.

## Dicas sobre como usar a integração Campaign-Experience Manager {#tips-aem}

* **Saber qual modelo usar com a integração**

  Como os modelos de email são editáveis no Adobe Experience Manager, pode parecer mais fácil editar qualquer modelo no Adobe Experience Manager. Mas alguns templates não são facilmente acomodados. Modelos individualizados específicos para um cliente não são recomendados para essa integração e devem ser editados diretamente no Adobe Campaign Standard.

  Para obter mais informações sobre templates, consulte esta [página](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html).

* **Verifique se o Externalizador foi configurado durante a implementação**

  Configurar o Externalizador ao implementar o Experience Manager para Adobe Campaign Standard torna possível transformar um caminho de recurso em um URL. Isso permite tornar as imagens visíveis na página. Se o Externalizador não estiver configurado corretamente, seus emails conterão imagens corrompidas.

  Para saber como configurar o Externalizador, consulte este [página](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/externalizer.html).

* **Organize seus modelos de email para evitar o uso indevido.**

  Manter os modelos organizados garante que os modelos apropriados estejam nas pastas apropriadas e que não sejam escolhidos os errados por engano. Durante a implementação, caminhos devem ser criados para salvar modelos nos lugares certos.

  Para obter mais informações sobre templates, consulte esta [página](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html#template-availability).

* **Comece rapidamente com componentes prontos para uso.**

  Os componentes prontos para uso no Adobe Experience Manager para Adobe Campaign Standard podem ajudar você a começar rapidamente se seus modelos não forem complexos.
Há sete componentes prontos para uso no Experience Manager que você pode começar a usar:

   * Cabeçalho
   * Imagem
   * Link
   * Modelo de imagem Scene7
   * Referência direcionada
   * Texto e imagem
   * Texto e personalização

* **O HTML para emails é diferente do HTML para web**

  É importante entender que você não pode usar os mesmos componentes usados no conteúdo da Web para modelos de email. O uso de componentes prontos para uso garante que seus componentes sejam compatíveis com email.

* **Desvincule o conteúdo dos modelos e reutilize-o várias vezes.**

  Ao configurar seus emails no Campaign Standard e selecionar um template de Experience Manager, você só pode escolher um que ainda não tenha sido vinculado a outra campanha. Caso contrário, se você alterar o conteúdo de uma campanha e atualizar no Adobe Experience Manager, poderá afetar involuntariamente o conteúdo da outra campanha.
Para evitar isso, após usar o template, você pode desvinculá-lo para usá-lo novamente. Basta selecionar o modelo e clicar em **[!UICONTROL Delete the link with Adobe Experience Manager content]**.

* **Use o Adobe Experience Manager para criar variações de emails para o Adobe Campaign Standard.**

  Essa integração permite transformar facilmente um email em várias versões com a segmentação.
Para saber como configurar a segmentação no Adobe Experience Manager e como criar emails com conteúdo direcionado, consulte este [página](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem).

* **Para uma sincronização bem-sucedida, o nome do segmento no Experience Manager deve corresponder ao nome do segmento no Campaign exato.**
