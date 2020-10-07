---
title: Identificação de duplicações antes de um delivery
description: O exemplo a seguir ilustra uma desduplicação que possibilita excluir os duplicados de um público alvo antes de enviar um email. Isso significa evitar o envio de uma comunicação várias vezes para o mesmo perfil.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 78%

---


# Identificação de duplicações antes de um delivery {#identifying-duplicates-before-a-delivery}

O exemplo a seguir ilustra uma desduplicação que possibilita excluir os duplicados de um público alvo antes de enviar um email. Isso significa evitar o envio de uma comunicação várias vezes para o mesmo perfil.

Este fluxo de trabalho é composto por:

![](assets/deduplication_example_workflow.png)

* A [Query](../../automating/using/query.md) which allows you to define the target of the email. Aqui, o fluxo de trabalho segmenta todos os perfis com idade entre 18 e 25 anos que estão no banco de dados do cliente por mais de um ano.

   ![](assets/deduplication_example_query.png)

* A [Deduplication](../../automating/using/deduplication.md) activity, which allows you to identify the duplicates that come from the preceding query. Neste exemplo, somente um registro é salvo para cada duplicata. As duplicatas são identificadas usando o endereço de email. Isso significa que o delivery de email só pode ser enviado uma vez para cada endereço que esteja presente no direcionamento.

   O método de desduplicação selecionado é **[!UICONTROL Non-empty value]**. Esse método assegura que, entre os registros mantidos em caso de duplicatas, seja dada prioridade àqueles em que foi fornecido o **nome**. Esse método se tornará mais coerente se o nome for usado nos campos de personalização do conteúdo do email.

   Além disso, uma transição adicional é incluída para manter as duplicatas e poder listá-las.

   ![](assets/deduplication_example_dedup.png)

* An [Email delivery](../../automating/using/email-delivery.md) placed after the main outbound transition of the deduplication.
* A [Save audience](../../automating/using/save-audience.md) activity placed after the additional transition of the deduplication to save the duplicates in a **Duplicates** audience. Esse público-alvo pode ser reutilizado para excluir diretamente membros de cada delivery de email.
