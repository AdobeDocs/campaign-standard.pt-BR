---
solution: Campaign Standard
product: campaign
title: Perguntas frequentes no aplicativo
description: Perguntas frequentes sobre mensagens no aplicativo
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: No aplicativo
role: Business Practitioner
exl-id: 986646b1-42d5-4169-ac38-d8e612a9a6d3
source-git-commit: 8e418be1fa880a4c23cbe4aa4e1a72fc4112b16b
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 2%

---


# Perguntas frequentes no aplicativo {#in-app-faq}

## Quais seriam algumas recomendações de recursos úteis para saber mais sobre o canal no aplicativo no Adobe Campaign Standard? {#resources-inapp}

Confira os recursos abaixo:

* [Tutoriais em vídeo](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/in-app/in-app-message-overview.html)
* [Publicação no blog](https://theblog.adobe.com/get-more-out-of-the-new-in-app-message-channel-from-adobe-campaign/)
* [Página da comunidade](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

## Qual é a finalidade das APIs de extensões do Campaign setLinkageField e resetLinkageField? {#extensions-apis}

Como as mensagens no aplicativo são obtidas pelo SDK do Campaign, queremos fornecer um mecanismo seguro para garantir que as mensagens no aplicativo que contêm dados de PII não caiam em mãos mal-intencionadas. Assim, temos o seguinte mecanismo em vigor para garantir a entrega segura de mensagens no dispositivo:

* Os clientes marcam campos de perfil móvel (tabela appSubscriberRcp) como Pessoal e confidencial se quiserem garantir que essas informações específicas sejam entregues com segurança.
* Os campos marcados como tal só podem ser usados no modelo de Perfil (não no modelo appSubscriber ou Broadcast) que tem mecanismo de segurança adicional integrado.
* As mensagens criadas usando o modelo de Perfil só podem ser enviadas quando o usuário tiver feito logon no aplicativo.
* Para facilitar esse handshake seguro, os desenvolvedores de aplicativos móveis devem passar detalhes de autenticação adicionais usando a API setLinkageField . Observe que o campo de vinculação é aquele identificado como o link entre o Perfil móvel e o Perfil de CRM ao estender a tabela appSubscriberRcp.
* Eles devem liberar as mensagens no aplicativo armazenadas no dispositivo e os campos resetLinkagequando o usuário sair do aplicativo usando resetLinkageField. Isso garante que, se um usuário diferente fizer logon no aplicativo, ele não visualize as mensagens destinadas ao usuário anterior.
* Consulte [APIs do SDK móvel](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference) para implementar este mecanismo de segurança no lado do cliente.

## O que preciso fazer para ativar os Relatórios no aplicativo no Campaign? {#enable-inapp-reporting}

Você precisa configurar o postback de rastreamento no aplicativo. Instruções podem ser encontradas [aqui](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#InApptrackingpostback).

Para implementar o rastreamento de notificação local, consulte esta [página](../../administration/using/local-tracking.md).

## Quais relatórios estão disponíveis para o canal no aplicativo? {#report-inapp}

Um relatório pronto para uso está disponível no Adobe Campaign para canal no aplicativo. Consulte esta [documentação](../../reporting/using/in-app-report.md).

Consulte esta [página](../../reporting/using/indicator-calculation.md#in-app-delivery) para entender como cada métrica no aplicativo é calculada.

## Você suporta variantes de conteúdo multilíngue para no aplicativo semelhantes ao push? {#multilingual-inapp}

Não há modelos em vários idiomas disponíveis para mensagens no aplicativo agora.

No entanto, se o objetivo for enviar uma mensagem no aplicativo em um idioma diferente do inglês, o conteúdo poderá ser colado diretamente nas caixas de texto disponíveis.

![](assets/faq_inapp.png)

## Os campos de personalização do Campaign podem ser adicionados ao HTML personalizado? {#custom-html-inapp}

Não, isso ainda não é suportado.

## Configurar uma mensagem de alerta, mas ela não é exibida no dispositivo. {#alert-message}

Para mensagens de alerta, pelo menos um botão de descarte (principal ou secundário deve ter uma ação de descarte) é necessário. Caso contrário, é possível salvar a mensagem, mas ela não será recebida.

## Se o som personalizado iOS de notificações locais não for reproduzido; o som padrão será reproduzido? {#local-notification-sound}

Para som personalizado no iOS, é necessário fornecer um nome de arquivo com extensão ao criar uma notificação local (por exemplo, sound.caf). Se essa extensão não for fornecida, o som padrão será usado.

## Os deep links são suportados em mensagens no aplicativo? {#inapp-deeplinks}

Sim, os deep links são suportados nas mensagens no aplicativo. Os deep links devem incluir:

* idioma que declara que o rastreamento de delivery precisa ser desativado para que os deep links funcionem.
* Appsflyer com Ramificação como parceiros que podem fazer o rastreamento de deep link. Para obter mais informações sobre a integração do Branch e do Adobe Campaign Standard, consulte esta [página](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).

## Uma mensagem no aplicativo pode ser acionada quando o usuário inicia o aplicativo por meio de uma notificação por push? {#inapp-push-trigger}

Sim, essas mensagens também são chamadas de mensagens de dia. Siga o processo abaixo:

1. Criar uma mensagem no aplicativo.

1. Defina um evento personalizado e selecione-o como um acionador de evento para esse IAM, por exemplo &quot;Acionar a partir da visualização do outono&quot;.

1. Ao criar sua mensagem de push, defina uma variável personalizada cujo valor possa ser definido como um evento usado para acionar o IAM, por exemplo, Chave = &quot;inappkey&quot; e valor = &quot;Acionador da pré-visualização do outono&quot;.

1. No código do aplicativo móvel, implemente o acionador de evento da seguinte maneira:

   ![](assets/faq_inapp_2.png)
