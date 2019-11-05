---
title: Entrega no aplicativo
description: A atividade de entrega no aplicativo permite configurar o envio de uma mensagem no aplicativo em um fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: atividades de canal
discoiquuid: 19796aca-6e9e-4d3a-8917-ba60ec7993c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Entrega no aplicativo{#in-app-delivery}

## Descrição {#description}

![](assets/wkf_in_app_1.png)

A atividade de entrega **** no aplicativo permite configurar o envio de uma mensagem no aplicativo em um fluxo de trabalho. As mensagens no aplicativo permitem exibir uma mensagem quando o usuário está ativo no aplicativo. Para obter mais informações sobre a entrega no aplicativo, consulte esta [seção](../../channels/using/about-in-app-messaging.md).

## Contexto de utilização {#context-of-use}

A **[!UICONTROL In-App delivery]** atividade é geralmente usada para automatizar o envio de uma mensagem no aplicativo para um público-alvo calculado no mesmo fluxo de trabalho.

Os destinatários são definidos como upstream da atividade no mesmo fluxo de trabalho, por meio de atividades de definição de metas, como consultas, interseções etc.

A preparação da mensagem é acionada de acordo com os parâmetros de execução do fluxo de trabalho. No painel de mensagens, você pode selecionar se deseja solicitar ou não uma confirmação manual para enviar a mensagem (obrigatório por padrão). Você pode iniciar o fluxo de trabalho manualmente ou colocar uma atividade do programador no fluxo de trabalho para automatizar a execução.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Query]** atividade em seu fluxo de trabalho. Observe que a dimensão de direcionamento de **[!UICONTROL Query]** atividade na guia **[!UICONTROL Properties]** precisa ser atualizada de acordo com o modelo escolhido na Etapa 4:

   * A dimensão de definição de metas deve ser definida como **[!UICONTROL mobileApp (mobileAppV5)]** para o **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]** modelo.
   * A dimensão de definição de metas deve ser definida como **[!UICONTROL profile (profile)]** para o **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** modelo.
   * A dimensão de definição de metas deve ser definida como **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** para o **[!UICONTROL Target users based on their Mobile profile (inApp)]** modelo.

1. Arraste e solte uma **[!UICONTROL In-App delivery]** atividade em seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.

   >[!NOTE]
   >
   >Você pode acessar as propriedades gerais e as opções avançadas da atividade (e não da entrega em si) por meio do ![](assets/dlv_activity_params-24px.png) botão das ações rápidas da atividade.

   ![](assets/wkf_in_app_3.png)

1. Selecione o tipo de mensagem no aplicativo. Isso dependerá dos dados direcionados na sua **[!UICONTROL Query]** atividade.

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: Esse tipo de mensagem permite direcionar perfis do Adobe Campaign que se inscreveram no aplicativo móvel e personalizar mensagens no aplicativo com atributos de perfil disponíveis no Campaign.
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: Esse tipo de mensagem permite que você envie uma mensagem para todos os usuários do aplicativo móvel mesmo se eles não tiverem um perfil existente no Campaign.
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**: Esse tipo de mensagem permite direcionar todos os usuários de um aplicativo móvel que têm um perfil móvel no Campaign, seja conhecido ou desconhecido, e personalizar mensagens no aplicativo com qualquer atributo de perfil obtido do dispositivo móvel.
   ![](assets/wkf_in_app_4.png)

1. Insira as propriedades de mensagem no aplicativo e selecione o aplicativo móvel no **[!UICONTROL Associate a Mobile App to a delivery]** campo.
1. Na **[!UICONTROL Triggers]** guia, arraste e solte o evento que acionará sua mensagem. Três categorias de eventos estão disponíveis:
1. Defina o conteúdo no aplicativo. Consulte a seção sobre personalização [no aplicativo](../../channels/using/customizing-an-in-app-message.md).
1. Por padrão, a **[!UICONTROL In-App delivery]** atividade não inclui nenhuma transição de saída. Se você deseja adicionar uma transição de saída à sua **[!UICONTROL In-App delivery]** atividade, vá para a **[!UICONTROL General]** guia das opções de atividade avançada ( ![](assets/dlv_activity_params-24px.png) botão nas ações rápidas da atividade) e verifique uma das seguintes opções:

   * **[!UICONTROL Add outbound transition without the population]**: isso permite gerar uma transição de saída que contém exatamente a mesma população da transição de entrada.
   * **[!UICONTROL Add outbound transition with the population]**: isso permite gerar uma transição de saída que contém a população para a qual a mensagem foi enviada. Os membros do alvo excluídos durante a preparação de entrega são excluídos desta transição.
   ![](assets/wkf_in_app_5.png)

1. Confirme a configuração da atividade e salve o fluxo de trabalho.

Ao reabrir a atividade, você é direcionado diretamente para o painel no aplicativo. Somente seu conteúdo pode ser editado.

Por padrão, iniciar um fluxo de trabalho de entrega aciona somente a preparação da mensagem. O envio de mensagens criadas a partir de um fluxo de trabalho ainda precisa ser confirmado depois que o fluxo de trabalho for iniciado. Mas no painel de mensagens, e somente se a mensagem foi criada a partir de um fluxo de trabalho, você pode desativar a **[!UICONTROL Request confirmation before sending messages]** opção. Ao desmarcar essa opção, as mensagens são enviadas sem aviso prévio após a preparação.

## Observações {#remarks}

As entregas criadas em um fluxo de trabalho podem ser acessadas na lista de atividades de marketing do aplicativo. Você pode exibir o status de execução do fluxo de trabalho usando o painel. Os links no painel de resumo da notificação por push permitem acessar diretamente os elementos vinculados (fluxo de trabalho, campanha etc.).

Nas entregas principais, que podem ser acessadas na lista de atividades de marketing, você pode exibir o número total de envios que foram processados (de acordo com o período de agregação especificado quando a **[!UICONTROL In-App delivery]** atividade foi configurada). Para fazer isso, abra a exibição detalhada do **[!UICONTROL Deployment]** bloco da entrega pai selecionando ![](assets/wkf_dlv_detail_button.png).
