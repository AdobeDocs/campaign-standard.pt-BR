---
title: Mapear recursos personalizados da Campanha e entidades personalizadas do Dynamics 365
description: Saiba como mapear recursos e entidades no contexto da integração entre o Adobe Campaign Standard e o Microsoft Dynamics 365.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e11de4d4482400e62be2db076c88da5ae30d60cc
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 1%

---


# Mapear recursos de Campanha e entidades do Dynamics 365

Saiba como mapear recursos personalizados e entidades personalizadas no contexto da integração entre o Adobe Campaign Standard e o Microsoft Dynamics 365.

>[!CAUTION]
>
>Esse recurso não está disponível para uso imediato como parte do produto. A implementação exige que a Adobe Consulting esteja envolvida. Entre em contato com seu representante de Adobe para saber mais.

## Pré-requisitos

A integração [do](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md) Microsoft Dynamics 365-Adobe Campaign Standard oferece suporte a entidades personalizadas, permitindo que entidades personalizadas no Dynamics 365 sejam sincronizadas com os recursos personalizados correspondentes na Campanha.

Os novos dados nos recursos personalizados podem ser usados para vários fins, incluindo segmentação e personalização.

A integração suporta tabelas vinculadas e não vinculadas. A vinculação é suportada até três níveis (ou seja, level1->level2->level3).

>[!CAUTION]
>
>Se qualquer registro de recurso personalizado de Campanha contiver informações pessoais, serão aplicadas recomendações específicas. Saiba mais [nesta seção](../../integrating/using/notices-and-recommendations-for-acs-and-ms-dynamics.md#privacy-linked-resources).

## Avisos

Ao configurar fluxos de dados de entidade personalizados, é importante ter em mente o seguinte:

* Criar e modificar recursos personalizados de Campanha são operações confidenciais que devem ser executadas somente por usuários especialistas.
* Para fluxos de dados de entidade personalizados, o rastreamento de alterações deve ser ativado no Dynamics 365 para entidades personalizadas sincronizadas.
* Se um registro pai e filho vinculado forem criados perto da mesma hora no Dynamics 365, devido ao processamento paralelo da integração, há uma pequena chance de que um novo registro filho possa ser gravado na Campanha antes de seu registro pai.

* Se o pai e o filho estiverem vinculados na Campanha usando a opção de link **simples de cardinalidade** 1, o registro filho permanecerá oculto e inacessível (via interface do usuário ou API) até que o registro pai chegue à Campanha.

* (Assumindo **1 conexão** simples de cardinalidade na Campanha) Se o registro filho for atualizado ou excluído no Dynamics 365 e essa alteração for gravada na Campanha antes que o registro pai seja exibido na Campanha (não é provável, mas uma possibilidade remota), essa atualização ou exclusão não será processada na Campanha e um erro será lançado. Em caso de atualização, o registro em questão terá de ser atualizado novamente no Dynamics 365 para sincronizar o registro atualizado. Em caso de supressão, o registro em questão terá de ser tratado separadamente do lado da Campanha, uma vez que já não existe um registro no Dynamics 365 para eliminar ou atualizar.

* Se você encontrar uma situação em que acredita ter ocultado registros secundários e não ter como acessá-los, poderá alterar temporariamente o tipo de link de cardinalidade para **0 ou 1 simples link** de cardinalidade para acessar esses registros.

Uma visão geral mais abrangente dos recursos personalizados da Campanha pode ser encontrada [nesta seção](../../developing/using/key-steps-to-add-a-resource.md).
