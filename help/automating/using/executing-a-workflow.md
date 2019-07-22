---
title: Execução de um fluxo de trabalho
seo-title: Execução de um fluxo de trabalho
description: Execução de um fluxo de trabalho
seo-description: Saiba como executar e monitorar um fluxo de trabalho.
page-status-flag: nunca ativado
uuid: ff 02 b 74 e -53 e 8-49 c 6-bf 8 e -0 c 729 eaa 7 d 25
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: fluxo de trabalho-geral-operação
discoiquuid: 906 c 85 ea -83 b 7-4268-86 da-cd 353 f 1 dc 591
context-tags: fluxo de trabalho, visão geral; fluxo de trabalho, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e33cbfbf6376dabfe81b9bd6f7cce817f35d1b75

---


# Executing a workflow{#executing-a-workflow}

## About workflow execution {#about-workflow-execution}

Um fluxo de trabalho sempre é iniciado manualmente. However, once started, it can remain inactive, depending on the information specified in a [Scheduler](../../automating/using/scheduler.md) activity.

>[!CAUTION]
>
> A Adobe recomenda que os clientes priorizem as execuções do fluxo de trabalho e sejam executados até vinte execuções de fluxo de trabalho simultâneo para atingir o desempenho máximo em toda a sua instância. Mais de vinte execuções simultâneas de fluxo de trabalho podem ser planejadas e executadas sequencialmente por padrão. Você pode ajustar as configurações padrão para o número máximo de execuções simultâneas de fluxos de trabalho enviando um ticket para o Atendimento ao cliente.

Ações relacionadas a execução (iniciar, parar, pausar etc.) are **asynchronous** processes: the command is saved and will become effective once the server is available to apply it.

Em um fluxo de trabalho, o resultado de cada atividade é geralmente enviado para a seguinte atividade por uma transição, representada por uma seta.

Uma transição não será encerrada se não estiver vinculada a uma atividade de destino.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>Um fluxo de trabalho contendo transições não finalizadas ainda pode ser executado: uma mensagem de aviso será gerada e o fluxo de trabalho pausará uma vez que chegar à transição, mas isso não gerará um erro. Também é possível iniciar um fluxo de trabalho sem concluir completamente o design e você pode concluí-lo conforme você avançar.

Após a execução de uma atividade, o número de registros enviados na transição é exibido acima dele.

![](assets/wkf_transition_count.png)

É possível abrir transições para verificar se os dados enviados estão corretos durante ou depois de executar o fluxo de trabalho. É possível exibir os dados e a estrutura dos dados.

Por padrão, somente os detalhes da última transição do fluxo de trabalho podem ser acessados. To be able to access the results of the preceding activities, you need to check the **[!UICONTROL Keep interim results]** option in the **[!UICONTROL Execution]** section of the workflow properties, before starting the workflow.

>[!NOTE]
>
>Essa opção consome muita memória e é projetada para ajudar a construir um fluxo de trabalho e garantir que esteja configurado corretamente e se comporte. Deixe desmarcada em instâncias de produção.

When a transition is open, you can edit its **[!UICONTROL Label]** or link a **[!UICONTROL Segment code]** to it. Para fazer isso, edite os campos correspondentes e confirme suas modificações.

## Controlling a workflow from the REST API {#controlling-a-workflow-from-the-rest-api}

Using the REST API, you can **start**, **pause**, **resume** and **stop** a workflow.

