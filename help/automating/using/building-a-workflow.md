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
source-git-commit: e04b70012188b455382406df167328f963d577da

---


# Criação de um fluxo de trabalho{#building-a-workflow}

Esta seção detalha os principais princípios e as práticas recomendadas para criação de novo workflow:

* Criação de um workflow.
* Adição e vínculo de atividades.
* Configuração de atividades.

## Criação de um workflow {#creating-a-workflow}

Você pode criar um fluxo de trabalho a partir de um programa, campanha ou lista de atividades de marketing.

A criação de uma atividade de marketing é detalhada na seção [Criação de atividades](../../start/using/marketing-activities.md#creating-a-marketing-activity) de marketing.

1. Depois de começar a criar uma atividade de marketing de tipo de fluxo de trabalho, selecione o modelo que deseja usar.

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >Cada atividade de marketing oferece vários tipos por padrão. Isso permite que você pré-configure determinados parâmetros de acordo com suas necessidades. For more information, refer to the [Managing templates](../../start/using/marketing-activity-templates.md) section.

1. Insira as propriedades gerais do fluxo de trabalho.

   ![](assets/workflow_creation_2.png)

   Você pode inserir um nome no campo **Rótulo** e modificar a ID. O nome da atividade e sua ID são exibidos na interface, mas não são visíveis pelos destinatários da mensagem.

   >[!NOTE]
   >
   >Você pode criar seu fluxo de trabalho dentro de uma campanha pai na lista de atividades de marketing. Você pode vincular esse fluxo de trabalho a uma campanha selecionando uma que já foi criada.

   Você pode adicionar uma descrição que o usuário pode ver no conteúdo da campanha.

   Como facilita a localização e a solução de problemas se não estiverem executando da forma esperada, a Adobe recomenda que os workflows tenham nomes e rótulos adequados: preencha o campo de descrição do workflow para resumir o processo para que o operador possa entender facilmente.

1. Confirme a criação da atividade e o painel dessa atividade será exibido. For more on this, refer to the [Workflow interface](../../automating/using/workflow-interface.md) section.

1. Quando o fluxo de trabalho estiver pronto para ser configurado, você poderá acessar opções adicionais clicando no **[!UICONTROL Edit properties]** botão. Por exemplo, você pode definir um fuso horário específico para usar por padrão em todas as atividades do fluxo de trabalho. Por padrão, o fuso horário do fluxo de trabalho é o definido para o operador atual da Campanha.

   ![](assets/workflow_properties.png)

**Tópico relacionado:**

* [Criação de um vídeo de fluxo de trabalho](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html)
* [Propriedades do workflow](../../automating/using/executing-a-workflow.md#workflow-properties)

## Adição e vínculo de atividades {#adding-and-linking-activities}

Defina agora as várias atividades e as vincule no diagrama.

>[!NOTE]
>
>Se a paleta não for exibida, clique no primeiro botão da barra de ferramentas para exibi-la.

As atividades são agrupadas por categoria dentro das diferentes seções da paleta.

* A primeira seção contém atividades de [direcionamento](../../automating/using/about-targeting-activities.md)
* The second section contains the [execution activities](../../automating/using/about-execution-activities.md), which are mainly used for coordinating other activities.
* A terceira seção contém atividades que podem ser usadas para enviar mensagens em diferentes [canais](../../automating/using/about-channel-activities.md). As atividades nesta seção podem variar dependendo dos canais ativados na sua instância.
* A quarta seção contém atividades [de manipulação de](../../automating/using/about-data-management-activities.md)arquivos e gerenciamento de dados.

Criação do diagrama:

1. Adicione uma atividade arrastando-a da paleta e soltando-a no diagrama.

   Por exemplo, adicione uma atividade **[Iniciar](../../automating/using/start-and-end.md)**e depois uma atividade de entrega**[ de](../../automating/using/email-delivery.md)** email no diagrama.

1. Link the activities together by dragging the **Start** activity transition and dropping it on to the **Email delivery** activity.

   >[!NOTE]
   >
   >Você pode vincular automaticamente uma atividade à anterior, colocando a nova atividade no final da transição da anterior.

1. Adicione as atividades necessárias e vincule-as para concluir o fluxo de trabalho.

   >[!NOTE]
   >
   >Também é possível duplicar atividades existentes colando-as. Desta forma, você mantém as configurações originalmente definidas. For more on this, refer to [Duplicating workflow activities](../../automating/using/workflow-interface.md#duplicating-workflow-activities).

Assim que suas atividades de fluxo de trabalho estiverem vinculadas, você poderá personalizar as transições entre elas com o **rótulo** de sua escolha. Para fazer isso, clique duas vezes na transição para acessar suas propriedades.

Além disso, **[!UICONTROL Targeting]** e **[!UICONTROL Data management (ETL)]** as atividades permitem definir códigos **de** segmento para suas transições de saída. Em seguida, você pode criar relatórios com base nesses códigos de segmento para medir a eficiência de suas campanhas de marketing. Para obter mais informações, consulte [esta seção](../../reporting/using/creating-a-report-workflow-segment.md).

**Casos de uso do fluxo de trabalho:**

* [Caso de uso: Criar uma entrega de email uma vez por semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: Criação de uma entrega segmentada no local](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: Criação de entregas com um complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: Fluxo de trabalho de redefinição de metas enviando uma nova entrega para não iniciantes](../../automating/using/workflow-cross-channel-retargeting.md)

## Configuração de atividades {#configuring-activities}

Por padrão, as atividades não são definidas e não processarão os dados corretamente se não estiverem configuradas. Cada atividade contém várias guias para gerenciar configurações específicas e opções genéricas de atividade, como transições de saída, etiquetas etc.

1. Verifique se todas as atividades estão conectadas corretamente. Algumas atividades exigem a detecção da estrutura ou da natureza dos dados recebidos para oferecer as opções de configuração corretas.
1. Clique duas vezes em uma atividade ou selecione-a e clique na ação **[!UICONTROL Edit]** contextual para abrir sua janela de configuração.
1. Edite o rótulo da atividade.
1. Defina todas as opções diferentes que você precisa para processar os dados. Consulte a seção específica da atividade desta documentação para saber mais sobre as possíveis opções para cada atividade.
1. Salve a atividade e repita essas operações para cada atividade do fluxo de trabalho.
1. Salve o workflow.
