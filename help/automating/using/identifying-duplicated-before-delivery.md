---
solution: Campaign Standard
product: campaign
title: Identificação de duplicações antes de um delivery
description: O exemplo a seguir ilustra uma desduplicação que possibilita excluir os duplicados de um público alvo antes de enviar um email. Isso significa evitar o envio de uma comunicação várias vezes para o mesmo perfil.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 78%

---


# Identificação de duplicações antes de um delivery {#identifying-duplicates-before-a-delivery}

O exemplo a seguir ilustra uma desduplicação que possibilita excluir os duplicados de um público alvo antes de enviar um email. Isso significa evitar o envio de uma comunicação várias vezes para o mesmo perfil.

Este fluxo de trabalho é composto por:

![](assets/deduplication_example_workflow.png)

* Um [Query](../../automating/using/query.md) que permite definir o público-alvo do email. Aqui, o fluxo de trabalho segmenta todos os perfis com idade entre 18 e 25 anos que estão no banco de dados do cliente por mais de um ano.

   ![](assets/deduplication_example_query.png)

* Uma atividade [Deduplication](../../automating/using/deduplication.md), que permite identificar os duplicados que vêm da query anterior. Neste exemplo, somente um registro é salvo para cada duplicata. As duplicatas são identificadas usando o endereço de email. Isso significa que o delivery de email só pode ser enviado uma vez para cada endereço que esteja presente no direcionamento.

   O método de desduplicação selecionado é **[!UICONTROL Non-empty value]**. Esse método assegura que, entre os registros mantidos em caso de duplicatas, seja dada prioridade àqueles em que foi fornecido o **nome**. Esse método se tornará mais coerente se o nome for usado nos campos de personalização do conteúdo do email.

   Além disso, uma transição adicional é incluída para manter as duplicatas e poder listá-las.

   ![](assets/deduplication_example_dedup.png)

* Um [Email delivery](../../automating/using/email-delivery.md) colocado após a transição de saída principal da desduplicação.
* Uma atividade [Save audience](../../automating/using/save-audience.md) colocada após a transição adicional da desduplicação para salvar as duplicatas em um público **Duplicates**. Esse público-alvo pode ser reutilizado para excluir diretamente membros de cada delivery de email.
