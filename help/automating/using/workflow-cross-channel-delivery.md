---
title: '"Caso de uso do fluxo de trabalho: Entrega entre canais"'
description: '"Caso de uso do fluxo de trabalho: Entrega entre canais"'
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
source-git-commit: f959441647d1fea41ecce2fc41e3cad3cb536bac

---


# Caso de uso do fluxo de trabalho:Criação de uma entrega entre canais{#cross-channel-delivery}

Este documento permite descobrir a seguinte funcionalidade do Adobe Campaign por meio de um caso de uso padrão: criação de um fluxo de trabalho de entrega entre canais.

O objetivo aqui é selecionar um público-alvo dos destinatários do banco de dados e segmentá-los em dois grupos diferentes com o objetivo de enviar um email para o primeiro grupo e uma mensagem SMS para o segundo grupo.

![](assets/wkf_segment_overview.png)

Para obter mais detalhes sobre fluxos de trabalho e os diferentes canais disponíveis no Adobe Campaign, consulte os seguintes documentos:

* [Descobrir fluxos de trabalho](../../automating/using/discovering-workflows.md)
* [Descobrir canais de comunicação](../../channels/using/discovering-communication-channels.md)

## Criação de um workflow {#creating-workflow}

Para enviar duas entregas diferentes para um determinado grupo, primeiro defina sua meta.

Para fazer isso, será necessário criar uma consulta para identificar os destinatários e, portanto, será necessário criar um fluxo de trabalho.

Crie um novo fluxo de trabalho no programa ou na campanha de sua escolha:

1. Em **[!UICONTROL Marketing Activities]**, clique**[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]**como tipo de fluxo de trabalho e clique em**[!UICONTROL Next]**.
1. Insira as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**.

As etapas detalhadas para criar um fluxo de trabalho são apresentadas na seção [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md) .

## Criando uma atividade de consulta {#creating-query-activity}

Depois que o fluxo de trabalho for criado, você poderá acessar sua interface.

Insira uma atividade de Consulta no fluxo de trabalho para direcionar os perfis que receberão suas entregas.

1. Em **[!UICONTROL Activities]**>**[!UICONTROL Targeting]**, arraste e solte um **[!UICONTROL Query activity]**.
1. Clique duas vezes na atividade.
1. Na **[!UICONTROL Target]**guia, navegue pelos atalhos e selecione um dos[públicos-alvo](../../audiences/using/about-audiences.md).
1. Arraste e solte o atalho na zona de edição. De acordo com o tipo de atalho selecionado, uma janela será exibida.
1. Configure os elementos de definição de metas e confirme sua consulta.

![](assets/wkf_segment_query.png)

É possível criar uma consulta em um ou vários elementos.

Use o **[!UICONTROL Count]**botão para ver uma estimativa do número de perfis direcionados pela consulta.

As etapas detalhadas para criar uma atividade de Consulta são apresentadas na seção [Consulta](../../automating/using/query.md) .

## Criação de uma atividade de segmentação {#creating-segmentation-activity}

Uma vez que sua meta é identificada pela atividade Consulta, você deve selecionar um critério para segmentar a meta em duas populações diferentes: um receberá um email e o outro receberá um SMS.

É necessário usar uma atividade de Segmentação para criar um ou vários segmentos a partir de uma população computada em upstream em uma consulta.

![](assets/wkf_segment_activity.png)

O grupo **Email** direcionará os destinatários que têm um endereço de email definido, mas nenhum número de telefone móvel. O grupo **SMS** conterá os destinatários cujo número de telefone celular é salvo em seu perfil.

Para configurar a primeira transição (Email):

1. Na **[!UICONTROL Segments]**guia, um primeiro segmento está presente por padrão. Edite suas propriedades para configurar esse segmento.

   ![](assets/wkf_segment_properties.png)

1. Selecione o perfil **[!UICONTROL Email]**como um critério de filtragem.

   ![](assets/wkf_segment_email.png)

1. Na nova janela que aparece na tela, selecione o **[!UICONTROL Is not empty]**operador.

   ![](assets/wkf_segment_email_not_empty.png)

1. Adicione um segundo critério de filtragem **[!UICONTROL Mobile]**e selecione o operador**[!UICONTROL Is empty]**.

   ![](assets/wkf_segment_mobile_empty.png)

   Todos os perfis provenientes da consulta que têm um email, mas não um número de telefone celular definido, estarão nessa transição.

