---
title: Perguntas frequentes no aplicativo
description: Perguntas frequentes sobre mensagens no aplicativo
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: In App
role: User
exl-id: 0101773d-b109-49a3-89d4-b4bb226d9ebd
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 0%

---

# Perguntas frequentes no aplicativo {#in-app-faq}

## Quais seriam algumas recomendações de recursos úteis para saber mais sobre o canal no aplicativo no Adobe Campaign Standard? {#resources-inapp}

Confira os recursos abaixo:

* [Tutorials de vídeo](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/in-app/in-app-message-overview.html)
* [Publicação do blog](https://theblog.adobe.com/get-more-out-of-the-new-in-app-message-channel-from-adobe-campaign/)
* [Página da comunidade](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

## Qual é a finalidade das APIs de extensões do Campaign setLinkageField e resetLinkageField? {#extensions-apis}

Como as mensagens no aplicativo são extraídas pelo SDK do Campaign, queremos fornecer um mecanismo seguro para garantir que as mensagens no aplicativo que contêm dados PII não caiam em mãos mal-intencionadas. Dessa forma, temos o seguinte mecanismo em vigor para garantir a entrega segura de mensagens para o dispositivo:

* Os clientes marcam os campos de perfil móvel (tabela appSubscriberRcp) como Pessoal e confidencial se quiserem garantir que essas informações específicas sejam entregues com segurança.
* Os campos marcados como tal só podem ser usados no modelo de Perfil (não no modelo appSubscriber ou no modelo de Difusão) que tem um mecanismo de segurança adicional integrado.
* As mensagens criadas usando o modelo de Perfil só podem ser enviadas quando o usuário estiver conectado ao aplicativo.
* Para facilitar esse handshake seguro, os desenvolvedores de aplicativos móveis devem passar detalhes de autenticação adicionais usando a API setLinkageField. Observe que os campos de vinculação são aqueles identificados como o link entre o Perfil móvel e o Perfil de CRM ao estender a tabela appSubscriberRcp.
* Eles devem liberar as mensagens no aplicativo armazenadas no dispositivo e redefinirLinkagefields quando o usuário faz logoff do aplicativo usando redefinirLinkageField. Isso garante que, se um usuário diferente fizer logon no aplicativo, ele não verá as mensagens destinadas ao usuário anterior.
* Consulte [APIs do SDK móvel](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/) para implementar esse mecanismo de segurança no lado do cliente.

## O que preciso fazer para habilitar os Relatórios no aplicativo no Campaign? {#enable-inapp-reporting}

Você precisa configurar o postback de rastreamento no aplicativo. As instruções podem ser encontradas [aqui](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback).

Para implementar o rastreamento de notificação local, consulte este [página](../../administration/using/local-tracking.md).

## Quais relatórios estão disponíveis para o canal no aplicativo? {#report-inapp}

Um relatório pronto para uso está disponível no Adobe Campaign para o canal no aplicativo. Consulte esta [documentação](../../reporting/using/in-app-report.md).

Veja isto [página](../../reporting/using/indicator-calculation.md#in-app-delivery) para entender como cada métrica no aplicativo é calculada.

## Você é compatível com variantes de conteúdo multilíngue no aplicativo, semelhantes ao Push? {#multilingual-inapp}

Não há modelos em vários idiomas disponíveis para Mensagens no aplicativo agora.

No entanto, se o objetivo for enviar uma mensagem no aplicativo em um idioma diferente do inglês, o conteúdo poderá ser colado diretamente nas caixas de texto disponíveis.

![](assets/faq_inapp.png)

## Os campos de personalização do Campaign podem ser adicionados ao HTML personalizado? {#custom-html-inapp}

Não, isso ainda não é suportado.

## Eu configurei uma mensagem de alerta, mas ela não é exibida no dispositivo. {#alert-message}

Para mensagens de alerta, é necessário pelo menos um botão para ignorar (principal ou secundário deve ter uma ação para ignorar). Caso contrário, é possível salvar a mensagem, mas ela não será recebida.

## Se Local notifications iOS custom sound does not play; will the default sound play? (O som personalizado do não é reproduzido. O som padrão será reproduzido?) {#local-notification-sound}

Para som personalizado no iOS, você precisa fornecer um nome de arquivo com extensão ao criar uma notificação local (por exemplo, sound.caf). Se essa extensão não for fornecida, o som padrão será usado.

## Os deeplinks são compatíveis com mensagens no aplicativo? {#inapp-deeplinks}

Sim, os deeplinks são compatíveis com mensagens no aplicativo. Os deeplinks devem incluir:

* linguagem que declara que o rastreamento de delivery precisa ser desativado para que os deeplinks funcionem.
* AppScript com Ramificação como parceiros que podem fazer o rastreamento de deep link. Para obter mais informações sobre a integração de Branch e Adobe Campaign Standard, consulte este [página](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).

## Uma mensagem no aplicativo pode ser acionada quando o usuário inicia o aplicativo a partir de uma notificação por push? {#inapp-push-trigger}

Sim, essas mensagens também são chamadas de mensagens em daisy chain. Siga o processo abaixo:

1. Criar uma mensagem no aplicativo.

1. Defina um evento personalizado e selecione-o como um acionador de evento para este IAM, por exemplo, &quot;Acionar a partir da visualização de outono - push&quot;.

1. Ao criar sua mensagem de push, defina uma variável personalizada cujo valor possa ser definido como um evento usado para acionar o IAM, por exemplo, Chave = &quot;inappkey&quot; e valor = &quot;Acionador da pré-visualização de outono Push&quot;.

1. No código do aplicativo móvel, implemente o acionador de evento da seguinte maneira:

   ![](assets/faq_inapp_2.png)
