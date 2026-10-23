---
title: AND-join
description: A atividade AND-join permite sincronizar várias ramificações de execução de um fluxo de trabalho.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: andjoin,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: b03c6df3-0104-4900-9468-46824d62e0a6
TQID: 'https://experienceleague.adobe.com/ydaYzPE9SwLuC-d4nVSaFgLLp-R0Kuceq7hUI89aN1Y'
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
source-wordcount: '181'
ht-degree: 98%
---
# AND-join{#and-join}

## Descrição {#description}

![](assets/and_join.png)

A atividade **[!UICONTROL AND-join]** permite sincronizar várias ramificações de execução de um fluxo de trabalho.

## Contexto de uso {#context-of-use}

A atividade **[!UICONTROL AND-join]** só acionará a transição de saída depois que todas as transições de entrada estiverem ativadas, ou seja, depois que todas as atividades anteriores estiverem concluídas.

## Configuração {#configuration}

1. Solte várias atividades, como consultas, no fluxo de trabalho para formar pelo menos duas ramificações de execução diferentes.
1. Arraste e solte uma atividade **[!UICONTROL AND-join]** no seu fluxo de trabalho.
1. Conecte-a depois das duas ramificações diferentes que você quer sincronizar.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Selecione o conjunto principal a ser mantido na transição de saída. Se você não selecionar nenhum conjunto, uma população aleatória será enviada da atividade.
1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.

## Exemplo {#example}

O exemplo a seguir mostra duas ramificações de fluxo de trabalho antes de elas serem unidas à atividade **[!UICONTROL AND-join]**. A extração de arquivos só poderá ocorrer quando as três transições de entrada da atividade **[!UICONTROL AND-join]** estiverem habilitadas.

![](assets/wkf_and-join_example.png)
