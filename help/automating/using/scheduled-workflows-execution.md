---
title: Execução sobreposta de workflows agendados
description: Saiba como evitar a execução sobreposta de workflows agendados.
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
source-wordcount: '422'
ht-degree: 1%

---

# Execução sobreposta de workflows agendados{#preventing-overlapping-execution-of-scheduled-workflows}

## Sobre a execução de workflows agendados

No Campaign Standard, o mecanismo de workflow garante que uma instância de workflow seja executada por apenas um processo. Bloquear atividades como importações, consultas de longa duração ou gravações no banco de dados impede a execução de qualquer outra tarefa ao ser executada.

Por outro lado, as atividades de não bloqueio não bloqueiam a execução de outras tarefas (normalmente, atividades aguardando um evento como o **[!UICONTROL Scheduler]** atividade ).

Isso pode levar a um cenário em que um fluxo de trabalho baseado em agendamento pode começar a ser executado mesmo quando a execução anterior desse mesmo fluxo de trabalho ainda não tiver sido concluída, possivelmente levando a problemas inesperados de dados.

Portanto, ao projetar um workflow agendado que inclui várias atividades, é necessário garantir que o workflow não seja reagendado até que seja concluído. Para fazer isso, é necessário configurar o workflow para impedir a execução se uma ou mais tarefas de uma execução anterior ainda estiverem pendentes.

## Configuração do workflow

Para verificar se uma ou mais tarefas de uma execução anterior do workflow ainda estão pendentes, é necessário usar um **[!UICONTROL Query]** e **[!UICONTROL Test]** atividade .

1. Adicione um **[!UICONTROL Query]** após a **[!UICONTROL Scheduler]** , em seguida, configure-a da seguinte maneira.

1. Altere o recurso da atividade para **[!UICONTROL WorkflowTaskDetail]**, o que significa que ele direcionará as tarefas atuais do fluxo de trabalho.

   ![](assets/scheduled-wkf-resource.png)

1. Configure o query com as regras abaixo:

   ![](assets/scheduled-wkf-query.png)

   * A primeira regra filtra a tarefa atual (query2), bem como a próxima tarefa de agendamento (schedule2) pertencente ao workflow atual.

      >[!NOTE]
      >
      >Quando uma **[!UICONTROL Scheduler]** A atividade é iniciada, ela adiciona imediatamente outra tarefa de agendamento para ser executada na próxima hora agendada e iniciar o workflow. Portanto, é importante filtrar o query e agendar tarefas ao procurar tarefas pendentes de uma execução anterior.

   * A segunda regra determina se qualquer tarefa de uma execução anterior do workflow ainda está ativa (pendente), o que corresponde ao status de execução 0.

1. Adicione um **[!UICONTROL Test]** para verificar o número de tarefas pendentes retornadas pela variável **[!UICONTROL Query]** atividade . Para fazer isso, configure duas transições de saída.

   ![](assets/scheduled-wkf-test.png)

   * A primeira transição continua a execução do workflow se não houver tarefas pendentes,
   * A segunda transição cancela a execução do workflow se houver tarefas pendentes.

   ![](assets/scheduled-wkf-workflow.png)

Agora é possível configurar o restante do fluxo de trabalho, conforme necessário. Se a execução do workflow for cancelada devido a tarefas pendentes, quando o workflow for executado novamente de acordo com o agendamento, ele poderá seguir essas etapas. Isso garantirá que a execução do workflow continue somente se não houver tarefas ativas (pendentes) de uma execução anterior.
