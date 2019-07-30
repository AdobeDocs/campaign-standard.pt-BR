---
title: Práticas recomendadas de fluxos de trabalho
seo-title: Práticas recomendadas de fluxos de trabalho
description: Práticas recomendadas de fluxos de trabalho
seo-description: Saiba mais sobre as práticas recomendadas a serem aplicadas aos seus fluxos de trabalho.
page-status-flag: nunca ativado
uuid: ff 02 b 74 e -53 e 8-49 c 6-bf 8 e -0 c 729 eaa 7 d 25
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: fluxo de trabalho-geral-operação
context-tags: fluxo de trabalho, visão geral; fluxo de trabalho, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e02ca92032c298fe1b5dbc7094de201d0a106be5

---


# Workflow best practices{#workflow-best-practices}

Com o Adobe Campaign, você pode configurar todos os tipos de fluxo de trabalho para executar um grande escopo das tarefas. No entanto, ao criar e executar fluxos de trabalho, você precisa ser muito cauteloso, pois uma implementação incorreta pode resultar em desempenhos incorretos, erros e problemas de plataforma. Você pode encontrar abaixo uma lista das práticas recomendadas e dicas de solução de problemas.

>[!NOTE]
>
>O design e a execução do fluxo de trabalho devem ser executados por um usuário avançado do Adobe Campaign.

## Naming{#naming}

Para facilitar a solução de problemas de fluxo de trabalho, a Adobe recomenda nomear e rotular seus fluxos de trabalho explicitamente. Preencha o campo de descrição do fluxo de trabalho para resumir o processo a ser executado para que o operador possa entendê-lo facilmente.
Se o fluxo de trabalho fizer parte de um processo envolvendo vários fluxos de trabalho, você poderá usar números ao digitar um rótulo para ordená-los claramente.

Por exemplo:

* 001 - Importar - Importar destinatários
* 002 - Importar - Importar vendas
* 003 - Importar - Importar detalhes de vendas
* 010 - Exportar - Exportar registros de entrega
* 011 - Exportar - Exportar registros de rastreamento

## Duplicating workflows{#duplicating-workflows}

Você pode duplicar fluxos de trabalho. In the **[!UICONTROL Marketing Activities]**, hover over the workflow and click **[!UICONTROL Duplicate element]**. Após a duplicação, as modificações do fluxo de trabalho não são transferidas para a cópia do fluxo de trabalho. A cópia do fluxo de trabalho pode ser editada.

![](assets/duplicating_workflow.png)

## Execution{#execution}

### Número de fluxos de trabalho

Por padrão, recomendamos não executar mais de 20 fluxos de trabalho ativos simultaneamente. Depois de atingir esse limite, os fluxos de trabalho serão colocados em fila para não afetar o desempenho. Da mesma forma, a Adobe recomenda que você distribua a sua execção do fluxo de trabalho ao longo do tempo.
Em contextos específicos, talvez seja necessário executar mais de 20 fluxos de trabalho. Ela não se aplica aos fluxos de trabalho que aguardam uma execução programada. Em caso positivo, você precisa verificar os casos de uso com um especialista da campanha e entrar em contato com o Atendimento ao cliente da Adobe para aumentar o limite.

### Frequência

Um fluxo de trabalho não pode ser executado automaticamente mais de uma vez a cada dez minutos.
A frequência de repetição da atividade não pode ser inferior a 10 minutos. Se a frequência de repetição for definida em 0 (também o valor padrão), essa opção não será levada em consideração e o fluxo de trabalho será executado de acordo com a frequência de execução.

### Fluxos de trabalho pausados

Os fluxos de trabalho que foram pausados ou reprovados por mais de 7 dias são interrompidos para consumir menos espaço em disco. A tarefa de limpeza é exibida nos registros de fluxo de trabalho.

### Transições

Um fluxo de trabalho contendo transições não finalizadas ainda pode ser executado: gerará uma mensagem de aviso e o fluxo de trabalho pausará uma vez que chegar à transição, mas não gerará um erro. Também é possível iniciar um fluxo de trabalho sem concluir o design e concluir o processo conforme você passa.

