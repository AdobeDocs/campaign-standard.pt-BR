---
title: Criação de conteúdo de email no Adobe Experience Manager.
description: Com a integração do Adobe Experience Manager, é possível criar conteúdo diretamente no AEM e usá-lo posteriormente no Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 72b99864-d9d9-4cf4-be06-dc5719a2e4f2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 16%

---

# Importação de conteúdo do Adobe Experience Manager para um email do Adobe Campaign {#creating-email-aem}

Com este documento, você aprenderá a criar e gerenciar conteúdo de email no Adobe Experience Manager e, em seguida, a usá-lo em suas campanhas de marketing, importando-o em seus emails para o Adobe Campaign Standard.

Os pré-requisitos são:

* Acesso a uma instância do AEM configurada para a integração.
* Acesso a uma instância do Adobe Campaign configurada para a integração.
* Um template de email do Adobe Campaign configurado para receber conteúdo AEM.

## Acesso a emails no Adobe Experience Manager {#email-content-aem}

Faça logon na instância de criação do Adobe Experience Manager e navegue em seu site para acessar a pasta que contém seu conteúdo de email.

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Criação de novo conteúdo de e-mail no Adobe Experience Manager {#creating-email-content-aem}

Vários modelos específicos para o Adobe Campaign estão disponíveis. Você deve usar um desses modelos, pois eles contêm componentes predefinidos suportados pelo Adobe Campaign.

Por padrão, dois modelos predefinidos permitem criar conteúdo de email para o Adobe Campaign.

* **[!UICONTROL Adobe Campaign Email]**: esse template contém um conteúdo padrão que pode ser personalizado. Você pode escolher entre Email do Adobe Campaign (AC6.1) e Email do Adobe Campaign (ACS).
* **[!UICONTROL Importer Page]**: esse modelo permite importar um arquivo ZIP contendo um arquivo HTML com conteúdo que você poderá personalizar.

1. No Adobe Experience Manager, crie uma nova **[!UICONTROL Page]**.

1. Selecione o **[!UICONTROL Adobe Campaign Email]** modelo. Consulte o vídeo a seguir para obter as etapas detalhadas.
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. Abra seu novo conteúdo de email.

1. No **[!UICONTROL Page properties]**, definir **[!UICONTROL Adobe Campaign]** como o **[!UICONTROL Cloud Service Configuration]**. Isso permite a comunicação entre seu conteúdo e sua instância do Adobe Campaign.

   Para obter mais informações, assista ao seguinte vídeo:

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## Edição e envio de um email {#editing-email-aem}

É possível editar o conteúdo do email adicionando componentes e ativos. Os campos de personalização podem ser usados para fornecer uma mensagem mais relevante com base nos dados dos recipients no Adobe Campaign.

Para criar um conteúdo de email no Adobe Experience Manager:

1. Edite o assunto e a variável **[!UICONTROL Plain text]** do seu e-mail acessando a **[!UICONTROL Page properties]** > **[!UICONTROL Email]** do sidekick.

1. Adicionar **[!UICONTROL Personalization fields]** por meio da **[!UICONTROL Text & Personalization]** componente. Cada componente corresponde a um uso específico: inserção de imagens, adição de personalização etc.

   Para obter mais informações, assista ao seguinte vídeo:
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. No **[!UICONTROL Workflow]** , selecione a **[!UICONTROL Approve for Adobe Campaign]** workflow de validação. Você não poderá enviar um e-mail no Adobe Campaign se ele usar um conteúdo que não tenha sido aprovado.

1. Após definir o conteúdo e os parâmetros de envio, você pode prosseguir para a aprovação, preparação e envio do email no Adobe Campaign Standard.

   Para obter mais informações, assista ao seguinte vídeo:

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
