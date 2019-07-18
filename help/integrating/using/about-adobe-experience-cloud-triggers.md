---
title: Sobre os Acionadores da Adobe Experience Cloud
seo-title: Sobre os Acionadores da Adobe Experience Cloud
description: Sobre os Acionadores da Adobe Experience Cloud
seo-description: Ao rastrear comportamentos específicos de clientes com o Adobe Analytics, agora você pode enviar emails personalizados aos seus clientes no Adobe Campaign.
page-status-flag: nunca ativado
uuid: 0 aa 4 bd 6 e -1 bb 5-4 d 0 b -913 b-eca 93 f 050 acd
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: e 526 b 205-2 d 01-4 a 8 b -9685-ba 1 d 9 a 1 f 459 f
context-tags: acionador, visão geral; acionador, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# About Adobe Experience Cloud Triggers{#about-adobe-experience-cloud-triggers}

Integration between the Experience Cloud Activation core service **[!UICONTROL Triggers]** and Adobe Campaign allows you to send personalized emails to your customers as a reaction to specific behaviors that are tracked on your website by Adobe Analytics (within 15 minutes).

Na Adobe Experience Cloud, você define os diferentes acionadores, isto é, os comportamentos do cliente que você gostaria de monitorar, como todos os clientes que abandonaram sua visita em seu site, fizeram uma pesquisa em seu site, mas não fizeram uma compra ou até mesmo os clientes cuja sessão expirou. Ao criar um acionador, você define a condição do acionador e os dados que serão enviados no evento (carregar) para o Adobe Campaign.

No Adobe Campaign, você seleciona o disparador criado anteriormente, aprimora os dados do evento com dados de dados e define um modelo de mensagem transacional vinculado a esse acionador. Por exemplo, quando um cliente abandona sua visita em seu site, um evento é enviado para o Adobe Campaign, que pode aproveitar esse evento por meio de um email de recomercialização enviado para o cliente em 15 minutos.

**Tópicos relacionados:**

* Learn about the different types of triggers: [Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html).
* Watch the [Trigger Remarketing Messages based on Site Activity](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) video.
* Discover our two [Abandonment Triggers use cases](../../integrating/using/abandonment-triggers-use-cases.md).

## Triggers user process {#triggers-user-process}

>[!CAUTION]
>
>Antes de executar as etapas principais do usuário, a funcionalidade precisa ser configurada. For more on this refer to [Activating the functionality](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality), [Configuring solutions and services](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) and [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign).

As etapas principais do processamento do usuário, no Adobe Campaign, são:

1. Crie um evento de acionamento vinculado a um acionador existente da Adobe Experience Cloud.
1. Publique o evento de acionamento.
1. Defina o conteúdo do modelo de mensagem transacional.
1. Teste o modelo (crie um perfil de teste e envie uma prova).
1. Publique o modelo de mensagem transacional.

Complete use cases are described in [this section](../../integrating/using/abandonment-triggers-use-cases.md).

## Important notes {#important-notes}

Estas são algumas observações importantes a serem levadas em conta antes de usar a integração Acionadores - Campanha:

* Notificações por push não são compatíveis com acionadores. Somente email e SMS são suportados.
* É possível aprimorar o acionador com metadados capturados por meio do Analytics, como ID de e-mail, nome da página etc.
* Você pode conectar o acionador a um perfil armazenado no Campaign Standard e usar os campos do perfil para personalizar a mensagem.
* Assim que um acionador é recebido, ele é processado e reconciliado e enviado. Leva cerca de 5 a 15 minutos, dependendo do volume de acionadores recebidos, o número de campos de personalização usados no modelo.

>[!NOTE]
>
>For more on best practices and technical limitations, refer to [Triggers best practices and limitations](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations).

