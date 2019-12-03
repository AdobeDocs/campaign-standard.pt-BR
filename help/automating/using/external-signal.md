---
title: Sinal externo
description: A atividade de sinal externo aciona um fluxo de trabalho quando algumas condições são atendidas com êxito em outro fluxo de trabalho.
page-status-flag: never-activated
uuid: 884b6daf-bfd9-440b-8336-004b80c76def
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 911c71b5-da8b-4916-b645-13bba6d21715
context-tags: signal,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Sinal externo{#external-signal}

## Descrição {#description}

![](assets/signal.png)

A **[!UICONTROL External signal]** atividade aciona um fluxo de trabalho quando algumas condições são atendidas com êxito em outro fluxo de trabalho ou a partir de uma chamada REST API.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL External signal]** atividade é usada para organizar e orquestrar diferentes processos que fazem parte da mesma jornada do cliente em fluxos de trabalho diferentes. Ele permite iniciar um fluxo de trabalho a partir de outro, permitindo suportar jornadas de clientes mais complexas, ao mesmo tempo que pode monitorar e reagir melhor em caso de problema.

A **[!UICONTROL External signal]** atividade é projetada para ser colocada como a primeira atividade de um fluxo de trabalho. Ele pode ser acionado a partir da **[!UICONTROL End]** atividade de outro fluxo de trabalho ou de uma chamada REST API (para obter mais informações, consulte a documentação [da](../../api/using/triggering-a-signal-activity.md)API).

Quando acionados, os parâmetros externos podem ser definidos e estar disponíveis nas variáveis de eventos do fluxo de trabalho. O processo para chamar um fluxo de trabalho com parâmetros externos está detalhado [nesta seção](../../automating/using/calling-a-workflow-with-external-parameters.md).

>[!NOTE]
>
>A atividade não pode ser acionada com mais frequência do que a cada 10 minutos.

Observe que uma **[!UICONTROL External signal]** atividade pode ser acionada a partir de vários eventos diferentes. Nesse caso, o **[!UICONTROL External signal]** é acionado assim que um dos fluxos de trabalho de origem ou uma chamada de API é executada. Não requer que todos os fluxos de trabalho de origem sejam concluídos.

## Configuração {#configuration}

Ao configurar um sinal externo, é importante primeiro configurar a **[!UICONTROL External signal]** atividade no fluxo de trabalho de destino. Quando essa configuração for concluída, a **[!UICONTROL External signal]** atividade desse fluxo de trabalho ficará disponível para configurar a **[!UICONTROL End]** atividade do fluxo de trabalho de origem.

1. Arraste e solte uma **[!UICONTROL External signal]** atividade em seu fluxo de trabalho de destino.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Edite o rótulo da atividade. Esse rótulo é necessário ao configurar o fluxo de trabalho de origem que aciona o **[!UICONTROL External signal]**.

   Se você quiser chamar o fluxo de trabalho com parâmetros, use a **[!UICONTROL Parameters]** área para declará-los. Para obter mais informações, consulte [esta seção](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity).

   ![](assets/external_signal_configuration.png)

1. Confirme a configuração de sua atividade, adicione qualquer outra atividade necessária e salve seu fluxo de trabalho.

   >[!NOTE]
   >
   >Se você quiser acionar o fluxo de trabalho de destino a partir de outro fluxo de trabalho, continue com as etapas a seguir. Se desejar acionar o fluxo de trabalho de destino a partir de uma chamada REST API, consulte a documentação [da](../../api/using/triggering-a-signal-activity.md) API para obter mais detalhes.

