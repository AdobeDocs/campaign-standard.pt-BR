---
title: Aguardar
description: A atividade Wait suspende temporariamente a execução de uma parte do fluxo de trabalho.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: wait,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 2ddc1b2b-0df5-4c91-a381-451cc094f2eb
TQID: 'https://experienceleague.adobe.com/PnbExucfP9-JLJA-0krFYAkYXJYExhHxEl7TRu5efec'
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
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 98%
---
# Aguardar{#wait}

## Descrição {#description}

![](assets/wait.png)

A atividade **[!UICONTROL Wait]** suspende temporariamente a execução de uma parte do fluxo de trabalho. Ela ativa a transição de saída após um atraso que pode variar de alguns segundos a vários meses, o que executa as atividades colocadas depois.

## Contexto de uso {#context-of-use}

A atividade **[!UICONTROL Wait]** é usada para permitir que um determinado período transcorra entre duas atividades que estão sendo executadas. Por exemplo, a espera de vários dias após uma atividade de entrega de email para depois analisar as aberturas e os cliques gerados durante esse período antes de executar qualquer operação de acompanhamento (email de lembrete, criação de público-alvo, etc.).

## Configuração {#configuration}

1. Arraste e solte uma atividade **[!UICONTROL Wait]** no seu fluxo de trabalho.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Especifique a **[!UICONTROL Duration]** da espera entre a ativação das transições de entrada e saída da atividade.

   Você pode inserir manualmente a duração ou usar o seletor disponível no campo.

   ![](assets/wait_duration.png)

1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.

## Exemplo {#example}

O exemplo a seguir ilustra a atividade **[!UICONTROL Wait]** em um caso de uso comum. Um convite é enviado por email para um evento. 24 horas após o envio, os logs de entrega do email são analisados e um email de lembrete é enviado para as pessoas que receberam o primeiro email, mas não se inscreveram.

O fluxo de trabalho é apresentado da seguinte forma:

![](assets/wait_example_workflow.png)

* Um primeiro **[!UICONTROL Query]** é direcionado aos perfis que receberão o convite por email.
* Um **[!UICONTROL Email delivery]** envia o convite pela primeira vez para os perfis selecionados.
* Uma atividade **[!UICONTROL Wait]** de 24 horas faz uma pausa entre o momento em que o convite foi enviado e o restante do fluxo de trabalho.
* Um segundo **[!UICONTROL Query]** é direcionado aos perfis que receberam o primeiro email, mas não clicaram no link de assinatura.
* Um segundo **[!UICONTROL Email delivery]** envia um lembrete do convite para as pessoas selecionadas.
