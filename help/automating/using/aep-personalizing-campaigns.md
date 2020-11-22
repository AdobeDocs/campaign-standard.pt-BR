---
solution: Campaign Standard
product: campaign
title: Personalização de campanhas usando atributos da Adobe Experience Platform
description: Saiba como personalizar suas campanhas usando os atributos da Plataforma de experiência do Adobe.
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 9%

---


# Personalização de campanhas usando atributos da Adobe Experience Platform {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>O serviço Destinos de audiência está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar acessá-lo.
>
>**Canais de push** e **no aplicativo** ainda não estão disponíveis para personalização usando dados contextuais da Adobe Experience Platform.

Depois que seu fluxo de trabalho for configurado com uma audiência [do](../../audiences/using/aep-about-audience-destinations-service.md)Adobe Experience Platform, você poderá personalizar mensagens com atributos de perfil que existem exclusivamente no Modelo de Dados de Experiência (XDM).

Para fazer isso, você deve adicionar esses atributos à **[!UICONTROL Read audience]** atividade:

1. Abra a atividade **[!UICONTROL Read audience]**. Na **[!UICONTROL Additional data]** guia, clique no **[!UICONTROL Create element]** botão.

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
