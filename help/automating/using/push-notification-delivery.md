---
title: Entrega por notificação por push
description: A atividade de Entrega por notificação por push permite configurar o envio de uma única notificação por push de envio ou uma notificação por push recorrente em um fluxo de trabalho.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: b6a43d51-32d4-4806-b4e4-33236f1e27f5
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 47%

---

# Entrega por notificação por push{#push-notification-delivery}

## Descrição {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

A variável **[!UICONTROL Push notification]** A atividade permite configurar o envio de uma notificação por push em um workflow. Pode ser uma única notificação de envio e enviada apenas uma vez ou pode ser uma notificação recorrente.

* **Solteiro** enviar notificações são entregas padrão de notificação por push de aplicativos móveis, enviadas uma vez.
* **Recorrente** as notificações permitem enviar a mesma entrega de notificação por push de aplicativo móvel várias vezes para públicos-alvos diferentes em um período definido. Você pode agregar os deliveries por período para obter relatórios que correspondam às suas necessidades.

## Contexto de uso {#context-of-use}

A variável **[!UICONTROL Push notification]** A atividade é geralmente usada para automatizar o envio de uma notificação para um público-alvo calculado no mesmo workflow.

Quando vinculado a um scheduler, você pode definir notificações por push recorrentes.

Os recipients são definidos no sentido upstream da atividade, no mesmo workflow, por meio de atividades de direcionamento, como consultas, interseções etc.

A preparação da mensagem é acionada de acordo com os parâmetros de execução do workflow. No painel da mensagem, você pode selecionar se deseja solicitar ou não uma confirmação manual para enviar a mensagem (obrigatório por padrão). Você pode iniciar o workflow manualmente ou colocar uma atividade de scheduler no workflow para automatizar a execução.

**Tópicos relacionados**

* [Envio de uma notificação por push recorrente com um workflow](../../automating/using/recurring-push-notifications.md)

## Configuração {#configuration}

1. Arraste e solte uma atividade **[!UICONTROL Push notification]** no seu fluxo de trabalho.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.

   >[!NOTE]
   >
   >Você pode acessar as propriedades gerais e as opções avançadas da atividade (e não do delivery propriamente dito) por meio do botão ![](assets/dlv_activity_params-24px.png) nas ações rápidas da atividade. Esse botão é específico para a atividade **[!UICONTROL Push notification]**. As propriedades da notificação por push podem ser acessadas pela barra de ação no painel de push.

1. Selecione o modo de envio da notificação por push:

   * **[!UICONTROL Single notification]**: a notificação por push é enviada uma única vez. Aqui, você pode especificar se deseja ou não adicionar uma transição de saída à atividade. Os diferentes tipos de transições estão detalhados na etapa 7 deste procedimento.
   * **[!UICONTROL Recurring notification]**: a notificação por push é enviada várias vezes, de acordo com a frequência definida em uma **[!UICONTROL Scheduler]** atividade. Selecione o período de agregação dos envios. Você pode agrupar todos os envios que ocorrerem durante o período definido em uma única notificação por push, também chamada de **execução recorrente** e podem ser acessadas na lista de atividade de marketing do aplicativo.

      Por exemplo, para uma notificação de aniversário recorrente, que é enviada diariamente, você pode optar por agregar os envios por mês. Isso permite receber relatórios sobre o delivery mensalmente, embora a notificação seja enviada todos os dias.

1. Selecione um tipo de notificação. Esses tipos vêm de modelos de notificações por push definidos no **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** menu.
1. Insira as propriedades gerais da notificação por push. Também é possível anexá-la a uma campanha existente. O rótulo da atividade de delivery do workflow é atualizado com o rótulo da notificação por push.
1. Defina o conteúdo da notificação por push. Consulte [Criação de uma notificação por push](../../channels/using/preparing-and-sending-a-push-notification.md)
1. Por padrão, a atividade **[!UICONTROL Push notification]** não inclui transições de saída. Se quiser adicionar uma transição de saída à sua atividade **[!UICONTROL Push Notification]**, acesse a guia **[!UICONTROL General]** das opções avançadas da atividade (o botão ![](assets/dlv_activity_params-24px.png) nas ações rápidas da atividade) e depois marque uma das seguintes opções:

   * **[!UICONTROL Add outbound transition without the population]**: permite gerar uma transição de saída que contém exatamente a mesma população da transição de entrada.
   * **[!UICONTROL Add outbound transition with the population]**: permite gerar uma transição de saída que contém a população para a qual a notificação foi enviada. Os membros do público-alvo excluídos durante a preparação do delivery são excluídos dessa transição.

1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.

Ao reabrir a atividade, você é levado diretamente ao painel de notificação por push. Somente seu conteúdo pode ser editado.

Por padrão, iniciar um workflow de delivery aciona somente a preparação da mensagem. O envio de mensagens criadas a partir de um workflow ainda precisará ser confirmado depois que o workflow for iniciado. Porém, no painel de mensagens, e somente se a mensagem tiver sido criada a partir de um workflow, você poderá desativar a opção **[!UICONTROL Request confirmation before sending messages]**. Ao desmarcar essa opção, as mensagens são enviadas sem aviso prévio após a preparação.

## Observações {#remarks}

Os deliveries criados em um workflow podem ser acessados na lista de atividade de marketing do aplicativo. Você pode visualizar o status de execução do workflow usando o painel. Os links no painel de resumo da notificação por push permitem acessar diretamente os elementos vinculados (workflow, campanha etc.).

Nas entregas pai, que podem ser acessadas na lista de atividades de marketing, é possível visualizar o número total de envios que foram processados (de acordo com o período de agregação especificado quando a variável **[!UICONTROL Push notification]** atividade foi configurada). Para fazer isso, abra a visualização detalhada do bloco **[!UICONTROL Deployment]** da entrega pai, selecionando ![](assets/wkf_dlv_detail_button.png).
