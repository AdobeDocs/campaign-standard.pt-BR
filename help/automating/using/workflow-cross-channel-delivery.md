---
title: delivery entre canais
description: Este caso de uso mostra como criar um delivery entre canais
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,wait,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e689e6bc362f4e948593c3b251f3825aab20ac
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 2%

---


# Criação de uma entrega entre canais{#cross-channel-delivery}

Este documento permite descobrir a seguinte funcionalidade de Adobe Campaign por meio de um caso de uso padrão: criação de um fluxo de trabalho de delivery entre canais.

O objetivo aqui é selecionar uma audiência dos recipient do banco de dados e segmentá-los em dois grupos diferentes com o objetivo de enviar um email para o primeiro grupo e uma mensagem SMS para o segundo grupo.

![](assets/wkf_segment_overview.png)

Para obter mais detalhes sobre os workflows e os diferentes canais disponíveis no Adobe Campaign, verifique os seguintes documentos:

* [Descobrir fluxos de trabalho](../../automating/using/get-started-workflows.md)
* [Descobrir canais de comunicação](../../channels/using/get-started-communication-channels.md)

## Criação de um workflow {#creating-workflow}

Para enviar dois delivery diferentes para um determinado grupo, primeiro defina seu público alvo.

Para fazer isso, será necessário criar um query para identificar os recipient e, portanto, criar um fluxo de trabalho.

Crie um novo fluxo de trabalho no programa ou na campanha de sua escolha:

1. Em **[!UICONTROL Marketing Activities]**, clique **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**.

As etapas detalhadas para criar um fluxo de trabalho são apresentadas na seção [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md) .

## Creating a Query activity {#creating-query-activity}

Depois que o fluxo de trabalho for criado, você poderá acessar sua interface.

Insira uma atividade de Query em seu fluxo de trabalho para público alvo dos perfis que receberão seus delivery.

1. Em **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arraste e solte uma atividade de [Query](../../automating/using/query.md) .
1. Duplo clique na atividade.
1. Na **[!UICONTROL Target]** guia, navegue pelos atalhos e selecione uma de suas [audiências](../../audiences/using/about-audiences.md).
1. Arraste e solte o atalho na zona de edição. De acordo com o tipo de atalho selecionado, uma janela será exibida.
1. Configure os elementos de definição de metas e confirme seu query.

![](assets/wkf_segment_query.png)

É possível criar um query em um ou vários elementos.

Use o **[!UICONTROL Count]** botão para ver uma estimativa do número de perfis direcionados pelo query.

## Criação de uma atividade de segmentação {#creating-segmentation-activity}

Depois que seu público alvo é identificado pela atividade do Query, é necessário selecionar um critério para segmentar o público alvo em duas populações diferentes: um receberá um email e o outro receberá um SMS.

É necessário usar uma atividade de [segmentação](../../automating/using/segmentation.md) para criar um ou vários segmentos a partir de uma população calculada em upstream em um query.

![](assets/wkf_segment_activity.png)

O grupo **Email** público alvo os recipient que têm um endereço de email definido, mas nenhum número de telefone móvel. O grupo **SMS** conterá os recipient cujo número de telefone celular é salvo em seus perfis.

Para configurar a primeira transição (Email):

1. Na **[!UICONTROL Segments]** guia, um primeiro segmento está presente por padrão. Edite suas propriedades para configurar esse segmento.

   ![](assets/wkf_segment_properties.png)

1. Selecione o perfil **[!UICONTROL Email]** como um critério de filtragem.

   ![](assets/wkf_segment_email.png)

1. Na nova janela que aparece na tela, selecione o **[!UICONTROL Is not empty]** operador.

   ![](assets/wkf_segment_email_not_empty.png)

1. Adicione um segundo critério de filtragem **[!UICONTROL Mobile]** e selecione o operador **[!UICONTROL Is empty]**.

   ![](assets/wkf_segment_mobile_empty.png)

   Todos os perfis provenientes do query que têm um email, mas não um número de telefone celular definido, estarão nessa transição.

