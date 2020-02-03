---
title: Personalização de campanhas usando atributos da plataforma Adobe Experience
description: Saiba como personalizar suas campanhas usando os atributos da plataforma Adobe Experience.
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
source-git-commit: 4b18f3b93394101eb569799bcfe362b4daf8f250

---


# Personalização de campanhas usando atributos da plataforma Adobe Experience {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>O serviço de Destinos de público-alvo está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar acessar.
>
>**Os canais de push** e **no aplicativo** ainda não estão disponíveis para personalização usando dados contextuais da Adobe Experience Platform.

Depois que seu fluxo de trabalho for configurado com um público [da plataforma](../../audiences/using/aep-about-audience-destinations-service.md)Adobe Experience, você poderá personalizar mensagens com atributos de perfil que existem exclusivamente no Modelo de Dados de Experiência (XDM).

Para fazer isso, você deve adicionar esses atributos à **[!UICONTROL Read audience]**atividade:

1. Open the **[!UICONTROL Read audience]**activity. Na**[!UICONTROL Additional data]** guia, clique no **[!UICONTROL Create element]**botão.

   Observe que a **[!UICONTROL Additional data]**guia só estará disponível depois que um público-alvo da plataforma Adobe Experience for selecionado.

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >Os tipos de dados de matriz e mapa não são suportados neste recurso. Além disso, somente os dados do esquema de união serão exibidos no seletor.

1. Selecione o campo XDM desejado na lista e clique em **[!UICONTROL Confirm]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. Clique no **[!UICONTROL Add]**botão para adicioná-lo à lista de dados adicionais.

   ![](assets/aep_wkf_readaudience_perso3.png)

1. Repita essas etapas para cada campo XDM que você deseja adicionar ao seu fluxo de trabalho.

   >[!NOTE]
   >
   >É possível adicionar um máximo de 20 campos XDM em uma **[!UICONTROL Read audience]**atividade.

1. Depois que todos os campos tiverem sido adicionados, clique no **[!UICONTROL Confirm]**botão para salvar as alterações. Eles agora estarão disponíveis para personalizar suas entregas.

Para obter mais informações sobre como criar e personalizar entregas, consulte a documentação do Campaign Standard:

* [Descobrir canais de comunicação](../../channels/using/discovering-communication-channels.md)
* [Sobre as atividades de canal](../../automating/using/about-channel-activities.md)
* [Personalização de deliveries](../../designing/using/personalization.md)
