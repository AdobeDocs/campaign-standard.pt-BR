---
title: Preparação e envio de uma mensagem no aplicativo
description: Crie uma mensagem no aplicativo para público alvo dos assinantes do aplicativo com conteúdo específico.
page-status-flag: never-activated
uuid: a79b0466-8641-46cc-a70f-e4e839587bb2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: in-app-messaging
discoiquuid: 18bf5297-a688-4302-abe4-e2fbcafdb515
context-tags: delivery,triggers,back;deliveryCreation,wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: tm+mt
source-wordcount: '1274'
ht-degree: 5%

---


# Preparação e envio de uma mensagem no aplicativo{#preparing-and-sending-an-in-app-message}

>[!NOTE]
>
>A personalização no aplicativo depende de um campo de vinculação que normalmente é uma ID CRM e/ou ID de logon do aplicativo móvel. Você é o único responsável pela proteção desse campo de ligação quando usado em conexão com o Adobe Campaign. Se você não conseguir manter seus campos de vinculação protegidos, sua mensagem personalizada pode estar vulnerável. A Adobe não será responsável por danos decorrentes do acesso não autorizado ou do uso de quaisquer dados de perfil se você não seguir as práticas de proteção, gerenciamento e composição de campo de ligação seguras.

Três tipos de mensagens no aplicativo estão disponíveis no Adobe Campaign:

* **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: Esse tipo de mensagem permite que você público alvo perfis (perfis CRM) que se inscreveram no seu aplicativo móvel. Esse tipo de mensagem pode ser personalizado com todos os atributos de perfil disponíveis no Adobe Campaign, mas requer um handshake seguro entre o SDK móvel e o serviço de mensagens no aplicativo Campaign para garantir que as mensagens com informações pessoais e confidenciais sejam usadas apenas por usuários autorizados.

   Para baixar esse tipo de mensagem nos dispositivos dos usuários, o SDK móvel precisa enviar campos de vinculação usados para conectar um perfil móvel a um perfil CRM no Adobe Campaign. Para obter mais informações sobre as APIs do SDK necessárias para oferecer suporte ao In-App, consulte esta [página](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference).

