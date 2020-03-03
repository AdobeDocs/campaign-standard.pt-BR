---
title: Criação de conteúdo de e-mail no Adobe Experience Manager.
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
source-git-commit: 9efce905cd767013a22afb2a4d642e42b6616ef1

---


# Importação de conteúdo do Adobe Experience Manager para um email do Adobe Campaign {#creating-email-aem}

Usando este documento, você aprenderá a criar e gerenciar conteúdo de email no Adobe Experience Manager e, em seguida, a usá-los em suas campanhas de marketing importando-os em seus emails para o Adobe Campaign Standard.

Os pré-requisitos são:

* Acesso a uma instância do AEM configurada para a integração.
* Acesso a uma instância do Adobe Campaign configurada para a integração.
* Um modelo de email do Adobe Campaign configurado para receber conteúdo do AEM.

## Acessar emails no Adobe Experience Manager {#email-content-aem}

Faça logon na instância de criação do Adobe Experience Manager e navegue no site para acessar a pasta que contém o conteúdo do email.

>[!VIDEO](https://images-tv.adobe.com/mpcv3/2674d459-d57b-413b-9d34-9fd941666023_1575035768.854x480at800_h264.mp4)

## Creating new email content in Adobe Experience Manager {#creating-email-content-aem}

Vários modelos específicos do Adobe Campaign estão disponíveis. Você deve usar um desses modelos, pois eles contêm componentes predefinidos suportados pelo Adobe Campaign.

Por padrão, dois modelos predefinidos permitem que você crie conteúdo de email para o Adobe Campaign.

* **[!UICONTROL Adobe Campaign Email]**: este modelo contém um conteúdo padrão que você pode personalizar. Você pode escolher entre o email do Adobe Campaign (AC6.1) e o email do Adobe Campaign (ACS).
* **[!UICONTROL Importer Page]**: esse modelo permite importar um arquivo ZIP contendo um arquivo HTML com conteúdo que você poderá personalizar.

1. No Adobe Experience Manager, crie um novo **[!UICONTROL Page]**.

1. Selecione o **[!UICONTROL Adobe Campaign Email]** modelo. Consulte o vídeo a seguir para ver as etapas detalhadas.
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. Abra seu novo conteúdo de email.

1. No **[!UICONTROL Page properties]**, defina **[!UICONTROL Adobe Campaign]** como o **[!UICONTROL Cloud Service Configuration]**. Isso permite a comunicação entre o seu conteúdo e a sua instância do Adobe Campaign.

   Para obter mais informações, assista ao seguinte vídeo:

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## Editar e enviar um email {#editing-email-aem}

Você pode editar o conteúdo do email adicionando componentes e ativos. Campos de personalização podem ser usados para fornecer uma mensagem mais relevante com base nos dados dos destinatários no Adobe Campaign.

Para criar um conteúdo de email no Adobe Experience Manager:

1. Edite o assunto e a **[!UICONTROL Plain text]** versão do seu email acessando a guia **[!UICONTROL Page properties]** > **[!UICONTROL Email]** no sidekick.

1. Adicione **[!UICONTROL Personalization fields]** **[!UICONTROL Text & Personalization]** o componente. Cada componente corresponde a um uso específico: inserir imagens, adicionar personalização etc.

   Para obter mais informações, assista ao seguinte vídeo:
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. Na **[!UICONTROL Workflow]** guia, selecione o fluxo de trabalho de **[!UICONTROL Approve for Adobe Campaign]** validação. Você não poderá enviar um email no Adobe Campaign se ele usar um conteúdo que não tenha sido aprovado.

1. Depois que o conteúdo e os parâmetros de envio forem definidos, você poderá continuar aprovando, preparando e enviando o email no Adobe Campaign Standard.

   Para obter mais informações, assista ao seguinte vídeo:

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
