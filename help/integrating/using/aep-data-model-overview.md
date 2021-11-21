---
title: Visão geral do Experience Data Model
description: O Experience Data Model (XDM) é um conjunto padrão de esquemas de dados em que os dados podem ser assimilados para uso com soluções e produtos da Adobe Experience Platform.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: cc1aa669-30cd-4ea4-9fab-4d1b6c373744
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# Visão geral do Experience Data Model {#experience-data-model-overview}

>[!IMPORTANT]
>
>No momento, o Adobe Experience Platform Data Connector está em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam ser hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar acesso.

O Experience Data Model (XDM) é um conjunto padrão de esquemas de dados em que os dados podem ser assimilados para uso com soluções e produtos da Adobe Experience Platform.

A criação e o gerenciamento de esquemas XDM estão disponíveis com uma API dedicada ou com a interface do usuário XDM.

## Espaço de trabalho XDM {#xdm-workspace}

O Espaço de trabalho XDM oferece a capacidade de exibir, criar e estender esquemas de dados.

Para acessar a interface do usuário do XDM, abra o Adobe Experience Platform. Navegue até a janela Modelo de dados para criar ou estender um esquema XDM.

Consulte o [Documentação do Espaço de trabalho XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html).

![](assets/aep_xdmworkspace.png)

## API XDM {#xdm-api}

Você pode executar as seguintes ações por meio da API do esquema XDM:

* Exibir uma lista de esquemas existentes
* Exibir um schema específico Estender um schema existente
* Adicionar campos a uma extensão
* Criar e atualizar um novo schema
* Exibir descritores de esquema
* Criar, atualizar e excluir descritores de esquema

Todos os detalhes para manipular chamadas de API estão disponíveis no [Guia do desenvolvedor](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html).
