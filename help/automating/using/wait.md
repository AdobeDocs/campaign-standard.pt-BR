---
title: Aguardar
description: A atividade Espera suspende temporariamente a execução de uma parte de um fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: atividades de execução
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: wait,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Aguardar{#wait}

## Descrição {#description}

![](assets/wait.png)

A **[!UICONTROL Wait]** atividade suspende temporariamente a execução de uma parte de um fluxo de trabalho. Ela ativa sua transição de saída após um atraso que pode variar de alguns segundos a vários meses, o que executa as atividades colocadas depois.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Wait]** atividade é usada para permitir que um determinado tempo passe entre duas atividades que estão sendo executadas. Por exemplo, para aguardar vários dias após uma atividade de entrega de email, analise as aberturas e cliques gerados durante esse período antes de executar qualquer operação de acompanhamento (email de lembrete, criação de um público-alvo etc.).

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Wait]** atividade em seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Especifique o intervalo **[!UICONTROL Duration]** de espera entre quando as transições de entrada e de saída da atividade são ativadas.

   Você pode inserir manualmente a duração ou usar o seletor disponível no campo.

   ![](assets/wait_duration.png)

1. Confirme a configuração da atividade e salve o fluxo de trabalho.

## Exemplo {#example}

O exemplo a seguir ilustra a **[!UICONTROL Wait]** atividade em um caso de uso típico. Um convite por email para um evento é enviado. 24 horas após o envio, os registros de entrega de email são analisados e um email de lembrete é enviado para as pessoas que receberam o primeiro email, mas não se inscreveram.

O fluxo de trabalho é apresentado da seguinte forma:

![](assets/wait_example_workflow.png)

* Um primeiro **[!UICONTROL Query]** direciona os perfis que serão enviados para o convite por email.
* Um **[!UICONTROL Email delivery]** envia o convite pela primeira vez para os perfis selecionados.
* Uma **[!UICONTROL Wait]** atividade de 24h faz uma pausa entre o momento em que o convite foi enviado e o restante do fluxo de trabalho.
* Um segundo **[!UICONTROL Query]** direciona os perfis que receberam o primeiro email, mas não clicaram no link de assinatura dentro.
* Um segundo **[!UICONTROL Email delivery]** envia um lembrete do convite às pessoas selecionadas.

