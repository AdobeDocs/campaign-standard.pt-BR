---
title: Perguntas frequentes sobre integração do Adobe Experience Platform SDK e Adobe Campaign
description: Perguntas frequentes sobre integração do Adobe Experience Platform SDK e Adobe Campaign
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 6b3c189d-8ddd-4dc0-8831-65ae62e04c70
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '909'
ht-degree: 4%

---

# Perguntas frequentes sobre a integração com o SDK da Experience Platform {#aep-faq}

Para enviar notificações por push e mensagens no aplicativo com o aplicativo Experience Platform SDK, um aplicativo para dispositivos móveis deve ser configurado no Adobe Experience Platform SDK e configurado no Adobe Campaign.

A seção abaixo lista perguntas comuns sobre essa sincronização.

Para obter mais informações sobre push ou no aplicativo, consulte as seguintes perguntas frequentes:

* [Perguntas frequentes sobre notificação por push](../../channels/using/about-push-notifications.md#push-faq)
* [Perguntas frequentes no aplicativo](../../channels/using/in-app-faq.md)
* [Perguntas frequentes sobre tags na sincronização do Adobe Experience Platform](../../administration/using/syncwithlaunch-faq.md)

## Recursos úteis antes de começar {#resource-mobile-property}

Confira os recursos abaixo para obter mais informações sobre o SDK do Adobe Experience Platform e a integração do Campaign Standard:

* Launch/Mobile [Vídeo de visão geral](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* Launch/Mobile [Guia de dicas e truques](https://www.adobe.com/content/dam/dx/us/en/products/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## A integração do SDK do Adobe Experience Platform está disponível para Adobe Campaign Standard e Adobe Campaign Classic? {#aep-validity}

Sim, [!DNL Adobe Experience Platform SDK] A integração está disponível para Adobe Campaign Standard e Adobe Campaign Classic. Você deve instalar o **[!UICONTROL Extension]** através da [!DNL Data Collection UI] para habilitar a integração.

Para obter mais informações, consulte esta [página](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).

## Quais recursos a integração do SDK do Adobe Experience Platform facilita no Adobe Campaign? {#aep-capabilities}

Consulte a tabela abaixo para saber mais sobre esses recursos.

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places] a integração inclui eventos do places como acionadores para mensagens no aplicativo (N/A para notificações por push), enriquecendo perfis com [!DNL Places] suporte a dados e notificações locais. Consulte esta [página](../../channels/using/preparing-and-sending-an-in-app-message.md) para obter mais informações. <br>[!DNL Places] a integração limitada inclui o enriquecimento de perfis com [!DNL Places] dados.

## Que caso de uso a integração do SDK do Adobe Experience Platform facilita no Adobe Campaign Standard? {#aep-use-cases}

Os seguintes casos de uso são suportados:

* Adquira um **[!UICONTROL Mobile Profile]** no Campaign (identificado pela ECID em **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]** guia )
* Enriqueça um **[!UICONTROL Mobile Profile]** no Adobe Campaign (requer **[!UICONTROL Custom resource Extension]** da tabela appSubscriberRcp)
* Adquirir um token de push para enviar mensagens de push (requer que o usuário opte por receber mensagens de push)
* Enviar mensagens de push e no aplicativo
* Acompanhar a interação do usuário com as mensagens de push e no aplicativo e fornecer relatórios sobre isso

## O que preciso fazer para adquirir um perfil móvel no Campaign? {#mobile-profile-campaign}

Para isso, siga as etapas abaixo:

1. Configure um **[!UICONTROL Mobile property]** em [!DNL Launch].
1. Instale a extensão Adobe Campaign Standard. Observe que a extensão Adobe Campaign Standard também requer **[!UICONTROL Mobile Core]**, **[!UICONTROL Profile]** e **[!UICONTROL Lifecycle]** extensões instaladas por padrão no [!DNL Launch].
   * Os usuários devem configurar o tempo limite da sessão em **[!UICONTROL Mobile Core]** extensão que afeta a frequência dos eventos do ciclo de vida.
   * Depois que a extensão é configurada, os usuários devem adicionar as dependências apropriadas no aplicativo móvel usando Cocoapods for iOS e Gradle for Android. Siga as instruções [here](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).
   * Sempre pegue as versões mais recentes das bibliotecas.
   * No aplicativo móvel, registre-se **[!UICONTROL Campaign]**, **[!UICONTROL UserProfile]**, **[!UICONTROL Identity]**, **[!UICONTROL Lifecycle]** e **[!UICONTROL Signal]** extensões. Siga as instruções [here](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core).
   * Depois que as extensões forem registradas, inicie o ACPCore. Para Android, certifique-se de definir Application onCreate(). Siga as instruções exatas fornecidas em Instruções de instalação em dispositivos móveis para sua propriedade móvel no Launch.
   * As APIs do SDK a seguir também serão necessárias. Implemente as APIs de início e pausa do ciclo de vida conforme descrito [here](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android) para Android e aqui para iOS.
1. Configure um **[!UICONTROL Mobile Property]** no Adobe Campaign Standard. Siga o procedimento [here](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## O que preciso fazer para enriquecer um perfil móvel no Campaign? {#enrich-mobile-profile}

Você deve configurar um postback CollectPII (consulte esta seção) [página](../../administration/using/configuring-rules-launch.md#pii-postback)) e implementar a API CollectPII a partir do SDK (consulte esta seção [página](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)).

## Com que frequência uma chamada CollectPII deve ser disparada? {#collect-pii}

O objetivo da chamada CollectPII é enriquecer o Perfil móvel no Campaign. Ele deve ser acionado sempre que houver novas informações significativas que os clientes gostariam de adicionar ao perfil, dependendo de seus casos de uso e das necessidades dos negócios.

## As chamadas CollectPII podem ser disparadas em resposta a vários eventos do acionador? {#collect-pii-calls}

Sim. Dependendo da necessidade da sua empresa, você pode disparar chamadas CollectPII em resposta ao logon do usuário no aplicativo, ou comprar algo ou evento de ciclo de vida ou usuário entrando em uma geofence etc. Resumindo, uma interação do usuário com o aplicativo que gera informações que você gostaria de usar para o enriquecimento do perfil.

## Posso disparar chamadas CollectPII em resposta a todos os eventos do Mobile? {#collect-pii-events}

A frequência e o design das chamadas CollectPII devem ser ditadas pelas necessidades dos negócios e não devem ser disparadas cegamente, pois criam carga extra no banco de dados.

### Quando tento acessar os aplicativos Adobe Experience Platform no Campaign ou no Launch, às vezes recebo um erro de propriedade não disponível. {#aep-error}

Esse é um problema conhecido e ocorre devido à expiração do token. Você deve tentar fazer logoff e logon.

## Quais seriam algumas recomendações úteis de recursos para saber mais sobre o SDK do Adobe Experience Platform (anteriormente conhecido como SDK V5)?{#resource-aep}

Confira os recursos abaixo:

* Experience Platform SDK [documentação](https://aep-sdks.gitbook.io/docs/)
* Introdução ao Launch e ao Experience Platform SDK [documentação](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* Atualização para o SDK do Experience Platform [documentação](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* SDK do Experience Platform Github [documentação](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)

## Estou recebendo o erro &quot;Você não tem acesso de gravação no delivery&quot; ao criar um delivery de notificação por push. {#write-access-error}

Você deve verificar o seguinte:

* O aplicativo móvel deve ser mapeado para a unidade organizacional do usuário que precisa criar e enviar deliveries por push. O usuário de uma unidade organizacional secundária não pode criar um delivery de push usando um aplicativo mapeado para a unidade organizacional principal.

* A campanha ou programa no qual o delivery de push é criado deve ser mapeado para a unidade organizacional do usuário que precisa criar e enviar deliveries por push. O usuário da unidade organizacional secundária não pode criar um delivery de push em uma campanha ou programa mapeado para a unidade organizacional principal.
