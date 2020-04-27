---
title: Execução de um fluxo de trabalho
description: Saiba como executar e monitorar um fluxo de trabalho.
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e5c21e1398d5fbe39761ab00ada24263317e6742

---


# Execução de um fluxo de trabalho{#executing-a-workflow}

## Sobre a execução do fluxo de trabalho {#about-workflow-execution}

Um workflow é sempre iniciado manualmente. No entanto, uma vez iniciado, ele pode permanecer inativo, dependendo das informações especificadas em uma atividade de [Scheduler](../../automating/using/scheduler.md) .

>[!CAUTION]
>
> A Adobe recomenda que os clientes priorizem execuções de fluxo de trabalho e executem até 20 execuções simultâneas de fluxo de trabalho para atingir de forma consistente o desempenho máximo em sua instância. Mais de vinte execuções de fluxo de trabalho simultâneas podem ser planejadas e serão executadas sequencialmente por padrão. Você pode ajustar as configurações padrão para o número máximo de execuções simultâneas de fluxo de trabalho enviando um ticket para o Atendimento ao cliente.

Ações relacionadas à execução (start, parada, pausa etc.) são processos **assíncronos** : o comando é salvo e entrará em vigor assim que o servidor estiver disponível para aplicá-lo.

Em um fluxo de trabalho, o resultado de cada atividade geralmente é enviado para a seguinte atividade por meio de uma transição, representada por uma seta.

Uma transição não será terminada se não estiver vinculada a uma atividade de destino.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>Um fluxo de trabalho contendo transições não finalizadas ainda pode ser executado: uma mensagem de aviso será gerada e o fluxo de trabalho pausará assim que chegar à transição, mas isso não gerará um erro. Você também pode start um fluxo de trabalho sem ter concluído completamente o design e pode concluí-lo conforme progride.

Depois que uma atividade é executada, o número de registros enviados na transição é exibido acima dela.

![](assets/wkf_transition_count.png)

Você pode abrir o transição para verificar se os dados enviados estão corretos durante ou após a execução do fluxo de trabalho. Você pode visualização os dados e a estrutura de dados.

Por padrão, somente os detalhes da última transição do fluxo de trabalho podem ser acessados. Para poder acessar os resultados das atividades anteriores, é necessário verificar a opção **[!UICONTROL Keep interim results]** na seção **[!UICONTROL Execution]** das propriedades do fluxo de trabalho antes de iniciar o fluxo de trabalho.

>[!NOTE]
>
>Essa opção consome muita memória e foi projetada para ajudar a construir um fluxo de trabalho e garantir que ele esteja configurado e se comportando corretamente. Deixe-o desmarcado em instâncias de produção.

Quando uma transição é aberta, você pode editá-la **[!UICONTROL Label]** ou vincular uma **[!UICONTROL Segment code]** a ela. Para fazer isso, edite os campos correspondentes e confirme suas modificações.

Usando APIs Campaign Standard REST, você pode **start**, **pausar**, **retomar** e **parar** um fluxo de trabalho. Você pode encontrar mais detalhes e exemplos de chamadas REST na documentação da [API.](../../api/using/controlling-a-workflow.md)

## Ciclo de vida {#life-cycle}

O ciclo de vida de um fluxo de trabalho inclui três etapas principais e cada etapa está vinculada a um status e a uma cor:

