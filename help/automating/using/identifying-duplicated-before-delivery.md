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
TQID: 'https://experienceleague.adobe.com/4t0TujgM3kHTT36-Gy2lmiVQIRMy3OeChAw-Xx5MnWY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
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
