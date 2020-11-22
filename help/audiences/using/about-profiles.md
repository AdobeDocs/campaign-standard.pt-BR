---
solution: Campaign Standard
product: campaign
title: Sobre perfis
description: Contatos são armazenados como perfis no banco de dados do Campaign e atualizados durante todo o ciclo de vida.
audience: audiences
content-type: reference
topic-tags: managing-profiles
context-tags: recipient,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 100%

---


# Sobre perfis{#about-profiles}

O Adobe Campaign permite gerenciar contatos em todo o ciclo de vida: criação, importação, direcionamento, rastreamento de ações, atualizações, etc. Os contatos são armazenados no banco de dados como perfis que contêm as informações relacionadas a eles: sobrenome, nome, endereço, assinaturas, deliveries etc.

>[!NOTE]
>
>Perfis também estão disponíveis usando a API do Adobe Campaign Standard. Para obter mais informações, consulte a [documentação dedicada](../../api/using/retrieving-profiles.md).

![](assets/marketing_history.png)

Ao criar campanhas, você pode definir o público-alvo dos deliveries selecionando perfis de acordo com critérios simples ou avançados. Tecnicamente, um perfil é uma entrada no banco de dados que contém todas as informações necessárias para direcionar, qualificar e rastrear comportamentos.

Um perfil pode ser: um cliente, um prospecto, uma pessoa inscrita em um informativo, um recipient, um usuário ou qualquer outra denominação dependendo da organização. Para definir vários tipos de perfis, use [target dimension](../../automating/using/query.md#targeting-dimensions-and-resources).
