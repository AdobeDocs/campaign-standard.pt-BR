---
solution: Campaign Standard
product: campaign
title: Interface do workflow 
description: Saiba mais sobre a interface e as opções para criar, editar e executar um workflow.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
context-tags: workflow,main;workflow,overview
feature: Fluxos de trabalho
role: Arquiteto de dados
level: Iniciante
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 4%

---


# Interface do workflow {#workflow-interface}

Você pode criar fluxos de trabalho para gerenciar processos inteiros em suas campanhas e programas.

A tela de edição do workflow é composta pelos seguintes elementos:

* A [Paleta](#palette), que faz referência às atividades disponíveis.
* O [Workspace](#workspace), no qual as atividades são configuradas e organizadas.
* A [Barra de ação](#action-bar), que é composta por botões que permitem interagir com o fluxo de trabalho e/ou seus componentes.
* As [Ações rápidas](#quick-actions), que aparecem ao redor de uma atividade selecionada, permitem que você interaja com ela.

![](assets/wkf_overview.png)

## Paleta {#palette}

A paleta fica no lado esquerdo da tela. Todas as atividades disponíveis são classificadas em várias categorias:

* [Direcionamento](../../automating/using/about-targeting-activities.md): atividades específicas para direcionamento, manipulação de dados de população e atividades de filtragem
* [Execução](../../automating/using/about-execution-activities.md): atividades específicas para organizar e executar workflows
* [Canais](../../automating/using/about-channel-activities.md): atividades que representam os diferentes canais de comunicação disponíveis
* [Gestão de Dados (ETL)](../../automating/using/about-data-management-activities.md): atividades específicas para manipular dados

Para usar uma atividade da paleta no fluxo de trabalho, arraste-a e solte-a no espaço de trabalho.

É necessário configurar cada atividade adicionada a partir da paleta antes de iniciar o fluxo de trabalho.

![](assets/workflow_palette.png)

## Espaço de trabalho {#workspace}

O espaço de trabalho é a zona central no editor de fluxo de trabalho. É nessa zona que você pode soltar suas atividades, vinculá-las usando transições e configurá-las.

Para vincular duas atividades, mova o final da seta da primeira atividade para a seguinte atividade até que elas se conectem. Também é possível mover a atividade em direção ao ponto da seta atrás dela para vinculá-la à atividade anterior. Se você mover qualquer uma das atividades, elas permanecerão vinculadas.

As transições que seguem atividades que processam dados contêm as populações intermediárias. Você pode acessá-los se marcar a opção **[!UICONTROL Keep interim results]** na seção **[!UICONTROL Execution]** das propriedades do workflow.

>[!CAUTION]
>
>Essa opção consome bastante espaço do disco e foi projetada para ajudar a criar um fluxo de trabalho e garantir a configuração e o comportamento adequados. Deixe-a desmarcada nas instâncias de produção.


Quando uma atividade é selecionada, as ações rápidas aparecem ao redor da atividade, permitindo que você interaja com ela. Por exemplo, para configurar uma atividade, selecione-a e depois a abra usando o botão ![](assets/edit_darkgrey-24px_table.png) nas ações rápidas.

Certas funções só são ativadas no espaço de trabalho:

* Selecione várias atividades e transições desenhando uma zona ao seu redor.
* Pressione **Ctrl** + clique com o botão esquerdo para selecionar várias atividades e/ou transições.
* Pressione **Enter** para visualizar os detalhes da atividade ou transição atualmente selecionada.
* Pressione **Delete** para excluir a atividade selecionada no momento.
* Pressione **Ctrl + C** para copiar as atividades selecionadas e **Ctrl + V** para colá-las no espaço de trabalho.

![](assets/workflow_workspace.png)

## Barra de ação {#action-bar}

Dependendo dos elementos selecionados no espaço de trabalho ou do status de execução do fluxo de trabalho, os botões disponíveis na barra de ação podem variar.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Permite editar as propriedades do fluxo de trabalho.

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>Inicia o workflow.

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>Pausa o workflow.

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>Interrompe a execução do workflow. Não pode ser retomado de onde parou.

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>Reinicia o fluxo de trabalho.

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>Abre o log de execução do workflow.

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>Ativa o modo de seleção múltipla. O fluxo de trabalho deve ser composto de pelo menos duas atividades.

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>Desativa o modo de seleção múltipla.<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>Abre a transição selecionada.<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>Reativa a seleção se ela tiver sido desativada ou marcada como pausada anteriormente.<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Pausa o fluxo de trabalho na atividade selecionada.<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Desativa a atividade.<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Exclui as atividades selecionadas.<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia as atividades selecionadas.

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>Cola as atividades que foram copiadas.

## Ações rápidas {#quick-actions}

Quando uma atividade é selecionada, os botões de ação rápida aparecem ao redor da atividade, permitindo que você interaja com ela.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Abre a atividade selecionada.

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia a atividade selecionada.

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>Abre as opções avançadas da atividade Email or SMS delivery selecionada.

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>Reativa a seleção se ela tiver sido desativada ou marcada como pausada anteriormente.

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Pausa o fluxo de trabalho na atividade selecionada.

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Desativa a atividade.

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>Força o processamento imediato da seleção. Este botão só está disponível para as atividades <span class="uicontrol">Scheduler</span> e <span class="uicontrol">Wait</span>.

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Exclui as atividades selecionadas.

## Duplicação de atividades de workflow {#duplicating-workflow-activities}

O espaço de trabalho permite duplicar atividades do workflow, copiando-as e colando-as no mesmo workflow ou em outro workflow da mesma instância do Campaign.

Após duplicar uma atividade, toda a configuração é mantida. Para atividades de delivery (Email, SMS, Notificação por push..), o objeto de delivery anexado à atividade é duplicado.

>[!NOTE]
>
>As atividades de workflow não podem ser duplicadas de uma instância para outra. Não é possível duplicar atividades de workflows técnicos.

Para duplicar uma atividade, siga as etapas abaixo:

1. Selecione a atividade e clique no botão **[!UICONTROL Copy selection]** nas ações rápidas.

   Você também pode usar o atalho de teclado **Ctrl + C**.

   ![](assets/wkf_copypaste1.png)

1. Clique com o botão direito do mouse no espaço de trabalho do workflow de destino e clique no botão **[!UICONTROL Paste]**.

   Você também pode usar o atalho de teclado **CTRL + V**.

   ![](assets/wkf_copypaste2.png)

1. A atividade é duplicada, com todas as configurações definidas inicialmente.

Também é possível copiar e colar várias atividades, permitindo que você duplique um fluxo de trabalho inteiro.

Para fazer isso, selecione as atividades desenhando uma zona ao redor delas. em seguida, clique no botão **[!UICONTROL Copy selection]** na barra de ações (ou pressione **Ctrl + C**). Em seguida, você pode colá-los no local desejado.

![](assets/wkf_copypaste3.png)

