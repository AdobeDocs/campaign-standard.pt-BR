---
title: Sobre tipologias e regras de tipologia
description: Saiba como as tipologias e regras de tipologia funcionam no Adobe Campaign.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
context-tags: typology,overview;typologyRule,main;typologyRule,overview
feature: Typology Rules
role: User
level: Intermediate
exl-id: dff72856-d28c-45c4-a073-12cc25f51f23
TQID: https://experienceleague.adobe.com/fFTJTgKfIhII-D6pefx9hqnX3a022odFZS5AAmNK1Ao
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 193
ht-degree: 100%

---

# Sobre tipologias e regras de tipologia{#about-typology-rules}

No Campaign Standard é possível vincular uma mensagem a uma **tipologia**, a fim de verificar se a mensagem é válida e atende aos seus critérios de qualidade.

Tipologias são conjuntos de **regras de tipologia**, que são executadas durante a fase de análise da mensagem. Elas possibilitam garantir que seus emails sempre contenham determinados elementos (como um link de cancelamento de assinatura ou uma linha de assunto) ou regras de filtragem para excluir grupos do público-alvo desejado (como clientes que não assinam, concorrentes ou clientes não fidelizados).

![](assets/typology_messagelink.png)

As tipologias e regras de tipologia prontas para uso estão disponíveis no Campaign Standard. Dependendo das suas necessidades, você também pode criar novas regras e adicioná-las a tipologias existentes ou novas para vincular às suas mensagens.

As etapas para criar e aplicar uma tipologia às mensagens são:

1. Criar regras de tipologia (consulte [esta seção](../../sending/using/managing-typology-rules.md#creating-a-typology-rule)).
1. Criar uma tipologia e fazer referência às regras criadas nela (consulte [esta seção](../../sending/using/managing-typologies.md#creating-a-typology)).
1. Configurar a entrega para usar a tipologia criada (consulte [esta seção](../../sending/using/managing-typologies.md#applying-typologies-to-messages)).
1. Durante a preparação da mensagem, os perfis são excluídos quando o critério é atendido. Você pode verificar os logs para monitorar exclusões.
