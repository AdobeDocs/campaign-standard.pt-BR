---
solution: Campaign Standard
product: campaign
title: Monitoramento da execução do workflow
description: Saiba como monitorar a execução de um fluxo de trabalho.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 6%

---


# Monitoramento da execução do workflow {#monitoring}

## Log de fluxo de trabalho e tarefas {#workflow-log-and-tasks}

O ![](assets/printpreview_darkgrey-24px.png) ícone abre o log de fluxo de trabalho e o menu tarefa.

O histórico do fluxo de trabalho é salvo pela duração especificada nas opções de execução do fluxo de trabalho (consulte as propriedades [do](../../automating/using/managing-execution-options.md)fluxo de trabalho). Durante esse período, todas as mensagens são salvas, mesmo após uma reinicialização. Se você não quiser salvar as mensagens de uma execução anterior, é necessário limpar o histórico clicando no ![](assets/delete_darkgrey-24px.png) botão.

A **[!UICONTROL Log]** guia contém o histórico de execução de todas as atividades ou de qualquer atividade selecionada. Eles indicam as operações efetuadas e os erros de execução por ordem cronológica.

![](assets/wkf_execution_4.png)

The **[!UICONTROL Tasks]** tab details the execution sequencing of the activities. Clique em uma tarefa para obter mais informações.

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
>Você pode aplicar essa configuração individualmente para cada atividade. Para fazer isso, selecione uma atividade e abra-a usando a ação rápida ![](assets/edit_darkgrey-24px.png). Em seguida, selecione o modo de gerenciamento de erros na guia Opções **** de execução. Consulte Opções [de execução de](../../automating/using/activity-properties.md)Atividade.

Nas propriedades [do](../../automating/using/managing-execution-options.md)fluxo de trabalho, opções adicionais relacionadas ao gerenciamento de erros estão disponíveis.

![](assets/wkf_execution_error.png)

As opções possíveis são:

* **[!UICONTROL Supervisors]**: permite que você defina o grupo de pessoas a ser notificado (notificação por email e no aplicativo) se o fluxo de trabalho encontrar um erro. Se nenhum grupo for definido, ninguém será notificado. Para obter mais informações sobre notificações Adobe Campaign, consulte notificações [da](../../administration/using/sending-internal-notifications.md)Adobe Campaign.

* **[!UICONTROL In case of error]**: permite especificar a ação a ser executada caso a atividade encontre um erro. Há duas opções disponíveis para isso:

   * **Suspenda o processo**: o fluxo de trabalho é suspenso automaticamente. O status do fluxo de trabalho é então **Errado** e a cor associada fica vermelha. Depois que o problema for resolvido, reinicie o fluxo de trabalho.
   * **Ignorar**: a atividade não é executada e, como resultado, nenhuma das atividades a seguir (na mesma ramificação). Isso pode ser útil para tarefas recorrentes. Se a ramificação tiver um scheduler colocado em upstream, isso deverá disparar na próxima data de execução.

* **[!UICONTROL Consecutive errors]** : permite que você defina uma série de erros consecutivos autorizados antes da execução do fluxo de trabalho ser automaticamente suspensa.

   * Se o número especificado for **[!UICONTROL 0]**, ou enquanto o número especificado não for atingido, as atividades que encontrarem erros serão ignoradas. As outras ramificações de fluxo de trabalho são executadas normalmente.

   * Se o número especificado for atingido, todo o fluxo de trabalho será suspenso e se tornará **[!UICONTROL Erroneous]**. Se os supervisores tiverem sido definidos, eles serão automaticamente notificados por email. Consulte [Notificações do Adobe Campaign](../../administration/using/sending-internal-notifications.md).
