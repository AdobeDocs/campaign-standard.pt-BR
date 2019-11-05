---
title: Interface do fluxo de trabalho
description: Saiba mais sobre a interface e as opções para criar, editar e executar um fluxo de trabalho.
page-status-flag: nunca ativado
uuid: aafe33ed-fa07-4dd9-825e-242099334f1a
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: sobre fluxos de trabalho e gerenciamento de dados
discoiquuid: 147fbb0d-17d2-444b-a215-9ad14179c549
context-tags: fluxo de trabalho,principal;fluxo de trabalho,visão geral
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Interface do fluxo de trabalho{#workflow-interface}

Você pode criar fluxos de trabalho para gerenciar processos inteiros em suas campanhas e programas.

A tela de edição do fluxo de trabalho é composta dos seguintes elementos:

* A [Paleta](#palette), que faz referência às atividades disponíveis.
* A [Workspace](#workspace), na qual as atividades são configuradas e organizadas.
* A barra [](#action-bar)de Ação, que é composta de botões que permitem interagir com o fluxo de trabalho e/ou seus componentes.
* As ações [](#quick-actions)Rápidas, que aparecem ao redor de uma atividade selecionada, permitem interagir com ela.

![](assets/wkf_overview.png)

## Paleta {#palette}

A paleta fica do lado esquerdo da tela. Todas as atividades disponíveis são classificadas em várias categorias:

* [Definição de metas](../../automating/using/about-targeting-activities.md): atividades específicas para segmentação, manipulação de dados populacionais e atividades de filtragem
* [Execução](../../automating/using/about-execution-activities.md): atividades específicas para organizar e executar fluxos de trabalho
* [Canais](../../automating/using/about-channel-activities.md): atividades que representam os diferentes canais de comunicação disponíveis
* [Gerenciamento de dados (ETL)](../../automating/using/about-data-management-activities.md): atividades específicas para manipular dados

Para usar uma atividade da paleta em seu fluxo de trabalho, arraste-a e solte-a em seu espaço de trabalho.

É necessário configurar cada atividade adicionada a partir da paleta antes de iniciar o fluxo de trabalho.

![](assets/workflow_palette.png)

## Área de Trabalho {#workspace}

O espaço de trabalho é a zona central no editor de fluxo de trabalho. É nessa zona que você pode soltar suas atividades, vinculá-las usando transições e configurá-las.

Para vincular duas atividades, mova o final da seta da primeira atividade para a seguinte atividade até que elas se conectem. Você também pode mover a atividade em direção ao ponto da seta atrás dela para vinculá-la à atividade anterior. Se você mover alguma das atividades, elas permanecerão ligadas.

As transições que seguem atividades que processam dados contêm as populações intermediárias. Você pode acessá-los se marcar a opção **[!UICONTROL Keep interim results]** na seção **[!UICONTROL Execution]** das propriedades do fluxo de trabalho.

Quando uma atividade é selecionada, ações rápidas aparecem ao redor da atividade, permitindo que você interaja com ela. Por exemplo, para configurar uma atividade, selecione-a e abra-a usando o ![](assets/edit_darkgrey-24px_table.png) botão nas ações rápidas.

Determinadas funções são ativadas somente no espaço de trabalho:

* Selecione várias atividades e transições desenhando uma zona ao seu redor.
* Pressione **Ctrl** + clique esquerdo para selecionar várias atividades e/ou transições.
* Pressione **Enter** para exibir os detalhes da atividade ou transição atualmente selecionada.
* Pressione **Excluir** para excluir a atividade atualmente selecionada.
* Pressione **Ctrl + C** para copiar as atividades selecionadas e **Ctrl + V** para colá-las no espaço de trabalho.

![](assets/workflow_workspace.png)

## Barra de ação {#action-bar}

Dependendo dos elementos selecionados no espaço de trabalho ou do status de execução do fluxo de trabalho, os botões disponíveis na barra de ações podem variar.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Permite editar as propriedades do fluxo de trabalho.

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>Inicia o fluxo de trabalho.

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

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>Abre as opções avançadas da atividade de entrega de email ou SMS selecionada.

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>Reativa a seleção se ela tiver sido desabilitada ou marcada como pausada anteriormente.

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Pausa o fluxo de trabalho na atividade selecionada.

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Desativa a atividade.

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>Força o processamento imediato da seleção. Este botão está disponível somente para as atividades <span class="uicontrol">Agendador</span> e <span class="uicontrol">Espera</span> .

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Exclui as atividades selecionadas.

## Duplicação de atividades de fluxo de trabalho {#duplicating-workflow-activities}

A área de trabalho permite duplicar atividades de fluxo de trabalho copiando-as para o mesmo fluxo de trabalho ou para outro fluxo de trabalho da mesma instância do Campaign.

Depois que uma atividade é duplicada, toda a sua configuração é mantida. Para atividades de entrega (Email, SMS, Notificação por push...), o objeto de entrega anexado à atividade é duplicado.

>[!NOTE]
>
>As atividades de fluxo de trabalho não podem ser duplicadas de uma instância para outra. As atividades dos fluxos de trabalho técnicos não podem ser duplicadas.

Para duplicar uma atividade, siga as etapas abaixo:

1. Selecione a atividade e clique no **[!UICONTROL Copy selection]** botão das ações rápidas.

   Você também pode usar o atalho de teclado **Ctrl + C** .

   ![](assets/wkf_copypaste1.png)

1. Clique com o botão direito do mouse na área de trabalho do fluxo de trabalho de destino e clique no **[!UICONTROL Paste]** botão.

   Você também pode usar o atalho de teclado **CTRL + V** .

   ![](assets/wkf_copypaste2.png)

1. A atividade é duplicada, com todas as configurações definidas inicialmente.

Também é possível copiar e colar várias atividades, permitindo duplicar um fluxo de trabalho inteiro.

Para fazer isso, selecione as atividades desenhando uma zona ao seu redor. em seguida, clique no **[!UICONTROL Copy selection]** botão da barra de ação (ou pressione **Ctrl + C**). Em seguida, você pode colá-los no local desejado.

![](assets/wkf_copypaste3.png)

