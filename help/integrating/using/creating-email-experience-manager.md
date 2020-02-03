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
source-git-commit: 5c1a540475b7d93c18c957243ee2a403b8154aa3

---


# Criação de conteúdo de e-mail no Adobe Experience Manager {#creating-email-aem}

Essa integração entre o Adobe Campaign Standard e o Adobe Experience Manager permite que você use conteúdo criado no Adobe Experience Manager em emails do Adobe Campaign.

Este caso de uso mostrará como criar um conteúdo de email no Adobe Experience Manager.

## Pré-requisitos {#prerequisites}

Verifique se você tem os seguintes elementos antecipadamente:

* Uma instância de **criação** do Adobe Experience Manager
* Uma instância de **publicação** do Adobe Experience Manager
* Uma instância do Adobe Campaign

## Configuração {#configuration}

Para usar essas duas soluções em conjunto, você deve configurá-las para se conectarem.

1. Configure o Adobe Campaign. Para fazer isso:

   * Configure uma conta externa do tipo Adobe Experience Manager.
   * Configure a **[!UICONTROL AEMResourceTypeFilter]**opção, que reconhece os tipos de conteúdo criados no Adobe Experience Manager para o Adobe Campaign.
   * Crie um modelo de e-mail especificando que é conteúdo do Adobe Experience Manager e vincule a conta externa criada anteriormente a esse modelo.

1. Configure o Adobe Experience Manager. Para fazer isso:

   * Configure a replicação entre as instâncias de criação e publicação do Adobe Experience Manager.
   * Connect Adobe Experience Manager to Adobe Campaign by configuring a dedicated **[!UICONTROL Cloud Service]**.

## Criação de conteúdo de e-mail no Adobe Experience Manager {#use-case}

Para criar um conteúdo de email no Adobe Experience Manager:

1. Crie um conteúdo de email usando um modelo criado especificamente para o Adobe Campaign.
1. Nas propriedades de conteúdo, selecione o **[!UICONTROL Cloud Service]**correspondente à sua instância do Adobe Campaign.
1. Edite o conteúdo inserindo texto, imagens, personalização etc.
1. Valide o conteúdo.

Para obter mais informações, consulte a [documentação detalhada](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/campaign.html).

![](assets/aem_content.png)

Para recuperar o conteúdo no Adobe Campaign:

1. Crie um email com base em um modelo de conteúdo do tipo Adobe Experience Manager.
1. Vincule um conteúdo criado com o Adobe Experience Manager usando a tela de definição de conteúdo de email do Adobe Campaign.

![](assets/aem_linked_content.png)

