---
title: Sobre a integração do Campaign-Experience Manager
description: Com a integração do Adobe Experience Manager, você pode criar conteúdo diretamente no AEM e usá-lo posteriormente no Adobe Campaign.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 37e86c6143c52841e69d610fa9db35dff70a3587

---


# Sobre a integração do Campaign-Experience Manager{#integrating-with-experience-manager}

Essa integração entre o Adobe Campaign Standard e o Adobe Experience Manager permite que você use conteúdo criado no Adobe Experience Manager em emails de Adobe Campaign.

Portanto, você pode aproveitar ao máximo as funcionalidades de edição de conteúdo do Adobe Experience Manager, bem como os recursos de delivery e gestão de dados do Adobe Campaign. Observe que não é possível executar testes A/B para conteúdos importados do Adobe Experience Manager.

O Adobe Campaign Standard é compatível com o Adobe Experience Manager 6.1, 6.2, 6.3, 6.4 e 6.5. As seções a seguir apresentam uma visão geral das ações que você pode executar. Para obter mais informações, consulte as seções dedicadas à [configuração](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html) e ao [uso](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) da integração.

>[!NOTE]
>
> Os modelos do Adobe Campaign Standard não estão mais disponíveis com o Adobe Experience Manager 6.5.

## Dicas sobre como usar a integração do Campaign-Experience Manager {#tips-aem}

* **Saiba qual modelo usar com a integração**

   Como os modelos de e-mail podem ser editados no Adobe Experience Manager, pode parecer mais fácil editar qualquer modelo no Adobe Experience Manager. Mas certos modelos não são facilmente acomodados. Modelos individuais específicos de um cliente não são recomendados para essa integração e devem ser editados diretamente no Adobe Campaign Standard.

   For more information on templates, refer to this [page](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html).

* **Verifique se o Externalizador foi configurado durante a implementação**

   A configuração do Externalizador ao implementar o Experience Manager for Adobe Campaign Standard permite transformar um caminho de recurso em um URL. Isso permite tornar suas imagens visíveis na página. Se o Externalizador não estiver configurado corretamente, seus emails conterão imagens quebradas.

   Para saber como configurar o Externalizador, consulte esta [página](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/externalizer.html).

* **Organize seus modelos de e-mail para evitar o uso indevido.**

   Manter os modelos organizados garante que os modelos apropriados estejam nas pastas apropriadas e que não escolha os errados por engano. Durante a implementação, os caminhos devem ser criados para salvar modelos nos locais certos.

   For more information on templates, refer to this [page](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html#template-availability).

* **Comece rapidamente com componentes prontos para uso.**

   Os componentes prontos para uso no Adobe Experience Manager for Adobe Campaign Standard podem ajudá-lo a começar rapidamente se seus modelos não forem complexos.
Há sete componentes prontos para uso no Experience Manager que podem ser start usando:

   * Cabeçalho
   * Imagem
   * Link
   * Modelo de imagem Scene7
   * Referência direcionada
   * Texto e imagem
   * Texto e personalização

* **O HTML para e-mails é diferente do HTML para a Web**

   É importante entender que você não pode usar os mesmos componentes usados no conteúdo da Web para modelos de e-mail. O uso de componentes prontos para uso garante que seus componentes sejam compatíveis com email.

* **Desvincule o conteúdo dos modelos e reutilize-os várias vezes.**

   Ao configurar seus emails no Campaign Standard e selecionar um modelo do Experience Manager, você só pode escolher um que ainda não tenha sido vinculado a outra campanha. Caso contrário, se você alterar o conteúdo no Adobe Experience Manager para uma campanha e atualizá-lo, poderá afetar o conteúdo involuntariamente na outra campanha.
Para evitar isso, depois que você terminar de usar seu modelo, poderá desvinculá-lo para usá-lo novamente. Basta selecionar o modelo e clicar em **[!UICONTROL Delete the link with Adobe Experience Manager content]**.

* **Use o Adobe Experience Manager para criar variações de e-mails para o Adobe Campaign Standard.**

   Essa integração permite transformar facilmente um e-mail em várias versões com a segmentação.
Para saber como configurar a segmentação no Adobe Experience Manager e como criar emails com conteúdo direcionado, consulte esta [página](https://docs.adobe.com/help/en/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem).

* **Para uma sincronização bem-sucedida, o nome do segmento no Experience Manager deve corresponder ao nome do segmento na Campanha exata.**