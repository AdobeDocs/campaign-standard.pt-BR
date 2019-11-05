---
title: '"Caso de uso do fluxo de trabalho: Criando entregas na data de criação do perfil"'
description: '"Caso de uso do fluxo de trabalho: Criando entregas na data de criação do perfil"'
page-status-flag: nunca ativado
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: 'atividades de execução '
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: fluxo de trabalho,use-case,query
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Caso de uso do fluxo de trabalho: Criar entregas na data de criação dos perfis {#creation-date-query}

Você pode enviar uma oferta por email no aniversário da criação do perfil do cliente.

1. Em **[!UICONTROL Marketing Activities]**, clique **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**.

## Criando uma atividade do Agendador {#creating-a-scheduler-activity}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**, arraste e solte um **[!UICONTROL Scheduler activity]**.
1. Clique duas vezes na atividade.
1. Configure a execução da entrega.
1. Em **[!UICONTROL Execution frequency]**, selecione **[!UICONTROL Daily]**.
1. Selecione um **[!UICONTROL Time]** e a execução **[!UICONTROL Repetition frequency]** do seu fluxo de trabalho.
1. Selecione uma **[!UICONTROL Start]** data e **[!UICONTROL Expiration]** para seu fluxo de trabalho.
1. Confirme sua atividade e salve seu fluxo de trabalho.

>[!NOTE]
>
>Para iniciar seu fluxo de trabalho em um fuso horário específico, na **[!UICONTROL Execution options]** guia, configure o fuso horário para seu agendador no **[!UICONTROL Time zone]** campo.

![](assets/time_zone.png)

## Criando uma atividade de consulta {#creating-a-query-activity}

1. Para selecionar destinatários, arraste e solte um **[!UICONTROL Query activity]** e clique nele duas vezes.
1. Adicione **[!UICONTROL Profiles]** e selecione **[!UICONTROL no longer contact by email]** com o valor **[!UICONTROL no]**.

### Recuperar perfis criados no mesmo dia da execução {#retriving-profiles-created-on-the-same-day}

1. Em **[!UICONTROL Profile]**, arraste e solte o **[!UICONTROL Created]** campo. e clique em **[!UICONTROL Advanced Mode]**.
   ![](assets/advanced_mode.png)
1. No **[!UICONTROL list of functions]**, clique duas vezes **[!UICONTROL Day]** no **[!UICONTROL Date]** nó.
1. Em seguida, insira o campo **[!UICONTROL Created]** como argumento.
1. Selecione **[!UICONTROL equals to (=)]** como operador.
1. Para Valor, selecione **[!UICONTROL Day]** no **[!UICONTROL Date]** nó no **[!UICONTROL List of functions]**.
1. Insira a **[!UICONTROL GetDate()]** função como argumento.

Você recuperou os perfis cujo dia de criação é igual ao dia atual.

Você deve acabar com:

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

Click **[!UICONTROL Confirm]**.

### Recuperar perfis criados no mesmo mês que o mês de execução{#retriving-profiles-created-on-the-same-month}

1. No **[!UICONTROL Query]** editor, selecione a primeira consulta e duplique-a.
1. Abra a duplicata.
1. Substituir **[!UICONTROL Day]** por **[!UICONTROL Month]** na consulta.
1. Click **[!UICONTROL Confirm]**.

![](assets/month_rule.png)

Você deve acabar com isso:

``` Month(@created) = Month(GetDate()) ```

A consulta final é exibida:

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## Creating an Email delivery{#creating-an-email-delivery}

1. Arraste e solte uma entrega de email.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) para editar.
1. Selecione **[!UICONTROL Recurring email]** e clique em **[!UICONTROL Next]**.
1. Selecione um modelo de email e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do email e clique em **[!UICONTROL Next]**.
1. Para criar o layout do seu email, clique em **[!UICONTROL Email Designer]**.
1. Insira elementos ou selecione um modelo existente.
1. Personalize seu email usando campos e links.
Para obter mais informações, consulte a [criação de um email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Clique **[!UICONTROL Preview]** para verificar seu layout.
1. Click **[!UICONTROL Save]**.

**Tópicos relacionados:**

* [Consulta](../../automating/using/query.md)
* [Agendador](../../automating/using/scheduler.md)
* [Entrega por email](../../automating/using/email-delivery.md)
* [Canal de email](../../channels/using/creating-an-email.md)
