---
title: Interface do fluxo de trabalho
seo-title: Interface do fluxo de trabalho
description: Interface do fluxo de trabalho
seo-description: Saiba mais sobre a interface e as opções para criar, editar e executar um fluxo de trabalho.
page-status-flag: nunca ativado
uuid: aafe 33 ed-fa 07-4 dd 9-825 e -242099334 f 1 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: sobre fluxos de trabalho e gerenciamento de dados
discoiquuid: 147 fbb 0 d -17 d 2-444 b-a 215-9 ad 14179 c 549
context-tags: fluxo de trabalho, principal; fluxo de trabalho, visão geral
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6748e59aaeafce9dc6e77dc0664a9024a53c3e35

---


# Workflow interface{#workflow-interface}

Você pode criar fluxos de trabalho para gerenciar processos inteiros em suas campanhas e programas.

A tela de edição do fluxo de trabalho é composta pelos seguintes elementos:

* [A paleta](../../automating/using/workflow-interface.md#palette), que faz referência às atividades disponíveis.
* [O Workspace](../../automating/using/workflow-interface.md#workspace), no qual as atividades são configuradas e organizadas.
* The [Action bar](../../automating/using/workflow-interface.md#action-bar), which is made up of buttons that allow you to interact with the workflow and/or its components.
* The [Quick actions](../../automating/using/workflow-interface.md#quick-actions), which appear around a selected activity, allow you to interact with it.

![](assets/wkf_overview.png)

## Palette {#palette}

A paleta está no lado esquerdo da tela. Todas as atividades disponíveis são classificadas em diversas categorias:

* [Definição de metas](../../automating/using/about-targeting-activities.md): atividades específicas da definição de metas, manipulação de dados de preenchimento e filtragem de atividades
* [Execução](../../automating/using/about-execution-activities.md): atividades específicas para organização e execução de fluxos de trabalho
* [Canais](../../automating/using/about-channel-activities.md): atividades que representam os canais de comunicação disponíveis diferentes
* [Gerenciamento de dados (ETL)](../../automating/using/about-data-management-activities.md): atividades específicas para manipular dados

Para usar uma atividade da paleta no seu fluxo de trabalho, arraste e solte-a em sua área de trabalho.

É necessário configurar cada atividade adicionada da paleta antes de iniciar o fluxo de trabalho.

![](assets/workflow_palette.png)

## Workspace {#workspace}

A área de trabalho é a zona central no editor de fluxo de trabalho. É nesta zona que você pode soltar suas atividades, vinculá-las ao mesmo tempo usando transições e configurá-las.

Para vincular duas atividades, mova o final da seta da primeira atividade até a seguinte atividade até que se conecte. Também é possível mover a atividade para o ponto da seta atrás dele para vinculá-la à atividade anterior. Se você mover qualquer atividade, elas permanecerão vinculadas.

Transições subsequentes de atividades que processam dados contêm populações intermediárias. You can access them if you check the **[!UICONTROL Keep interim results]** option in the **[!UICONTROL Execution]** section of the workflow properties.

Quando uma atividade é selecionada, as ações rápidas aparecem ao redor da atividade, permitindo interagir com ela. For example, to configure an activity, select it then open it using the ![](assets/edit_darkgrey-24px_table.png) button in the quick actions.

Algumas funções só estão habilitadas no espaço de trabalho:

* Selecione várias atividades e transições ao desenhar uma zona em torno delas.
* Press **Ctrl** + left click to select several activities and/or transitions.
* Press **Enter** to view the detail of the currently selected activity or transition.
* Press **Delete** to delete the currently selected activity.
* Press **Ctrl + C** to copy the selected activities, and **Ctrl + V** to paste them into the workspace.

![](assets/workflow_workspace.png)

## Action bar {#action-bar}

Dependendo dos elementos selecionados no espaço de trabalho ou no status de execução do fluxo de trabalho, os botões disponíveis na barra de ação podem variar.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Permite editar as propriedades do fluxo de trabalho.

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>Inicia o fluxo de trabalho.

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>Pausa o fluxo de trabalho.

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>Interrompe a execução do fluxo de trabalho. Não pode ser retomado de onde foi interrompido.

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>Reinicia o fluxo de trabalho.

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>Abre o log de execução do fluxo de trabalho.

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>Permite o modo de seleção múltipla. O fluxo de trabalho deve ser composto de pelo menos duas atividades.

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>Desativa o modo de várias seleções.<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>Abre a transição selecionada.<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>Habilite novamente a seleção se ela tiver sido desativada ou marcada como pausada.<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Pausa o fluxo de trabalho na atividade selecionada.<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Desativa a atividade.<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Exclui as atividades selecionadas.<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia as atividades selecionadas.

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>Cola as atividades que foram copiadas.

## Quick actions {#quick-actions}

Quando uma atividade é selecionada, os botões de ação rápida aparecem em torno da atividade, permitindo interagir com ela.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Abre a atividade selecionada.

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia a atividade selecionada.

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>Abre as opções avançadas da atividade de entrega de Email ou SMS selecionada.

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>Habilite novamente a seleção se ela tiver sido desativada ou marcada como pausada.

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Pausa o fluxo de trabalho na atividade selecionada.

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Desativa a atividade.

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>Força o processamento imediato da seleção. This button is only available for the <span class="uicontrol">Scheduler</span> and <span class="uicontrol">Wait</span> activities.

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Exclui as atividades selecionadas.

## Duplicating workflow activities {#duplicating-workflow-activities}

A área de trabalho permite duplicar as atividades do fluxo de trabalho copiando-as no mesmo fluxo de trabalho, ou em outro fluxo de trabalho da mesma instância Campanha.

Uma vez que uma atividade é duplicada, toda a configuração é mantida. Para atividades de entrega (Email, SMS, Notificação por push…), o objeto de entrega anexado à atividade é duplicado.

>[!NOTE]
>
>As atividades de fluxo de trabalho não podem ser duplicadas de uma instância para outra. As atividades de fluxos de trabalho técnicos não podem ser duplicadas.

Para duplicar uma atividade, siga as etapas abaixo:

1. Select the activity, then click the **[!UICONTROL Copy selection]** button from the quick actions.

   You can also use the **Ctrl + C** keyboard shortcut.

   ![](assets/wkf_copypaste1.png)

1. Right-click in the target workflow workspace, then click the **[!UICONTROL Paste]** button.

   You can also use the **CTRL + V** keyboard shortcut.

   ![](assets/wkf_copypaste2.png)

1. A atividade é duplicada, com todas as configurações que foram definidas inicialmente.

Também é possível copiar várias ativações, permitindo duplicar um fluxo inteiro.

Para fazer isso, selecione as atividades ao desenhar uma zona ao seu redor. then click the **[!UICONTROL Copy selection]** button from the action bar (or press **Ctrl + C**). Você pode colá-los no local desejado.

![](assets/wkf_copypaste3.png)

