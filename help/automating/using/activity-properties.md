---
solution: Campaign Standard
product: campaign
title: Gerenciamento de propriedades de atividades
description: Saiba como gerenciar as propriedades das atividades do workflow.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 1%

---


# Gerenciamento de propriedades de atividades {#activity-properties}

## Propriedades globais de uma atividade {#global-properties-of-an-activity}

Cada atividade tem uma guia **[!UICONTROL General]** , que permite modificar parâmetros gerais específicos da atividade.

![](assets/activity-properties.png)

A guia **[!UICONTROL Properties]** permite modificar os parâmetros globais da atividade, especialmente o rótulo e a ID. A configuração dessa guia é opcional.

![](assets/activity-properties2.png)

## Gerenciamento de transições de saída de uma atividade {#managing-an-activity-s-outbound-transitions}

Por padrão, certas atividades não têm uma transição de saída. Você pode adicionar um na guia **[!UICONTROL Transitions]** ou na guia **[!UICONTROL Properties]** da atividade para aplicar outros processos ao seu público no mesmo fluxo de trabalho.

Dependendo das atividades, você pode adicionar vários tipos de transições de saída:

* **Transição** padrão: população calculada pela atividade
* **Transição sem população**: esse tipo de transição de saída pode ser adicionado para continuar o workflow e não contém nenhuma população para não consumir espaço desnecessário no sistema.
* **Rejeições**: população rejeitada. Por exemplo, se os dados de entrada da atividade não puderem ser processados porque estavam incorretos ou incompletos.
* **Complemento**: população restante após a execução da atividade. Por exemplo, se uma atividade de segmentação estiver configurada para salvar apenas uma porcentagem da população de entrada.

Se aplicável, especifique um **[!UICONTROL Segment code]** para a transição de saída da atividade. Esse código de segmento permitirá identificar de onde os subconjuntos da população do target vêm e pode, posteriormente, servir para fins de personalização de mensagens.

## Opções de execução da atividade {#activity-execution-options}

Na tela de propriedades da atividade, há uma guia **[!UICONTROL Advanced options]** que permite definir o modo e o comportamento de execução da atividade em caso de erros.

Para acessar essas opções, selecione uma atividade em um workflow e depois a abra usando o botão ![](assets/edit_darkgrey-24px.png) na barra de ações.

![](assets/wkf_advanced_parameters.png)

O campo **[!UICONTROL Execution]** permite definir a ação a ser executada quando a tarefa for iniciada. Há três opções para isso:

* **Normal**: a atividade é executada normalmente.
* **Ativar, mas não executar**: a atividade é pausada e, como consequência, qualquer processo futuro é seguido. Isso pode ser útil se você quiser estar presente quando a tarefa for iniciada.
* **Não ativar**: a atividade não é executada e, como consequência, nem todas as atividades subsequentes (na mesma ramificação).

O campo **[!UICONTROL In case of error]** permite especificar a ação a ser executada caso a atividade encontre um erro. Há duas opções disponíveis para isso:

* **Suspender o processo**: o workflow é suspenso automaticamente. O status do workflow é então **Errrado** e a cor associada fica vermelha. Depois que o problema for resolvido, reinicie o workflow.
* **Ignorar**: a atividade não é executada e, como resultado, nenhuma das atividades a sucede (na mesma ramificação). Isso pode ser útil para tarefas recorrentes. Se a ramificação tiver um programador a montante, ele deverá ser acionado na próxima data de execução.

O campo **[!UICONTROL Behavior]** permite definir o procedimento a ser seguido se tarefas assíncronas forem usadas. Há duas opções disponíveis para isso:

* **Várias tarefas autorizadas**: várias tarefas podem ser executadas ao mesmo tempo, mesmo que a primeira não tenha sido concluída.
* **A tarefa atual tem prioridade**: assim que uma tarefa estiver em andamento, ela terá prioridade. Enquanto uma tarefa ainda estiver em andamento, nenhuma outra tarefa será executada.

O campo **[!UICONTROL Max. execution duration]** permite especificar uma duração, como &quot;30s&quot; ou &quot;1h&quot;. Se a atividade não for concluída após o período especificado ter decorrido, um alerta será disparado. Isso não afeta o funcionamento do workflow.

O campo **[!UICONTROL Affinity]** permite forçar a execução de um fluxo de trabalho ou de uma atividade de fluxo de trabalho em uma máquina específica. Para fazer isso, é necessário especificar uma ou várias afinidades para o workflow ou atividade em questão.

O campo **[!UICONTROL Time zone]** permite selecionar o fuso horário da atividade. O Adobe Campaign permite gerenciar as diferenças de tempo entre vários países na mesma instância. A configuração aplicada é configurada quando a instância é criada.

>[!NOTE]
>
>Por padrão, se nenhum fuso horário for selecionado, a atividade usará o fuso horário definido nas propriedades do workflow.

O campo **Comment** é um campo livre que permite a adição de uma nota.
