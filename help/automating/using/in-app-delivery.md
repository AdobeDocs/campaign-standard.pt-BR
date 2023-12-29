---
title: Entrega no aplicativo
description: A atividade In-App delivery permite configurar o envio de uma mensagem no aplicativo em um workflow.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8d5a35c4-e22b-498e-b71c-c5922cf8c2fd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 39%

---

# Entrega no aplicativo{#in-app-delivery}

## Descrição {#description}

![](assets/wkf_in_app_1.png)

A variável **Entrega no aplicativo** A atividade permite configurar o envio de uma mensagem no aplicativo em um workflow. As mensagens no aplicativo permitem exibir uma mensagem quando o usuário está ativo no aplicativo. Para obter mais informações sobre o delivery no aplicativo, consulte este [seção](../../channels/using/about-in-app-messaging.md).

## Contexto de uso {#context-of-use}

A variável **[!UICONTROL In-App delivery]** A atividade geralmente é usada para automatizar o envio de uma mensagem no aplicativo para um público-alvo calculado no mesmo fluxo de trabalho.

Os recipients são definidos no sentido upstream da atividade, no mesmo workflow, por meio de atividades de direcionamento, como consultas, interseções etc.

A preparação da mensagem é acionada de acordo com os parâmetros de execução do workflow. No painel da mensagem, você pode selecionar se deseja solicitar ou não uma confirmação manual para enviar a mensagem (obrigatório por padrão). Você pode iniciar o workflow manualmente ou colocar uma atividade de scheduler no workflow para automatizar a execução.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Query]** atividade ao seu fluxo de trabalho. Observe que a variável **[!UICONTROL Query]** targeting dimension de atividade no **[!UICONTROL Properties]** precisa ser atualizada de acordo com o modelo escolhido na Etapa 4:

   * Dimensão de direcionamento deve ser definida como **[!UICONTROL mobileApp (mobileAppV5)]** para o **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]** modelo.
   * Dimensão de direcionamento deve ser definida como **[!UICONTROL profile (profile)]** para o **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** modelo.
   * Dimensão de direcionamento deve ser definida como **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** para o **[!UICONTROL Target users based on their Mobile profile (inApp)]** modelo.

1. Arraste e solte uma atividade **[!UICONTROL In-App delivery]** no seu fluxo de trabalho.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.

   >[!NOTE]
   >
   >Você pode acessar as propriedades gerais e as opções avançadas da atividade (e não do delivery propriamente dito) por meio da ![](assets/dlv_activity_params-24px.png) nas ações rápidas da atividade.

   ![](assets/wkf_in_app_3.png)

1. Selecione o tipo de mensagem no aplicativo. Isso dependerá dos dados direcionados no **[!UICONTROL Query]** atividade.

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: esse tipo de mensagem permite direcionar perfis do Adobe Campaign que assinaram seu aplicativo para dispositivos móveis e personalizar mensagens no aplicativo com atributos de perfil disponíveis no Campaign.
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: esse tipo de mensagem permite enviar uma mensagem para todos os usuários do seu aplicativo móvel, mesmo que eles não tenham um perfil existente no Campaign.
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**: esse tipo de mensagem permite direcionar todos os usuários de um aplicativo móvel que tem um perfil móvel no Campaign, seja conhecido ou desconhecido, e personalizar mensagens no aplicativo com quaisquer atributos de perfil que foram obtidos de um dispositivo móvel.

   ![](assets/wkf_in_app_4.png)

1. Insira as propriedades de mensagens no aplicativo e selecione o aplicativo móvel na caixa **[!UICONTROL Associate a Mobile App to a delivery]** campo.
1. Na guia **[!UICONTROL Triggers]**, arraste e solte o evento que acionará sua mensagem. Três categorias de eventos estão disponíveis:
1. Defina o conteúdo no aplicativo. Consulte a seção sobre [Personalização no aplicativo](../../channels/using/customizing-an-in-app-message.md).
1. Por padrão, a atividade **[!UICONTROL In-App delivery]** não inclui transições de saída. Se quiser adicionar uma transição de saída à sua atividade **[!UICONTROL In-App delivery]**, acesse a guia **[!UICONTROL General]** das opções avançadas da atividade (o botão ![](assets/dlv_activity_params-24px.png) nas ações rápidas da atividade) e depois marque uma das seguintes opções:

   * **[!UICONTROL Add outbound transition without the population]**: permite gerar uma transição de saída que contém exatamente a mesma população da transição de entrada.
   * **[!UICONTROL Add outbound transition with the population]**: permite gerar uma transição de saída que contém a população para a qual a mensagem foi enviada. Os membros do público-alvo excluídos durante a preparação do delivery são excluídos dessa transição.

   ![](assets/wkf_in_app_5.png)

1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.

Ao reabrir a atividade, você é levado diretamente ao painel No aplicativo. Somente seu conteúdo pode ser editado.

Por padrão, iniciar um workflow de entrega aciona somente a preparação da mensagem. O envio de mensagens criadas a partir de um workflow ainda precisará ser confirmado depois que o workflow for iniciado. Porém, no painel de mensagens, e somente se a mensagem tiver sido criada a partir de um workflow, você poderá desabilitar a opção **[!UICONTROL Request confirmation before sending messages]**. Ao desmarcar essa opção, as mensagens são enviadas sem aviso prévio após a preparação.

## Observações {#remarks}

As entregas criadas em um workflow podem ser acessadas na lista de atividade de marketing do aplicativo. Você pode visualizar o status de execução do workflow usando o painel. Os links no painel de resumo da notificação por push permitem acessar diretamente os elementos vinculados (workflow, campanha etc.).

Nas entregas pai, que podem ser acessadas na lista de atividades de marketing, é possível visualizar o número total de envios que foram processados (de acordo com o período de agregação especificado quando a variável **[!UICONTROL In-App delivery]** atividade foi configurada). Para fazer isso, abra a visualização detalhada do bloco **[!UICONTROL Deployment]** da entrega pai, selecionando ![](assets/wkf_dlv_detail_button.png).
