---
title: Cross-channel delivery
description: Este caso de uso mostra como criar uma entrega entre canais
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,wait,delivery
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 9cee2005-a99b-47cb-b573-a25812614409
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 84%

---

# Criar uma entrega em vários canais{#cross-channel-delivery}

Este documento permite descobrir a seguinte funcionalidade do Adobe Campaign por meio de um caso de uso padrão: criação de um fluxo de trabalho de entrega entre canais.

O objetivo aqui é selecionar um público dos destinatários do banco de dados e segmentá-los em dois grupos diferentes com a finalidade de enviar um email para o primeiro grupo e uma mensagem SMS para o segundo.

![](assets/wkf_segment_overview.png)

Para obter mais detalhes sobre os fluxos de trabalho e os diferentes canais disponíveis no Adobe Campaign, verifique os seguintes documentos:

* [Descobrir fluxos de trabalho](../../automating/using/get-started-workflows.md)
* [Descobrir canais de comunicação](../../channels/using/get-started-communication-channels.md)

## Criar um fluxo de trabalho {#creating-workflow}

Para enviar duas entrega diferentes para um determinado grupo, primeiro defina o público-alvo.

Para fazer isso, será necessário criar um query para identificar os destinatários e, portanto, criar um fluxo de trabalho.

Crie um novo fluxo de trabalho no programa ou na campanha de sua escolha:

1. Em **[!UICONTROL Marketing Activities]**, clique em **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**.

As etapas detalhadas para criar um fluxo de trabalho são apresentadas na seção [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md).

## Criação de uma atividade Query {#creating-query-activity}

Depois que o fluxo de trabalho for criado, você poderá acessar sua interface.

Insira uma atividade Query em seu fluxo de trabalho para segmentar os perfis que receberão suas entregas.

1. Em **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arraste e solte uma atividade de [Query](../../automating/using/query.md).
1. Clique duas vezes na atividade.
1. Na guia **[!UICONTROL Target]**, navegue pelos atalhos e selecione uma dos [públicos-alvo](../../audiences/using/about-audiences.md).
1. Arraste e solte o atalho na zona de edição. De acordo com o tipo de atalho selecionado, uma janela será exibida.
1. Configure os elementos de direcionamento de elementos, depois confirme o query.

![](assets/wkf_segment_query.png)

É possível criar um query em um ou vários elementos.

Use o botão **[!UICONTROL Count]** para ver uma estimativa do número de perfis segmentados pelo query.

## Criação de uma atividade de segmentação {#creating-segmentation-activity}

Depois que o público-alvo for identificado pela atividade Query, é necessário selecionar um critério para segmentar o público-alvo em duas populações diferentes: uma receberá um email e a outra receberá um SMS.

Você precisa usar uma atividade de [Segmentação](../../automating/using/segmentation.md) para criar um ou vários segmentos a partir de uma população computada upstream em uma consulta.

![](assets/wkf_segment_activity.png)

O grupo **Email** segmentará os destinatários que têm um endereço de email definido, mas nenhum número de celular. O grupo **SMS** conterá os destinatários cujo número de telefone celular está salvo em seus perfis.

Para configurar a primeira transição (Email):

1. Na guia **[!UICONTROL Segments]**, há um primeiro segmento presente por padrão. Edite as propriedades desse segmento para configurá-lo.

   ![](assets/wkf_segment_properties.png)

1. Selecione o **[!UICONTROL Email]** do perfil como um critério de filtragem.

   ![](assets/wkf_segment_email.png)

1. Na nova janela que aparece na tela, selecione o operador **[!UICONTROL Is not empty]**.

   ![](assets/wkf_segment_email_not_empty.png)

1. Adicione um segundo critério de filtragem, **[!UICONTROL Mobile]**, e selecione o operador **[!UICONTROL Is empty]**.

   ![](assets/wkf_segment_mobile_empty.png)

   Todos os perfis provenientes do query que têm um email, mas não um número de celular definido, estarão nessa transição.

