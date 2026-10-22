---
title: Criação de um serviço
description: Saiba como criar seu primeiro serviço e configurá-lo para enviar confirmações por email aos assinantes.
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
context-tags: service,wizard;service,main
feature: Audiences
role: User
level: Beginner
exl-id: 6f42251e-75da-4707-a855-6ba9a86256c9
TQID: 'https://experienceleague.adobe.com/uSoAvkY4kGrVnzSmHbgj1gd4YKPFFzSBC-4maW-9VEw'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 92%
---
# Criação de um serviço{#creating-a-service}

Para gerenciar assinaturas, primeiro crie e configure um serviço. A configuração de um novo serviço permite especificar as confirmações por email que os perfis receberão quando assinarem ou cancelarem a assinatura do serviço. Você também definirá as páginas de destino de assinatura e unsubscription vinculadas ao serviço. Por exemplo, um link de assinatura de serviço inserido em um email direcionará o perfil automaticamente para a página de destino de assinatura especificada no serviço.

![](assets/do-not-localize/how-to-video.png) [Conheça este recurso no vídeo](#video)

Para configurar um serviço:

1. No menu avançado **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Services]** no logotipo do Adobe Campaign, adicione um novo serviço ou selecione um serviço existente. Se você criar um novo serviço, siga as etapas mostradas na tela.

   Um modelo de serviço padrão está disponível. Ele é pré-configurado com páginas de destino padrão e emails de confirmação. Você pode criar outros modelos para definir configurações específicas. Para saber mais, consulte a seção [Gerenciamento de modelos](../../start/using/marketing-activity-templates.md).

1. Na seção **[!UICONTROL Service properties]**, acessada pelo botão ![](assets/edit_darkgrey-24px.png) no painel de serviço, configure as mensagens de confirmação para assinaturas e unsubscriptions.

   ![](assets/lp_service_parameters.png)

1. Selecione a opção **[!UICONTROL Subscriptions with an expiration date]** para definir uma duração de validade para a assinatura.

   ![](assets/lp_service_expiration.png)

   Você pode usar a data de expiração em uma atividade Segmentação para direcionar os perfis que assinaram um serviço que não expirou.

1. Preencha o campo **[!UICONTROL Service label]**. O rótulo do serviço é obrigatório para usar uma mensagem de confirmação personalizada.

1. Selecione um modelo de mensagem de confirmação para assinaturas e unsubscriptions. Três modos estão disponíveis:

   * **[!UICONTROL No message]**: este modo permite criar um serviço sem uma mensagem de confirmação.
   * **[!UICONTROL Default message]**: este modo usará a mensagem transacional de confirmação de assinatura ou unsubscription. As mensagens de confirmação padrão são genéricas e serão as mesmas para todos os serviços que usam o modo padrão.

     >[!NOTE]
     >
     >Você pode modificar uma mensagem padrão clicando no rótulo na seção **[!UICONTROL Service properties]** ou selecionando-a na lista de mensagens transacionais do Adobe Campaign depois de marcar a caixa **[!UICONTROL Show internal transactional messages]**.

   * **[!UICONTROL Custom message]**: este modo permite processar as mensagens de confirmação personalizadas, específicas de cada serviço. Em seguida, selecione a opção **[!UICONTROL Custom subscription event configuration]** que está associada a um modelo de [mensagem transacional](../../channels/using/getting-started-with-transactional-msg.md) específico. Para saber mais, consulte [Confirmação da assinatura em um serviço](../../audiences/using/confirming-subscription-to-a-service.md).

1. Salve o serviço. Agora ele está pronto para ser usado.

Depois que um serviço é criado, você poderá promovê-lo.

**Tópicos relacionados:**

* [Promoção de um serviço](../../audiences/using/promoting-a-service.md)
* [Criação de um público-alvo com assinantes](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [Vinculação de uma landing page a um serviço](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)

## Tutorial em vídeo {#video}

Este vídeo mostra como criar um serviço e gerenciar suas assinaturas.

>[!VIDEO](https://video.tv.adobe.com/v/24673?quality=12)

Vídeos extras explicativos do Campaign Standard estão disponíveis [aqui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=pt-BR).
