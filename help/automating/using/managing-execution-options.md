---
title: Gerenciamento de opções de execução
description: Saiba como gerenciar opções de execução de workflows.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: b0cc38fe-cf71-4350-8b4e-7daf0bf94066
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 14%

---

# Gerenciamento de opções de execução {#managing-execution-options}

Para modificar as opções de execução de um fluxo de trabalho, use o ![](assets/edit_darkgrey-24px.png) para acessar as propriedades do workflow e selecionar a variável **[!UICONTROL Execution]** seção.

![](assets/wkf_execution_6.png)

As opções possíveis são:

* **[!UICONTROL Default affinity]**: este campo permite forçar a execução de um workflow ou de uma atividade de workflow em uma máquina específica.

* **[!UICONTROL History in days]**: especifica o número de dias após o qual o histórico deve ser apagado. O histórico contém elementos relacionados ao workflow: logs, tarefas, eventos (objetos técnicos vinculados à operação do workflow), bem como arquivos baixados pelo **[!UICONTROL Transfer file]** atividade. O valor padrão é de 30 dias para modelos de fluxo de trabalho prontos para uso.

  A limpeza do histórico é executada pelo fluxo de trabalho técnico de limpeza do banco de dados, que é executado todos os dias por padrão (consulte [Lista de workflows técnicos](../../administration/using/technical-workflows.md).)

  >[!IMPORTANT]
  >
  >Se a variável **[!UICONTROL History in days]** for deixado em branco, seu valor será considerado como &quot;1&quot;, o que significa que o histórico será limpo após 1 dia.

* **[!UICONTROL Save SQL queries in the log]**: permite salvar as consultas SQL do workflow nos logs.

* **[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]**: marque esta opção se quiser que todo o plano de execução seja registrado. Ela está desativada por padrão.

  Para obter mais informações sobre essa opção, consulte esta [seção](#diagnostic-mode).

* **[!UICONTROL Keep interim results]**: marque esta opção se desejar visualizar os detalhes das transições.

  >[!CAUTION]
  >
  >Essa opção consome bastante espaço do disco e foi projetada para ajudar a criar um fluxo de trabalho e garantir a configuração e o comportamento adequados. Deixe-a desmarcada nas instâncias de produção.

* **[!UICONTROL Execute in the engine (do not use in production)]**: permite executar o workflow localmente, para fins de teste do ambiente de desenvolvimento.

* **[!UICONTROL Severity]**: permite especificar um nível de prioridade para executar workflows na instância do Adobe Campaign. Este campo é usado por equipes do Adobe somente para fins de monitoramento.

A variável **[!UICONTROL Error management]** A seção fornece opções adicionais que permitem gerenciar como os workflows se comportam em caso de erros. Essas opções são detalhadas na seção [Gerenciamento de erros](../../automating/using/monitoring-workflow-execution.md#error-management) seção.

## Modo de diagnóstico {#diagnostic-mode}

>[!CAUTION]
>
>Essa opção pode afetar significativamente o desempenho do fluxo de trabalho e deve ser usada com moderação.

Quando ativado, a variável **[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]** opção no **[!UICONTROL Execution]** A seção das propriedades do fluxo de trabalho registra todo o plano de execução se uma consulta levar mais de um minuto.

![](assets/wkf_diagnostic.png)

Depois de ativar essa opção e iniciar o fluxo de trabalho, se a consulta levar mais de um minuto, o plano de execução será registrado. Você pode recuperar seu plano de execução usando uma ANÁLISE DE EXPLICAÇÃO.

Para obter mais informações, consulte [Documentação do PostgreSQL](https://www.postgresql.org/docs/9.4/using-explain.html).

Se você tiver uma varredura de sequência nessa consulta, a variável **[!UICONTROL Diagnostic mode]** O também fornecerá recomendações para criar um índice com a ajuda de uma expressão de filtro.

>[!NOTE]
>
> Essas recomendações são destinadas apenas para fins de referência e devem ser usadas com cuidado, dependendo do seu caso de uso.

![](assets/wkf_diagnostic_4.png)

As duas condições a seguir devem ser atendidas durante a execução do workflow para acionar recomendações:

* A verificação em sequência leva mais de 40% do tempo da consulta.

* As linhas resultantes após a verificação em sequência são inferiores a 1 % do total de linhas presentes na tabela.

Você pode gerenciar a opção no menu avançado selecionando **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**:

* **[!UICONTROL Time of query execution (in milliseconds)(DiagnosticModeQueryTime)]**: No **[!UICONTROL Value]** , você pode definir um novo horário para a execução da consulta. Se a execução da consulta exceder esse valor, o plano de execução será registrado.

  ![](assets/wkf_diagnostic_2.png)

* **[!UICONTROL Percentage of seq scan time (DiagnosticModeSeqScanPercentage)]**: No **[!UICONTROL Value]** , você pode alterar a porcentagem de tempo de consulta que a verificação de sequência deve levar para que a recomendação seja gerada.

  ![](assets/wkf_diagnostic_3.png)