* **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: Esse tipo de mensagem permite que você envie mensagens para todos os usuários (atuais ou futuros) do seu aplicativo móvel mesmo se eles não tiverem um perfil existente no Adobe Campaign. Assim, a personalização não é possível ao personalizar as mensagens, pois o perfil do usuário pode nem mesmo existir no Adobe Campaign.
* **[!UICONTROL Target users based on their Mobile profile (inApp)]**: Esse tipo de mensagem permite que você público alvo todos os usuários conhecidos ou anônimos de um aplicativo móvel que tem um perfil móvel no Adobe Campaign. Esse tipo de mensagem pode ser personalizado usando apenas atributos não pessoais e não confidenciais e não requer handshake seguro entre o SDK móvel e o serviço de mensagens no aplicativo do Adobe Campaign.

   Para obter mais informações sobre como lidar com dados pessoais e confidenciais, consulte [Manuseio de campos de perfis móveis com dados](#handling-mobile-profile-fields-with-personal-and-sensitive-data)pessoais e confidenciais.

![](assets/diagram_inapp.png)

## Tratamento de campos de perfil para dispositivos móveis com dados pessoais e confidenciais {#handling-mobile-profile-fields-with-personal-and-sensitive-data}

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications&#39; subscribers.

Esse recurso precisa ser estendido para coletar dados que você pretende enviar do dispositivo móvel para o Adobe Campaign. Para fazer isso, consulte esta [página](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) para obter as etapas detalhadas.

Para permitir a personalização de suas mensagens no aplicativo com mais segurança, os campos do perfil móvel desse recurso precisam ser configurados adequadamente. In your **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, when creating your new mobile profiles fields, check **[!UICONTROL Personal and Sensitive]** to make them unavailable during In-App messages personalization.

>[!NOTE]
>
>Se você tiver uma implementação existente com extensão de recurso personalizada nesta tabela, recomendamos que você rotule os campos apropriadamente antes de aproveitá-los para personalização de mensagens no aplicativo.

![](assets/in_app_personal_data_2.png)

Once your **[!UICONTROL Subscriptions to an application]** custom resource is configured and published, you can start preparing your In-App delivery using the **[!UICONTROL Target users based on their Mobile profile (inApp)]** template. Only non-personal and non-sensitive fields will be available from **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource for personalization.

If you require personalization with **Personal and Sensitive** fields, we recommend using the **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** template which has additional security mechanism to ensure that your users&#39; PII data remains secure.

## Preparando sua mensagem no aplicativo {#preparing-your-in-app-message}

As etapas para criar uma mensagem independente no aplicativo com o Adobe Campaign são:

1. No home page Adobe Campaign, clique na **[!UICONTROL In-App messaging]** placa.

   Você também pode criar um aplicativo no aplicativo na guia **Marketing atividade** clicando no **[!UICONTROL Create]** botão.

   Observe que uma mensagem no aplicativo também pode ser criada a partir de uma campanha ou do home page Adobe Campaign ou em um fluxo de trabalho.

1. Selecione Mensagem **no aplicativo**.

   ![](assets/inapp_creating.png)

1. Selecione um modelo apropriado com base nas suas necessidades de direcionamento de audiência.

   ![](assets/inapp_creating_2.png)

   Por padrão, você pode selecionar um dos três modelos prontos para uso a seguir:

   * **[!UICONTROL Target users based on their Campaign CRM profile (inAppProfile)]**
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**

1. Digite as propriedades de mensagens no aplicativo e selecione seu aplicativo móvel no **[!UICONTROL Associate a Mobile App to a delivery]** campo. Observe que se você não configurou seu aplicativo móvel com Adobe Campaign Standard, ele não aparecerá na lista. For more information on mobile application configuration, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

   ![](assets/inapp_creating_3.png)

1. Selecione a audiência que deseja público alvo para a sua mensagem no aplicativo. Sua audiência é pré-filtrada dependendo do aplicativo móvel associado a esse delivery.

   Observe que essa etapa não é necessária com o **[!UICONTROL Broadcast an In-App message (inAppBroadcast)]** , pois público alvo todos os usuários de um aplicativo móvel.

   ![](assets/inapp_creating_8.png)

1. Na **[!UICONTROL Triggers]** guia, arraste e solte o evento que acionará sua mensagem. Ao escolher um acionador, você escolhe uma ação executada pelos usuários que fará com que a mensagem no aplicativo seja exibida.

   Quatro categorias de eventos estão disponíveis:

   * **[!UICONTROL Mobile Application events]**: eventos personalizados implementados em seu aplicativo móvel.

      For more on events creations, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

   * **[!UICONTROL Life Cycle events]**: eventos de ciclo de vida prontos para uso suportados pelo Adobe Mobile SDK.

      Para obter mais informações sobre eventos de ciclo de vida, consulte esta [página](https://docs.adobe.com/content/help/en/mobile-services/android/metrics.html).

   * **[!UICONTROL Analytics Events]**: As três categorias a seguir são suportadas, dependendo do instrumentado no aplicativo móvel: Adobe Analytics, dados de contexto ou estado de Visualização.

      Observe que esses eventos só estarão disponíveis se você tiver uma licença da Adobe Analytics.

   * **[!UICONTROL Places]**: As três categorias a seguir aproveitam os dados de localização em tempo real para fornecer experiências móveis relevantes contextualmente: Posiciona dados de contexto, insere metadados personalizados ou tipo de evento Locais.

      Para obter mais informações sobre o Adobe Places, consulte a documentação [](https://placesdocs.com/)Locais.
   ![](assets/inapp_creating_4.png)

1. Se você usar um evento **[!UICONTROL Analytics Events]**, o Adobe Analytics e o estado da Visualização serão automaticamente preenchidos com base nos conjuntos de relatórios configurados na extensão do Analytics na inicialização de Adobe Experience Platform, enquanto os eventos de dados de contexto precisam ser adicionados manualmente.

   Observe que esses eventos só estarão disponíveis se você tiver uma licença da Adobe Analytics.

   ![](assets/inapp_creating_7.png)

1. Se você usar um **[!UICONTROL Places]** acionador, os dados de contexto do Local, os metadados personalizados do Local ou o tipo de evento Locais serão automaticamente preenchidos com base em todas as Bibliotecas e seus Pontos de interesse criados no Adobe Places.

   Observe que esse acionador será aplicado no dispositivo somente para os Pontos de interesse das Bibliotecas selecionadas na extensão Locais no Experience Platform Launch. Para obter mais informações sobre a extensão Locais e como instalá-la, consulte esta [documentação](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/places-extension.html).

1. Na **[!UICONTROL Frequency & duration]** guia, escolha a frequência do seu acionador, a data de start e término, o dia da semana e a hora do dia em que a mensagem no aplicativo estará ativa.

   ![](assets/inapp_creating_5.png)

1. Edite o conteúdo de sua mensagem e defina as opções avançadas. See [Customizing an In-App message](https://helpx.adobe.com/campaign/standard/channels/using/customizing-a-push-notification.html).

   ![](assets/inapp_creating_6.png)

1. Clique em **[!UICONTROL Create]**.

Sua mensagem no aplicativo agora está pronta para ser enviada para sua audiência direcionada.

**Tópicos relacionados:**

* [Personalizar uma mensagem no aplicativo](../../channels/using/customizing-an-in-app-message.md)
* [Relatório no aplicativo](../../reporting/using/in-app-report.md)
* [Enviar uma mensagem no aplicativo em um fluxo de trabalho](../../automating/using/in-app-delivery.md)

## Envio da mensagem no aplicativo {#sending-your-in-app-message}

Depois que terminar de preparar seu delivery e as etapas de aprovação tiverem sido executadas, você poderá enviar sua mensagem.

1. Clique em **[!UICONTROL Prepare]** para calcular o público alvo e gerar as mensagens.

   ![](assets/inapp_sending_4.png)

1. Ao concluir com êxito a preparação, a janela **Implantação** apresenta os seguintes KPIs: **Direcionamento** e **Para entregar**.

   Você pode verificar a janela Implantação clicando no ![](assets/lp_link_properties.png) botão para possíveis exclusões ou erros no seu delivery.

   ![](assets/inapp_sending_5.png)

1. Clique em **[!UICONTROL Confirm]** start para enviar sua mensagem no aplicativo.

   ![](assets/inapp_sending_6.png)

1. Verifique o status do seu delivery através do painel de mensagens e registros. Para obter mais informações, consulte esta [seção](../../sending/using/monitoring-a-delivery.md).

   **[!UICONTROL Delivered]** e as contagens de **[!UICONTROL Sent]** KPIs são baseadas no que é enviado com êxito da Campanha para o serviço delivery de mensagens. Observe que esses KPIs não são uma indicação da contagem de dispositivos móveis que receberam ou baixaram a mensagem com êxito do serviço de delivery de mensagens.

   ![](assets/inapp_sending_7.png)

1. Meça o impacto de suas mensagens no aplicativo com relatórios do delivery. For more on reporting, refer to [this section](../../reporting/using/in-app-report.md).

**Tópicos relacionados:**

* [Relatório no aplicativo](../../reporting/using/in-app-report.md)
* [Enviar uma mensagem no aplicativo em um fluxo de trabalho](../../automating/using/in-app-delivery.md)

