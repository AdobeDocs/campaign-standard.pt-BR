---
solution: Campaign Standard
product: campaign
title: Criação de conteúdo de e-mail no Adobe Experience Manager.
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
source-wordcount: '418'
ht-degree: 16%

---


# Importação de um conteúdo Adobe Experience Manager para um email do Adobe Campaign {#creating-email-aem}

Com este documento, você aprenderá a criar e gerenciar conteúdo de email no Adobe Experience Manager e, em seguida, a usá-lo em suas campanhas de marketing, importando-o em seus emails para o Adobe Campaign Standard.

Os pré-requisitos são:

* Acesso a uma instância de AEM configurada para a integração.
* Acesso a uma instância do Adobe Campaign configurada para a integração.
* Um modelo de email do Adobe Campaign configurado para receber conteúdo AEM.

## Acessar emails no Adobe Experience Manager {#email-content-aem}

Faça logon na instância de criação do Adobe Experience Manager e navegue pelo site para acessar a pasta que contém o conteúdo do email.

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Criação de novo conteúdo de e-mail no Adobe Experience Manager {#creating-email-content-aem}

Vários modelos específicos para o Adobe Campaign estão disponíveis. Você deve usar um desses modelos, pois eles contêm componentes predefinidos suportados pelo Adobe Campaign.

Por padrão, dois templates predefinidos permitem criar conteúdo de email para o Adobe Campaign.

* **[!UICONTROL Adobe Campaign Email]**: esse template contém um conteúdo padrão que pode ser personalizado. Você pode escolher entre Adobe Campaign Email (AC6.1) e Adobe Campaign Email (ACS).
* **[!UICONTROL Importer Page]**: esse template permite importar um arquivo ZIP contendo um arquivo HTML com conteúdo que você poderá personalizar.

1. No Adobe Experience Manager, crie um novo **[!UICONTROL Page]**.

1. Selecione o modelo **[!UICONTROL Adobe Campaign Email]**. Consulte o vídeo a seguir para ver as etapas detalhadas.
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. Abra seu novo conteúdo de email.

1. No **[!UICONTROL Page properties]**, defina **[!UICONTROL Adobe Campaign]** como **[!UICONTROL Cloud Service Configuration]**. Isso permite a comunicação entre seu conteúdo e sua instância do Adobe Campaign.

   Para obter mais informações, assista ao vídeo a seguir:

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## Editar e enviar um email {#editing-email-aem}

É possível editar o conteúdo do email adicionando componentes e ativos. Os campos de personalização podem ser usados para fornecer uma mensagem mais relevante com base nos dados dos recipients no Adobe Campaign.

Para criar um conteúdo de email no Adobe Experience Manager:

1. Edite o assunto e a versão **[!UICONTROL Plain text]** do email acessando a guia **[!UICONTROL Page properties]** > **[!UICONTROL Email]** no sidekick.

1. Adicione **[!UICONTROL Personalization fields]** por meio do componente **[!UICONTROL Text & Personalization]**. Cada componente corresponde a um uso específico: inserir imagens, adicionar personalização etc.

   Para obter mais informações, assista ao vídeo a seguir:
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. Na guia **[!UICONTROL Workflow]** , selecione o **[!UICONTROL Approve for Adobe Campaign]** fluxo de trabalho de validação. Você não poderá enviar um e-mail no Adobe Campaign se ele usar um conteúdo que não tenha sido aprovado.

1. Depois que os parâmetros de conteúdo e envio forem definidos, você poderá prosseguir com a aprovação, preparação e envio do email no Adobe Campaign Standard.

   Para obter mais informações, assista ao vídeo a seguir:

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
