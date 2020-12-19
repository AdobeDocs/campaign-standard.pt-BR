---
solution: Campaign Standard
product: campaign
title: Ler público-alvo
description: A atividade Read audience permite recuperar um público-alvo para refiná-lo aplicando condições de filtragem adicionais.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 87%

---


# Ler público-alvo{#read-audience}

## Descrição {#description}

![](assets/prefill.png)

A atividade **[!UICONTROL Read audience]** permite recuperar um público-alvo para refiná-lo aplicando condições de filtragem adicionais.

## Contexto de uso {#context-of-use}

A atividade **[!UICONTROL Read audience]** é uma versão mais simples da atividade **[!UICONTROL Query]** criada para os casos em que você precisa apenas selecionar um público-alvo existente.

**Tópicos relacionados**

* [Caso de uso: União em duas audiências refinadas](../../automating/using/union-on-two-refined-audiences.md)
* [Caso de uso: Reconciliar uma audiência de arquivo com o banco de dados](../../automating/using/reconcile-file-audience-with-database.md)

## Configuração {#configuration}

1. Solte uma atividade **[!UICONTROL Read audience]** no seu fluxo de trabalho.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Selecione o público-alvo que deseja recuperar na guia **[!UICONTROL Properties]**.

   Você pode recuperar públicos-alvo dos seguintes tipos: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** e **[!UICONTROL Experience Cloud]**. Para saber mais sobre tipos de público-alvo, consulte a documentação sobre [Públicos-alvo](../../audiences/using/about-audiences.md).

   A opção **[!UICONTROL Use a dynamic audience]** permite definir o nome do público-alvo de direcionamento com base nas variáveis de eventos do fluxo de trabalho. Para obter mais informações, consulte a seção [this page](../../automating/using/customizing-workflow-external-parameters.md).

   ![](assets/readaudience_activity1.png)

1. Para aplicar uma outra filtragem ao público-alvo selecionado, adicione condições usando a guia **[!UICONTROL Source filtering]** da atividade.

   Para saber mais sobre como criar condições de filtragem, consulte a documentação [Criação de consultas](../../automating/using/editing-queries.md#creating-queries).

1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.