For more information, refer to [Executing workflows](../../automating/using//executing-a-workflow.md).

## Activity{#activity}

### Design de fluxo de trabalho

To ensure that the workflow ends properly, use an **[!UICONTROL End activity]**. Evite deixar a última transição de um fluxo de trabalho sozinho.

To access the detail view of the transitions, check the **[!UICONTROL Keep interim results]** option in the Execution section of the workflow properties.

>[!CAUTION]
>
>Essa opção consome muito espaço em disco e é projetada para ajudar a criar um fluxo de trabalho e garantir a configuração e o comportamento adequados. Deixe desmarcada em instâncias de produção.

![](assets/keep_interim_best_practices.png)


### Labelling activities{#activity-labeling}

Ao desenvolver seu fluxo de trabalho, um nome é gerado para cada atividade, como para todos os objetos do Adobe Campaign. Embora o nome de uma atividade seja gerado pela ferramenta e não possa ser editado, recomendamos rotulá-lo com um nome explícito ao configurá-lo.

### Duplicating activities{#activity-duplicating}

Para duplicar atividades existentes, você pode usar a cópia de cópia. Dessa forma, você mantém as configurações definidas originalmente. For more information, refer to [Duplicating workflow activities](../../automating/using/workflow-interface.md).

### Scheduler activity{#acheduler-activity}

When building your workflow, only use one **[!UICONTROL Scheduler activity]** per branch. Se o mesmo ramo de um fluxo de trabalho tiver vários agendadores (vinculados entre si), o número de tarefas a serem executadas será multiplicado exponencialmente, o que sobrecarregaria consideravelmente o banco de dados.

You can preview the next ten executions of your workflows by clicking **[!UICONTROL Preview next executions]**.

![](assets/preview_scheduler.png)

For more information, refer to [Scheduler activity](../../automating/using/scheduler.md).

## Calling workflow with parameters{#workflow-with-parameters}

Make sure that the name and number of parameters are identical to what is defined when calling the workflow (see [Defining the parameters when calling the workflow](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)). Os tipos de parâmetros também devem ser consistentes com os valores esperados.

Make sure that all the parameters have been declared in the **[!UICONTROL External signal activity]**. Caso contrário, ocorrerá um erro ao executar a atividade.

For more information, see [Calling a workflow with external parameters](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Exporting packages{#exporting-packages}

Para exportar pacotes, os recursos exportados não devem conter IDs padrão. Portanto, as IDs de recursos exportáveis devem ser alteradas usando um nome diferente dos modelos fornecidos como padrão pelo Adobe Campaign Standard.
For more information, see [Managing packages](../../automating/using/managing-packages.md).

## Exporting lists{#exporting-lists}

The export list option allows you to export a maximum of 100,000 lines by default and defined by the **Nms_ExportListLimit option**. This option can be managed by the functional administrator, under **Administration** &gt; **Application settings** &gt; **Options**.
For more information, see [Exporting lists](../../automating/using/exporting-lists.md).

## Troubleshooting{#workflow-troubleshooting}

O Adobe Campaign oferece vários logs para entender melhor seus problemas de fluxo de trabalho.

### Using workflow logs{#using-workflow-logs}

Você pode acessar logs de fluxo de trabalho para monitorar a execução de suas atividades. Ele indexa as operações realizadas e os erros de execução por ordem cronológica.
For more information, refer to [Monitoring workflow execution](../../automating/using/executing-a-workflow.md#monitoring).

### Using delivery logs{#using-delivery-logs}

Os logs de entrega permitem monitorar o sucesso das entregas. Os logs de exclusão retornam mensagens excluídas durante a preparação do envio. O envio de logs fornece o status da entrega para cada perfil.
For more information, refer to [Understanding delivery failures](../../sending/using/understanding-delivery-failures.md).

### Using delivery alerting{#delivery-alerting}

O recurso de alertas de entrega é um sistema de gerenciamento de alertas que permite que um grupo de usuários receba notificações automaticamente com informações sobre a execução de suas entregas.
For more information, refer to [Delivery alerting](../../sending/using/receiving-alerts-when-failures-happen.md).
