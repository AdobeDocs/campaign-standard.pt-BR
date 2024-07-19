---
title: Configuração da integração do Campaign com o Experience Manager
description: Com a integração do Adobe Experience Manager, é possível criar conteúdo diretamente no AEM e usá-lo posteriormente no Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: f56f5a19-6283-4eef-8127-c69a16a42a37
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 9%

---

# Configuração da integração do Campaign com o Experience Manager {#configuration-aem}

Essa integração entre o Adobe Campaign Standard e o Adobe Experience Manager permite usar o conteúdo criado no Adobe Experience Manager em seus emails do Adobe Campaign.

Com esse caso de uso, você aprenderá a criar e gerenciar conteúdo de email no Adobe Experience Manager e, em seguida, usá-los para suas campanhas de marketing, importando-os em seus emails para o Adobe Campaign Standard.

## Pré-requisitos {#prerequisites}

Verifique se você tem os seguintes elementos antecipadamente:

* Uma instância **de criação** do Adobe Experience Manager
* Uma instância do Adobe Experience Manager **publishing**
* Uma instância do Adobe Campaign

## Configuração no Adobe Campaign Standard {#config-acs}

Para usar essas duas soluções em conjunto, você deve configurá-las para se conectarem.
Para configurar o Adobe Campaign:

1. Primeiro, é necessário configurar a conta externa do **[!UICONTROL Adobe Experience Manager instance]** em **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**.

1. Configure a conta externa do tipo Adobe Experience Manager com sua URL **[!UICONTROL Server]**, **[!UICONTROL Account]** e **[!UICONTROL Password]**.

   ![](assets/aem_1.png)

1. Verifique se a opção **[!UICONTROL AEMResourceTypeFilter]** foi configurada corretamente. Acesse o menu **[!UICONTROL Options]** em **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > menu **[!UICONTROL Options]**.

1. No campo **[!UICONTROL Value (text)]**, verifique se a sintaxe a seguir está correta:

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. Em seguida, no menu avançado, em **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**, duplique um dos modelos existentes para criar um modelo de email específico para o Adobe Experience Manager.

   ![](assets/aem_3.png)

1. Clique no ícone **[!UICONTROL Edit properties]**.

   ![](assets/aem_4.png)

1. Na lista suspensa **[!UICONTROL Content]**, selecione **[!UICONTROL Adobe Experience Manager]** no campo **[!UICONTROL Content source]** e depois na conta externa criada anteriormente no **[!UICONTROL Adobe Experience Manager account]**.

Agora, é necessário configurar a integração no Adobe Experience Manager.

## Configuração no Adobe Experience Manager {#config-aem}

Para configurar o Adobe Experience Manager com o Adobe Campaign Standard, siga estas etapas:

1. Primeiro, é necessário configurar a replicação entre as instâncias de criação e publicação do Adobe Experience Manager. Consulte esta [seção](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager).

1. Em seguida, conecte o Adobe Experience Manager ao Adobe Campaign configurando um **[!UICONTROL Cloud Service]** dedicado. Consulte esta [seção](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign).

1. Agora é necessário configurar o externalizador no Adobe Experience Manager na instância do autor. Consulte esta [seção](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer).
