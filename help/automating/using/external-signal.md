---
solution: Campaign Standard
product: campaign
title: Sinal externo
description: A atividade de sinal externo aciona um workflow quando algumas condições são atendidas com êxito em outro workflow.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: signal,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 96%

---


# Sinal externo{#external-signal}

## Descrição {#description}

![](assets/signal.png)

A atividade **[!UICONTROL External signal]** aciona um workflow quando algumas condições são atendidas com êxito em outro workflow ou a partir de uma chamada à API REST.

## Contexto de uso {#context-of-use}

A atividade **[!UICONTROL External signal]** é usada para organizar e orquestrar diferentes processos que fazem parte da mesma jornada do cliente para workflows diferentes. Ele permite iniciar um workflow a partir de outro, permitindo oferecer suporte a jornadas de clientes mais complexas, além de poder monitorar e reagir melhor em caso de problemas.

A atividade **[!UICONTROL External signal]** foi projetada para ser colocada como a primeira atividade de um workflow. Ela pode ser acionado a partir da atividade **[!UICONTROL End]** de outro workflow ou de uma chamada à API REST (para obter mais informações, consulte a [documentação sobre APIs](../../api/using/triggering-a-signal-activity.md)).

Quando acionados, os parâmetros externos podem ser definidos e estar disponíveis nas variáveis de eventos de workflow. O processo para chamar um workflow com parâmetros externos está detalhado [nesta seção](../../automating/using/calling-a-workflow-with-external-parameters.md).

>[!NOTE]
>
>A atividade não pode ser acionada com mais frequência do que a cada 10 minutos.

Observe que uma atividade **[!UICONTROL External signal]** pode ser acionada a partir de vários eventos diferentes. Nesse caso, o evento **[!UICONTROL External signal]** é acionado assim que um dos workflows de origem ou uma chamada à API é executada. Não é necessário que todos os workflows de origem sejam concluídos.

**Tópicos relacionados**

* [Caso de uso: Atividade do sinal externo e importação](../../automating/using/external-signal-data-import.md) de dados.
* [Caso de uso: Como chamar um fluxo de trabalho para criar uma audiência a partir de um arquivo usando parâmetros externos](../../automating/using/use-case-calling-workflow.md)

## Configuração {#configuration}Fi

Ao configurar um sinal externo, é importante primeiro configurar a atividade **[!UICONTROL External signal]** no workflow de destino. Quando essa configuração for concluída, a **[!UICONTROL External signal]** atividade desse workflow ficará disponível para configurar a atividade **[!UICONTROL End]** do workflow de origem.

1. Arraste e solte uma atividade **[!UICONTROL External signal]** no workflow de destino.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Edite o rótulo da atividade. Esse rótulo é necessário ao configurar o workflow de origem que aciona **[!UICONTROL External signal]**.

   Se quiser chamar o workflow com parâmetros, use a área **[!UICONTROL Parameters]** para declará-los. Para obter mais informações, consulte [esta página](../../automating/using/declaring-parameters-external-signal.md).

   ![](assets/external_signal_configuration.png)

1. Confirme a configuração da atividade, adicione qualquer outra atividade necessária e salve o workflow.

   >[!NOTE]
   >
   >Se quiser acionar o workflow de destino a partir de outro workflow, continue com as etapas a seguir. Se quiser acionar o workflow de destino a partir de uma chamada à API REST, consulte a [documentação sobre APIs](../../api/using/triggering-a-signal-activity.md) para obter mais detalhes.

1. Abra o workflow de origem e selecione uma atividade **[!UICONTROL End]**. Se não houver uma atividade **[!UICONTROL End]** disponível, adicione uma após a última atividade de uma ramificação do workflow.

   Algumas atividades não têm transição de saída por padrão. Na guia **[!UICONTROL Properties]** dessas atividades, é possível adicionar uma transição de saída.

   Por exemplo, em uma atividade **[!UICONTROL Update data]**, acesse a guia **[!UICONTROL Transitions]** e marque a opção **[!UICONTROL Add an outbound transition without the population]**. Essa opção permite adicionar uma transição que não contém dados e não consome espaço desnecessário no sistema. Ela é usada apenas para conectar a atividade extra **[!UICONTROL End]**, que aciona o workflow de destino.

   ![](assets/external_signal_empty_transition.png)

1. Na guia **[!UICONTROL External signal]** da atividade **[!UICONTROL End]**, selecione o workflow de destino, bem como a atividade **[!UICONTROL External signal]** a ser acionada dentro desse workflow.

   Ao definir uma **[!UICONTROL End]** atividade para acionar outro workflow, seu ícone é atualizado com um símbolo de sinal adicional.

   Se quiser chamar o workflow com parâmetros, use a área **[!UICONTROL Parameters and values]**. Para obter mais informações, consulte [esta página](../../automating/using/defining-parameters-calling-workflow.md).

   ![](assets/external_signal_end.png)

1. Salve o workflow de origem.

Depois que a atividade **[!UICONTROL End]** do workflow de origem ou da chamada à API REST for executada, o workflow de destino será automaticamente acionado a partir da atividade **[!UICONTROL External signal]**.

>[!NOTE]
>
>O workflow de destino deve ser iniciado manualmente antes de poder ser acionado. Quando iniciado, o **[!UICONTROL External activity]** é ativado e aguarda o sinal do workflow de origem.