1. Para tornar seu fluxo de trabalho mais claro, você pode editar a etiqueta de transição. Confirme suas alterações.

   ![](assets/wkf_segment_transition_label.png)

Sua primeira transição está configurada. Para configurar a segunda transição (SMS):

1. Clique no **[!UICONTROL Add an element]** botão para adicionar uma nova transição.
1. Defina uma condição que permita recuperar todos os perfis cujos números de telefone celular foram fornecidos. Para fazer isso, crie uma regra no **[!UICONTROL Mobile]** campo com o operador **[!UICONTROL Is not empty]** lógico.

   ![](assets/wkf_segment_mobile_not_empty.png)

   Todos os perfis provenientes do query que têm um número de telefone celular definido estarão nessa transição.

1. Você pode editar o rótulo da transição. Confirme suas alterações.

Sua segunda transição agora também está configurada.

![](assets/wkf_segment_transitions.png)

## Criar entregas {#creating-deliveries}

Como duas transições já foram criadas, você deve adicionar dois tipos de delivery às transições de saída da atividade de Segmentação: uma atividade [de delivery](../../automating/using/email-delivery.md) por email e uma atividade de delivery [](../../automating/using/sms-delivery.md) SMS.

O Adobe Campaign permite que você adicione delivery a um fluxo de trabalho. Para fazer isso, selecione um delivery na **[!UICONTROL Channels]** categoria da paleta atividade do fluxo de trabalho.

![](assets/wkf_segment_deliveries1.png)

Para criar um delivery de email:

1. Arraste e solte uma atividade de delivery [](../../automating/using/email-delivery.md) de email após o primeiro segmento.
1. Clique com o Duplo do mouse na atividade para editá-la.
1. Selecione **[!UICONTROL Simple email]**.
1. Selecione **[!UICONTROL Add an outbound transition with the population]** e clique em **[!UICONTROL Next]**.

   ![](assets/wkf_segment_deliveries2.png)

   A transição de saída permitirá que você recupere a população e os logs de rastreamento. Você poderá usar isso, por exemplo, para enviar um segundo email às pessoas que não clicaram no primeiro email.

1. Selecione um modelo de email e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do email e clique em **[!UICONTROL Next]**.
1. Para criar o layout do seu email, selecione **[!UICONTROL Use the Email Designer]**.
1. Edite e salve seu conteúdo.
1. Na **[!UICONTROL Schedule]** seção do painel de mensagem, desmarque a opção **[!UICONTROL Request confirm antes de enviar mensagens}** .

Para criar um delivery SMS:

1. Arraste e solte uma atividade de delivery [](../../automating/using/sms-delivery.md) SMS após o outro segmento.
1. Clique com o Duplo do mouse na atividade para editá-la.
1. Selecione **[!UICONTROL SMS]** e clique em **[!UICONTROL Next]**.
1. Selecione um modelo SMS e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do SMS e clique em **[!UICONTROL Next]**.
1. Edite e salve seu conteúdo.

Depois que seus delivery forem criados e editados, seu fluxo de trabalho estará pronto para ser iniciado.

![](assets/wkf_segment_deliveries.png)

## Execução do fluxo de trabalho {#running-the-workflow}

Assim que o fluxo de trabalho for iniciado, a população alvo da **[!UICONTROL Query]** atividade será segmentada para receber um delivery de email ou SMS.

Para executar seu fluxo de trabalho, clique no **[!UICONTROL Start]** botão da barra de ações.

Você pode acessar seus delivery no menu **[!UICONTROL Marketing plans]** **[!UICONTROL Marketing activities]** > avançado por meio do logotipo do Adobe Campaign. Clique no delivery e no **[!UICONTROL Reports]** botão para acessar os [relatórios do delivery](../../reporting/using/about-dynamic-reports.md#accessing-dynamic-reports), como o resumo do delivery, a taxa de abertura ou a renderização de email de acordo com a caixa de entrada de mensagens dos recipient.
