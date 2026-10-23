---
title: Início e término
description: As atividades Start e End permitem que você marque claramente o início e o término do fluxo de trabalho.
audience: automating
content-type: reference
topic-tags: execution-activities
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 1dfc547f-747d-403e-a5b7-a68f56191c71
TQID: 'https://experienceleague.adobe.com/JbfMoJzvulqLurUn904RKXvg2aqb74BTTwFpSNkL9MU'
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
source-wordcount: '274'
ht-degree: 97%
---
# Início e término{#start-and-end}

## Descrição {#description}

![](assets/start.png)

![](assets/end.png)

As atividades **[!UICONTROL Start]** e **[!UICONTROL End]** permitem que você marque claramente o início e o término do fluxo de trabalho.

## Contexto de uso {#context-of-use}

A execução de um fluxo de trabalho inicia com atividades sem transição de entrada e é interrompida quando não há mais tarefas em andamento. No entanto, você pode adicionar as atividades **[!UICONTROL Start]** e **[!UICONTROL End]** para marcar claramente os pontos de início e término de um fluxo de trabalho. Isso é útil principalmente para fluxos de trabalho relativamente complexos.

Como prática recomendada, use uma atividade **[!UICONTROL End]** em vez de deixar que a última transição de um fluxo de trabalho ocorra automaticamente para garantir que o fluxo de trabalho termine sem erros.

## Configuração {#configuration}

1. Arraste e solte uma atividade **[!UICONTROL Start]** ou **[!UICONTROL End]** no fluxo de trabalho.
1. Coloque a atividade **[!UICONTROL Start]** na frente de outras atividades, como consultas, e a atividade **[!UICONTROL End]** após uma série de atividades.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Você pode configurar o objeto **End** para que ele interrompa todas as tarefas em andamento do fluxo de trabalho, inclusive as que ainda não foram concluídas. Para isso, selecione a opção correspondente.
1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.

## Acionamento de outro fluxo de trabalho {#triggering-another-workflow}

Na guia **[!UICONTROL External signal]** de uma atividade **[!UICONTROL End]**, é possível acionar outro fluxo de trabalho. Consulte a seção [Sinal externo](../../automating/using/external-signal.md).

## Exemplo {#example}

O exemplo a seguir mostra como um fluxo de trabalho complexo é executado com uma atividade **[!UICONTROL Start]** e várias atividades **[!UICONTROL End]**. A caixa **[!UICONTROL Stop all tasks in progress]** foi marcada para a primeira atividade **[!UICONTROL End]**. Quando a tarefa correspondente for concluída, todo o fluxo de trabalho será interrompido: isso terá o mesmo efeito do botão ![](assets/stop_darkgrey-24px.png) (consulte a seção [Barra de ação](../../automating/using/workflow-interface.md#action-bar)).

![](assets/wkf_start_end_example.png)
