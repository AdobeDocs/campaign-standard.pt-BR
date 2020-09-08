---
title: Gerenciamento de opções de execução
description: Saiba como gerenciar as opções de execução de workflows.
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
source-git-commit: 8ebded956ef52bb742160d62ebbd8095c390d51c
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 2%

---


# Gerenciamento de opções de execução {#managing-execution-options}

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

* **[!UICONTROL Severity]**: permite que você especifique um nível de prioridade para executar workflows na sua instância do Adobe Campaign. Este campo é usado pelas equipes de Adobe apenas para fins de monitoramento.

A **[!UICONTROL Error management]** seção fornece opções adicionais que permitem gerenciar como os workflows se comportam em caso de erros. Essas opções são detalhadas na seção Gerenciamento [de](../../automating/using/monitoring-workflow-execution.md#error-management) erros.
