---
title: Entrega por email
description: A atividade delivery Email permite configurar o envio de um único email de envio ou de um email recorrente em um fluxo de trabalho.
page-status-flag: never-activated
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: delivery,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 15e5aebdd67e8f5ddee89506c0469a101d94d2e8
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 0%

---


# Entrega por email{#email-delivery}

## Descrição {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

A **[!UICONTROL Email delivery]** atividade permite configurar o envio de um email em um fluxo de trabalho. Pode ser um **único email de envio** e enviado apenas uma vez, ou um email **recorrente** .

Os emails de envio único são emails padrão, enviados uma vez.

Os emails recorrentes permitem que você envie o mesmo email várias vezes para públicos alvos diferentes em um período definido. Você pode agregação os delivery por período para obter relatórios que correspondam às suas necessidades.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Email delivery]** atividade geralmente é usada para automatizar o envio de um email para um público alvo calculado no mesmo fluxo de trabalho.

Quando vinculado a um scheduler, você pode definir emails recorrentes.

Os recipient de e-mail são definidos a montante da atividade no mesmo fluxo de trabalho, por meio de atividades de direcionamento, como query, interseções etc.

A preparação da mensagem é acionada de acordo com os parâmetros de execução do fluxo de trabalho. No painel da mensagem, você pode selecionar se deseja solicitar ou não uma confirmação manual para enviar a mensagem (obrigatório por padrão). Você pode start o fluxo de trabalho manualmente ou colocar uma atividade de scheduler no fluxo de trabalho para automatizar a execução.

**Tópicos relacionados:**

* [Caso de uso: Criar um delivery de email uma vez por semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: Criação de um delivery segmentado na localização](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: Criação de delivery com um complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: Fluxo de trabalho de redefinição de metas enviando um novo delivery para não iniciantes](../../automating/using/workflow-cross-channel-retargeting.md)
* [Caso de uso: delivery de aniversário](../../automating/using/birthday-delivery.md)

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Email delivery]** atividade no seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.

   >[!NOTE]
   >
   >Você pode acessar as propriedades gerais e as opções avançadas da atividade (e não do próprio delivery) por meio do ![](assets/dlv_activity_params-24px.png) botão das ações rápidas da atividade. Este botão é específico para a **[!UICONTROL Email delivery]** atividade. As propriedades do email podem ser acessadas pela barra de ação no painel de email.

1. Selecione o modo de envio de email:

   * **[!UICONTROL Email]**: o email é enviado uma única vez. Você pode especificar aqui se deseja ou não adicionar uma transição de saída à atividade. Os diferentes tipos de transições são detalhados na etapa 7 deste procedimento.
   * **[!UICONTROL Recurring email]**: o e-mail é enviado várias vezes, de acordo com a frequência definida em uma **[!UICONTROL Scheduler]** atividade. Selecione o período de agregação dos envios. Isso permite que você agrupe todos os envios que ocorrem durante o período definido em um único email, também chamado de Execução **** recorrente e que podem ser acessados a partir da lista de atividade de marketing do aplicativo.

      Por exemplo, para um email de aniversário recorrente, que é enviado diariamente, você pode optar por agregação dos envios por mês. Isso permite que você receba relatórios sobre seu delivery mensalmente, embora o email seja enviado todos os dias.
   >[!NOTE]
   >
   >Os delivery recorrentes são preparados com base no período **de** agregação. Por exemplo, se o período de agregação for &quot;por dia&quot;, o delivery será repreparado somente uma vez por dia. Se você planeja chamar esse fluxo de trabalho várias vezes por dia, use [!UICONTROL No aggregation].

1. Selecione um tipo de email. Os tipos de e-mail vêm de modelos de e-mail definidos no menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** .
1. Insira as propriedades gerais do email. Também é possível anexá-lo a uma campanha existente. A etiqueta da atividade de delivery do fluxo de trabalho é atualizada com a etiqueta de e-mail.
1. Defina o conteúdo do email. Consulte a seção sobre edição [de](../../designing/using/designing-content-in-adobe-campaign.md)conteúdo.
1. Por padrão, a **[!UICONTROL Email delivery]** atividade não inclui nenhuma transição de saída. Se você quiser adicionar uma transição de saída à sua **[!UICONTROL Email delivery]** atividade, vá para a guia **[!UICONTROL General]** das opções avançadas de atividade ( ![](assets/dlv_activity_params-24px.png) botão nas ações rápidas de atividade) e depois verifique uma das seguintes opções:

   * **[!UICONTROL Add outbound transition without the population]**: isso permite gerar uma transição de saída que contém exatamente a mesma população da transição de entrada.
   * **[!UICONTROL Add outbound transition with the population]**: isso permite gerar uma transição de saída que contém a população para a qual o email foi enviado. Os membros do público alvo foram excluídos durante a preparação do delivery (quarentena, email inválido etc.) são excluídos desta transição.

1. Confirme a configuração da atividade e salve o fluxo de trabalho.

Ao reabrir a atividade, você será direcionado diretamente para o painel de email. Somente seu conteúdo pode ser editado.

Por padrão, iniciar um fluxo de trabalho de delivery aciona somente a preparação da mensagem. O envio de mensagens criadas a partir de um fluxo de trabalho ainda precisa ser confirmado depois que o fluxo de trabalho for iniciado. Mas a partir do painel de mensagem e somente se a mensagem tiver sido criada a partir de um fluxo de trabalho, você poderá desativar a **[!UICONTROL Request confirmation before sending messages]** opção. Ao desmarcar essa opção, as mensagens são enviadas sem aviso prévio após a preparação.

## Observações {#remarks}

Os delivery criados em um fluxo de trabalho podem ser acessados na lista de atividade de marketing do aplicativo. Você pode visualização o status de execução do fluxo de trabalho usando o painel. Os links no painel de resumo de email permitem acessar diretamente os elementos vinculados (fluxo de trabalho, campanha, delivery pai no caso de um email recorrente).

![](assets/wkf_display_recurrent_executions_2.png)

No entanto, as execuções de delivery recorrentes são mascaradas por padrão. Para visualização, marque a opção **[!UICONTROL Show recurring executions]** no painel de pesquisa do atividade de marketing.

![](assets/wkf_display_recurrent_executions.png)

Nos delivery pais, que podem ser acessados a partir da lista de atividade de marketing ou diretamente por meio das execuções recorrentes associadas, é possível visualização o número total de envios que foram processados (de acordo com o período de agregação especificado quando a **[!UICONTROL Email delivery]** atividade foi configurada). Para fazer isso, abra a visualização detalhada do bloco pai do delivery **[!UICONTROL Deployment]** selecionando ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3.png)
