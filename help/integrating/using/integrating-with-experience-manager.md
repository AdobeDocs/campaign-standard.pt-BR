---
title: Integração com o Experience Manager
description: Com a integração do Adobe Experience Manager, você pode criar conteúdo diretamente no AEM e usá-lo posteriormente no Adobe Campaign.
page-status-flag: nunca ativado
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: integrando
content-type: referência
topic-tags: trabalhar com campanha e gerente de experiência
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Integração com o Experience Manager{#integrating-with-experience-manager}

Essa integração entre o Adobe Campaign Standard e o Adobe Experience Manager permite que você use conteúdo criado no Adobe Experience Manager em emails do Adobe Campaign.

Portanto, você pode aproveitar ao máximo as funcionalidades de edição de conteúdo do Adobe Experience Manager, bem como os recursos de entrega e gerenciamento de dados do Adobe Campaign.

>[!NOTE]
>
>Não é possível executar testes A/B para conteúdos importados do Adobe Experience Manager.

O Adobe Campaign Standard é compatível com o Adobe Experience Manager 6.1, 6.2, 6.3 e 6.4. As seções a seguir apresentam uma visão geral das ações que você pode executar. Para obter mais informações, consulte as seções dedicadas à [configuração](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html) e ao [uso](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/campaign.html) da integração.

## Pré-requisitos {#prerequisites}

Verifique se você tem os seguintes elementos antecipadamente:

* Uma instância de **criação** do Adobe Experience Manager
* Uma instância de **publicação** do Adobe Experience Manager
* Uma instância do Adobe Campaign

## Caso de uso {#use-case}

Para criar um conteúdo de email no Adobe Experience Manager:

1. Crie um conteúdo de email usando um modelo criado especificamente para o Adobe Campaign.
1. Nas propriedades de conteúdo, selecione o **[!UICONTROL Cloud Service]** correspondente à sua instância do Adobe Campaign.
1. Edite o conteúdo inserindo texto, imagens, personalização etc.
1. Valide o conteúdo.

Para obter mais informações, consulte a [documentação detalhada](https://docs.adobe.com/docs/en/aem/6-2/author/personalization/adobe-campaign/campaign.html).

![](assets/aem_content.png)

Para recuperar o conteúdo no Adobe Campaign:

1. Crie um email com base em um modelo de conteúdo do tipo Adobe Experience Manager.
1. Vincule um conteúdo criado com o Adobe Experience Manager usando a tela de definição de conteúdo de email do Adobe Campaign.

![](assets/aem_linked_content.png)

## Configuração {#configuration}

Para usar essas duas soluções em conjunto, você deve configurá-las para se conectarem.

1. Configure o Adobe Campaign. Para fazer isso:

   * Configure uma conta externa do tipo Adobe Experience Manager.
   * Configure a opção **AEMResourceTypeFilter** , que reconhece os tipos de conteúdo criados no Adobe Experience Manager para o Adobe Campaign.
   * Crie um modelo de e-mail especificando que é conteúdo do Adobe Experience Manager e vincule a conta externa criada anteriormente a esse modelo.

1. Configure o Adobe Experience Manager. Para fazer isso:

   * Configure a replicação entre as instâncias de criação e publicação do Adobe Experience Manager.
   * Connect Adobe Experience Manager to Adobe Campaign by configuring a dedicated **[!UICONTROL Cloud Service]**.

