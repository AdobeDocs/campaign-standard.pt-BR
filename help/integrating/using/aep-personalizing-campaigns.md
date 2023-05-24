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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 9%

---

# Personalização de campanhas usando atributos da Adobe Experience Platform {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>O serviço Audience Destinations está atualmente em versão beta, que pode estar sujeita a atualizações frequentes sem aviso prévio. Os clientes precisam ser hospedados no Azure (atualmente na versão beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar obter acesso.
>
>**Push** e **No aplicativo** os canais ainda não estão disponíveis para personalização usando dados contextuais do Adobe Experience Platform.

Assim que o workflow estiver configurado com um [Público-alvo do Adobe Experience Platform](../../integrating/using/aep-about-audience-destinations-service.md), você pode personalizar mensagens com atributos de perfil que existem exclusivamente no Experience Data Model (XDM).

Para fazer isso, você deve adicionar esses atributos na variável **[!UICONTROL Read audience]** atividade:

1. Abra a atividade **[!UICONTROL Read audience]**. No **[!UICONTROL Additional data]** clique na guia **[!UICONTROL Create element]** botão.

   Observe que **[!UICONTROL Additional data]** A guia só estará disponível depois que um público-alvo do Adobe Experience Platform for selecionado.

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >Os tipos de dados de matriz e mapa não são compatíveis com esse recurso. Além disso, somente os dados do esquema de união serão exibidos no seletor.

1. Selecione o campo XDM desejado na lista e clique em **[!UICONTROL Confirm]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. Clique em **[!UICONTROL Add]** para adicioná-lo à lista de dados adicionais.

   ![](assets/aep_wkf_readaudience_perso3.png)

1. Repita essas etapas para cada campo XDM que deseja adicionar ao fluxo de trabalho.

   >[!NOTE]
   >
   >É possível adicionar no máximo 20 campos XDM em uma **[!UICONTROL Read audience]** atividade.

1. Depois que todos os campos forem adicionados, clique no **[!UICONTROL Confirm]** botão para salvar as alterações. Agora eles estarão disponíveis para personalizar seus deliveries.

Para obter mais informações sobre como criar e personalizar deliveries, consulte a documentação do Campaign Standard:

* [Introdução aos canais de comunicação](../../channels/using/get-started-communication-channels.md)
* [Sobre as atividades de canal](../../automating/using/about-channel-activities.md)
* [Personalização de deliveries](../../designing/using/personalization.md)
