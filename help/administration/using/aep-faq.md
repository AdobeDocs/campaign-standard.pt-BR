---
title: Perguntas frequentes sobre integração de Adobe Experience Platform SDK e Adobe Campaign
description: Perguntas frequentes sobre integração de Adobe Experience Platform SDK e Adobe Campaign
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d0a0c59763af8babc9701206cc39fe41b98e0cd4
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---


# Perguntas frequentes sobre integração de Adobe Experience Platform SDK e Adobe Campaign {#aep-faq}

## A integração do SDK do Adobe Experience Platform está disponível para o Adobe Campaign Standard e o Adobe Campaign Classic? {#aep-validity}

Sim, a integração está disponível para Adobe Campaign Standard e Adobe Campaign Classic. [!DNL Adobe Experience Platform SDK] É necessário instalar o correspondente **[!UICONTROL Extension]** via [!DNL Adobe Launch] para habilitar a integração.

Para obter mais informações, consulte esta [página](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic) para Campaign Classic e esta [página](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) para Campaign Standard.

## Quais recursos a integração do SDK do Adobe Experience Platform facilita no Adobe Campaign? {#aep-capabilities}

Consulte a tabela abaixo para saber mais sobre esses recursos.

![](assets/faq.png)

>[!Nnota]
>
>[!DNL Places] a integração inclui eventos de local como acionadores para mensagens no aplicativo (N/A para notificações por push), enriquecendo perfis com suporte a notificações locais e [!DNL Places] dados. Refer to this [page](../../channels/using/preparing-and-sending-an-in-app-message.md) for more information. <br>[!DNL Places] a integração limitada inclui perfis enriquecedores com [!DNL Places] dados.

## Que caso de uso a integração do SDK do Adobe Experience Platform facilita no Adobe Campaign Standard? {#aep-use-cases}

Os seguintes casos de uso são suportados:

* Adquira uma Campanha **[!UICONTROL Mobile Profile]** (identificada pelo ECID em **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]** >
* Enriquecer um **[!UICONTROL Mobile Profile]** **[!UICONTROL Custom resource Extension]** no Adobe Campaign (requer a tabela appSubscriberRcp)
* Adquira um token de push para enviar mensagens de push (requer que o usuário opte por receber mensagens de push)
* Enviar mensagens de push e no aplicativo
* Rastrear a interação do usuário com mensagens de push e no aplicativo e fornecer relatórios sobre isso

## O que devo fazer para adquirir um Perfil para dispositivos móveis em Campanhas? {#mobile-profile-campaign}

Para isso, siga as etapas abaixo:

1. Configure um **[!UICONTROL Mobile property]** em [!DNL Launch].
1. Instale a extensão Adobe Campaign Standard. Observe que a extensão Adobe Campaign Standard também exige **[!UICONTROL Mobile Core]**, **[!UICONTROL Profile]** e **[!UICONTROL Lifecycle]** extensões que são instaladas por padrão em [!DNL Launch].
   * Os usuários devem configurar o tempo limite da sessão na **[!UICONTROL Mobile Core]** extensão, o que afeta a frequência dos eventos do ciclo de vida.
   * Depois que a extensão é configurada, os usuários devem adicionar as dependências apropriadas no aplicativo móvel usando Cocoapods para iOS e Gradle para Android. Siga as instruções [aqui](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).
   * Tenha sempre as versões mais recentes das bibliotecas.
   * No aplicativo móvel, registre **[!UICONTROL Campaign]**, **[!UICONTROL UserProfile]****[!UICONTROL Identity]** e **[!UICONTROL Lifecycle]** **[!UICONTROL Signal]** extensões. Siga as instruções [aqui](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core).
   * Depois que as extensões forem registradas, o start ACPCore. Para Android, certifique-se de setApplication onCreate(). Siga as instruções exatas fornecidas em Instruções de instalação móvel para sua propriedade móvel no Launch.
   * As APIs do SDK a seguir também serão necessárias. Implemente o Start de ciclo de vida e as APIs de pausa conforme descrito [aqui](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android) para Android e aqui para iOS.
1. Configure um **[!UICONTROL Mobile Property]** no Adobe Campaign Standard. Siga o procedimento [aqui](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## O que devo fazer para enriquecer um Perfil móvel na Campanha? {#enrich-mobile-profile}

É necessário configurar um postback CollectPII (consulte esta [página](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)) e implementar a API CollectPII do SDK (consulte esta [página](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)).

## Com que frequência uma chamada CollectPII deve ser acionada? {#collect-pii}

O objetivo da chamada CollectPII é enriquecer o Perfil móvel na Campanha. Ele deve ser acionado sempre que houver novas informações significativas que os clientes queiram adicionar ao perfil, dependendo de seus casos de uso e das necessidades dos negócios.

## As chamadas CollectPII podem ser acionadas em resposta a vários eventos de disparo? {#collect-pii-calls}

Sim. Dependendo das necessidades de sua empresa, você pode acionar chamadas CollectPII em resposta ao logon do usuário no aplicativo, ou comprar algo ou evento do ciclo de vida ou o usuário inserir uma geofence etc. Resumindo, uma interação do usuário com o aplicativo que gera informações que você deseja usar para o Perfil.

## Posso apenas disparar chamadas CollectPII em resposta a todos os eventos móveis? {#collect-pii-events}

A frequência e o design de chamadas CollectPII devem ser ditados pelas necessidades da empresa e não devem ser disparados às cegas, pois isso cria carga extra no BD.

### Quando tento acessar aplicativos Adobe Experience Platform no Campaign ou no Launch, às vezes recebo um erro de propriedade não disponível. {#aep-error}

Esse é um problema conhecido e ocorre devido à expiração do token. Você deve tentar fazer logout e login.

## Quais seriam algumas recomendações de recursos úteis para saber mais sobre a configuração da propriedade Mobile no Adobe Experience Platform Launch? {#resource-mobile-property}

Confira os recursos abaixo:

* Vídeo de [visão geral do Launch/Mobile](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* Guia de [dicas e truques para inicialização/dispositivos móveis](https://www.adobe.com/content/dam/www/us/en/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Quais seriam algumas recomendações de recursos úteis para saber mais sobre o Adobe Experience Platform SDK (anteriormente conhecido como SDK V5)?{#resource-aep}

Confira os recursos abaixo:

* Experience Platform SDK [documentação](https://aep-sdks.gitbook.io/docs/)
* Introdução à [documentação do Launch &amp; Experience Platform SDK](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* Atualização para a [documentação do SDK do Experience Platform](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* Documentação [do Github Experience Platform SDK](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)
