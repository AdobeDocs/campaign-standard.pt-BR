---
title: Criação de um serviço
seo-title: Criação de um serviço
description: Criação de um serviço
seo-description: Saiba como criar seu primeiro serviço e configurá-lo para enviar confirmações de e-mail aos assinantes.
page-status-flag: nunca ativado
uuid: 0 d 95 d 852-0 f 22-4 b 7 b-b 301-8 fb 4844 c 3 ca 2
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: públicos-alvo
content-type: reference
topic-tags: gerenciando assinaturas
discoiquuid: 6 b 7788 fe-fa 6 c -472 a -97 db -765595 ce 1589
context-tags: serviço, assistente; serviço, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Creating a service{#creating-a-service}

Para poder gerenciar assinaturas, primeiro você precisa criar um serviço e configurá-lo. Configurar um novo serviço permite especificar as confirmações de e-mail que os perfis receberão ao assinar ou cancelar a inscrição do serviço. Você também definirá as páginas de aterrissagem de assinatura e cancelamento de assinatura vinculadas ao serviço. Por exemplo, um link de assinatura de serviço inserido em um email direciona automaticamente o perfil para a página de aterrissagem de assinatura especificada no serviço.

Para configurar um serviço:

1. From the advanced menu **Profiles &amp; audiences** &gt; **Services** via the Adobe Campaign logo, add a new service or select an existing service. Se você criar um novo serviço, siga as etapas mostradas na tela.

   Um modelo de serviço padrão está disponível. Este modelo é pré-configurado com páginas de aterrissagem padrão e e-mails de confirmação. É possível criar outros modelos para definir configurações específicas. For more on this, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. In the **Service properties** section, accessed via the ![](assets/edit_darkgrey-24px.png) button in the service dashboard, configure the confirmation messages for subscriptions and unsubscriptions.

   ![](assets/lp_service_parameters.png)

1. Selecione um modelo de mensagem de confirmação para assinaturas e cancelamento de assinaturas. Há três modos disponíveis:

   * **[!UICONTROL No message]**: esse modo permite criar um serviço sem uma mensagem de confirmação.
   * **[!UICONTROL Default message]**: esse modo usará a mensagem transacional de assinatura ou cancelamento de assinatura padrão. As mensagens de confirmação padrão são genéricas e serão as mesmas para todos os serviços que usam o modo padrão.
   * **[!UICONTROL Custom message]**: esse modo permite que você manipule mensagens de confirmação personalizadas, específicas para cada serviço. You then select the **[!UICONTROL Custom subscription event configuration]** which is associated with a specific transactional message template. Refer to [Transactional messages](../../channels/using/about-transactional-messaging.md) for more information on transactional event and message configuration.

1. Salve o serviço. Agora está pronto para ser usado.

Depois que um serviço for criado, você poderá começar a promovê-lo.

**Tópicos relacionados:**

* [Gerenciamento de](https://helpx.adobe.com/campaign/kt/acs/using/acs-services-and-subscriptions-feature-video-use.html) vídeos e assinaturas
* [Promoção de um serviço](../../audiences/using/promoting-a-service.md)
* [Criação de um público-alvo feito por assinantes](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [Vincular um formulário a um serviço em uma página de aterrissagem](../../channels/using/designing-a-landing-page.md#linking-a-form-to-a-service)

