---
title: Sobre tipologias e regras de tipologia
description: Descubra como as tipologias e regras de tipologia funcionam no Adobe Campaign.
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a9c0e3cc4609e747bbfebeb90049862f29c9d8d9

---


# Sobre tipologias e regras de tipologia{#about-typology-rules}

O Campaign Standard permite que você vincule uma mensagem a uma **tipologia**, para verificar se a mensagem é válida e se atende aos seus critérios de qualidade.

As tipologias são conjuntos de **regras de tipologia**, que são executados durante a fase de análise da mensagem. Eles permitem que você se certifique de que seus emails sempre contenham determinados elementos (como um link de unsubscription ou uma linha de assunto) ou regras de filtragem para excluir grupos do público alvo desejado (como clientes que não assinam, concorrentes ou não fazem fidelidade).

![](assets/typology_messagelink.png)

As tipologias e regras de tipologia prontas para uso estão disponíveis no Campaign Standard. Dependendo das suas necessidades, você também pode criar novas regras e adicioná-las a tipologias existentes ou novas para vincular às suas mensagens.

As etapas para criar e aplicar uma tipologia às mensagens são:

1. Criar regras de tipologia (consulte [esta seção](../../sending/using/managing-typology-rules.md#creating-a-typology-rule)).
1. Create a typology and reference the rules you created into it (see [this section](../../sending/using/managing-typologies.md#creating-a-typology)).
1. Configure seu delivery para usar a tipologia criada (consulte [esta seção](../../sending/using/managing-typologies.md#applying-typologies-to-messages)).
1. Durante a preparação da mensagem, os perfis são excluídos quando o critério é atendido. Você pode verificar logs para monitorar exclusões.
