---
title: Bifurcação
description: A atividade Fork permite criar transições de saída para iniciar várias atividades ao mesmo tempo.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: fork,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 1a5e1ecd-b3f1-4dbe-a816-12d27a3bc0f7
TQID: https://experienceleague.adobe.com/1-9VY3TjBBHAb-7bFikis3Ue5eWy5KXKSR4hXxXDLwc
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 213
ht-degree: 98%

---

# Bifurcação{#fork}

## Descrição {#description}

![](assets/fork.png)

A atividade **[!UICONTROL Fork]** permite criar transições de saída para iniciar várias atividades ao mesmo tempo.

## Contexto de uso {#context-of-use}

A atividade **[!UICONTROL Fork]** permite realizar várias atividades diferentes de maneira independente no mesmo fluxo de trabalho.

## Configuração {#configuration}

1. Arraste e solte uma atividade **[!UICONTROL Fork]** no seu fluxo de trabalho.
1. Conecte-a às outras atividades anteriores a ela, como consultas.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Especifique o número de transições de saída criando, excluindo ou duplicando-as. Você também pode atribuir um nome e um rótulo a elas.
1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.

## Exemplo {#example}

O exemplo a seguir mostra uma intersecção de duas atividades de consulta que segmenta perfis do banco de dados do Adobe Campaign, neste caso, mulheres morando em Paris. A atividade Fork, portanto, permite que você use várias atividades ao mesmo tempo: uma que salva o público-alvo para lembrar a população calculada, e outra que segmenta a população para enviar dois emails diferentes com um conteúdo direcionado para cada segmento. O primeiro email é enviado para mulheres parisienses entre 18 e 40 anos e outro para mulheres parisienses com mais de 40 anos.

![](assets/wkf_fork_example.png)