1. Abra o fluxo de trabalho de origem e selecione uma **[!UICONTROL End]** atividade. Se não houver nenhuma **[!UICONTROL End]** atividade disponível, adicione uma após a última atividade de uma ramificação do fluxo de trabalho.

   Algumas atividades não têm nenhuma transição de saída por padrão. Na **[!UICONTROL Properties]** guia dessas atividades, é possível adicionar uma transição de saída.

   Por exemplo, em uma **[!UICONTROL Update data]** atividade, vá para a **[!UICONTROL Transitions]** guia e marque a opção **[!UICONTROL Add an outbound transition without the population]** . Essa opção permite adicionar uma transição que não contenha dados e não consuma espaço desnecessário no sistema. É usado apenas para conectar a atividade extra **[!UICONTROL End]** que aciona o fluxo de trabalho de destino.

   ![](assets/external_signal_empty_transition.png)

1. Na **[!UICONTROL External signal]** guia da **[!UICONTROL End]** atividade, selecione o fluxo de trabalho de destino, bem como a **[!UICONTROL External signal]** atividade a ser acionada dentro desse fluxo de trabalho.

   Quando você define uma **[!UICONTROL End]** atividade para acionar outro fluxo de trabalho, seu ícone é atualizado com um símbolo de sinal adicional.

   Se você quiser chamar o fluxo de trabalho com parâmetros, use a **[!UICONTROL Parameters and values]** área. Para obter mais informações, consulte [esta seção](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow).

   ![](assets/external_signal_end.png)

1. Salve o fluxo de trabalho de origem.

Depois que a **[!UICONTROL End]** atividade do fluxo de trabalho de origem ou a chamada REST API é executada, o fluxo de trabalho de destino é automaticamente disparado da **[!UICONTROL External signal]** atividade.

>[!NOTE]
>
>O fluxo de trabalho de destino deve ser iniciado manualmente antes de poder ser acionado. Quando iniciado, o **[!UICONTROL External activity]** é ativado e aguarda o sinal do fluxo de trabalho de origem.

## Exemplo {#example}

O exemplo a seguir ilustra a **[!UICONTROL External signal]** atividade em um caso de uso típico. Uma importação de dados é executada em um fluxo de trabalho de origem. Quando a importação for concluída e o banco de dados for atualizado, um segundo fluxo de trabalho será acionado. Esse segundo fluxo de trabalho é usado para atualizar um agregado nos dados importados.

O fluxo de trabalho de origem é apresentado da seguinte maneira:

* Uma atividade [Carregar arquivo](../../automating/using/load-file.md) carrega um arquivo contendo novos dados de compra. Observe que o [banco de dados foi estendido](../../developing/using/data-model-concepts.md) de acordo com esse procedimento, pois os dados de compra não estão presentes por padrão no datamart.

   Por exemplo:

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2015;dannymars@example.com;A2;799
   aze124;28/05/2015;dannymars@example.com;A7;8
   aze125;31/07/2015;john.smith@example.com;A7;8
   aze126;14/12/2015;john.smith@example.com;A10;4
   aze127;02/01/2016;dannymars@example.com;A3;79
   aze128;04/03/2016;clara.smith@example.com;A8;149
   ```

* Uma atividade de [Reconciliação](../../automating/using/reconciliation.md) cria os links entre os dados importados e o banco de dados para que os dados de transações sejam conectados corretamente aos perfis e produtos.
* Uma atividade de dados [](../../automating/using/update-data.md) Update insere e atualiza o recurso Transações do banco de dados com os dados recebidos.
* Uma **[!UICONTROL End]** atividade aciona o fluxo de trabalho de destino, que é usado para atualizar agregados.

![](assets/signal_example_source1.png)

O fluxo de trabalho de destino é apresentado da seguinte forma:

* Uma **[!UICONTROL External signal]** atividade aguarda a conclusão com êxito do fluxo de trabalho de origem.
* Uma atividade de [Consulta](../../automating/using/query.md#enriching-data) direciona perfis e os enriquece com uma coleção definida para recuperar a data da última compra.
* Uma atividade [Atualizar dados](../../automating/using/update-data.md) armazena os dados adicionais em um campo personalizado dedicado. Observe que o recurso de perfil foi estendido para adicionar o campo Data **da** última compra.

![](assets/signal_example_source2.png)