* **Edição** (cinza)

   Esta é a fase de design inicial de um fluxo de trabalho (consulte [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md#creating-a-workflow)). O fluxo de trabalho ainda não é manipulado pelo servidor e pode ser modificado sem nenhum risco.

* **Em andamento** (azul)

   Quando a fase de design inicial estiver concluída, o fluxo de trabalho poderá ser iniciado e será manipulado pelo servidor.

* **Concluído** (verde)

   Um fluxo de trabalho é concluído quando não há mais tarefas em andamento ou quando um operador tiver parado explicitamente a instância.

Depois de iniciado, um fluxo de trabalho também pode ter dois outros status:

* **Aviso** (amarelo)

   O fluxo de trabalho não pôde ser concluído ou foi pausado usando os ![](assets/pause_darkgrey-24px.png) botões ou ![](assets/check_pause_darkgrey-24px.png) .

* **Errado** (vermelho)

   Ocorreu um erro quando um fluxo de trabalho foi executado. O fluxo de trabalho foi interrompido e o usuário deve executar uma ação. Para saber mais sobre esse erro, use o ![](assets/printpreview_darkgrey-24px.png) botão para acessar o log do fluxo de trabalho (consulte [Monitoramento](#monitoring)).

A lista de atividades de marketing permite exibir todos os workflows, bem como seus status. Para obter mais informações, consulte [Gerenciamento de atividades](../../start/using/marketing-activities.md#about-marketing-activities)de marketing.

![](assets/wkf_execution_3.png)

## Comandos de execução {#execution-commands}

Os ícones na barra de ações permitem que você start, rastreie e modifique a execução de um fluxo de trabalho. Consulte Barra [de ação](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

As opções disponíveis são as seguintes:

**Start**

O ![](assets/play_darkgrey-24px.png) botão start executando um fluxo de trabalho, que assume o status **Em andamento** (azul). Se o fluxo de trabalho foi pausado, ele será retomado, caso contrário, ele será iniciado e as atividades iniciais serão ativadas.

>[!NOTE]
>
>O início é um processo assíncrono: a solicitação é salva e será processada o mais rápido possível pelo mecanismo de execução do fluxo de trabalho.

**Pause**

O ![](assets/pause_darkgrey-24px.png) botão pausa a execução. O fluxo de trabalho assume o status **Aviso** (amarelo). Nenhuma nova atividade será ativada até que seja retomada, mas as operações em andamento não serão suspensas.

**Stop**

O ![](assets/stop_darkgrey-24px.png) botão para um fluxo de trabalho que está sendo executado, que assumirá o status **Concluído** (verde). As operações em andamento são interrompidas, se possível, e as importações ou query SQL em andamento são imediatamente cancelados. Não é possível retomar do fluxo de trabalho a partir do mesmo local em que ele foi interrompido.

**Restart**

O ![](assets/pauseplay_darkgrey-24px.png) botão envolve parar e reiniciar um fluxo de trabalho. Na maioria dos casos, isso permite reiniciar mais rapidamente. Também pode ser útil automatizar a reinicialização depois que a interrupção levar um determinado tempo, pois o ![](assets/play_darkgrey-24px.png) botão só estará disponível quando a interrupção for efetiva.

Quando uma ou várias atividades em um fluxo de trabalho são selecionadas, há outras ações que você pode realizar, como:

**Execução imediata**

O ![](assets/pending_darkgrey-24px.png) botão start qualquer atividade pendente selecionada o mais rápido possível.

**Execução normal**

O ![](assets/check_darkgrey-24px.png) botão reativa as atividades pausadas ou desativadas.

**Execução suspensa**

O ![](assets/check_pause_darkgrey-24px.png) botão pausa o fluxo de trabalho na atividade selecionada: esta tarefa, bem como todos os que a sucedem (na mesma ramificação) não são executados.

**Nenhuma execução**

O ![](assets/checkdisable.png) botão desativa qualquer atividade selecionada.

>[!NOTE]
>
>As ações rápidas permitem acessar ações diferentes relacionadas a uma atividade específica e aparecem quando uma atividade é selecionada.

## Monitoring {#monitoring}

O ![](assets/printpreview_darkgrey-24px.png) ícone abre o log de fluxo de trabalho e o menu tarefa.

O histórico do fluxo de trabalho é salvo pela duração especificada nas opções de execução do fluxo de trabalho (consulte as propriedades [do](#workflow-properties)fluxo de trabalho). Durante esse período, todas as mensagens são salvas, mesmo após uma reinicialização. Se você não quiser salvar as mensagens de uma execução anterior, é necessário limpar o histórico clicando no ![](assets/delete_darkgrey-24px.png) botão.

A **[!UICONTROL Log]** guia contém o histórico de execução de todas as atividades ou de qualquer atividade selecionada. Indica as operações efetuadas e os erros de execução por ordem cronológica.

![](assets/wkf_execution_4.png)

A **[!UICONTROL Tasks]** guia detalha a sequência de execução das atividades. Clique em uma tarefa para obter mais informações.

![](assets/wkf_execution_5.png)

Nestas duas listas:

* Clique no contador para ver o número total de atividades de acordo com o filtro aplicado. O contador é exibido por padrão se o número de elementos na lista for menor que 30.
* O **[!UICONTROL Configure list]** botão permite escolher as informações exibidas, definir a ordem das colunas e classificar a lista.
* Você pode usar filtros para encontrar as informações de que precisa mais rapidamente. Use o campo de pesquisa para procurar um texto específico em nomes de atividade de fluxo de trabalho (por exemplo: &quot;query&quot;) e registros.

## Gerenciamento de erros {#error-management}

Quando ocorre um erro, o fluxo de trabalho é pausado e a atividade que estava sendo executada quando o erro foi encontrado pisca em vermelho.

O status do fluxo de trabalho fica vermelho e o erro é registrado no registro.

Você pode configurar o fluxo de trabalho para que ele não pause e continue a execução sem erros. Para fazer isso, vá para as propriedades do fluxo de trabalho por meio do ![](assets/edit_darkgrey-24px.png) botão e, na **[!UICONTROL Execution]** seção, selecione a opção **Ignorar** no campo **Em caso de erro** .

Nesse caso, a tarefa errada é abortada. Esse modo é especialmente adequado para workflows projetados para tentar a operação novamente mais tarde (ações periódicas).

>[!NOTE]
>
>Você pode aplicar essa configuração individualmente para cada atividade. Para fazer isso, selecione uma atividade e abra-a usando a ação rápida ![](assets/edit_darkgrey-24px.png). Em seguida, selecione o modo de gerenciamento de erros na guia Opções **** de execução. Consulte Opções [de execução de](#activity-execution-options)Atividade.

Nas propriedades [do](#workflow-properties)fluxo de trabalho, opções adicionais relacionadas ao gerenciamento de erros estão disponíveis.

![](assets/wkf_execution_error.png)

As opções possíveis são:

* **[!UICONTROL Supervisors]**: permite que você defina o grupo de pessoas a ser notificado (notificação por email e no aplicativo) se o fluxo de trabalho encontrar um erro. Se nenhum grupo for definido, ninguém será notificado. Para obter mais informações sobre notificações de Adobe Campaign, consulte notificações [de](../../administration/using/sending-internal-notifications.md)Adobe Campaign.

* **[!UICONTROL In case of error]**: permite especificar a ação a ser executada caso a atividade encontre um erro. Há duas opções disponíveis para isso:

   * **Suspenda o processo**: o fluxo de trabalho é suspenso automaticamente. O status do fluxo de trabalho é então **Errado** e a cor associada fica vermelha. Depois que o problema for resolvido, reinicie o fluxo de trabalho.
   * **Ignorar**: a atividade não é executada e, como resultado, nenhuma das atividades a seguir (na mesma ramificação). Isso pode ser útil para tarefas recorrentes. Se a ramificação tiver um scheduler colocado em upstream, isso deverá disparar na próxima data de execução.

* **[!UICONTROL Consecutive errors]** : permite que você defina uma série de erros consecutivos autorizados antes da execução do fluxo de trabalho ser automaticamente suspensa.

   * Se o número especificado for **[!UICONTROL 0]**, ou enquanto o número especificado não for atingido, as atividades que encontrarem erros serão ignoradas. As outras ramificações de fluxo de trabalho são executadas normalmente.

   * Se o número especificado for atingido, todo o fluxo de trabalho será suspenso e se tornará **[!UICONTROL Erroneous]**. Se os supervisores tiverem sido definidos, eles serão automaticamente notificados por email. Consulte Notificações [de Adobe Campaign](../../administration/using/sending-internal-notifications.md).

## Propriedades do workflow {#workflow-properties}

Para modificar as opções de execução de um fluxo de trabalho, use o ![](assets/edit_darkgrey-24px.png) botão para acessar as propriedades do fluxo de trabalho e selecione a **[!UICONTROL Execution]** seção.

![](assets/wkf_execution_6.png)

As opções possíveis são:

* **[!UICONTROL Default affinity]**: esse campo permite forçar a execução de um fluxo de trabalho ou de uma atividade de fluxo de trabalho em uma máquina específica.

* **[!UICONTROL History in days]**: especifica o número de dias após os quais o histórico deve ser expurgado. O histórico contém elementos relacionados ao fluxo de trabalho: registros, tarefas, eventos (objetos técnicos vinculados à operação do fluxo de trabalho), bem como arquivos baixados pela **[!UICONTROL Transfer file]** atividade. O valor padrão é 30 dias para modelos de fluxo de trabalho predefinidos.

   A remoção do histórico é executada pelo fluxo de trabalho técnico de limpeza do Banco de Dados, que é executado por padrão todos os dias (consulte [Lista de workflows técnicos](../../administration/using/technical-workflows.md)).

   >[!IMPORTANT]
   >
   >Se o **[!UICONTROL History in days]** campo ficar em branco, seu valor será considerado como &quot;1&quot;, o que significa que o histórico será limpo após 1 dia.

* **[!UICONTROL Save SQL queries in the log]**: permite salvar os query SQL do fluxo de trabalho nos logs.

* **[!UICONTROL Keep interim results]**: marque essa opção se quiser ser capaz de visualização dos detalhes das transições. Aviso: a verificação dessa opção pode retardar significativamente a execução do fluxo de trabalho.

* **[!UICONTROL Execute in the engine (do not use in production)]**: permite que você execute o fluxo de trabalho localmente, para fins de teste de ambiente de desenvolvimento.

* **[!UICONTROL Severity]**: permite que você especifique um nível de prioridade para executar workflows na instância Adobe Campaign. Os workflows críticos serão executados primeiro.

A **[!UICONTROL Error management]** seção fornece opções adicionais que permitem gerenciar como os workflows se comportam em caso de erros. Essas opções são detalhadas na seção Gerenciamento [de](#error-management) erros.

## Propriedades da Atividade {#activity-properties}

### Propriedades gerais de uma atividade {#general-properties-of-an-activity}

Cada atividade tem uma **[!UICONTROL Properties]** guia. Essa guia permite modificar os parâmetros gerais da atividade, especialmente o rótulo e a ID. Configurar essa guia é opcional.

### Gerenciando transições de saída de atividades {#managing-an-activity-s-outbound-transitions}

Por padrão, certas atividades não têm uma transição de saída. Você pode adicionar um da **[!UICONTROL Transitions]** guia ou da guia atividade **[!UICONTROL Properties]** para aplicar outros processos à sua população no mesmo fluxo de trabalho.

Dependendo das atividades, é possível adicionar vários tipos de transições de saída:

* transição padrão: população calculada pela atividade
* Transição sem população: esse tipo de transição de saída pode ser adicionado para continuar o fluxo de trabalho e não contém nenhuma população para não consumir nenhum espaço desnecessário no sistema.
* Rejeita: população rejeitada. Por exemplo, se os dados de entrada da atividade não puderam ser processados porque estavam incorretos ou incompletos.
* Complemento: população restante após a execução da atividade. Por exemplo, se uma atividade de segmentação estiver configurada para salvar apenas uma porcentagem da população de entrada.

Se aplicável, especifique um **[!UICONTROL Segment code]** para a transição de saída da atividade. Este código de segmento permitirá identificar de onde vêm os subconjuntos da população do público alvo e poderá, posteriormente, servir para fins de personalização de mensagens.

### Opções de execução de Atividade {#activity-execution-options}

Na tela de propriedades do atividade, há uma **[!UICONTROL Advanced options]** guia que permite definir o modo de execução e o comportamento do atividade em caso de erros.

Para acessar essas opções, selecione uma atividade em um fluxo de trabalho e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão da barra de ações.

![](assets/wkf_advanced_parameters.png)

The **[!UICONTROL Execution]** field allows you to define the action to be carried out when the task is started. Há três opções para isso:

* **Normal**: a atividade é executada normalmente.
* **Habilitar, mas não executar**: a atividade é pausada e, consequentemente, qualquer processo futuro que se suceda. Isso pode ser útil se você quiser estar presente quando a tarefa for iniciada.
* **Não ativar**: a atividade não é executada e, consequentemente, nem todas as atividades subsequentes (no mesmo ramo).

O **[!UICONTROL In case of error]** campo permite especificar a ação a ser executada caso a atividade encontre um erro. Há duas opções disponíveis para isso:

* **Suspenda o processo**: o fluxo de trabalho é suspenso automaticamente. O status do fluxo de trabalho é então **Errado** e a cor associada fica vermelha. Depois que o problema for resolvido, reinicie o fluxo de trabalho.
* **Ignorar**: a atividade não é executada e, como resultado, nenhuma das atividades a seguir (na mesma ramificação). Isso pode ser útil para tarefas recorrentes. Se a ramificação tiver um scheduler colocado em upstream, isso deverá disparar na próxima data de execução.

O **[!UICONTROL Behavior]** campo permite definir o procedimento a ser seguido se tarefas assíncronas forem usadas. Há duas opções disponíveis para isso:

* **Várias tarefas autorizadas**: várias tarefas podem ser executadas ao mesmo tempo, mesmo que a primeira não tenha sido concluída.
* **A tarefa atual tem prioridade**: quando uma tarefa está em andamento, isso tem prioridade. Enquanto uma tarefa estiver em andamento, nenhuma outra tarefa será executada.

O **[!UICONTROL Max. execution duration]** campo permite especificar uma duração, como &quot;30s&quot; ou &quot;1h&quot;. Se a atividade não for concluída após a duração especificada, um alerta será disparado. Isso não afeta o funcionamento do fluxo de trabalho.

O **[!UICONTROL Affinity]** campo permite forçar a execução de um fluxo de trabalho ou de uma atividade de fluxo de trabalho em uma máquina específica. Para fazer isso, você deve especificar uma ou várias afinidades para o fluxo de trabalho ou a atividade em questão.

O **[!UICONTROL Time zone]** campo permite selecionar o fuso horário da atividade. O Adobe Campaign permite gerenciar as diferenças de tempo entre vários países na mesma instância. A configuração aplicada é configurada quando a instância é criada.

>[!NOTE]
>
>Por padrão, se nenhum fuso horário for selecionado, a atividade usará o fuso horário definido nas propriedades do fluxo de trabalho.

The **Comment** field is a free field that allows you to add a note.
