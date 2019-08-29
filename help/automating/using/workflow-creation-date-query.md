---
title: '" Caso de uso de fluxo de trabalho: Criação de entregas na data de criação do perfil "'
seo-title: '" Caso de uso de fluxo de trabalho: Criação de entregas na data de criação do perfil "'
description: '" Caso de uso de fluxo de trabalho: Criação de entregas na data de criação do perfil "'
seo-description: '" Caso de uso de fluxo de trabalho: Criação de entregas na data de criação do perfil "'
page-status-flag: nunca ativado
uuid: 396 a 3 de 1-6 ffa -4385-ac 9 f -15 fdeae 5 a 366
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: 'execução-atividades '
discoiquuid: 377821 e 6-69 f 8-41 cc-a 1 ad -8 a 2 f 5 ed 4 d 409
context-tags: fluxo de trabalho, caso de uso, consulta
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f57775ec88925d43046fe4162f2753c189d50c62

---


# Caso de uso do fluxo de trabalho: Criar entregas na data de criação dos perfis {#creation-date-query}

Você pode enviar uma oferta por email no aniversário da criação do perfil do cliente.

1. Em **[!UICONTROL Marketing Activities]**, clique **[!UICONTROL Create]** em e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique **[!UICONTROL Next]** em.
1. Insira as propriedades do fluxo de trabalho e clique **[!UICONTROL Create]** em.

## Criação de uma atividade programada {#creating-a-scheduler-activity}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**, arraste e solte a **[!UICONTROL Scheduler activity]**![](assets/scheduler_icon.png).
1. Clique duas vezes na atividade.
1. Configure a execução da entrega.
1. Em **[!UICONTROL Execution frequency]**, selecione **[!UICONTROL Daily]**.
1. Selecione a **[!UICONTROL Time]** e a **[!UICONTROL Repetition frequency]** execução do seu fluxo de trabalho.
1. Selecione **[!UICONTROL Start]** uma data e **[!UICONTROL Expiration]** seu fluxo de trabalho.

>[!NOTE]
>
>Para iniciar o fluxo de trabalho em um fuso horário específico, na **[!UICONTROL Execution options]** guia, configure o fuso horário do seu programador no **[!UICONTROL Time zone]** campo.

![](assets/time_zone.png)

1. Confirme sua atividade e salve seu fluxo de trabalho.

## Criação de uma atividade de consulta {#creating-a-query-activity}

1. Para selecionar destinatários, arraste e solte a **[!UICONTROL Query activity]** e clique duas vezes nele.
1. Adicione **[!UICONTROL Profiles]** e selecione **[!UICONTROL no longer contact by email]** com o valor **[!UICONTROL no]**.

### Recuperar perfis criados no mesmo dia do dia da execução {#retriving-profiles-created-on-the-same-day}

1. Em **[!UICONTROL Profile]**, arraste e solte o **[!UICONTROL Created]** campo. e clique **[!UICONTROL Advanced Mode]**em.
   ![](assets/advanced_mode.png)
1. No **[!UICONTROL list of functions]**, clique duas vezes **[!UICONTROL Day]** no **[!UICONTROL Date]** nó.
1. Em seguida, insira o campo **[!UICONTROL Created]** como argumento.
1. Selecione **[!UICONTROL equals to (=)]** o operador.
1. Em Valor, selecione **[!UICONTROL Day]** do **[!UICONTROL Date]** nó no **[!UICONTROL List of functions]**.
1. Insira **[!UICONTROL GetDate()]** a função como argumento.

Você recuperou os perfis que o dia de criação é igual ao dia atual.

Você deve terminar com:

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

Click **[!UICONTROL Confirm]**.

### Recuperar perfis criados no mesmo mês do mês de execução{#retriving-profiles-created-on-the-same-month}

1. No **[!UICONTROL Query]** editor, selecione a primeira consulta e duplique-a.
1. Abra a duplicata.
1. Substitua **[!UICONTROL Day]** por **[!UICONTROL Month]** na consulta.
Você deve acabar com isso:

``` Month(@created) = Month(GetDate()) ```

1. Click **[!UICONTROL Confirm]**.

![](assets/month_rule.png)

A consulta final é exibida:

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## Criação de uma entrega por email{#creating-an-email-delivery}

1. Arraste e solte uma entrega de email.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) editar.
1. Selecione **[!UICONTROL Recurring email]** e clique **[!UICONTROL Next]** em.
1. Selecione um modelo de e-mail e clique **[!UICONTROL Next]** em.
1. Insira as propriedades e clique **[!UICONTROL Next]** em.
1. Para criar o layout de seu email, clique **[!UICONTROL Email Designer]** em.
1. Inserir elementos ou selecionar um modelo existente.
1. Personalize seu email usando campos e links.
Para obter mais informações, consulte [Criar um email](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch).
1. Clique **[!UICONTROL Preview]** em para verificar o layout.
1. Click **[!UICONTROL Save]**.

**Tópicos relacionados:**

* [Consulta](../../automating/using/query.md)
* [Programador](../../automating/using/scheduler.md)
* [Entrega por email](../../automating/using/email-delivery.md)
* [Canal de email](../../channels/using/creating-an-email.md)
