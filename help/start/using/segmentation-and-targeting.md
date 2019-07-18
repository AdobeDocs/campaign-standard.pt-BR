---
title: Segmentação e segmentação
seo-title: Segmentação e segmentação
description: Segmentação e segmentação
seo-description: '" Saiba mais sobre perfis, direcionamento e criação de público-alvo no Campaign: criar públicos-alvo, importar contatos compartilhe públicos com soluções da Experience Cloud e evite o esgotamento de marketing. "'
page-status-flag: nunca ativado
uuid: 71 f 53808-0309-49 f 6-a 4 ee -3446 eac 9758 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d 8 c 8 a 318-9433-4 peo@-@ b 378-fd 0 beb 50 e 9 fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Segmentation and targeting{#segmentation-and-targeting}

## Profiles {#profiles}

Use o modelo de dados flexível do Adobe Campaign para aprimorar os dados de perfil do cliente e adicionar novos atributos ou tabelas. Em seguida, use esses perfis de clientes para segmentação, personalização e relatórios mais precisos.

Os perfis do Adobe Campaign representam todos os contatos armazenados no banco de dados. Cada perfil corresponde a uma entrada no banco de dados que contém as informações necessárias para que o perfil seja direcionado, qualificado e monitorado individualmente. Isso significa que um perfil pode ser: um cliente, uma perspectiva, uma pessoa individual inscrita em um boletim informativo, um destinatário, um usuário ou qualquer outra denominação dependendo da organização.

O recurso de perfis do cliente integra todos os dados do cliente em um local:

![](assets/mkt_hist_view.png)

Adobe Campaign proposes various mechanisms for profile acquisition: collecting data online via [landing pages](../../channels/using/about-landing-pages.md), manual or [automated import mechanisms](../../automating/using/about-data-import-and-export.md), [direct input](../../audiences/using/creating-profiles.md) in the Adobe Campaign interface, bulk creation through [Campaign APIs](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).

**Tópicos relacionados:**

* Learn about different types of profiles in the [Profiles](../../audiences/using/about-profiles.md) section.
* Access the number of **Active Profiles** in your organization in [this section](../../audiences/using/active-profiles.md).
* Learn how to customize your data, handle complex data management tasks, such as calculations, aggregates, de-dupes, and merges, using [workflow targeting capabilities](../../automating/using/about-targeting-activities.md)

## Audiences {#audiences}

Para permitir que você forneça mensagens relevantes e eficazes e envolva seus clientes efetivamente, o Adobe Campaign integra a análise avançada e as funcionalidades de definição de metas. Graças aos fluxos de trabalho e ao editor de consultas, você pode criar públicos-alvo que serão direcionados por suas campanhas diferentes, dependendo das informações que você possui, das suas atividades, do idioma, das preferências ou do histórico de marketing. Isso permite filtrar perfis assinados por exemplo ou criar públicos alvo em um número ilimitado de critérios.

Audiences are presented [in this page](../../audiences/using/about-audiences.md) and detailed in the [Audiences](../../audiences/using/creating-audiences.md) section.

**Tópicos relacionados:**

* Learn how to reach multilingual audiences across multiple regions by sending [multilingual push notifications](../../channels/using/creating-a-multilingual-push-notification.md) or [multilingual emails](../../channels/using/creating-a-multilingual-email.md)
* Learn how to [create queries](../../audiences/using/creating-audiences.md#creating-query-audiences) to build audiences
* Learn how to [create list audiences](../../audiences/using/creating-audiences.md#creating-list-audiences) in a workflow
* Learn how to [import an audience from a file](../../audiences/using/creating-audiences.md#creating-file-audiences) in a workflow
* Learn how to [share audiences](../../audiences/using/creating-audiences.md#creating-experience-cloud-audiences) with Experience Cloud solutions

## General Data Protection Regulation {#general-data-protection-regulation}

O RGPD é a nova legislação de privacidade da União Europeia (EU) que harmoniza e moderniza as exigências de proteção de dados. O RGPD se aplica aos clientes do Adobe Campaign que detêm dados para os Dados de dados residentes na UE. Além dos recursos de privacidade já disponíveis no Adobe Campaign (incluindo gerenciamento de consentimento, configurações de retenção de dados e funções de usuário), estamos aproveitando essa oportunidade na nossa função como um Processador de dados para incluir recursos adicionais, para ajudar a facilitar sua execução como um Controlador de dados para certas solicitações RGPD.

Refer to this [guide](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) to learn more about the tools and functionalities that Adobe Campaign provides to help you become GDPR compliant.

## Fatigue management {#fatigue-management}

As regras de esgotamento permitem que os profissionais de marketing definam regras de negócios entre canais globais que excluirão automaticamente perfis pré-solicitados das campanhas.

Para implementar regras de fadiga, você define um número máximo de mensagens por perfil e seleciona um período em que a regra será aplicada. Durante a preparação de entrega, os perfis são excluídos da entrega se aplicável, dependendo do número de mensagens que já foram enviadas a eles.

**Tópicos relacionados:**

* Learn how to [design fatigue rules](../../administration/using/fatigue-rules.md#examples) through a set of samples
* Learn how to create [typology rules](../../administration/using/about-typology-rules.md)
* Use [filter rules](../../administration/using/filtering-rules.md) to refine the audience of your messages