1. Para deixar seu fluxo de trabalho mais claro, você pode editar o rótulo de transição. Confirme as alterações.

   ![](assets/wkf_segment_transition_label.png)

A primeira transição está configurada. Para configurar a segunda transição (SMS):

1. Clique no botão **[!UICONTROL Add an element]** para adicionar uma nova transição.
1. Defina uma condição que permita recuperar todos os perfis cujos números de celular foram fornecidos. Para fazer isso, crie uma regra no campo **[!UICONTROL Mobile]**, com o operador lógico **[!UICONTROL Is not empty]**.

   ![](assets/wkf_segment_mobile_not_empty.png)

   Todos os perfis provenientes do query que têm um número de celular definido estarão nessa transição.

1. Você pode editar o rótulo da transição. Confirme as alterações.

A segunda transição agora também está configurada.

![](assets/wkf_segment_transitions.png)

## Criação de entregas {#creating-deliveries}

Como duas transições já foram criadas, agora você precisa adicionar dois tipos de entrega às transições de saída da atividade de Segmentação: uma atividade de [Entrega de email](../../automating/using/email-delivery.md) e uma atividade de [Entrega de SMS](../../automating/using/sms-delivery.md).

O Adobe Campaign permite adicionar entregas a um fluxo de trabalho. Para fazer isso, selecione uma entrega na categoria **[!UICONTROL Channels]** da paleta de atividades do fluxo de trabalho.

![](assets/wkf_segment_deliveries1.png)

Para criar uma entrega de email:

1. Arraste e solte uma atividade [Delivery de email](../../automating/using/email-delivery.md) após o primeiro segmento.
1. Clique duas vezes na atividade para editá-la.
1. Selecione **[!UICONTROL Simple email]**.
1. Selecione **[!UICONTROL Add an outbound transition with the population]** e clique em **[!UICONTROL Next]**.

   ![](assets/wkf_segment_deliveries2.png)

   A transição de saída permitirá que você recupere a população e os logs de rastreamento. Você poderá usar essa opção, por exemplo, para enviar um segundo email às pessoas que não clicaram no primeiro email.

1. Selecione um template de email e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do email e clique em **[!UICONTROL Next]**.
1. Para criar o layout do email, selecione **[!UICONTROL Use the Email Designer]**.
1. Edite e salve o conteúdo.
1. Na seção **[!UICONTROL Schedule]** do painel de mensagens, desmarque a opção **[!UICONTROL Request confirmation before sending messages]**.

Para criar uma entrega de SMS:

1. Arraste e solte uma atividade [Delivery de SMS](../../automating/using/sms-delivery.md) após o outro segmento.
1. Clique duas vezes na atividade para editá-la.
1. Selecione **[!UICONTROL SMS]** e clique em **[!UICONTROL Next]**.
1. Selecione um modelo de SMS e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do SMS e clique em **[!UICONTROL Next]**.
1. Edite e salve o conteúdo.

Depois de as entregas serem criadas e editadas, o fluxo de trabalho estará pronto para ser iniciado.

![](assets/wkf_segment_deliveries.png)

## Execução do fluxo de trabalho {#running-the-workflow}

Quando o fluxo de trabalho for iniciado, a população segmentada pela atividade **[!UICONTROL Query]** receberá uma entrega de Email ou SMS.

Para executar o fluxo de trabalho, clique no botão **[!UICONTROL Start]** da barra de ações.

Você pode acessar as entregas no menu avançado **[!UICONTROL Marketing plans]** > **[!UICONTROL Marketing activities]** por meio do logotipo do Adobe Campaign. Clique na entrega e no botão **[!UICONTROL Reports]** para acessar os [relatórios da entrega](../../reporting/using/about-dynamic-reports.md#accessing-dynamic-reports), como o resumo da entrega, a taxa de abertura ou a renderização de email de acordo com a caixa de entrada de mensagens dos destinatários.
