---
title: Interface de fluxo de trabalho
description: Saiba mais sobre a interface e as opções para criar, editar e executar um fluxo de trabalho.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
context-tags: workflow,main;workflow,overview
feature: Workflows
role: Data Architect
level: Beginner
exl-id: a3f35bb9-e61e-4f3f-b855-1d677422f75a
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 4%

---

# Interface de fluxo de trabalho{#workflow-interface}

Você pode criar workflows para gerenciar processos inteiros em suas campanhas e programas.

A tela de edição do workflow é composta pelos seguintes elementos:

* A variável [Paleta](#palette), que faz referência às atividades disponíveis.
* A variável [Workspace](#workspace), no qual as atividades são configuradas e organizadas.
* A variável [Barra de ação](#action-bar), que é composto por botões que permitem a interação com o fluxo de trabalho e/ou seus componentes.
* A variável [Ações rápidas](#quick-actions), que aparecem ao redor de uma atividade selecionada, permitem que você interaja com ela.

![](assets/wkf_overview.png)

## Paleta {#palette}

A paleta está no lado esquerdo da tela. Todas as atividades disponíveis são classificadas em várias categorias:

* [Direcionamento](../../automating/using/about-targeting-activities.md): atividades específicas para direcionamento, manipulação de dados de população e atividades de filtragem
* [Execução](../../automating/using/about-execution-activities.md): atividades específicas para organizar e executar workflows
* [Canais](../../automating/using/about-channel-activities.md): atividades que representam os diferentes canais de comunicação disponíveis
* [Gerenciamento de dados (ETL)](../../automating/using/about-data-management-activities.md): atividades específicas para manipulação de dados

Para usar uma atividade da paleta no seu fluxo de trabalho, arraste-a e solte-a no espaço de trabalho.

É necessário configurar cada atividade adicionada da paleta antes de iniciar o workflow.

![](assets/workflow_palette.png)

## Workspace {#workspace}

O espaço de trabalho é a zona central no editor de fluxo de trabalho. É nessa zona que você pode descartar suas atividades, vinculá-las usando transições e configurá-las.

Para vincular duas atividades, mova o final da seta da primeira atividade para a atividade seguinte até que elas se conectem. Você também pode mover a atividade em direção ao ponto da seta atrás dela para vinculá-la à atividade anterior. Se você mover qualquer uma das atividades, elas permanecerão vinculadas.

As transições após atividades que processam dados contêm as populações intermediárias. Você pode acessá-las se marcar a opção **[!UICONTROL Keep interim results]** opção no **[!UICONTROL Execution]** das propriedades do workflow.

>[!CAUTION]
>
>Essa opção consome bastante espaço do disco e foi projetada para ajudar a criar um fluxo de trabalho e garantir a configuração e o comportamento adequados. Deixe-a desmarcada nas instâncias de produção.


Quando uma atividade é selecionada, ações rápidas aparecem ao redor da atividade, permitindo que você interaja com ela. Por exemplo, para configurar uma atividade, selecione-a e depois abra-a usando o ![](assets/edit_darkgrey-24px_table.png) nas ações rápidas.

Determinadas funções só são ativadas no espaço de trabalho:

* Selecione várias atividades e transições desenhando uma zona ao redor delas.
* Pressione **Ctrl** + clique com o botão esquerdo para selecionar várias atividades e/ou transições.
* Pressione **Enter** para exibir os detalhes da atividade ou transição selecionada no momento.
* Pressione **Excluir** para excluir a atividade selecionada no momento.
* Pressione **Ctrl+C** para copiar as atividades selecionadas, e **Ctrl+V** para colá-los no espaço de trabalho.

![](assets/workflow_workspace.png)

## Barra de ação {#action-bar}

Dependendo dos elementos selecionados no espaço de trabalho ou no status de execução do fluxo de trabalho, os botões disponíveis na barra de ação podem variar.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Permite editar as propriedades do workflow.

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>Inicia o workflow.

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>Pausa o workflow.

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>Interrompe a execução do workflow. Não é possível retomar de onde parou.

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>Reinicia o workflow.

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>Abre o log de execução do workflow.

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>Ativa o modo de seleção múltipla. O fluxo de trabalho deve ser composto de pelo menos duas atividades.

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>Desativa o modo de seleção múltipla.<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>Abre a transição selecionada.<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>Reativa a seleção se ela tiver sido previamente desativada ou marcada como pausada.<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Pausa o fluxo de trabalho na atividade selecionada.<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Desativa a atividade.<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Exclui as atividades selecionadas.<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia as atividades selecionadas.

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>Cola as atividades copiadas.

## Ações rápidas {#quick-actions}

Quando uma atividade é selecionada, botões de ação rápida são exibidos ao redor dela, permitindo que você interaja com ela.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Abre a atividade selecionada.

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia a atividade selecionada.

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>Abre as opções avançadas da atividade Email ou SMS delivery selecionada.

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>Reativa a seleção se ela tiver sido previamente desativada ou marcada como pausada.

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Pausa o fluxo de trabalho na atividade selecionada.

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Desativa a atividade.

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>Força o processamento imediato da seleção. Esse botão só está disponível para o <span class="uicontrol">Scheduler</span> e <span class="uicontrol">Aguardar</span> atividades.

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Exclui as atividades selecionadas.

## Duplicação de atividades de workflow {#duplicating-workflow-activities}

O espaço de trabalho permite duplicar atividades de fluxo de trabalho, copiando-as no mesmo fluxo de trabalho ou em outro fluxo de trabalho da mesma instância do Campaign.

Depois que uma atividade é duplicada, toda a sua configuração é mantida. Para atividades de delivery (Email, SMS, Notificação por push...), o objeto de delivery anexado à atividade é duplicado.

>[!NOTE]
>
>As atividades de fluxo de trabalho não podem ser duplicadas de uma instância para outra. Atividades de workflows técnicos não podem ser duplicadas.

Para duplicar uma atividade, siga as etapas abaixo:

1. Selecione a atividade e clique no botão **[!UICONTROL Copy selection]** nas ações rápidas.

   Você também pode usar a variável **Ctrl+C** atalho de teclado.

   ![](assets/wkf_copypaste1.png)

1. Clique com o botão direito do mouse no espaço de trabalho do workflow desejado e clique no **[!UICONTROL Paste]** botão.

   Você também pode usar a variável **CTRL + V** atalho de teclado.

   ![](assets/wkf_copypaste2.png)

1. A atividade é duplicada, com todas as configurações definidas inicialmente.

Também é possível copiar e colar várias atividades, permitindo duplicar um fluxo de trabalho inteiro.

Para fazer isso, selecione as atividades desenhando uma zona ao redor delas. em seguida, clique no link **[!UICONTROL Copy selection]** na barra de ações (ou pressione **Ctrl+C**). É possível colá-los no local desejado.

![](assets/wkf_copypaste3.png)
