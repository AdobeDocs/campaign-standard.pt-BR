---
title: Criação de um fluxo de trabalho
description: Esta seção detalha os principais princípios e as práticas recomendadas para criação de novo workflow.
page-status-flag: never-activated
uuid: 11374f64-8d34-40da-937b-09f419250f4c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: c26fcb0e-19d5-4bd5-b7d6-2d22ce92ad90
context-tags: workflow,wizard;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 422f5eb7011dfcc1d923079e7346394a64934a9a
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 13%

---


# Criação de um fluxo de trabalho{#building-a-workflow}

Esta seção detalha os principais princípios e as práticas recomendadas para criação de novo workflow.

## Princípios operacionais do fluxo de trabalho{#workflow-operating-principles}

Um fluxo de trabalho é uma **sequência de atividades** configuráveis. Cada atividade tem um papel específico no processo. O resultado de cada atividade é encaminhado para a seguinte atividade por uma **transição**, representada por uma seta.

O tipo de dados trocados entre uma atividade e outra pode afetar a forma como as atividades a seguir são configuradas. Por exemplo, se uma população for estabelecida antes da atividade do delivery de email, ela poderá servir como público alvo do email em questão.

Você pode abrir o atividade para verificar ou editar parâmetros antes ou depois de executar o fluxo de trabalho.

Você pode abrir o transição para verificar se os dados enviados estão corretos durante ou após a execução do fluxo de trabalho. Para acessar a visualização detalhada das transições, é necessário verificar a opção **[!UICONTROL Keep interim results]** na seção **[!UICONTROL Execution]** das propriedades do fluxo de trabalho.

![](assets/workflow_overview.png)


## Criação de um workflow {#creating-a-workflow}

Você pode criar um fluxo de trabalho a partir de um programa, de uma campanha ou da lista da atividade de marketing.

A criação de uma atividade de marketing é detalhada na seção [Criação de atividades](../../start/using/marketing-activities.md#creating-a-marketing-activity) de marketing.

1. Depois de começar a criar uma atividade de marketing de tipo de fluxo de trabalho, selecione o modelo que deseja usar.

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >Cada atividade de marketing oferta vários tipos por padrão. Isso permite que você pré-configure determinados parâmetros de acordo com suas necessidades. For more information, refer to the [Managing templates](../../start/using/marketing-activity-templates.md) section.

1. Insira as propriedades gerais do fluxo de trabalho.

   ![](assets/workflow_creation_2.png)

   Você pode inserir um nome no campo **Rótulo** e modificar a ID. O nome da atividade e sua ID são exibidos na interface, mas não são visíveis pelos recipient de mensagem.

   >[!NOTE]
   >
   >Você pode criar seu fluxo de trabalho em uma campanha pai a partir da lista de atividades de marketing. Você pode vincular esse fluxo de trabalho a uma campanha selecionando uma que já foi criada.

   Você pode adicionar uma descrição que o usuário pode ver no conteúdo da campanha.

   Como facilita a localização e a solução de problemas se não estiverem executando da forma esperada, a Adobe recomenda que os workflows tenham nomes e rótulos adequados: preencha o campo de descrição do workflow para resumir o processo para que o operador possa entender facilmente.

1. Confirme se a criação da atividade e o painel da atividade será exibido. For more on this, refer to the [Workflow interface](../../automating/using/workflow-interface.md) section.

1. Quando o fluxo de trabalho estiver pronto para ser configurado, você poderá acessar opções adicionais clicando no **[!UICONTROL Edit properties]** botão. Por exemplo, você pode definir um fuso horário específico para usar por padrão em todas as atividades do fluxo de trabalho. Por padrão, o fuso horário do fluxo de trabalho é o definido para o operador de Campanha atual.

   ![](assets/workflow_properties.png)

**Tópicos relacionados:**

* [Criação de um vídeo de fluxo de trabalho](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html)
* [Propriedades do workflow](../../automating/using/managing-execution-options.md)

## Adição e vínculo de atividades {#adding-and-linking-activities}

Defina agora as várias atividades e as vincule no diagrama.

>[!NOTE]
>
>Se a paleta não for exibida, clique no primeiro botão da barra de ferramentas para exibi-la.

As Atividades são agrupadas por categoria dentro das diferentes seções da paleta.

* A primeira seção contém atividades de [definição de metas](../../automating/using/about-targeting-activities.md)
* The second section contains the [execution activities](../../automating/using/about-execution-activities.md), which are mainly used for coordinating other activities.
* A terceira seção contém atividades que podem ser usadas para enviar mensagens em diferentes [canais](../../automating/using/about-channel-activities.md). As Atividades nesta seção podem variar dependendo dos canais que estão ativados em sua instância.
* A quarta seção contém manipulação de [arquivos e atividades](../../automating/using/about-data-management-activities.md)de gestão de dados.

Criação do diagrama:

1. Adicione uma atividade arrastando-a da paleta e soltando-a no diagrama.

   Por exemplo, adicione uma atividade de **[Start](../../automating/using/start-and-end.md)**e depois uma atividade de delivery**[ de](../../automating/using/email-delivery.md)** email no diagrama.

1. Link the activities together by dragging the **Start** activity transition and dropping it on to the **Email delivery** activity.

   >[!NOTE]
   >
   >Você pode vincular automaticamente uma atividade à anterior, colocando a nova atividade no final da transição anterior.

1. Adicione as atividades necessárias e vincule-as para concluir o fluxo de trabalho.

   >[!NOTE]
   >
   >Você também pode duplicado atividades existentes colando-as. Desta forma, você mantém as configurações originalmente definidas. For more on this, refer to [Duplicating workflow activities](../../automating/using/workflow-interface.md#duplicating-workflow-activities).

Assim que suas atividades de fluxo de trabalho estiverem vinculadas, você poderá personalizar as transições entre elas com o **rótulo** de sua escolha. Para fazer isso, clique com o duplo na transição para acessar suas propriedades.

Além disso, **[!UICONTROL Targeting]** e **[!UICONTROL Data management (ETL)]** as atividades permitem definir **códigos de segmento** para suas transições de saída. Em seguida, você pode criar relatórios com base nesses códigos de segmento para medir a eficiência de suas campanhas de marketing. Para obter mais informações, consulte [esta seção](../../reporting/using/creating-a-report-workflow-segment.md).

**Casos de uso do fluxo de trabalho:**

* [Caso de uso: Criar um delivery de email uma vez por semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: Criação de um delivery segmentado na localização](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: Criação de delivery com um complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: Fluxo de trabalho de redefinição de metas enviando um novo delivery para não iniciantes](../../automating/using/workflow-cross-channel-retargeting.md)

## Configuração de atividades {#configuring-activities}

Por padrão, o atividade não está definido e não processará os dados corretamente se não estiverem configurados. Cada atividade contém várias guias para gerenciar configurações específicas e opções genéricas de atividade, como transições de saída, etiquetas etc.

1. Verifique se todas as atividades estão conectadas corretamente. Algumas atividades exigem a detecção da estrutura ou da natureza dos dados recebidos para oferta das opções de configuração corretas.
1. Clique em uma atividade com o Duplo do mouse ou selecione-a e clique na ação **[!UICONTROL Edit]** contextual para abrir sua janela de configuração.
1. Edite o rótulo da atividade.
1. Defina todas as opções diferentes que você precisa para processar os dados. Consulte a seção específica da atividade desta documentação para saber mais sobre as opções possíveis para cada atividade.
1. Salve a atividade e repita essas operações para cada atividade do fluxo de trabalho.
1. Salve o workflow.
