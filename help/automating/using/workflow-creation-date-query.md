---
title: Criação de delivery na data de criação do perfil
description: Este caso de uso mostra como criar delivery na data de criação do perfil.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 2%

---


# Creating deliveries on profiles&#39; creation date {#creation-date-query}

Você pode enviar uma oferta por email no aniversário da criação do perfil do cliente.

1. Em **[!UICONTROL Marketing Activities]**, clique **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**.

## Criação de uma atividade de Scheduler {#creating-a-scheduler-activity}

1. Em **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, arraste e solte uma atividade de [Scheduler](../../automating/using/scheduler.md) .
1. Duplo clique na atividade.
1. Configure a execução do seu delivery.
1. Em **[!UICONTROL Execution frequency]**, selecione **[!UICONTROL Daily]**.
1. Selecione um **[!UICONTROL Time]** e a execução **[!UICONTROL Repetition frequency]** do seu fluxo de trabalho.
1. Selecione uma **[!UICONTROL Start]** data e **[!UICONTROL Expiration]** para seu fluxo de trabalho.
1. Confirme sua atividade e salve seu fluxo de trabalho.

>[!NOTE]
>
>Para start do fluxo de trabalho em um fuso horário específico, na guia **[!UICONTROL Execution options]**, configure o fuso horário para o scheduler no **[!UICONTROL Time zone]** campo. Por padrão, o fuso horário selecionado é o definido nas propriedades do fluxo de trabalho (consulte [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md)).

![](assets/time_zone.png)

## Creating a Query activity {#creating-a-query-activity}

1. Para selecionar recipient, arraste e solte uma atividade de [Query](../../automating/using/query.md) e clique nele com o botão duplo.
1. Adicione **[!UICONTROL Profiles]** e selecione **[!UICONTROL no longer contact by email]** com o valor **[!UICONTROL no]**.

### Recuperando perfis criados no mesmo dia que o dia da execução {#retriving-profiles-created-on-the-same-day}

1. Em **[!UICONTROL Profile]**, arraste e solte o **[!UICONTROL Created]** campo. e clique em **[!UICONTROL Advanced Mode]**.
   ![](assets/advanced_mode.png)
1. No **[!UICONTROL list of functions]**, clique com o duplo **[!UICONTROL Day]** do **[!UICONTROL Date]** nó.
1. Em seguida, insira o campo **[!UICONTROL Created]** como argumento.
1. Selecione **[!UICONTROL equals to (=)]** como operador.
1. Para Valor, selecione **[!UICONTROL Day]** no **[!UICONTROL Date]** nó no **[!UICONTROL List of functions]**.
1. Insira a **[!UICONTROL GetDate()]** função como argumento.

Você recuperou os perfis cujo dia de criação é igual ao dia atual.

Você deve acabar com:

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

Clique em **[!UICONTROL Confirm]**.

### Recuperando perfis criados no mesmo mês que o mês de execução{#retriving-profiles-created-on-the-same-month}

1. No **[!UICONTROL Query]** editor, selecione o primeiro query e duplicado.
1. Abra o duplicado.
1. Substitua **[!UICONTROL Day]** por **[!UICONTROL Month]** no query.
1. Clique em **[!UICONTROL Confirm]**.

![](assets/month_rule.png)

Você deve acabar com isso:

``` Month(@created) = Month(GetDate()) ```

O query final exibe:

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## Creating an Email delivery{#creating-an-email-delivery}

1. Arraste e solte uma atividade de delivery [](../../automating/using/email-delivery.md) de e-mail.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) para editar.
1. Selecione **[!UICONTROL Recurring email]** e clique em **[!UICONTROL Next]**.
1. Selecione um modelo de email e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do email e clique em **[!UICONTROL Next]**.
1. Para criar o layout do seu email, clique em **[!UICONTROL Email Designer]**.
1. Insira elementos ou selecione um modelo existente.
1. Personalize seu email usando campos e links.
Para obter mais informações, consulte a [criação de um email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Clique **[!UICONTROL Preview]** para verificar seu layout.
1. Clique em **[!UICONTROL Save]**.

**Tópicos relacionados:**

* [Canal de email](../../channels/using/creating-an-email.md)
