---
title: Monitoramento da execução do fluxo de trabalho
description: Saiba como monitorar a execução de um workflow.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d2ce702b-92d1-4b94-bd47-34ef46a8bd9f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 6%

---

# Monitoramento da execução do fluxo de trabalho {#monitoring}

## Log e tarefas do fluxo de trabalho {#workflow-log-and-tasks}

A variável ![](assets/printpreview_darkgrey-24px.png) ícone abre o log de workflow e o menu de tarefas.

O histórico do workflow é salvo pela duração especificada nas opções de execução do workflow (consulte [Propriedades do fluxo de trabalho](../../automating/using/managing-execution-options.md)). Durante essa duração, todas as mensagens são salvas, mesmo após uma reinicialização. Se não quiser salvar as mensagens de uma execução anterior, você precisará expurgar o histórico clicando no link ![](assets/delete_darkgrey-24px.png) botão.

A variável **[!UICONTROL Log]** contém o histórico de execução de todas as atividades ou de qualquer atividade selecionada. Ele indexa as operações realizadas e os erros de execução por ordem cronológica.

![](assets/wkf_execution_4.png)

A variável **[!UICONTROL Tasks]** A guia detalha a sequência de execução das atividades. Clique em uma tarefa para obter mais informações.

![](assets/wkf_execution_5.png)

Nestas duas listas:

* Clique no contador para ver o número total de atividades de acordo com o filtro aplicado. O contador é exibido por padrão se o número de elementos na lista for menor que 30.
* A variável **[!UICONTROL Configure list]** permite escolher as informações exibidas, definir a ordem das colunas e classificar a lista.
* Você pode usar filtros para encontrar as informações que precisa mais rapidamente. Use o campo de pesquisa para procurar um texto específico em nomes de atividades de workflow (por exemplo: &quot;query&quot;) e logs.

## Gerenciamento de erros {#error-management}

Quando ocorre um erro, o workflow é pausado e a atividade que estava sendo executada quando o erro foi encontrado pisca em vermelho.

O status do workflow fica vermelho e o erro é registrado no log.

Você pode configurar o workflow para que ele não seja pausado e continue a ser executado sem erros. Para fazer isso, vá para as propriedades do workflow por meio de ![](assets/edit_darkgrey-24px.png) e, no campo **[!UICONTROL Execution]** , selecione a **Ignorar** opção no **Em caso de erro** campo.

Nesse caso, a tarefa incorreta é anulada. Esse modo é particularmente adequado para workflows projetados para tentar novamente a operação mais tarde (ações periódicas).

>[!NOTE]
>
>Você pode aplicar essa configuração individualmente para cada atividade. Para fazer isso, selecione uma atividade e abra-a usando a ação rápida ![](assets/edit_darkgrey-24px.png). Em seguida, selecione o modo de gerenciamento de erro na caixa **Opções de execução** guia. Consulte [Opções de execução da atividade](../../automating/using/activity-properties.md).

No [propriedades do fluxo de trabalho](../../automating/using/managing-execution-options.md), opções adicionais relacionadas ao gerenciamento de erros estão disponíveis.

![](assets/wkf_execution_error.png)

As opções possíveis são:

* **[!UICONTROL Supervisors]**: permite definir o grupo de pessoas a notificar (notificação por email e no aplicativo) se o fluxo de trabalho encontrar um erro. Se nenhum grupo for definido, ninguém será notificado. Para obter mais informações sobre notificações do Adobe Campaign, consulte [Notificações do Adobe Campaign](../../administration/using/sending-internal-notifications.md).

* **[!UICONTROL In case of error]**: permite especificar a ação que será executada caso a atividade encontre um erro. Há duas opções disponíveis para isso:

   * **Suspender processo**: o workflow é suspenso automaticamente. O status do workflow é então **Errado** e a cor associada fica vermelha. Depois que o problema for resolvido, reinicie o workflow.
   * **Ignorar**: a atividade não é executada e, como resultado, nenhuma das atividades que a seguem (na mesma ramificação). Isso pode ser útil para tarefas recorrentes. Se a ramificação tiver um scheduler colocado upstream, ele deverá ser acionado na próxima data de execução.

* **[!UICONTROL Consecutive errors]** : permite definir vários erros consecutivos que são autorizados antes que a execução do workflow seja suspensa automaticamente.

   * Se o número especificado for **[!UICONTROL 0]** ou, desde que o número especificado não seja atingido, as atividades que encontram erros serão ignoradas. As outras ramificações de fluxo de trabalho são executadas normalmente.

   * Se o número especificado for atingido, todo o fluxo de trabalho será suspenso e se tornará **[!UICONTROL Erroneous]**. Se os supervisores tiverem sido definidos, eles serão automaticamente notificados por um e-mail. Consulte [Notificações do Adobe Campaign](../../administration/using/sending-internal-notifications.md).
