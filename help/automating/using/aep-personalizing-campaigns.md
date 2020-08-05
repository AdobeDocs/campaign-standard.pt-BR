---
title: Personalização de campanhas usando atributos da Adobe Experience Platform
description: Saiba como personalizar suas campanhas usando os atributos da Plataforma de experiência do Adobe.
page-status-flag: never-activated
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ad110413fd325894405b421999baccda2c7cef4a
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 8%

---


# Personalização de campanhas usando atributos da Adobe Experience Platform {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>O serviço Destinos de Audiência está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar acessá-lo.
>
>**canais de push** e **no aplicativo** ainda não estão disponíveis para personalização usando dados contextuais da Adobe Experience Platform.

Depois que seu fluxo de trabalho for configurado com uma audiência [do](../../audiences/using/aep-about-audience-destinations-service.md)Adobe Experience Platform, você poderá personalizar mensagens com atributos de perfil que existem exclusivamente no Modelo de Dados de Experiência (XDM).

Para fazer isso, você deve adicionar esses atributos à **[!UICONTROL Read audience]** atividade:

1. Open the **[!UICONTROL Read audience]** activity. In the **[!UICONTROL Additional data]** tab, click the **[!UICONTROL Create element]** button.

   Observe que a **[!UICONTROL Additional data]** guia só estará disponível depois que uma audiência Adobe Experience Platform for selecionada.

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >Os tipos de dados de matriz e mapa não são suportados neste recurso. Além disso, somente os dados do schema da união serão exibidos no seletor.

1. Selecione o campo XDM desejado na lista e clique em **[!UICONTROL Confirm]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. Clique no **[!UICONTROL Add]** botão para adicioná-lo à lista de dados adicionais.

   ![](assets/aep_wkf_readaudience_perso3.png)

1. Repita essas etapas para cada campo XDM que você deseja adicionar ao seu fluxo de trabalho.

   >[!NOTE]
   >
   >É possível adicionar um máximo de 20 campos XDM em uma **[!UICONTROL Read audience]** atividade.

1. Depois que todos os campos tiverem sido adicionados, clique no **[!UICONTROL Confirm]** botão para salvar as alterações. Eles agora estarão disponíveis para personalizar seus delivery.

Para obter mais informações sobre como criar e personalizar delivery, consulte a documentação do Campaign Standard:

* [Introdução aos canais de comunicação](../../channels/using/get-started-communication-channels.md)
* [Sobre as atividades de canal](../../automating/using/about-channel-activities.md)
* [Personalização de deliveries](../../designing/using/personalization.md)
