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
source-git-commit: 3ed76cc48c94510b40e7a946031ec4331c6e0905

---


# Práticas recomendadas de fluxo de trabalho{#workflow-best-practices}

Com o Adobe Campaign, você pode configurar todos os tipos de fluxo de trabalho para executar um grande escopo das tarefas. No entanto, ao criar e executar fluxos de trabalho, você precisa ser muito cauteloso, pois uma implementação incorreta pode resultar em desempenhos incorretos, erros e problemas de plataforma. Você pode encontrar abaixo uma lista das práticas recomendadas e dicas de solução de problemas.

>[!NOTE]
>
>O design e a execução do fluxo de trabalho devem ser executados por um usuário avançado do Adobe Campaign.

## Nomeação{#naming}

Para facilitar a solução de problemas de fluxo de trabalho, a Adobe recomenda nomear e rotular seus fluxos de trabalho explicitamente. Preencha o campo de descrição do fluxo de trabalho para resumir o processo a ser executado para que o operador possa entendê-lo facilmente.
Se o fluxo de trabalho fizer parte de um processo envolvendo vários fluxos de trabalho, você poderá usar números ao digitar um rótulo para ordená-los claramente.

Por exemplo:

* 001 - Importar - Importar destinatários
* 002 - Importar - Importar vendas
* 003 - Importar - Importar detalhes de vendas
* 010 - Exportar - Exportar registros de entrega
* 011 - Exportar - Exportar registros de rastreamento

## Duplicação de fluxos de trabalho{#duplicating-workflows}

Você pode duplicar fluxos de trabalho. No **[!UICONTROL Marketing Activities]**, passe o mouse sobre o fluxo de trabalho e clique **[!UICONTROL Duplicate element]** em. Após a duplicação, as modificações do fluxo de trabalho não são transferidas para a cópia do fluxo de trabalho. A cópia do fluxo de trabalho pode ser editada.

![](assets/duplicating_workflow.png)

## Execução{#execution}

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

Para obter mais informações, consulte [Executar fluxos de trabalho](../../automating/using//executing-a-workflow.md).

## Atividade{#activity}

### Design de fluxo de trabalho

Para garantir que o fluxo de trabalho termina corretamente, use um **[!UICONTROL End activity]**. Evite deixar a última transição de um fluxo de trabalho sozinho.

Para acessar a exibição detalhada das transições, verifique a **[!UICONTROL Keep interim results]** opção na seção Execução das propriedades do fluxo de trabalho.

>[!CAUTION]
>
>Essa opção consome muito espaço em disco e é projetada para ajudar a criar um fluxo de trabalho e garantir a configuração e o comportamento adequados. Deixe desmarcada em instâncias de produção.

![](assets/keep_interim_best_practices.png)


### Atividades de rotulagem{#activity-labeling}

Ao desenvolver seu fluxo de trabalho, um nome é gerado para cada atividade, como para todos os objetos do Adobe Campaign. Embora o nome de uma atividade seja gerado pela ferramenta e não possa ser editado, recomendamos rotulá-lo com um nome explícito ao configurá-lo.

### Duplicação de atividades{#activity-duplicating}

Para duplicar atividades existentes, você pode usar a cópia de cópia. Dessa forma, você mantém as configurações definidas originalmente. Para obter mais informações, consulte [Duplicar atividades do fluxo de trabalho Duplicando](../../automating/using/workflow-interface.md).

### Atividade do agendador{#acheduler-activity}

Ao criar seu fluxo de trabalho, use apenas um **[!UICONTROL Scheduler activity]** por ramo. Se o mesmo ramo de um fluxo de trabalho tiver vários agendadores (vinculados entre si), o número de tarefas a serem executadas será multiplicado exponencialmente, o que sobrecarregaria consideravelmente o banco de dados.

Você pode visualizar as próximas dez execuções de seus fluxos de trabalho clicando **[!UICONTROL Preview next executions]** em.

![](assets/preview_scheduler.png)

Para obter mais informações, consulte Atividade [do programador](../../automating/using/scheduler.md).

## Chamada do fluxo de trabalho com parâmetros{#workflow-with-parameters}

Certifique-se de que o nome e o número de parâmetros sejam idênticos ao que é definido ao chamar o fluxo de trabalho (consulte [Definição dos parâmetros ao chamar o fluxo de trabalho](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)). Os tipos de parâmetros também devem ser consistentes com os valores esperados.

Verifique se todos os parâmetros foram declarados no **[!UICONTROL External signal activity]**. Caso contrário, ocorrerá um erro ao executar a atividade.

Para obter mais informações, consulte [Chamar um fluxo de trabalho com parâmetros externos](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Exportação de pacotes{#exporting-packages}

Para exportar pacotes, os recursos exportados não devem conter IDs padrão. Portanto, as IDs de recursos exportáveis devem ser alteradas usando um nome diferente dos modelos fornecidos como padrão pelo Adobe Campaign Standard.
Para obter mais informações, consulte [Gerenciamento de pacotes](../../automating/using/managing-packages.md).

## Exportar listas{#exporting-lists}

A opção de lista de exportação permite exportar no máximo 100,000 linhas por padrão e definido pela opção **Nms_ exportlistlimit**. Essa opção pode ser gerenciada pelo administrador funcional em **Administração** &gt; **Configurações do aplicativo** &gt; **Opções**.
Para obter mais informações, consulte [Exportar listas](../../automating/using/exporting-lists.md).

## Solução de problemas{#workflow-troubleshooting}

O Adobe Campaign oferece vários logs para entender melhor seus problemas de fluxo de trabalho.

### Uso de logs de fluxo de trabalho{#using-workflow-logs}

Você pode acessar logs de fluxo de trabalho para monitorar a execução de suas atividades. Ele indexa as operações realizadas e os erros de execução por ordem cronológica. A guia Logs consiste no histórico da execução de todas ou algumas atividades selecionadas.
A guia Tarefas detalha a sequência de execução das atividades. Para obter mais informações sobre uma atividade, clique em uma tarefa.
Para obter mais informações, consulte [Monitoramento da execução do fluxo de trabalho](../../automating/using/executing-a-workflow.md#monitoring).

#### Solução de problemas de gerenciamento de dados{#troubleshooting-data-management-activities}

Você pode analisar consultas SQL na guia Log.

1. Na área de trabalho do fluxo de trabalho, clique **em Editar propriedades**.
1. **Em Geral** &gt; **Execução**, marque **as consultas Salvar SQL no log** e **Execute nas opções de mecanismo** e clique **em Confirmar**.

**Para consultar consultas SQL no Log:**
1. Clique **em Log e tarefas**.
1. Na guia **Log** , abra o painel **Pesquisar** .
1. Marque **Apenas registros SQL de exibição**.

A consulta é exibida na coluna **Mensagem** dos logs.

### Uso de logs de entrega{#using-delivery-logs}

Os logs de entrega permitem monitorar o sucesso das entregas. Os logs de exclusão retornam mensagens excluídas durante a preparação do envio. O envio de logs fornece o status da entrega para cada perfil.
Para obter mais informações, consulte [Noções básicas sobre problemas de entrega](../../sending/using/understanding-delivery-failures.md).

### Uso de alertas de entrega{#delivery-alerting}

O recurso de alertas de entrega é um sistema de gerenciamento de alertas que permite que um grupo de usuários receba notificações automaticamente com informações sobre a execução de suas entregas.
Para obter mais informações, consulte Alertas [de entrega](../../sending/using/receiving-alerts-when-failures-happen.md).

**Tópicos relacionados:**

* [Gerenciamento de erros](../../automating/using/executing-a-workflow.md#error-management)
