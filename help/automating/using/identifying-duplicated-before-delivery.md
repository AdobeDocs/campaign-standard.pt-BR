---
title: Identificação de duplicações antes de uma entrega
description: O exemplo a seguir ilustra uma desduplicação que possibilita excluir os duplicados de um público alvo antes de enviar um email. Isso significa evitar o envio de uma comunicação várias vezes para o mesmo perfil.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: a09b101b-f76f-4377-9854-1fcffaad4f9a
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 79%

---

# Identificação de duplicações antes de uma entrega {#identifying-duplicates-before-a-delivery}

O exemplo a seguir ilustra uma desduplicação que possibilita excluir os duplicados de um público alvo antes de enviar um email. Isso significa evitar o envio de uma comunicação várias vezes para o mesmo perfil.

Este fluxo de trabalho é composto por:

![](assets/deduplication_example_workflow.png)

* Uma [Consulta](../../automating/using/query.md) que permite definir o destino do email. Aqui, o fluxo de trabalho segmenta todos os perfis com idade entre 18 e 25 anos que estão no banco de dados do cliente por mais de um ano.

  ![](assets/deduplication_example_query.png)

* Uma atividade [Deduplication](../../automating/using/deduplication.md), que permite identificar os duplicados que vêm da consulta anterior. Neste exemplo, somente um registro é salvo para cada duplicado. Os duplicados são identificados usando o endereço de email. Isso significa que a entrega de email só pode ser enviada uma vez para cada endereço que esteja presente no direcionamento.

  O método de desduplicação selecionado é **[!UICONTROL Non-empty value]**. Esse método assegura que, entre os registros mantidos em caso de duplicados, seja dada prioridade àqueles em que foi fornecido o **nome**. Esse método se tornará mais coerente se o nome for usado nos campos de personalização do conteúdo do email.

  Além disso, uma transição adicional é incluída para manter os duplicados e poder listá-los.

  ![](assets/deduplication_example_dedup.png)

* Uma [Entrega de email](../../automating/using/email-delivery.md) colocada após a transição de saída principal da desduplicação.
* Uma atividade [Save audience](../../automating/using/save-audience.md) foi colocada após a transição adicional da desduplicação para salvar as duplicatas em um público-alvo **Duplicates**. Esse público-alvo pode ser reutilizado para excluir diretamente membros de cada entrega de email.
