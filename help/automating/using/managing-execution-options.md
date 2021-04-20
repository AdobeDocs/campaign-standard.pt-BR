---
solution: Campaign Standard
product: campaign
title: Gerenciamento de opções de execução
description: Saiba como gerenciar opções de execução de workflows.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 14%

---


# Gerenciamento de opções de execução {#managing-execution-options}

Para modificar as opções de execução de um workflow, use o botão ![](assets/edit_darkgrey-24px.png) para acessar as propriedades do workflow e selecione a seção **[!UICONTROL Execution]** .

![](assets/wkf_execution_6.png)

As opções possíveis são:

* **[!UICONTROL Default affinity]**: este campo permite que você force a execução de um fluxo de trabalho ou de uma atividade de fluxo de trabalho em uma máquina específica.

* **[!UICONTROL History in days]**: especifica o número de dias após o qual o histórico deve ser removido. O histórico contém elementos relacionados ao workflow : logs, tarefas, eventos (objetos técnicos vinculados à operação do workflow), bem como arquivos baixados pela atividade **[!UICONTROL Transfer file]** . O valor padrão é 30 dias para modelos de fluxo de trabalho prontos para uso.

   A limpeza do histórico é executada pelo workflow técnico Database cleanup , que é executado por padrão todos os dias (consulte [List of technical workflows](../../administration/using/technical-workflows.md).)

   >[!IMPORTANT]
   >
   >Se o campo **[!UICONTROL History in days]** for deixado em branco, seu valor será considerado &quot;1&quot;, significando que o histórico será removido após 1 dia.

* **[!UICONTROL Save SQL queries in the log]**: permite salvar as consultas SQL do workflow nos logs.

* **[!UICONTROL Keep interim results]**: marque esta opção se desejar visualizar os detalhes das transições.

   >[!CAUTION]
   >
   >Essa opção consome bastante espaço do disco e foi projetada para ajudar a criar um fluxo de trabalho e garantir a configuração e o comportamento adequados. Deixe-a desmarcada nas instâncias de produção.

* **[!UICONTROL Execute in the engine (do not use in production)]**: O permite executar o workflow localmente para fins de teste de ambiente de desenvolvimento.

* **[!UICONTROL Severity]**: O permite especificar um nível de prioridade para executar workflows na instância do Adobe Campaign. Este campo é usado pelas equipes Adobe somente para fins de monitoramento.

A seção **[!UICONTROL Error management]** fornece opções adicionais que permitem gerenciar o comportamento dos workflows em caso de erros. Essas opções são detalhadas na seção [Error management](../../automating/using/monitoring-workflow-execution.md#error-management) .
