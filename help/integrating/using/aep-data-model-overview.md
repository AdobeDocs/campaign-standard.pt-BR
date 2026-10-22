---
title: Visão geral do modelo de dados de experiência
description: O Experience Data Model (XDM) é um conjunto padrão de esquemas de dados nos quais os dados podem ser assimilados para uso com soluções e produtos da Adobe Experience Platform.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: cc1aa669-30cd-4ea4-9fab-4d1b6c373744
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: dd99420f-367d-4a14-bbc4-5140615992c2
    internal-label: Microsoft CRM integration
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%
---
# Visão geral do modelo de dados de experiência {#experience-data-model-overview}

>[!IMPORTANT]
>
>O Conector de dados do Adobe Experience Platform está atualmente na versão beta, que pode estar sujeita a atualizações frequentes sem aviso prévio. Os clientes precisam ser hospedados na Azure (atualmente na versão beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar obter acesso.

O Experience Data Model (XDM) é um conjunto padrão de esquemas de dados nos quais os dados podem ser assimilados para uso com soluções e produtos da Adobe Experience Platform.

A criação e o gerenciamento de esquemas XDM estão disponíveis com uma API dedicada ou com a interface do usuário XDM.

## Espaço de trabalho XDM {#xdm-workspace}

O XDM Workspace oferece a capacidade de exibir, criar e estender esquemas de dados.

Para acessar a interface do usuário XDM, abra o Adobe Experience Platform. Navegue até a janela Modelo de dados para criar ou estender um esquema XDM.

Consulte a [documentação completa do XDM Workspace](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=pt-BR).

![](assets/aep_xdmworkspace.png)

## API XDM {#xdm-api}

Você pode executar as seguintes ações por meio da API do esquema XDM:

* Exibir uma lista de esquemas existentes
* Exibir um esquema específico Estender um esquema existente
* Adicionar campos a uma extensão
* Criar e atualizar um novo esquema
* Exibir descritores de esquema
* Criar, atualizar e excluir descritores de esquema

Todos os detalhes para manipular chamadas de API estão disponíveis no [Guia do Desenvolvedor](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=pt-BR).
