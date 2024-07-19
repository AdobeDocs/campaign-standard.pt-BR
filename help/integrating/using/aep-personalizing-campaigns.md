---
title: Personalização de campanhas usando atributos da Adobe Experience Platform
description: Saiba como personalizar suas campanhas usando atributos da Adobe Experience Platform.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 4d4e7e58-e161-4e5a-898a-b5c29ffb20e0
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 6%

---

# Personalização de campanhas usando atributos da Adobe Experience Platform {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>O serviço Audience Destinations está atualmente em versão beta, que pode estar sujeita a atualizações frequentes sem aviso prévio. Os clientes precisam ser hospedados no Azure (atualmente na versão beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar obter acesso.
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
