---
title: Personalização de campanhas usando atributos da Adobe Experience Platform
description: Saiba como personalizar suas campanhas usando atributos da Adobe Experience Platform.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 4d4e7e58-e161-4e5a-898a-b5c29ffb20e0
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: dd99420f-367d-4a14-bbc4-5140615992c2
    internal-label: Microsoft CRM integration
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 8%
---
# Personalização de campanhas usando atributos da Adobe Experience Platform {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>O serviço Audience Destinations está atualmente em versão beta, que pode estar sujeita a atualizações frequentes sem aviso prévio. Os clientes precisam ser hospedados na Azure (atualmente na versão beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar obter acesso.
>
>Os canais **Push** e **No aplicativo** ainda não estão disponíveis para personalização usando dados contextuais do Adobe Experience Platform.

Depois que o fluxo de trabalho for configurado com um [público-alvo do Adobe Experience Platform](../../integrating/using/aep-about-audience-destinations-service.md), você poderá personalizar mensagens com atributos de perfil que existem exclusivamente no Experience Data Model (XDM).

Para fazer isso, você deve adicionar estes atributos na atividade **[!UICONTROL Read audience]**:

1. Abra a atividade **[!UICONTROL Read audience]**. Na guia **[!UICONTROL Additional data]**, clique no botão **[!UICONTROL Create element]**.

   Observe que a guia **[!UICONTROL Additional data]** só estará disponível depois que um público-alvo do Adobe Experience Platform for selecionado.

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >Os tipos de dados de matriz e mapa não são compatíveis com esse recurso. Além disso, somente os dados do esquema de união serão exibidos no seletor.

1. Selecione o campo XDM desejado na lista e clique em **[!UICONTROL Confirm]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. Clique no botão **[!UICONTROL Add]** para adicioná-lo à lista de dados adicionais.

   ![](assets/aep_wkf_readaudience_perso3.png)

1. Repita essas etapas para cada campo XDM que deseja adicionar ao fluxo de trabalho.

   >[!NOTE]
   >
   >Você pode adicionar no máximo 20 campos XDM em uma atividade **[!UICONTROL Read audience]**.

1. Depois que todos os campos forem adicionados, clique no botão **[!UICONTROL Confirm]** para salvar suas alterações. Agora eles estarão disponíveis para personalizar seus deliveries.

Para obter mais informações sobre como criar e personalizar deliveries, consulte a documentação do Campaign Standard:

* [Descobrir canais de comunicação](../../channels/using/get-started-communication-channels.md)
* [Sobre as atividades de canal](../../automating/using/about-channel-activities.md)
* [Personalização de entregas](../../designing/using/personalization.md)
