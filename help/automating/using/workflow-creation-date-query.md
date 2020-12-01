---
solution: Campaign Standard
product: campaign
title: Criação de delivery na data de criação do perfil
description: Este caso de uso mostra como criar delivery na data de criação do perfil.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query
translation-type: tm+mt
source-git-commit: 45c80b5e6bf2169c5acf6eea70da9e2f130982c8
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 38%

---


# Criar deliveries na data de criação de perfis {#creation-date-query}

Você pode enviar uma oferta por email no aniversário da criação do perfil do cliente.

1. Em **[!UICONTROL Marketing Activities]**, clique em **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**.

## Criação de uma atividade do Scheduler {#creating-a-scheduler-activity}

1. Em **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, arraste e solte uma atividade [Scheduler](../../automating/using/scheduler.md).
1. Clique duas vezes na atividade.
1. Configure a execução do delivery.
1. Em **[!UICONTROL Execution frequency]**, selecione **[!UICONTROL Daily]**.
1. Selecione **[!UICONTROL Time]** e **[!UICONTROL Repetition frequency]** de execução para seu fluxo de trabalho.
1. Selecione uma data **[!UICONTROL Start]** e **[!UICONTROL Expiration]** para o seu fluxo de trabalho.
1. Confirme sua atividade e salve o fluxo de trabalho.

>[!NOTE]
>
>Para start do fluxo de trabalho em um fuso horário específico, na guia **[!UICONTROL Execution options]**, configure o fuso horário para o scheduler no campo **[!UICONTROL Time zone]**. Por padrão, o fuso horário selecionado é o definido nas propriedades do fluxo de trabalho (consulte [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md)).

![](assets/time_zone.png)

## Criação de uma atividade Query {#creating-a-query-activity}

1. Para selecionar recipient, arraste e solte uma atividade [Query](../../automating/using/query.md) e clique nela com o botão duplo.
1. Adicione **[!UICONTROL Profiles]** e selecione **[!UICONTROL no longer contact by email]** com o valor **[!UICONTROL no]**.

### Recuperando perfis criados no mesmo dia que o dia da execução {#retrieving-profiles-created-on-the-same-day}

1. Em **[!UICONTROL Profile]**, arraste e solte o campo **[!UICONTROL Created]**. e clique em **[!UICONTROL Advanced Mode]**.
   ![](assets/advanced_mode.png)
1. No nó **[!UICONTROL list of functions]**, clique com o duplo **[!UICONTROL Day]** no nó **[!UICONTROL Date]**.
1. Em seguida, insira o campo **[!UICONTROL Created]** como argumento.
1. Selecione **[!UICONTROL equals to (=)]** como operador.
1. Para Valor, selecione **[!UICONTROL Day]** no nó **[!UICONTROL Date]** em **[!UICONTROL List of functions]**.
1. Insira a função **[!UICONTROL GetDate()]** como argumento.

Você recuperou os perfis cujo dia de criação é igual ao dia atual.

Você deve acabar com:

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

Clique em **[!UICONTROL Confirm]**.

### Recuperando perfis criados no mesmo mês que o mês de execução{#retrieving-profiles-created-on-the-same-month}

1. No editor **[!UICONTROL Query]**, selecione o primeiro query e o duplicado.
1. Abra o duplicado.
1. Substitua **[!UICONTROL Day]** por **[!UICONTROL Month]** no query.
1. Clique em **[!UICONTROL Confirm]**.

![](assets/month_rule.png)

Você deve acabar com isso:

``` Month(@created) = Month(GetDate()) ```

O query final exibe:

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## Criação de um delivery de email{#creating-an-email-delivery}

1. Arraste e solte uma atividade [delivery de e-mail](../../automating/using/email-delivery.md).
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) para editar.
1. Selecione **[!UICONTROL Recurring email]** e clique em **[!UICONTROL Next]**.
1. Selecione um template de email e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do email e clique em **[!UICONTROL Next]**.
1. Para criar o layout do email, clique em **[!UICONTROL Email Designer]**.
1. Insira elementos ou selecione um template.
1. Personalize o email usando campos e links.
Para obter mais informações, consulte [Design de email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Clique em **[!UICONTROL Preview]** para verificar o layout.
1. Clique em **[!UICONTROL Save]**.

**Tópicos relacionados:**

* [Canal de email](../../channels/using/creating-an-email.md)
