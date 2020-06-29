---
title: Identificação de duplicados antes de um delivery
description: O exemplo a seguir ilustra uma desduplicação-duplicada que permite excluir os duplicados de um público alvo antes de enviar um email. Isso significa que você evita enviar uma comunicação várias vezes para o mesmo perfil.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---


# Identificação de duplicados antes de um delivery {#identifying-duplicates-before-a-delivery}

O exemplo a seguir ilustra uma desduplicação-duplicada que permite excluir os duplicados de um público alvo antes de enviar um email. Isso significa que você evita enviar uma comunicação várias vezes para o mesmo perfil.

O fluxo de trabalho é composto de:

![](assets/deduplication_example_workflow.png)

* Um [Query](../../automating/using/query.md) que permite definir o público alvo do email. Aqui, o fluxo de trabalho público alvo todos os perfis com idade entre 18 e 25 anos que estão no banco de dados do cliente por mais de um ano.

   ![](assets/deduplication_example_query.png)

* Uma atividade [Desduplicação-duplicada](../../automating/using/deduplication.md) , que permite identificar os duplicados que vêm do query anterior. Neste exemplo, apenas um registro é salvo para cada duplicado. Os duplicados são identificados usando o endereço de email. Isso significa que o delivery de email só pode ser enviado uma vez para cada endereço de email que esteja presente na definição de metas.

   O método desduplicação-duplicado selecionado é **[!UICONTROL Non-empty value]**. Isso permite garantir que, entre os registros mantidos em caso de duplicados, seja dada prioridade àqueles em que foi fornecido o **nome** . Isso tornará mais coerente se o nome for usado nos campos de personalização do conteúdo do email.

   Além disso, uma transição extra é adicionada para manter os duplicados e ser capaz de lista.

   ![](assets/deduplication_example_dedup.png)

* Um delivery [de](../../automating/using/email-delivery.md) email colocado após a transição de saída principal do desduplicação-duplicado.
* Uma atividade [Salvar audiência](../../automating/using/save-audience.md) colocada após a transição adicional do desduplicação-duplicado para salvar os duplicados em uma audiência de **Duplicados** . Essa audiência pode ser reutilizada para excluir diretamente seus membros de cada delivery de email.
