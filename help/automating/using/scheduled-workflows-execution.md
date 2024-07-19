---
title: Execução sobreposta de workflows agendados
description: Saiba como evitar a sobreposição da execução de workflows agendados.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8d9820a4-3c44-45f5-815e-4ed48a96276d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 1%

---

# Execução sobreposta de workflows agendados{#preventing-overlapping-execution-of-scheduled-workflows}

## Sobre a execução de workflows agendados

No Campaign Standard, o mecanismo de fluxo de trabalho garante que uma instância de fluxo de trabalho seja executada por apenas um processo. O bloqueio de atividades, como importações, consultas ou gravações de longa duração no banco de dados, impede a execução de qualquer outra tarefa durante a execução.

Por outro lado, as atividades não bloqueadoras não bloqueiam a execução de outras tarefas (geralmente atividades aguardando um evento como a atividade **[!UICONTROL Scheduler]**).

Isso pode levar a um cenário em que um fluxo de trabalho com base em agendamento pode começar a ser executado mesmo quando a execução anterior desse mesmo fluxo de trabalho ainda não foi concluída, resultando potencialmente em problemas de dados inesperados.

Portanto, ao projetar um workflow agendado que inclua várias atividades, é necessário garantir que o workflow não seja reagendado até que seja concluído. Para fazer isso, é necessário configurar o workflow para impedir sua execução se uma ou mais tarefas de uma execução anterior ainda estiverem pendentes.

## Configuração do fluxo de trabalho

Para verificar se uma ou mais tarefas de uma execução de fluxo de trabalho anterior ainda estão pendentes, é necessário usar uma atividade **[!UICONTROL Query]** e **[!UICONTROL Test]**.

1. Adicione uma atividade **[!UICONTROL Query]** após a atividade **[!UICONTROL Scheduler]**, em seguida, configure-a da seguinte maneira.

1. Altere o recurso da atividade para **[!UICONTROL WorkflowTaskDetail]**, o que significa que ele segmentará as tarefas atuais do fluxo de trabalho.

   ![](assets/scheduled-wkf-resource.png)

1. Configure o query com as regras abaixo:

   ![](assets/scheduled-wkf-query.png)

   * A primeira regra filtra a tarefa atual (query2), bem como a próxima tarefa de agendamento (schedule2) pertencente ao fluxo de trabalho atual.

     >[!NOTE]
     >
     >Quando uma atividade **[!UICONTROL Scheduler]** é iniciada, ela adiciona imediatamente outra tarefa de agendamento para ser executada no próximo horário agendado e iniciar o fluxo de trabalho. Portanto, é importante filtrar as tarefas de query e agendamento ao procurar tarefas pendentes de uma execução anterior.

   * A segunda regra determina se alguma tarefa de uma execução anterior do workflow ainda está ativa (pendente), o que corresponde ao status de execução 0.

1. Adicione uma atividade **[!UICONTROL Test]** para verificar o número de tarefas pendentes retornadas pela atividade **[!UICONTROL Query]**. Para fazer isso, configure duas transições de saída.

   ![](assets/scheduled-wkf-test.png)

   * A primeira transição continuará a execução do workflow se não houver tarefas pendentes,
   * A segunda transição cancela a execução do workflow se houver tarefas pendentes.

   ![](assets/scheduled-wkf-workflow.png)

Agora você pode configurar o restante do fluxo de trabalho conforme necessário. Se a execução do workflow for cancelada devido a tarefas pendentes, quando o workflow for executado novamente de acordo com o agendamento, ele poderá passar por essas etapas. Isso garantirá que a execução do workflow continuará somente se não houver tarefas ativas (pendentes) de uma execução anterior.
