---
solution: Campaign Standard
product: campaign
title: Gerenciamento de opções de execução
description: Saiba como gerenciar as opções de execução de workflows.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 14%

---


# Gerenciamento de opções de execução {#managing-execution-options}

Para modificar as opções de execução de um fluxo de trabalho, use o botão ![](assets/edit_darkgrey-24px.png) para acessar as propriedades do fluxo de trabalho e selecione a seção **[!UICONTROL Execution]**.

![](assets/wkf_execution_6.png)

As opções possíveis são:

* **[!UICONTROL Default affinity]**: esse campo permite forçar a execução de um fluxo de trabalho ou de uma atividade de fluxo de trabalho em uma máquina específica.

* **[!UICONTROL History in days]**: especifica o número de dias após os quais o histórico deve ser expurgado. O histórico contém elementos relacionados ao fluxo de trabalho: registros, tarefas, eventos (objetos técnicos vinculados à operação do fluxo de trabalho), bem como arquivos baixados pela atividade **[!UICONTROL Transfer file]**. O valor padrão é 30 dias para modelos de fluxo de trabalho predefinidos.

   A remoção do histórico é executada pelo fluxo de trabalho técnico de limpeza do Banco de Dados, que é executado por padrão todos os dias (consulte [Lista de workflows técnicos](../../administration/using/technical-workflows.md).)

   >[!IMPORTANT]
   >
   >Se o campo **[!UICONTROL History in days]** for deixado em branco, seu valor será considerado como &quot;1&quot;, o que significa que o histórico será limpo após 1 dia.

* **[!UICONTROL Save SQL queries in the log]**: permite salvar os query SQL do fluxo de trabalho nos logs.

* **[!UICONTROL Keep interim results]**: marque essa opção se quiser ser capaz de visualização dos detalhes das transições.

   >[!CAUTION]
   >
   >Essa opção consome bastante espaço do disco e foi projetada para ajudar a criar um fluxo de trabalho e garantir a configuração e o comportamento adequados. Deixe-a desmarcada nas instâncias de produção.

* **[!UICONTROL Execute in the engine (do not use in production)]**: permite que você execute o fluxo de trabalho localmente, para fins de teste de ambiente de desenvolvimento.

* **[!UICONTROL Severity]**: permite que você especifique um nível de prioridade para executar workflows na sua instância do Adobe Campaign. Este campo é usado pelas equipes de Adobe apenas para fins de monitoramento.

A seção **[!UICONTROL Error management]** fornece opções adicionais que permitem gerenciar como os workflows se comportam em caso de erros. Essas opções são detalhadas na seção [Gerenciamento de erros](../../automating/using/monitoring-workflow-execution.md#error-management).