You can find more details and examples of REST calls in the [API documentation.](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#controlling-a-workflow)

## Life cycle {#life-cycle}

O ciclo de vida do fluxo de trabalho inclui três etapas principais e cada etapa está vinculada a um status e uma cor:

* **Edição** (cinza)

   This is the initial design phase of a workflow (refer to [Creating a workflow](../../automating/using/building-a-workflow.md#creating-a-workflow)). O fluxo de trabalho ainda não é manipulado pelo servidor e pode ser modificado sem qualquer risco.

* **Em andamento** (azul)

   Quando a fase inicial do design for concluída, o fluxo de trabalho poderá ser iniciado e manipulado pelo servidor.

* **Concluído** (verde)

   Um fluxo de trabalho é concluído depois que não há mais tarefas em andamento ou quando um operador parou explicitamente a instância.

Uma vez iniciada, um fluxo de trabalho também pode ter dois outros status:

* **Aviso** (amarelo)

   The workflow could not finish or was paused using the ![](assets/pause_darkgrey-24px.png) or ![](assets/check_pause_darkgrey-24px.png) buttons.

* **Errôneo** (vermelho)

   Um erro ocorria quando um fluxo de trabalho era executado. O fluxo de trabalho foi interrompido e o usuário deve executar uma ação. To find out more about this error, use the ![](assets/printpreview_darkgrey-24px.png) button to access the workflow log (refer to [Monitoring](../../automating/using/executing-a-workflow.md#monitoring)).

A lista de atividades de marketing permite exibir todos os fluxos de trabalho e seus status. For more on this, see [Managing marketing activities](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)

## Execution commands {#execution-commands}

Os ícones na barra de ação permitem iniciar, rastrear e modificar a execução de um fluxo de trabalho. See [Action bar](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

As ações disponíveis são as seguintes:

**Início**

The ![](assets/play_darkgrey-24px.png) button starts executing a workflow, which then takes on the **In progress** (blue) status. Se o fluxo de trabalho foi pausado, ele é retomado; caso contrário, ele será iniciado e as atividades iniciais serão ativadas.

>[!NOTE]
>
>Início é um processo assíncrono: a solicitação é salva e será processada assim que possível pelo mecanismo de execução do fluxo de trabalho.

**Pausar**

The ![](assets/pause_darkgrey-24px.png) button pauses the execution. The workflow takes on the **Warning** (yellow) status. Nenhuma atividade nova será ativada até que seja retomada, mas as operações em andamento não serão suspensas.

**Parar**

The ![](assets/stop_darkgrey-24px.png) button stops a workflow that is being executed, which will then take on the **Finished** (green) status. As operações em andamento são interrompidas se possível, e as importações ou consultas SQL em andamento são canceladas imediatamente. Não é possível retomar a partir do fluxo de trabalho a partir do mesmo local em que foi interrompido.

**Reiniciar**

The ![](assets/pauseplay_darkgrey-24px.png) button involves stopping, then restarting a workflow. Na maioria dos casos, isso permite reiniciar mais rápido. It can also be useful to automate restarting once stopping takes a certain amount of time, because the ![](assets/play_darkgrey-24px.png) button is only available when the stop is effective.

Quando uma ou várias atividades em um fluxo de trabalho são selecionadas, há outras ações que podem ser executadas, como:

**Execução imediata**

The ![](assets/pending_darkgrey-24px.png) button starts any pending activities selected as soon as possible.

**Execução normal**

The ![](assets/check_darkgrey-24px.png) button reactivates any paused or deactivated activities.

**Execução suspensa**

The ![](assets/check_pause_darkgrey-24px.png) button pauses the workflow at the selected activity: this task as well as all those that follow it (in the same branch) are not executed.

**Nenhuma execução**

The ![](assets/checkdisable.png) button deactivates any selected activities.

>[!NOTE]
>
>As ações rápidas permitem acessar ações diferentes relacionadas a uma atividade específica e aparecem quando uma atividade é selecionada.

## Monitoring {#monitoring}

The ![](assets/printpreview_darkgrey-24px.png) icon opens the workflow log and task menu.

The workflow history is saved for the duration specified in the workflow execution options (refer to [Workflow properties](../../automating/using/executing-a-workflow.md#workflow-properties)). Durante essa duração, todas as mensagens são salvas, mesmo após uma reinicialização. If you do not want to save the messages from a previous execution, you have to purge the history by clicking the ![](assets/delete_darkgrey-24px.png) button.

The **[!UICONTROL Log]** tab contains the execution history of all the activities or any selected activities. Ele indexa as operações realizadas e os erros de execução por ordem cronológica.

![](assets/wkf_execution_4.png)

The **[!UICONTROL Tasks]** tab details the execution sequencing of the activities. Clique em uma tarefa para obter mais informações.

![](assets/wkf_execution_5.png)

Nessas duas listas:

* Clique no contador para ver o número total de atividades de acordo com o filtro aplicado. O contador é exibido por padrão se o número de elementos na lista for menor que 30.
* The **[!UICONTROL Configure list]** button allows you to choose the information displayed, define the column order, and sort the list.
* Você pode usar filtros para encontrar as informações necessárias. Use o campo de pesquisa para procurar um texto específico nos nomes de atividade do fluxo de trabalho (por exemplo: " consulta ") e registros.

## Error management {#error-management}

Quando ocorre um erro, o fluxo de trabalho é pausado e a atividade que estava sendo executada quando o erro foi encontrado em vermelho.

O status do fluxo de trabalho fica vermelho e o erro é registrado no log.

Você pode configurar o fluxo de trabalho para que ele não pause e continue a execução sem erros. To do this, go to the workflow properties via the ![](assets/edit_darkgrey-24px.png) button and, in the **[!UICONTROL Execution]** section, select the **Ignore** option in the **In case of error** field.

Nesse caso, a tarefa errada é abortada. Esse modo é particularmente adequado para fluxos de trabalho projetados para tentar novamente a operação mais tarde (ações periódicas).

>[!NOTE]
>
>É possível aplicar essa configuração individualmente para cada atividade. To do this, select an activity and open it using the quick action ![](assets/edit_darkgrey-24px.png). Then select the error management mode in the **Execution options** tab. See [Activity execution options](../../automating/using/executing-a-workflow.md#activity-execution-options).

The **[!UICONTROL Execution]** section of the workflow properties also allows you to define a number of **[!UICONTROL Consecutive errors]** that are authorized before the workflow execution is automatically suspended. Desde que esse número não seja atingido, os elementos errôneos são ignorados e as outras ramificações do fluxo de trabalho são executadas normalmente. Se esse número for atingido, o fluxo de trabalho será suspenso e as controladores de fluxo de trabalho serão notificadas automaticamente (email e notificação no aplicativo). See [Workflow properties](../../automating/using/executing-a-workflow.md#workflow-properties) and [Adobe Campaign notifications](../../administration/using/sending-internal-notifications.md).

As controladores também podem ser definidas nas propriedades de execução do fluxo de trabalho.

## Workflow properties {#workflow-properties}

To modify a workflow's execution options, use the ![](assets/edit_darkgrey-24px.png) button to access the workflow properties and select the **[!UICONTROL Execution]** section.

The **[!UICONTROL Default affinity]** field allows you to force a workflow or a workflow activity to execute on a particular machine.

In the **[!UICONTROL History in days]** field, specify the duration after which the history must be purged.

You can choose to check the **[!UICONTROL Save SQL queries in the log]** and **[!UICONTROL Execute in the engine (do not use in production)]** options if necessary.

Check the **[!UICONTROL Keep interim results]** option if you would like to be able to view the detail of transitions. Aviso: marcar essa opção pode atrasar significativamente a execução do fluxo de trabalho.

The **[!UICONTROL Severity]** field allows you to specify a level of priority for executing workflows in your Adobe Campaign instance. Os fluxos de trabalho críticos serão executados primeiro.

The **[!UICONTROL Supervisors]** field is where you can define the group of people to notify (email and in-app notification) if the workflow encounters an error. Se nenhum grupo estiver definido, ninguém será notificado. For more on Adobe Campaign notifications, refer to [Adobe Campaign notifications](../../administration/using/sending-internal-notifications.md).

**[!UICONTROL In case of error]** O campo permite especificar a ação a ser executada caso a atividade encontre um erro. Há duas opções disponíveis para isso:

* **Suspender o processo**: o fluxo de trabalho é suspenso automaticamente. The workflow status is then **Erroneous** and the color associated turns red. Depois que o problema for resolvido, reinicie o fluxo de trabalho.
* **Ignorar**: a atividade não é executada e, como resultado, nenhuma das atividades a seguir (na mesma ramificação). Isso pode ser útil para tarefas recorrentes. Se a ramificação tiver um agendador colocado como upstream, ele deverá ser acionado na próxima data de execução.

   By selecting this option, you can also define a number of **[!UICONTROL Consecutive errors]** that are authorized:

   * If the number specified is **[!UICONTROL 0]**, or as long as the number specified is not reached, activities that encounter errors are ignored. As outras ramificações de fluxo de trabalho são executadas normalmente.
   * If the number specified is reached, the whole of the workflow is suspended and becomes **[!UICONTROL Erroneous]**. Se as controladores tiverem sido definidas, elas serão notificadas automaticamente por um email.

![](assets/wkf_execution_6.png)

## Activity properties {#activity-properties}

### General properties of an activity {#general-properties-of-an-activity}

Each activity has a **[!UICONTROL Properties]** tab. Essa guia permite modificar os parâmetros gerais da atividade, particularmente a etiqueta e a ID. A configuração dessa guia é opcional.

### Managing an activity's outbound transitions {#managing-an-activity-s-outbound-transitions}

Por padrão, determinadas atividades não têm uma transição de saída. You can add one from the **[!UICONTROL Transitions]** tab or from the activity's **[!UICONTROL Properties]** tab to apply other processes to your population in the same workflow.

Dependendo das atividades, você pode adicionar vários tipos de transições de saída:

* Transição padrão: população calculada pela atividade
* Transição sem população: esse tipo de transição de saída pode ser adicionado para continuar o fluxo de trabalho e não contém nenhum público para consumir nenhum espaço desnecessário no sistema.
* Rejeita: população rejeitada. Por exemplo, se os dados de entrada da atividade não puderam ser processados porque estavam incorretos ou incompletos.
* Complementar: população restante após executar a atividade. Por exemplo, se uma atividade de segmentação estiver configurada para salvar apenas uma porcentagem da população de entrada.

If applicable, specify a **[!UICONTROL Segment code]** for the activity's outbound transition. Esse código do segmento permitirá identificar onde os subconjuntos da população de destino vêm e podem, posteriormente, servir para fins de personalização de mensagens.

### Activity execution options {#activity-execution-options}

In the activity's properties screen, there is an **[!UICONTROL Advanced options]** tab that lets you define the activity's execution mode and behavior in case of errors.

To access these options, select an activity in a workflow, then open it using the ![](assets/edit_darkgrey-24px.png) button from the action bar.

![](assets/wkf_advanced_parameters.png)

The **[!UICONTROL Execution]** field allows you to define the action to be carried out when the task is started. Há três opções para isso:

* **Normal**: a atividade é executada normalmente.
* **Ativar, mas não executar**: a atividade está pausada e, como consequência, são quaisquer processos futuros que seguem. Isso pode ser útil para ser útil quando a tarefa é iniciada.
* **Não ative**: a atividade não é executada e, como consequência, nenhuma das atividades subsequentes (na mesma ramificação).

**[!UICONTROL In case of error]** O campo permite especificar a ação a ser executada caso a atividade encontre um erro. Há duas opções disponíveis para isso:

* **Suspender o processo**: o fluxo de trabalho é suspenso automaticamente. The workflow status is then **Erroneous** and the color associated turns red. Depois que o problema for resolvido, reinicie o fluxo de trabalho.
* **Ignorar**: a atividade não é executada e, como resultado, nenhuma das atividades a seguir (na mesma ramificação). Isso pode ser útil para tarefas recorrentes. Se a ramificação tiver um agendador colocado como upstream, ele deverá ser acionado na próxima data de execução.

**[!UICONTROL Behavior]** O campo permite que você defina o procedimento a ser seguido se tarefas assíncronas forem usadas. Há duas opções disponíveis para isso:

* **Várias tarefas autorizadas**: várias tarefas podem ser executadas simultaneamente mesmo se a primeira não tiver terminado.
* **A tarefa atual tem prioridade**: quando uma tarefa estiver em andamento, isso terá prioridade. Contanto que uma tarefa ainda esteja em andamento, nenhuma outra tarefa será executada.

The **[!UICONTROL Max. execution duration]** field allows you to specify a duration such as "30s" or "1h". Se a atividade não for concluída depois que a duração especificada tiver sido ultrapassada, um alerta será acionado. Isso não afeta a forma como as funções do fluxo de trabalho funcionam.

The **[!UICONTROL Affinity]** field allows you to force a workflow or a workflow activity to execute on a particular machine. Para fazer isso, você deve especificar uma ou várias afinidades para o fluxo de trabalho ou atividade em questão.

**[!UICONTROL Time zone]** O campo permite selecionar o fuso horário da atividade. O Adobe Campaign permite gerenciar as diferenças de tempo entre vários países na mesma instância. A configuração aplicada é configurada quando a instância é criada.

The **Comment** field is a free field that allows you to add a note.
