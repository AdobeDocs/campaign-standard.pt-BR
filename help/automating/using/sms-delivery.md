---
title: Entrega por SMS
description: A atividade de delivery SMS permite configurar o envio de um único SMS de envio ou um SMS recorrente em um fluxo de trabalho.
page-status-flag: never-activated
uuid: 736078c6-ac91-4440-825b-4a6ae31894ef
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 978592b8-989a-446a-8a84-12b7fecfc130
context-tags: sms,main;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 16afc307df6902584624d6457954a472b11c5129
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 0%

---


# Entrega por SMS{#sms-delivery}

## Descrição {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

A **[!UICONTROL SMS delivery]** atividade permite configurar o envio de um SMS em um fluxo de trabalho. Isto pode ser um **único SMS enviado** e enviado apenas uma vez, ou pode ser um SMS **recorrente** .

As mensagens SMS de envio único são SMS padrão, enviadas uma vez.

Mensagens SMS recorrentes permitem enviar o mesmo SMS várias vezes para públicos alvos diferentes em um período definido. Você pode agregação os delivery por período para obter relatórios que correspondam às suas necessidades.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL SMS delivery]** atividade é geralmente usada para automatizar o envio de um SMS para um público alvo calculado no mesmo fluxo de trabalho.

Quando vinculado a um scheduler, você pode definir mensagens SMS recorrentes.

Os recipient SMS são definidos a montante da atividade no mesmo fluxo de trabalho, por meio de atividades de definição de metas, como query, interseções etc.

A preparação da mensagem é acionada de acordo com os parâmetros de execução do fluxo de trabalho. No painel da mensagem, você pode selecionar se deseja solicitar ou não uma confirmação manual para enviar a mensagem (obrigatório por padrão). Você pode start o fluxo de trabalho manualmente ou colocar uma atividade de scheduler no fluxo de trabalho para automatizar a execução.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL SMS delivery]** atividade no seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.

   >[!NOTE]
   >
   >É possível acessar as propriedades gerais e as opções avançadas da atividade (e não do próprio delivery) por meio do ![](assets/dlv_activity_params-24px.png) botão na barra de ação do fluxo de trabalho. Este botão é específico para a **[!UICONTROL SMS delivery]** atividade. As propriedades SMS podem ser acessadas pela barra de ação no painel SMS.

1. Selecione o modo de envio de SMS:

   * **[!UICONTROL SMS]**: o SMS é enviado uma única vez. Você pode especificar aqui se deseja ou não adicionar uma transição de saída à atividade. Os diferentes tipos de transições são detalhados na etapa 7 deste procedimento.
   * **[!UICONTROL Recurring SMS]**: o SMS é enviado várias vezes, de acordo com a frequência definida numa **[!UICONTROL Scheduler]** atividade. Selecione o período de agregação dos envios. Isso permite que você reagrupe todas as envios que ocorrem durante o período definido em uma única visualização, também chamada de Execução **** recorrente e que pode ser acessada a partir da lista de atividade de marketing do aplicativo.

      Por exemplo, para um SMS de aniversário recorrente, que é enviado diariamente, você pode optar por agregação dos envios por mês. Isso permite que você receba relatórios sobre seu delivery mensalmente, embora o SMS seja enviado todos os dias.

1. Selecione um tipo de SMS. Os tipos SMS vêm de modelos SMS definidos no menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** .
1. Insira as propriedades gerais do SMS. Também é possível anexá-lo a uma campanha existente. A etiqueta da atividade de delivery do fluxo de trabalho é atualizada com a etiqueta SMS.
1. Defina o conteúdo do SMS. Consulte a seção sobre como [criar uma mensagem](../../channels/using/creating-an-sms-message.md)SMS.
1. Por padrão, a **[!UICONTROL SMS delivery]** atividade não inclui nenhuma transição de saída. Se você quiser adicionar uma transição de saída à sua **[!UICONTROL SMS delivery]** atividade, vá para a guia **[!UICONTROL General]** das opções avançadas de atividade ( ![](assets/dlv_activity_params-24px.png) botão nas ações rápidas de atividade) e depois verifique uma das seguintes opções:

   * **[!UICONTROL Add outbound transition without the population]**: isso permite gerar uma transição de saída que contém exatamente a mesma população da transição de entrada.
   * **[!UICONTROL Add outbound transition with the population]**: isso permite gerar uma transição de saída contendo a população para a qual o SMS foi enviado. Os membros do público alvo foram excluídos durante a preparação do delivery (quarentena, número inválido, etc.) são excluídos desta transição.

1. Confirme a configuração da atividade e salve o fluxo de trabalho.

Ao reabrir a atividade, você é levado diretamente para o painel SMS. Somente seu conteúdo pode ser editado.

Por padrão, iniciar um fluxo de trabalho de delivery aciona somente a preparação da mensagem. O envio de mensagens criadas a partir de um fluxo de trabalho ainda precisa ser confirmado depois que o fluxo de trabalho for iniciado. Mas a partir do painel de mensagem e somente se a mensagem tiver sido criada a partir de um fluxo de trabalho, você poderá desativar a **[!UICONTROL Request confirmation before sending messages]** opção. Ao desmarcar essa opção, as mensagens são enviadas sem aviso prévio após a preparação.

## Observações {#remarks}

Os delivery criados em um fluxo de trabalho podem ser acessados na lista de atividade de marketing do aplicativo. Você pode visualização o status de execução do fluxo de trabalho usando o painel. Os links no painel de resumo do SMS permitem acessar diretamente os elementos vinculados (fluxo de trabalho, campanha, delivery pai no caso de um SMS recorrente).

No entanto, as execuções de delivery recorrentes são mascaradas por padrão. Para visualização, marque a opção **[!UICONTROL Show recurring executions]** no painel de pesquisa do atividade de marketing.

Nos delivery pais, que podem ser acessados a partir da lista de atividade de marketing ou diretamente por meio das execuções recorrentes associadas, é possível visualização o número total de envios que foram processados (de acordo com o período de agregação especificado quando a **[!UICONTROL SMS delivery]** atividade foi configurada). Para fazer isso, abra a visualização detalhada do bloco pai do delivery **[!UICONTROL Deployment]** selecionando ![](assets/wkf_dlv_detail_button.png).
