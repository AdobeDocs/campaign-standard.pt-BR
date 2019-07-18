---
title: Criação de um fluxo de trabalho
seo-title: Criação de um fluxo de trabalho
description: Criação de um fluxo de trabalho
seo-description: Esta seção detalha os principais princípios e práticas recomendadas para criar um novo fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 11374 f 64-8 d 34-40 da -937 b -09 f 419250 f 4 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: fluxo de trabalho-geral-operação
discoiquuid: c 26 fcb 0 e -19 d 5-4 bd 5-b 7 d 6-2 d 22 ce 92 ad 90
context-tags: fluxo de trabalho, assistente; fluxo de trabalho, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Building a workflow{#building-a-workflow}

Esta seção apresenta os principais princípios e práticas recomendadas para criar um novo fluxo de trabalho:

* Criação de um fluxo de trabalho.
* Adicionar e vincular atividades.
* Configuração das atividades.

## Creating a workflow {#creating-a-workflow}

Você pode criar um fluxo de trabalho a partir de um programa, uma campanha ou uma lista de atividades de marketing.

Creating a marketing activity is detailed in the [Creating marketing activities](../../start/using/marketing-activities.md#creating-a-marketing-activity) section.

1. Depois de começar a criar uma atividade de marketing de tipo de fluxo de trabalho, selecione o modelo que deseja usar.

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >Cada atividade de marketing oferece vários tipos por padrão. Eles permitem pré-configurar determinados parâmetros de acordo com suas necessidades. For more information, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. Insira as propriedades gerais do fluxo de trabalho.

   ![](assets/workflow_creation_2.png)

   You can enter a name in the **Label** field and modify the ID. O nome da atividade e sua ID aparecem na interface, mas não são visíveis pelos destinatários da mensagem.

   >[!NOTE]
   >
   >Você pode criar seu fluxo de trabalho em uma campanha principal da lista de atividades de marketing. Você pode vincular esse fluxo de trabalho a uma campanha selecionando um que já foi criado.

   Você pode adicionar uma descrição que o usuário pode visualizar no conteúdo da campanha.

   Como facilita encontrar e solucionar problemas se não estiverem realizando das formas esperadas, a Adobe recomenda dar aos seus fluxos de trabalho nomes e rótulos próprios: preencha o campo de descrição do fluxo de trabalho para resumir o processo a ser executado para que o operador possa entendê-lo facilmente.

1. Confirme se a atividade e o painel para essa atividade serão exibidos. For more on this, refer to the [Workflow interface](../../automating/using/workflow-interface.md) section.

**Tópico relacionado:**

[Criação de](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-workflow-feature-video-use.html) um vídeo de fluxo de trabalho

## Adding and linking activities {#adding-and-linking-activities}

Agora, você deve definir as várias atividades e vinculá-las em conjunto no diagrama.

>[!NOTE]
>
>Se a paleta não for exibida, clique no primeiro botão da barra de ferramentas para exibi-la.

As atividades são agrupadas por categoria dentro das diferentes seções da paleta.

* A primeira seção contém atividades de definição de metas.
* A segunda seção contém as atividades de execução, que são usadas principalmente para coordenar outras atividades.
* A terceira seção contém atividades que podem ser usadas para enviar mensagens em diferentes canais. As atividades nesta seção podem variar dependendo dos canais que estão ativados na sua instância.
* A quarta seção contém atividades de manipulação de arquivos e gerenciamento de dados.

Para criar o diagrama:

1. Adicione uma atividade arrastando-a da paleta e soltando-a no diagrama.

   For example, add a **Start** activity and then an **Email delivery** activity on the diagram.

1. Link the activities together by dragging the **Start** activity transition and dropping it on to the **Email delivery** activity.

   >[!NOTE]
   >
   >É possível vincular automaticamente uma atividade ao anterior colocando a nova atividade no final da transição do anterior.

1. Adicione as atividades necessárias e vincule-as para concluir seu fluxo de trabalho.

   >[!NOTE]
   >
   >Também é possível duplicar atividades existentes copiando-as. Dessa forma, você mantém as configurações definidas originalmente. For more on this, refer to [Duplicating workflow activities](../../automating/using/workflow-interface.md#duplicating-workflow-activities).

## Configuring activities {#configuring-activities}

Por padrão, as atividades não são definidas e não processarão os dados corretamente se não estiverem configuradas. Cada atividade contém várias guias para gerenciar configurações específicas e opções genéricas de atividade, como transições de saída, rótulos etc.

1. Verifique se todas as atividades estão corretamente conectadas. Algumas atividades exigem a detecção da estrutura ou da natureza dos dados recebidos para oferecer as opções de configuração corretas.
1. Double-click an activity or select it and click the **[!UICONTROL Edit]** contextual action to open its configuration window.
1. Edite o rótulo da atividade.
1. Defina todas as opções diferentes necessárias para processar os dados. Consulte a seção específica da atividade desta documentação para saber as opções possíveis para cada atividade.
1. Salve a atividade e repita essas operações para cada atividade do fluxo de trabalho.
1. Salve o fluxo de trabalho.

