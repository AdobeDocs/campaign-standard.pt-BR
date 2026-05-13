---
title: Sobre perfis
description: Contatos são armazenados como perfis no banco de dados do Campaign e atualizados durante todo o ciclo de vida.
audience: audiences
content-type: reference
topic-tags: managing-profiles
context-tags: recipient,overview
feature: Profiles
role: User
level: Beginner
exl-id: 65310e00-567f-4fae-89bc-b1d5591fca77
TQID: https://experienceleague.adobe.com/8netKX93BsN9JxgyckV44tpKK5uPjFMrrnD8F4FCpJM
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 155
ht-degree: 74%

---

# Sobre perfis{#about-profiles}

O Adobe Campaign permite gerenciar contatos em todo o ciclo de vida: criação, importação, direcionamento, rastreamento de ações, atualizações, etc. Os contatos são armazenados no banco de dados como perfis que contêm as informações vinculadas a eles: sobrenome, nome, endereço, assinaturas, deliveries etc.

>[!NOTE]
>
>Perfis também estão disponíveis usando a API do Adobe Campaign Standard. Para obter mais informações, consulte a [documentação dedicada](../../api/using/retrieving-profiles.md).

![](assets/marketing_history.png)

Ao criar campanhas, você pode definir o público-alvo das entregas selecionando perfis de acordo com critérios simples ou avançados. Tecnicamente, um perfil é uma entrada no banco de dados que contém todas as informações necessárias para direcionar, qualificar e rastrear comportamentos.

Um perfil pode ser: um cliente, um cliente potencial, uma pessoa inscrita em um informativo, um destinatário, um usuário ou qualquer outra denominação dependendo da organização. Para definir vários tipos de perfis, use [target dimension](../../automating/using/query.md#targeting-dimensions-and-resources).
