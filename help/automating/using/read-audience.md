---
title: Ler público-alvo
description: A atividade Ler audiência permite recuperar uma audiência existente e refiná-la aplicando condições de filtragem adicionais.
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 3%

---


# Ler público-alvo{#read-audience}

## Descrição {#description}

![](assets/prefill.png)

A **[!UICONTROL Read audience]** atividade permite recuperar uma audiência existente e refiná-la aplicando condições de filtragem adicionais.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Read audience]** atividade é uma versão mais simples da **[!UICONTROL Query]** atividade projetada para casos em que você precisa apenas selecionar uma audiência existente.

**Tópicos relacionados**

* [Caso de uso: União em duas audiências refinadas](../../automating/using/union-on-two-refined-audiences.md)
* [Caso de uso: Reconciliar uma audiência de arquivo com o banco de dados](../../automating/using/reconcile-file-audience-with-database.md)

## Configuração {#configuration}

1. Solte uma **[!UICONTROL Read audience]** atividade em seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Selecione a audiência que deseja recuperar na **[!UICONTROL Properties]** guia.

   Você pode recuperar audiências dos seguintes tipos: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** e **[!UICONTROL Experience Cloud]**. Para obter mais informações sobre tipos de audiência, consulte a documentação do [Audiência](../../audiences/using/about-audiences.md) .

   A **[!UICONTROL Use a dynamic audience]** opção permite que você defina o nome da audiência como público alvo com base nas variáveis de eventos do fluxo de trabalho. Para obter mais informações, consulte a seção [Personalizar atividades com variáveis](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) de eventos.

   ![](assets/readaudience_activity1.png)

1. Se desejar aplicar filtragem adicional à audiência selecionada, adicione condições por meio da guia **[!UICONTROL Source filtering]** da atividade.

   Para obter mais informações sobre como criar condições de filtragem, consulte a documentação [Criação de query](../../automating/using/editing-queries.md#creating-queries) .

1. Confirme a configuração da atividade e salve o fluxo de trabalho.
