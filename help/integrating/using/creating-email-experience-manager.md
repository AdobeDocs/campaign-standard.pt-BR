---
solution: Campaign Standard
product: campaign
title: Criação de conteúdo de e-mail no Adobe Experience Manager.
description: Com a integração do Adobe Experience Manager, você pode criar conteúdo diretamente no AEM e usá-lo posteriormente no Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 16%

---


# Importação de conteúdo Adobe Experience Manager para um email Adobe Campaign {#creating-email-aem}

Usando este documento, você aprenderá a criar e gerenciar conteúdo de e-mail no Adobe Experience Manager e, em seguida, usá-los para suas campanhas de marketing importando-os em seus e-mails para o Adobe Campaign Standard.

Os pré-requisitos são:

* Acesso a uma instância AEM configurada para a integração.
* Acesso a uma instância do Adobe Campaign configurada para a integração.
* Um modelo de e-mail da Adobe Campaign configurado para receber AEM conteúdo.

## Acessar emails no Adobe Experience Manager {#email-content-aem}

Faça logon na instância de criação do Adobe Experience Manager e navegue pelo site para acessar a pasta que contém o conteúdo do email.

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Criação de novo conteúdo de e-mail no Adobe Experience Manager {#creating-email-content-aem}

Vários modelos específicos do Adobe Campaign estão disponíveis. Você deve usar um desses modelos, pois eles contêm componentes predefinidos suportados pelo Adobe Campaign.

Por padrão, dois modelos predefinidos permitem que você crie conteúdo de email para Adobe Campaign.

* **[!UICONTROL Adobe Campaign Email]**: este modelo contém um conteúdo padrão que você pode personalizar. Você pode escolher entre Adobe Campaign Email (AC6.1) e Adobe Campaign Email (ACS).
* **[!UICONTROL Importer Page]**: esse modelo permite importar um arquivo ZIP contendo um arquivo HTML com conteúdo que você poderá personalizar.

1. No Adobe Experience Manager, crie um novo **[!UICONTROL Page]**.

1. Select the **[!UICONTROL Adobe Campaign Email]** template. Consulte o vídeo a seguir para ver as etapas detalhadas.
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. Abra seu novo conteúdo de email.

1. No **[!UICONTROL Page properties]**, defina **[!UICONTROL Adobe Campaign]** como o **[!UICONTROL Cloud Service Configuration]**. Isso permite a comunicação entre seu conteúdo e sua instância do Adobe Campaign.

   Para obter mais informações, assista ao seguinte vídeo:

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## Editar e enviar um email {#editing-email-aem}

Você pode editar o conteúdo do email adicionando componentes e ativos. Os campos de personalização podem ser usados para fornecer uma mensagem mais relevante com base nos dados dos recipient no Adobe Campaign.

Para criar um conteúdo de email no Adobe Experience Manager:

1. Edite o assunto e a **[!UICONTROL Plain text]** versão do seu email acessando a guia **[!UICONTROL Page properties]** > **[!UICONTROL Email]** no sidekick.

1. Adicione **[!UICONTROL Personalization fields]** **[!UICONTROL Text & Personalization]** o componente. Cada componente corresponde a um uso específico: inserir imagens, adicionar personalização etc.

   Para obter mais informações, assista ao seguinte vídeo:
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. Na **[!UICONTROL Workflow]** guia, selecione o fluxo de trabalho de **[!UICONTROL Approve for Adobe Campaign]** validação. Você não poderá enviar um e-mail no Adobe Campaign se ele usar um conteúdo que não tenha sido aprovado.

1. Depois que o conteúdo e os parâmetros de envio forem definidos, você poderá continuar aprovando, preparando e enviando o email no Adobe Campaign Standard.

   Para obter mais informações, assista ao seguinte vídeo:

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
