---
title: Fork
description: A atividade de bifurcação permite criar transições de saída para iniciar várias atividades ao mesmo tempo.
page-status-flag: nunca ativado
uuid: e4eaf69b-84ee-4f79-8b80-99284697cd2c
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: atividades de execução
discoiquuid: f8ffe7af-e18c-4599-8fd0-fcd192565323
context-tags: garfo, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Fork{#fork}

## Descrição {#description}

![](assets/fork.png)

A **[!UICONTROL Fork]** atividade permite criar transições de saída para iniciar várias atividades ao mesmo tempo.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Fork]** atividade permite que você realize várias atividades diferentes independentemente dentro do mesmo fluxo de trabalho.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Fork]** atividade em seu fluxo de trabalho.
1. Conecte-o às outras atividades que vêm antes dele, como consultas.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Especifique o número de transições de saída criando, excluindo ou duplicando-as. Você também pode atribuir um nome e um rótulo a eles.
1. Confirme a configuração da atividade e salve o fluxo de trabalho.

## Exemplo {#example}

O exemplo a seguir mostra uma interseção de duas atividades de consulta que direcionam perfis do banco de dados do Adobe Campaign, neste caso mulheres que vivem em Paris. A atividade de garfo, portanto, permite que você use várias atividades ao mesmo tempo: uma que salva o público para lembrar a população calculada e outra que segmenta a população para enviar dois e-mails diferentes com um conteúdo direcionado para cada segmento. O primeiro email é enviado para mulheres parisienses entre 18 e 40 anos e outro para mulheres parisienses com mais de 40 anos.

![](assets/wkf_fork_example.png)

