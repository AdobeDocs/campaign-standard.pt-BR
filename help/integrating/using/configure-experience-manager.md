---
title: Configuração da integração do Campaign-Experience Manager
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
source-git-commit: 37b1c17234a300b092db3c810a32de3600bb8f2f

---


# Configuração da integração do Campaign-Experience Manager {#configuration-aem}

Essa integração entre o Adobe Campaign Standard e o Adobe Experience Manager permite que você use conteúdo criado no Adobe Experience Manager em emails do Adobe Campaign.

Com esse caso de uso, você aprenderá a criar e gerenciar conteúdo de email no Adobe Experience Manager e, em seguida, usá-los em suas campanhas de marketing importando-os em seus emails para o Adobe Campaign Standard.

## Pré-requisitos {#prerequisites}

Verifique se você tem os seguintes elementos antecipadamente:

* Uma instância de **criação** do Adobe Experience Manager
* Uma instância de **publicação** do Adobe Experience Manager
* Uma instância do Adobe Campaign

## Configuração no Adobe Campaign Standard {#config-acs}

Para usar essas duas soluções em conjunto, você deve configurá-las para se conectarem.
Para configurar o Adobe Campaign:

1. Primeiro, é necessário configurar a conta **[!UICONTROL Adobe Experience Manager instance]** externa em **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**.

1. Configure a conta externa do tipo Adobe Experience Manager com seu **[!UICONTROL Server]** URL **[!UICONTROL Account]** e **[!UICONTROL Password]**.

   ![](assets/aem_1.png)

1. Verifique se a **[!UICONTROL AEMResourceTypeFilter]** opção foi configurada corretamente. Acesse o **[!UICONTROL Options]** menu em **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** .

1. No **[!UICONTROL Value (text)]** campo, verifique se a seguinte sintaxe está correta:

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. Em seguida, no menu avançado em **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**, duplique um dos modelos existentes para criar um modelo de email específico ao Adobe Experience Manager.

   ![](assets/aem_3.png)

1. Clique no **[!UICONTROL Edit properties]** ícone.

   ![](assets/aem_4.png)

1. Na lista **[!UICONTROL Content]** suspensa, selecione **[!UICONTROL Adobe Experience Manager]** no **[!UICONTROL Content source]** campo e depois sua conta externa criada anteriormente no **[!UICONTROL Adobe Experience Manager account]**.

Agora é necessário configurar a integração no Adobe Experience Manager.

## Configuration in Adobe Experience Manager {#config-aem}

Para configurar o Adobe Experience Manager com o Adobe Campaign Standard, siga estas etapas:

1. Primeiro, é necessário configurar a replicação entre as instâncias de criação e publicação do Adobe Experience Manager. Consulte esta [seção](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager).

1. Then, connect Adobe Experience Manager to Adobe Campaign by configuring a dedicated **[!UICONTROL Cloud Service]**. Consulte esta [seção](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign).

1. Agora é necessário configurar o externalizador no Adobe Experience Manager na instância do autor. Consulte esta [seção](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer).

