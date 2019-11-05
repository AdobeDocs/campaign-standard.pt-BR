---
title: Práticas recomendadas para fluxos de trabalho
description: Saiba como aplicar as práticas recomendadas aos seus fluxos de trabalho.
page-status-flag: nunca ativado
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: fluxo de trabalho geral-operação
context-tags: fluxo de trabalho,visão geral;fluxo de trabalho,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Práticas recomendadas do fluxo de trabalho{#workflow-best-practices}

Com o Adobe Campaign, você pode configurar todos os tipos de fluxo de trabalho para executar um grande escopo de tarefas. No entanto, ao projetar e executar seus fluxos de trabalho, é necessário ter muita cautela, pois uma implementação ruim pode levar a problemas de desempenho, erros e plataforma. Você pode encontrar abaixo uma lista de práticas recomendadas e dicas para solução de problemas.

>[!NOTE]
>
>O design e a execução do fluxo de trabalho devem ser executados por um usuário avançado do Adobe Campaign.

## Nomeação{#naming}

Para facilitar a solução de problemas do fluxo de trabalho, a Adobe recomenda nomear e rotular seus fluxos de trabalho explicitamente. Preencha o campo de descrição do fluxo de trabalho para resumir o processo a ser executado para que o operador possa entendê-lo facilmente.
Se o fluxo de trabalho for parte de um processo que envolve vários fluxos de trabalho, você poderá usar números ao inserir um rótulo para solicitar com clareza.

Por exemplo:

* 001 – Importar – Importar recipients
* 002 – Importar – Importar vendas
* 003 – Importar – Importar detalhes de vendas
* 010 – Exportar – Exportar logs de deliveries
* 011 – Exportar – Exportar logs de rastreamento

## Fluxos de trabalho duplicados{#duplicating-workflows}

É possível duplicar fluxos de trabalho. No **[!UICONTROL Marketing Activities]**, passe o mouse sobre o fluxo de trabalho e clique em **[!UICONTROL Duplicate element]**. Após a duplicação, as modificações do fluxo de trabalho não são transferidas para a cópia do fluxo de trabalho. A cópia do fluxo de trabalho pode ser editada.

![](assets/duplicating_workflow.png)

## Execução{#execution}

### Número de fluxos de trabalho

Por padrão, recomendamos não executar mais de 20 execuções de fluxos de trabalho ativos simultaneamente. Após atingir esse limite, os fluxos de trabalho serão enfileirados para não afetar os desempenhos. Da mesma forma, a Adobe recomenda que você espalhe sua execução de fluxo de trabalho ao longo do tempo.
Em contextos específicos, talvez seja necessário executar mais de 20 fluxos de trabalho. Não se aplica a fluxos de trabalho que aguardam uma execução programada.  Em caso positivo, verifique os casos de uso com um especialista do Campaign e entre em contato com o Atendimento ao cliente da Adobe para aumentar o limite.

### Frequência

Um fluxo de trabalho não pode ser executado automaticamente com mais de uma vez a cada dez minutos.
A frequência de repetição da atividade não pode ser inferior a 10 minutos. Se a frequência de repetição for definida como 0 (também o valor padrão), essa opção não será considerada e o fluxo de trabalho será executado de acordo com a frequência de execução.

### Fluxos de trabalho pausados

Os fluxos de trabalho que estão em estado de pausa ou de falha há mais de 7 dias são interrompidos para consumir menos espaço em disco. A tarefa de limpeza é exibida nos registros do fluxo de trabalho.

### Transições

Um fluxo de trabalho que contém transições não terminadas ainda pode ser executado: ela gerará uma mensagem de aviso e o fluxo de trabalho pausará quando chegar à transição, mas não gerará um erro. Também é possível iniciar um fluxo de trabalho sem um design finalizado e concluí-lo conforme você avança.

Para obter mais informações, consulte [Executando fluxos de trabalho](../../automating/using//executing-a-workflow.md).

## Activity{#activity}

### Design do fluxo de trabalho

Para garantir que o fluxo de trabalho termine corretamente, use um **[!UICONTROL End activity]**. Evite deixar a última transição de um fluxo de trabalho por conta própria.

Para acessar a exibição detalhada das transições, marque a **[!UICONTROL Keep interim results]** opção na seção Execução das propriedades do fluxo de trabalho.

>[!CAUTION]
>
>Essa opção consome muito espaço em disco e foi projetada para ajudá-lo a criar um fluxo de trabalho e garantir a configuração e o comportamento adequados. Deixe-o desmarcado em instâncias de produção.

![](assets/keep_interim_best_practices.png)


### Atividades de rotulagem{#activity-labeling}

Ao desenvolver seu fluxo de trabalho, um nome é gerado para cada atividade, como para todos os objetos do Adobe Campaign. Embora o nome de uma atividade seja gerado pela ferramenta e não possa ser editado, recomendamos rotular com um nome explícito ao configurá-la.

### Duplicação de atividades{#activity-duplicating}

Para duplicar atividades existentes, é possível usar copiar e colar. Desta forma, você mantém as configurações originalmente definidas. Para obter mais informações, consulte Atividades [de fluxo de trabalho](../../automating/using/workflow-interface.md)duplicadas.

###  Atividade do agendador{#acheduler-activity}

When building your workflow, only use one **[!UICONTROL Scheduler activity]** per branch. Se a mesma ramificação de um workflow tiver vários schedulers (vinculados uns aos outros), o número de tarefas a serem executadas será multiplicado exponencialmente, o que irá sobrecarregar consideravelmente o banco de dados.

Você pode visualizar as próximas dez execuções dos fluxos de trabalho clicando em **[!UICONTROL Preview next executions]**.

![](assets/preview_scheduler.png)

Para obter mais informações, consulte a atividade [do](../../automating/using/scheduler.md)Agendador.

## Chamada de fluxo de trabalho com parâmetros{#workflow-with-parameters}

Certifique-se de que o nome e o número de parâmetros sejam idênticos ao definido ao chamar o fluxo de trabalho (consulte [Definição dos parâmetros ao chamar o fluxo de trabalho](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)). Os tipos de parâmetros também devem ser consistentes com os valores esperados.

Verifique se todos os parâmetros foram declarados no **[!UICONTROL External signal activity]**. Caso contrário, ocorrerá um erro ao executar a atividade.

Para obter mais informações, consulte [Chamar um fluxo de trabalho com parâmetros](../../automating/using/calling-a-workflow-with-external-parameters.md)externos.

## Exportação de pacotes{#exporting-packages}

Para exportar pacotes, os recursos exportados não devem conter IDs padrão. Portanto, as IDs de recursos exportáveis devem ser alteradas usando um nome diferente dos modelos fornecidos como padrão pelo Adobe Campaign Standard.
Para obter mais informações, consulte [Gerenciamento de pacotes](../../automating/using/managing-packages.md).

## Exportar listas{#exporting-lists}

A opção de lista de exportação permite exportar um máximo de 100.000 linhas por padrão e definidas pela opção **** Nms_ExportListLimit. Essa opção pode ser gerenciada pelo administrador funcional, em **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]**.
Para obter mais informações, consulte [Exportar listas](../../automating/using/exporting-lists.md).

## Solução de problemas{#workflow-troubleshooting}

O Adobe Campaign oferece vários logs para entender melhor seus problemas de fluxo de trabalho.

### Uso de logs de fluxo de trabalho{#using-workflow-logs}

Você pode acessar logs de fluxo de trabalho para monitorar a execução de suas atividades. Indica as operações efetuadas e os erros de execução por ordem cronológica. A guia Logs consiste no histórico da execução de todas ou algumas atividades selecionadas.
A guia Tarefas detalha a sequência de execução das atividades. Para obter mais informações sobre uma atividade, clique em uma tarefa.
Para obter mais informações, consulte [Monitoramento da execução](../../automating/using/executing-a-workflow.md#monitoring)do fluxo de trabalho.

#### Troubleshooting data management activities{#troubleshooting-data-management-activities}

É possível analisar consultas SQL na guia Log.

1. Na área de trabalho do fluxo de trabalho, clique em **[!UICONTROL Edit properties]**.
1. Em **[!UICONTROL General]** &gt; **[!UICONTROL Execution]**, verifique as opções **[!UICONTROL Save SQL queries in the log]** e **[!UICONTROL Execute in the engine]** e clique em **[!UICONTROL Confirm]**.

**Para ver consultas SQL no Log:**
1. Click **[!UICONTROL Log and Tasks]**.
1. Na **[!UICONTROL Logs]** guia, abra o **[!UICONTROL Search]** painel.
1. Cheque **[!UICONTROL Display SQL logs only]**.

A consulta é exibida na **[!UICONTROL Message]** coluna dos logs.

### Uso de registros de entrega{#using-delivery-logs}

Os registros de entrega permitem monitorar o sucesso de suas entregas. Os logs de exclusão retornam mensagens excluídas durante a preparação do envio. Os logs de envio fornecem o status da entrega para cada perfil.
Para obter mais informações, consulte [Entendendo falhas](../../sending/using/understanding-delivery-failures.md)de entrega.

### Uso de alertas de entrega{#delivery-alerting}

O recurso de alerta Entrega é um sistema de gerenciamento de alertas que permite que um grupo de usuários receba automaticamente notificações contendo informações sobre a execução de suas entregas.
Para obter mais informações, consulte Alerta de [entrega](../../sending/using/receiving-alerts-when-failures-happen.md).

**Tópicos relacionados:**

* [Gerenciamento de erros](../../automating/using/executing-a-workflow.md#error-management)
