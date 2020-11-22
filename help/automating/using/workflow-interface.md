---
solution: Campaign Standard
product: campaign
title: Interface do workflow 
description: Saiba mais sobre a interface e as opções para criar, editar e executar um fluxo de trabalho.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
context-tags: workflow,main;workflow,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 4%

---


# Interface do workflow {#workflow-interface}

Você pode criar workflows para gerenciar processos inteiros em suas campanhas e programas.

A tela de edição do fluxo de trabalho é composta dos seguintes elementos:

* A [Paleta](#palette), que faz referência às atividades disponíveis.
* A [Workspace](#workspace), na qual as atividades são configuradas e organizadas.
* A barra [](#action-bar)de Ação, que é composta de botões que permitem interagir com o fluxo de trabalho e/ou seus componentes.
* As ações [](#quick-actions)Rápidas, que aparecem ao redor de uma atividade selecionada, permitem interagir com ela.

![](assets/wkf_overview.png)

## Paleta {#palette}

A paleta fica do lado esquerdo da tela. Todas as atividades disponíveis são classificadas em várias categorias:

* [Definição de metas](../../automating/using/about-targeting-activities.md): atividades específicas para segmentação, manipulação de dados de população e filtragem de atividades
* [Execução](../../automating/using/about-execution-activities.md): atividades específicas para organizar e executar workflows
* [Canais](../../automating/using/about-channel-activities.md): atividades que representam os diferentes canais de comunicação disponíveis
* [gestão de dados (ETL)](../../automating/using/about-data-management-activities.md): atividades específicas para manipular dados

Para usar uma atividade da paleta em seu fluxo de trabalho, arraste-a e solte-a em seu espaço de trabalho.

É necessário configurar cada atividade adicionada a partir da paleta antes de iniciar o fluxo de trabalho.

![](assets/workflow_palette.png)

## Espaço de trabalho {#workspace}

O espaço de trabalho é a zona central no editor de fluxo de trabalho. É nessa zona que você pode soltar suas atividades, vinculá-las usando o transição e configurá-las.

Para vincular duas atividades, mova a extremidade da seta da primeira atividade para a seguinte atividade até que elas se conectem. Você também pode mover a atividade em direção ao ponto da seta atrás dela para vinculá-la à atividade anterior. Se você mover qualquer uma das atividades, elas permanecerão ligadas.

Transições que seguem atividades que processam dados contêm as populações intermediárias. Você pode acessá-los se marcar a opção **[!UICONTROL Keep interim results]** na seção **[!UICONTROL Execution]** das propriedades do fluxo de trabalho.

>[!CAUTION]
>
>Essa opção consome bastante espaço do disco e foi projetada para ajudar a criar um fluxo de trabalho e garantir a configuração e o comportamento adequados. Deixe-a desmarcada nas instâncias de produção.


Quando uma atividade é selecionada, ações rápidas são exibidas ao redor da atividade, permitindo que você interaja com ela. Por exemplo, para configurar uma atividade, selecione-a e abra-a usando o ![](assets/edit_darkgrey-24px_table.png) botão nas ações rápidas.

Determinadas funções são ativadas somente no espaço de trabalho:

* Selecione várias atividades e transições desenhando uma zona ao seu redor.
* Pressione **Ctrl** + clique esquerdo para selecionar várias atividades e/ou transições.
* Pressione **Enter** para visualização dos detalhes da atividade ou transição atualmente selecionada.
* Pressione **Excluir** para excluir a atividade atualmente selecionada.
* Pressione **Ctrl + C** para copiar as atividades selecionadas e **Ctrl + V** para colá-las no espaço de trabalho.

![](assets/workflow_workspace.png)

## Barra de ação {#action-bar}

Dependendo dos elementos selecionados no espaço de trabalho ou do status de execução do fluxo de trabalho, os botões disponíveis na barra de ações podem variar.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Permite editar as propriedades do fluxo de trabalho.

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>Start o fluxo de trabalho.

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>Pausa o fluxo de trabalho.

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>Interrompe a execução do fluxo de trabalho. Não pode ser retomado de onde foi parado.

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>Reinicia o fluxo de trabalho.

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>Abre o log de execução do fluxo de trabalho.

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>Ativa o modo de seleção múltipla. O fluxo de trabalho deve ser composto de pelo menos duas atividades.

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>Desativa o modo de seleção múltipla.<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>Abre a transição selecionada.<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>Reativa a seleção se ela tiver sido desabilitada ou marcada como pausada anteriormente.<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Pausa o fluxo de trabalho na atividade selecionada.<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Desativa a atividade.<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Exclui as atividades selecionadas.<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia as atividades selecionadas.

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>Cola as atividades que foram copiadas.

## Ações rápidas {#quick-actions}

Quando uma atividade é selecionada, os botões de ação rápida aparecem ao redor da atividade, permitindo que você interaja com ela.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Abre a atividade selecionada.

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia a atividade selecionada.

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>Abre as opções avançadas da atividade de E-mail ou delivery SMS selecionada.

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>Reativa a seleção se ela tiver sido desabilitada ou marcada como pausada anteriormente.

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Pausa o fluxo de trabalho na atividade selecionada.

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Desativa a atividade.

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>Força o processamento imediato da seleção. Este botão só está disponível para as atividades <span class="uicontrol">Scheduler</span> e <span class="uicontrol">Espera</span> .

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Exclui as atividades selecionadas.

## Duplicação de atividades de fluxo de trabalho {#duplicating-workflow-activities}

A área de trabalho permite que você duplicado atividades de fluxo de trabalho copiando-as colando no mesmo fluxo de trabalho ou em outro fluxo de trabalho da mesma instância de Campanha.

Depois que uma atividade é duplicada, toda a sua configuração é mantida. Para atividades delivery (Email, SMS, Notificação por push...), o objeto delivery anexado à atividade é duplicado.

>[!NOTE]
>
>Atividades de fluxo de trabalho não podem ser duplicadas de uma instância para outra. Atividades de workflows técnicos não podem ser duplicadas.

Para duplicado de uma atividade, siga as etapas abaixo:

1. Selecione a atividade e clique no **[!UICONTROL Copy selection]** botão das ações rápidas.

   Você também pode usar o atalho de teclado **Ctrl + C** .

   ![](assets/wkf_copypaste1.png)

1. Clique com o botão direito do mouse na área de trabalho do fluxo de trabalho do público alvo e clique no **[!UICONTROL Paste]** botão.

   Você também pode usar o atalho de teclado **CTRL + V** .

   ![](assets/wkf_copypaste2.png)

1. A atividade é duplicada, com todas as configurações definidas inicialmente.

Também é possível copiar e colar várias atividades, permitindo que você duplicado um fluxo de trabalho inteiro.

Para fazer isso, selecione as atividades desenhando uma zona ao seu redor. em seguida, clique no **[!UICONTROL Copy selection]** botão da barra de ação (ou pressione **Ctrl + C**). Em seguida, você pode colá-los no local desejado.

![](assets/wkf_copypaste3.png)