1. Para tornar seu fluxo de trabalho mais claro, você pode editar o rótulo de transição. Confirme suas alterações.

   ![](assets/wkf_segment_transition_label.png)

Sua primeira transição está configurada. Para configurar a segunda transição (SMS):

1. Clique no **[!UICONTROL Add an element]**botão para adicionar uma nova transição.
1. Defina uma condição que permita recuperar todos os perfis cujos números de telefone celular foram fornecidos. Para fazer isso, crie uma regra no **[!UICONTROL Mobile]**campo com o operador**[!UICONTROL Is not empty]** lógico.

   ![](assets/wkf_segment_mobile_not_empty.png)

   Todos os perfis provenientes da consulta que têm um número de telefone celular definido estarão nessa transição.

1. Você pode editar o rótulo da transição. Confirme suas alterações.

Sua segunda transição agora também está configurada.

![](assets/wkf_segment_transitions.png)

As etapas detalhadas para criar uma atividade de Segmentação são apresentadas na seção [Segmentação](../../automating/using/segmentation.md) .

## Criar entregas {#creating-deliveries}

Como duas transições já foram criadas, você deve adicionar dois tipos de entregas às transições de saída da atividade de Segmentação: um **[!UICONTROL Email delivery]**e um**[!UICONTROL SMS delivery]**.

O Adobe Campaign permite que você adicione entregas a um fluxo de trabalho. Para fazer isso, selecione uma entrega na **[!UICONTROL Channels]**categoria da paleta atividade do seu fluxo de trabalho.

![](assets/wkf_segment_deliveries1.png)

Para criar uma entrega por email:

1. Arraste e solte um **[!UICONTROL Email delivery]**depois do primeiro segmento.
1. Clique duas vezes na atividade para editá-la.
1. Select **[!UICONTROL Simple email]**.
1. Selecione **[!UICONTROL Add an outbound transition with the population]**e clique em**[!UICONTROL Next]**.

   ![](assets/wkf_segment_deliveries2.png)

   A transição de saída permitirá a recuperação da população e dos registros de rastreamento. Você poderá usar isso, por exemplo, para enviar um segundo email às pessoas que não clicaram no primeiro email.

1. Selecione um modelo de email e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do email e clique em **[!UICONTROL Next]**.
1. Para criar o layout do seu email, selecione **[!UICONTROL Use the Email Designer]**.
1. Edite e salve seu conteúdo.
1. Na **[!UICONTROL Schedule]**seção do painel de mensagens, desmarque a opção**[!UICONTROL Request confirm antes de enviar mensagens}**.

As etapas detalhadas para criar uma atividade de Email são apresentadas na seção de entrega [de](../../automating/using/email-delivery.md) Email.

Para criar uma entrega SMS:

1. Arraste e solte um **[!UICONTROL SMS delivery]**depois do outro segmento.
1. Clique duas vezes na atividade para editá-la.
1. Selecione **[!UICONTROL SMS]**e clique em**[!UICONTROL Next]**.
1. Selecione um modelo SMS e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do SMS e clique em **[!UICONTROL Next]**.
1. Edite e salve seu conteúdo.

As etapas detalhadas para criar uma atividade de SMS são apresentadas na seção de entrega [de](../../automating/using/sms-delivery.md) SMS.

Depois que suas entregas forem criadas e editadas, seu fluxo de trabalho estará pronto para ser iniciado.

![](assets/wkf_segment_deliveries.png)

## Execução do fluxo de trabalho {#running-the-workflow}

Assim que o fluxo de trabalho for iniciado, a população alvo da atividade de Consulta será segmentada para receber uma entrega de email ou SMS.

Para executar seu fluxo de trabalho, clique no **[!UICONTROL Start]**botão da barra de ações.

Você pode acessar suas entregas no menu **[!UICONTROL Marketing plans]**>**[!UICONTROL Marketing activities]** avançado pelo logotipo do Adobe Campaign. Clique na entrega e, em seguida, no **[!UICONTROL Reports]**botão para acessar os relatórios[de](../../reporting/using/about-dynamic-reports.md#accessing-dynamic-reports)entrega, como o resumo da entrega, a taxa de abertura ou a renderização do email de acordo com a caixa de entrada da mensagem dos destinatários.