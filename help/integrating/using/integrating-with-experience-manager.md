---
solution: Campaign Standard
product: campaign
title: Sobre a integração do Campaign-Experience Manager
description: Com a integração do Adobe Experience Manager, você pode criar conteúdo diretamente no AEM e usá-lo posteriormente no Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 1%

---


# Sobre a integração do Campaign-Experience Manager{#integrating-with-experience-manager}

Essa integração entre o Adobe Campaign Standard e o Adobe Experience Manager permite usar o conteúdo criado no Adobe Experience Manager nos emails do Adobe Campaign.

Portanto, você pode aproveitar ao máximo as funcionalidades de edição de conteúdo do Adobe Experience Manager, bem como os recursos de entrega e gerenciamento de dados do Adobe Campaign. Observe que não é possível executar testes A/B para conteúdo importado do Adobe Experience Manager.

O Adobe Campaign Standard é compatível com o Adobe Experience Manager 6.1, 6.2, 6.3, 6.4 e 6.5. As seções a seguir apresentam uma visão geral das ações que você pode executar. Para obter mais informações, consulte as seções dedicadas a [configuração](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html) e [use](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) da integração.

>[!NOTE]
>
> Os modelos do Adobe Campaign Standard não estão mais disponíveis com o Adobe Experience Manager 6.5.

## Dicas sobre como usar a integração Campaign-Experience Manager {#tips-aem}

* **Saiba qual modelo usar com a integração**

   Como os modelos de email podem ser editados no Adobe Experience Manager, pode ser mais fácil editar qualquer modelo no Adobe Experience Manager. Mas certos modelos não são facilmente acomodados. Os modelos individuais específicos a um cliente não são recomendados para essa integração e devem ser editados diretamente no Adobe Campaign Standard.

   Para obter mais informações sobre templates, consulte esta [página](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html).

* **Verifique se o Externalizador foi configurado durante a implementação**

   Configurar o Externalizador ao implementar o Experience Manager para Adobe Campaign Standard possibilita transformar um caminho de recurso em um URL. Isso permite que você torne suas imagens visíveis na página. Se o Externalizador não estiver configurado corretamente, seus emails conterão imagens quebradas.

   Para saber como configurar o Externalizador, consulte esta [página](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/externalizer.html).

* **Organize seus modelos de email para evitar mau uso.**

   Manter os modelos organizados garante que os modelos apropriados estejam nas pastas apropriadas e não escolha os errados por engano. Durante a implementação, os caminhos devem ser criados para salvar os modelos nos locais corretos.

   Para obter mais informações sobre templates, consulte esta [página](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html#template-availability).

* **Comece rapidamente com componentes prontos para uso.**

   Componentes prontos para uso no Adobe Experience Manager for Adobe Campaign Standard podem ajudar você a começar a usar rapidamente se os modelos não forem complexos.
Há sete componentes prontos para uso no Experience Manager que você pode começar a usar:

   * Cabeçalho
   * Imagem
   * Link
   * Modelo de imagem do Scene7
   * Referência direcionada
   * Texto e imagem
   * Texto e personalização

* **O HTML para emails é diferente do HTML para Web**

   É importante entender que você não pode usar os mesmos componentes usados no conteúdo da Web para modelos de email. Usar componentes prontos para uso garante que seus componentes sejam compatíveis com email.

* **Desvincule o conteúdo dos modelos e reutilize-o repetidas vezes.**

   Ao configurar seus emails no Campaign Standard e selecionar um template Experience Manager, você só pode escolher um que ainda não tenha sido vinculado a outra campanha. Caso contrário, se você alterar o conteúdo do Adobe Experience Manager para uma campanha e atualizá-lo, poderá afetar o conteúdo involuntariamente em outra campanha.
Para evitar isso, uma vez terminado de usar seu template, você pode desvinculá-lo para usá-lo novamente. Basta selecionar o modelo e clicar em **[!UICONTROL Delete the link with Adobe Experience Manager content]**.

* **Use o Adobe Experience Manager para criar variações de emails para o Adobe Campaign Standard.**

   Essa integração permite transformar facilmente um email em várias versões com a segmentação.
Para saber como configurar a segmentação no Adobe Experience Manager e criar emails com conteúdo direcionado, consulte esta [página](https://docs.adobe.com/help/en/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem).

* **Para uma sincronização bem-sucedida, o nome do segmento no Experience Manager deve corresponder ao nome do segmento no Campaign exato.**