---
title: Criar um serviço
description: Saiba como criar seu primeiro serviço e configurá-lo para enviar confirmações por email aos seus assinantes.
page-status-flag: never-activated
uuid: 0d95d852-0f22-4b7b-b301-8fb4844c3ca2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
discoiquuid: 6b7788fe-fa6c-472a-97db-765595ce1589
context-tags: service,wizard;service,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c26f98c8edd832beeedfedafb8ad27730cc30d25

---


# Criar um serviço{#creating-a-service}

Para poder gerenciar assinaturas, é necessário criar um serviço e configurá-lo. A configuração de um novo serviço permite especificar as confirmações de email que os perfis receberão ao se inscreverem ou cancelarem a assinatura do serviço. Você também definirá as páginas iniciais de assinatura e cancelamento de assinatura vinculadas ao serviço. Por exemplo, um link de assinatura de serviço inserido em um email direcionará automaticamente o perfil para a página inicial de assinatura especificada no serviço.

Para configurar um serviço:

1. No menu avançado **[!UICONTROL Profiles & audiences]**>**[!UICONTROL Services]** por meio do logotipo do Adobe Campaign, adicione um novo serviço ou selecione um serviço existente. Se você criar um novo serviço, siga as etapas mostradas na tela.

   Um modelo de serviço padrão está disponível. Este modelo é pré-configurado com páginas iniciais e e-mails de confirmação padrão. Você pode criar outros modelos para definir configurações específicas. For more on this, refer to the [Managing templates](../../start/using/marketing-activity-templates.md) section.

1. Na **[!UICONTROL Service properties]**seção, acessada pelo![](assets/edit_darkgrey-24px.png)botão no painel de serviço, configure as mensagens de confirmação para assinaturas e desassinaturas.

   ![](assets/lp_service_parameters.png)

1. Fill in the **[!UICONTROL Service label]**field. O rótulo do serviço é obrigatório ao usar uma mensagem de confirmação personalizada.

1. Selecione um modelo de mensagem de confirmação para assinaturas e cancelamentos de assinaturas. Três modos estão disponíveis:

   * **[!UICONTROL No message]**: este modo permite que você crie um serviço sem uma mensagem de confirmação.
   * **[!UICONTROL Default message]**: este modo usará a mensagem de transação padrão de assinatura ou de confirmação de não assinatura. As mensagens de confirmação padrão são genéricas e serão as mesmas para todos os serviços que usam o modo padrão.

      >[!NOTE]
      >
      >Você pode modificar uma mensagem padrão clicando em seu rótulo na **[!UICONTROL Service properties]**seção ou selecionando-a na lista de mensagens transacionais do Adobe Campaign, depois de marcar a**[!UICONTROL Show internal transactional messages]** caixa.

   * **[!UICONTROL Custom message]**: esse modo permite que você manipule mensagens de confirmação personalizadas, específicas para cada serviço. Em seguida, selecione o**[!UICONTROL Custom subscription event configuration]** que está associado a um modelo de mensagem [](../../channels/using/about-transactional-messaging.md) transacional específico. Para obter mais informações, consulte [Confirmação da assinatura de um serviço](../../audiences/using/confirming-subscription-to-a-service.md).

1. Salve o serviço. Agora está pronto para ser usado.

Depois que um serviço for criado, você poderá começar a promovê-lo.

**Tópicos relacionados:**

* [Gerenciamento de um serviço e assinatura](https://helpx.adobe.com/campaign/kt/acs/using/acs-services-and-subscriptions-feature-video-use.html) de vídeo
* [Promover um serviço](../../audiences/using/promoting-a-service.md)
* [Criação de um público-alvo feito de assinantes](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [Vincular uma página de aterrissagem a um serviço](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)
