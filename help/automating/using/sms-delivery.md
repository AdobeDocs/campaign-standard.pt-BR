---
solution: Campaign Standard
product: campaign
title: Delivery por SMS
description: A atividade SMS delivery permite configurar o envio de um único SMS de envio ou um SMS recorrente em um workflow.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: sms,main;delivery,smsContent,back
feature: Fluxos de trabalho
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 99%

---


# Delivery por SMS{#sms-delivery}

## Descrição {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

A atividade **[!UICONTROL SMS delivery]** permite configurar o envio de um SMS em um workflow. Pode ser um SMS de envio único e enviado apenas uma vez ou pode ser um SMS recorrente.

* **As mensagens SMS de envio único são SMS padrão, enviadas uma vez.**
* **Mensagens SMS recorrentes permitem enviar o mesmo SMS várias vezes para públicos-alvos diferentes em um período definido.** Você pode agregar os deliveries por período para obter relatórios que correspondam às suas necessidades.

## Contexto de uso {#context-of-use}

A atividade **[!UICONTROL SMS delivery]** é geralmente usada para automatizar o envio de um SMS para um público-alvo calculado no mesmo workflow.

Quando vinculado a um scheduler, você pode definir mensagens SMS recorrentes.

Os destinatários do SMS são definidos no sentido upstream da atividade, no mesmo workflow, por meio de atividades de direcionamento, como consultas, interseções etc.

A preparação da mensagem é acionada de acordo com os parâmetros de execução do workflow. No painel da mensagem, você pode selecionar se deseja solicitar ou não uma confirmação manual para enviar a mensagem (obrigatório por padrão). Você pode iniciar o workflow manualmente ou colocar uma atividade de scheduler no workflow para automatizar a execução.

## Configuração {#configuration}

1. Arraste e solte uma atividade **[!UICONTROL SMS delivery]** no seu workflow.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.

   >[!NOTE]
   >
   >É possível acessar as propriedades gerais e as opções avançadas da atividade (e não do delivery propriamente dito) por meio do botão ![](assets/dlv_activity_params-24px.png) na barra de ação do workflow. Esse botão é específico para a atividade **[!UICONTROL SMS delivery]**. As propriedades do SMS podem ser acessadas pela barra de ação no painel de SMS.

1. Selecione o modo de envio do SMS:

   * **[!UICONTROL SMS]**: o SMS é enviado uma única vez. Aqui, você pode especificar se deseja ou não adicionar uma transição de saída à atividade. Os diferentes tipos de transições estão detalhados na etapa 7 deste procedimento.
   * **[!UICONTROL Recurring SMS]**: o SMS é enviado várias vezes, de acordo com a frequência definida em uma **[!UICONTROL Scheduler]** atividade. Selecione o período de agregação dos envios. Você pode agrupar todos os envios que ocorrerem durante o período definido em uma única visualização, também chamada de **Execução recorrente**, e que pode ser acessada na lista de atividade de marketing do aplicativo.

      Por exemplo, para um SMS de aniversário recorrente, que é enviado diariamente, você pode optar por agregar os envios por mês. Ele permite receber relatórios sobre o delivery mensalmente, embora o SMS seja enviado todos os dias.

1. Selecione um tipo de SMS. Os tipos SMS vêm de templates SMS definidos no menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Insira as propriedades gerais do SMS. Também é possível anexá-la a uma campanha existente. O rótulo da atividade de delivery do workflow é atualizado com o rótulo do SMS.
1. Defina o conteúdo do SMS. Consulte a seção sobre como [Criar uma mensagem SMS](../../channels/using/creating-an-sms-message.md).
1. Por padrão, a atividade **[!UICONTROL SMS delivery]** não inclui transições de saída. Se quiser adicionar uma transição de saída à sua atividade **[!UICONTROL SMS delivery]**, acesse a guia **[!UICONTROL General]** das opções avançadas da atividade (o botão ![](assets/dlv_activity_params-24px.png) nas ações rápidas da atividade) e depois marque uma das seguintes opções:

   * **[!UICONTROL Add outbound transition without the population]**: permite gerar uma transição de saída que contém exatamente a mesma população da transição de entrada.
   * **[!UICONTROL Add outbound transition with the population]**: permite gerar uma transição de saída que contém a população para a qual o SMS foi enviado. Os membros do público-alvo excluídos durante a preparação do delivery (quarentena, número inválido etc.) são excluídos dessa transição.

1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.

Ao reabrir a atividade, você é levado diretamente ao painel de SMS. Somente seu conteúdo pode ser editado.

Por padrão, iniciar um workflow de delivery aciona somente a preparação da mensagem. O envio de mensagens criadas a partir de um workflow ainda precisará ser confirmado depois que o workflow for iniciado. Porém, no painel de mensagens, e somente se a mensagem tiver sido criada a partir de um workflow, você poderá desativar a opção **[!UICONTROL Request confirmation before sending messages]**. Ao desmarcar essa opção, as mensagens são enviadas sem aviso prévio após a preparação.

## Observações {#remarks}

Os deliveries criados em um workflow podem ser acessados na lista de atividade de marketing do aplicativo. Você pode visualizar o status de execução do workflow usando o painel. Os links no painel de resumo do SMS permitem acessar diretamente os elementos vinculados (workflow, campanha, delivery pai no caso de um SMS recorrente).

No entanto, as execuções de deliveries recorrentes são mascaradas por padrão. Para visualizá-las, marque a opção **[!UICONTROL Show recurring executions]** no painel de pesquisa das atividades de marketing.

Nas entregas pai, que podem ser acessadas na lista de atividades de marketing ou diretamente por meio das execuções recorrentes associadas, é possível visualizar o número total de envios que foram processados (de acordo com o período de agregação especificado quando a atividade **[!UICONTROL SMS delivery]** foi configurada). Para fazer isso, abra a visualização detalhada do bloco **[!UICONTROL Deployment]** da entrega pai, selecionando ![](assets/wkf_dlv_detail_button.png).
