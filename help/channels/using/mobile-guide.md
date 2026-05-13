---
title: Guia do Campaign Standard Mobile
description: Saiba mais sobre as diretrizes gerais para entregas móveis no Adobe Campaign Standard, como configurar seus aplicativos móveis ou criar notificações por push e mensagens no aplicativo.
audience: channels
content-type: reference
topic-tags: mobile-guide
feature: Overview
role: User
level: Beginner
exl-id: d4e1b935-b21f-4a24-99ba-f455db0f7cfc
TQID: https://experienceleague.adobe.com/sBjTFd0Su7In8xai4J8cp5QAsAh6pOVOf4OVAijQmXo
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 799
ht-degree: 18%

---

# Introdução aos canais para dispositivos móveis {#mobile-guide}

<table style="table-layout:fixed">
<tr>
<td><img src="assets/do-not-localize/config_push.png" width="60px"><p>Saiba como configurar seu aplicativo móvel para notificações por push </br><a href="#configuration-push">Clique aqui</a></p></td>
<td><img src="assets/do-not-localize/config_inapp.png" width="60px"><p>Saiba como configurar seu aplicativo móvel para mensagens no aplicativo </br><a href="#configuring-mobile-app">Clique aqui</a></p></td>
</tr>
<tr>
<td><img src="assets/do-not-localize/push2.png" width="60px"><p>Saiba como criar notificações por push </br><a href="#create-push">Clique aqui</a></p></td>
<td><img src="assets/do-not-localize/inapp.png" width="60px"><p>Saiba como criar mensagens no aplicativo</br><a href="#create-inapp">Clique aqui</a></p></td></tr>
</table>

## Sobre a entrega móvel {#about-mobile}

O Adobe Campaign permite criar e enviar mensagens personalizadas em vários canais e medir sua eficácia por meio de relatórios dedicados.

Com o Adobe Campaign Standard, você pode enviar deliveries para dispositivos móveis por três canais diferentes:

* SMS, apresentado na seção Sobre mensagens SMS.
* Notificações por push, apresentadas na seção Sobre notificações por push.
* Mensagens no aplicativo, apresentadas na seção Sobre mensagens no aplicativo.

## Configurar o aplicativo móvel para notificações por push {#configuration-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Configurar um aplicativo para dispositivos móveis usando SDKs do Adobe Experience Platform</strong></p>
    </div>
    <p>Para enviar mensagens no aplicativo e notificações por push, seus aplicativos móveis precisam ser configurados no Adobe Campaign utilizando os SDKs da Adobe Experience Platform.</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>Clique aqui</strong></a> para obter mais informações.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Como entender a estrutura de payload das notificações de push do Campaign Standard</strong></p>
    </div>
    <p>Saiba mais sobre a estrutura da carga útil recebida em aplicativos móveis quando uma notificação por push é enviada com êxito para um aplicativo do Adobe Campaign Standard.</br><a href="../../administration/using/push-payload.md"><strong>Clique aqui</strong></a> para obter mais informações.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Implementação do rastreamento de notificação local</strong></p>
    </div>
    <p>Saiba aqui como garantir que o rastreamento de notificação local tenha sido implementado corretamente. </br><a href="../../administration/using/local-tracking.md"><strong>Clique aqui</strong></a> para obter mais informações.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Implementação do rastreamento de push</strong></p>
    </div>
    <p>Saiba como garantir que o rastreamento de notificação por push tenha sido implementado corretamente no iOS e no Android.</br><a href="../../administration/using/push-tracking.md"><strong>Clique aqui</strong></a> para obter mais informações.</p>
    <br>
  </td>
</tr>
</table>

## Configurar um aplicativo para dispositivos móveis para mensagens no aplicativo {#configuring-mobile-app}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Configurar um aplicativo para dispositivos móveis usando SDKs do Adobe Experience Platform</strong></p>
    </div>
    <p>Para enviar mensagens no aplicativo e notificações por push, seus aplicativos móveis precisam ser configurados no Adobe Campaign utilizando os SDKs da Adobe Experience Platform.</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>Clique aqui</strong></a> para obter mais informações.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Casos de uso de publicação de conteúdo para dispositivos móveis compatíveis com SDKs da Adobe Experience Platform</strong></p>
    </div>
    <p>Saiba mais sobre os casos de uso de publicação de conteúdo para dispositivos móveis compatíveis com o Adobe Campaign Standard usando os SDKs da Adobe Experience Platform.</br><a href="../../administration/using/supported-mobile-use-cases.md"><strong>Clique aqui</strong></a> para obter mais informações.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Configuração das regras de tag para oferecer suporte a casos de uso do Adobe Campaign Standard</strong></p>
    </div>
    <p><a href="../../administration/using/configuring-rules-launch.md"><strong>Clique aqui</strong></a> para começar a criar elementos de dados e regras na interface da Coleção de Dados para enviar PII e outros dados de aplicativos móveis para o Adobe Campaign Standard.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Implementação do rastreamento de notificação local</strong></p>
    </div>
    <p>Saiba aqui como garantir que o rastreamento de notificação local tenha sido implementado corretamente. </br><a href="../../administration/using/local-tracking.md"><strong>Clique aqui</strong></a> para obter mais informações.</p>
    <br>
  </td>
</tr>
</table>

## Criar uma notificação por push {#create-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Preparação e envio de uma notificação por push</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-a-push-notification.md"><strong>Saiba aqui</strong></a> como preparar sua notificação por push e como enviá-la para seu público-alvo direcionado.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Personalização de uma notificação por push</strong></p>
    </div>
    <p>Para ajustar o delivery, o Adobe Campaign permite acessar um conjunto de opções ao projetar uma notificação por push.</br><a href="../../channels/using/customizing-a-push-notification.md"><strong>Clique aqui</strong></a> para obter mais informações.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Criação de uma notificação por push multilíngue</strong></p>
    </div>
    <p>Personalize o conteúdo da notificação por push enviando mensagens com base nos idiomas e regiões de preferência dos usuários.</br><a href="../../channels/using/creating-a-multilingual-push-notification.md"><strong>Clique aqui</strong></a> para obter mais informações.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Exibir uma imagem a partir de uma notificação por push do Adobe Campaign Standard</strong></p>
    </div>
    <p><a href="../../administration/using/image-push-notification.md"><strong>Saiba aqui</strong></a> como exibir uma imagem de uma notificação por push do Adobe Campaign em um dispositivo iOS.</p>
    <br>
  </td>
</tr>
</table>

## Criar uma mensagem no aplicativo {#create-inapp}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Preparação e envio de uma mensagem no aplicativo</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-an-in-app-message.md"><strong>Saiba aqui</strong></a> como preparar suas mensagens no aplicativo e como enviá-las para o público-alvo direcionado.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Personalização de mensagens no aplicativo</strong></p>
    </div>
    <p>Para ajustar a entrega, o Adobe Campaign permite que você acesse um conjunto de opções avançadas ao criar uma mensagem no aplicativo.</br><a href="../../channels/using/customizing-an-in-app-message.md"><strong>Clique aqui</strong></a> para obter mais informações.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Personalização de tipos de mensagens de notificação local</strong></p>
    </div>
    <p>As notificações locais só podem ser acionadas por um aplicativo em um horário específico e dependendo de um evento. </br><a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type"><strong>Clique aqui</strong></a> para obter mais informações.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Relatório no aplicativo</strong></p>
    </div>
    <p>O relatório No aplicativo fornece detalhes relacionados às entregas no aplicativo.</br><a href="../../reporting/using/in-app-report.md"><strong>Clique aqui</strong></a> para obter mais informações.</p>
    <br>
  </td>
</tr>
</table>

## Criar mensagens SMS {#create-sms}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Criação de uma mensagem SMS</strong></p>
    </div>
    <p>A criação de uma entrega de SMS é muito semelhante à criação de um email comum. </br>As etapas <a href="../../channels/using/creating-an-sms-message.md"><strong>detalhadas aqui</strong></a> descrevem a configuração específica para este canal.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Personalização de uma mensagem SMS
</strong></p>
    </div>
    <p>Para ajustar o delivery, o Adobe Campaign permite acessar um conjunto de opções avançadas ao projetar uma mensagem SMS.</br><a href="../../channels/using/sms-and-push-content-editor-interface.md"><strong>Clique aqui para obter mais informações.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Gerenciamento de SMS de entrada</strong></p>
    </div>
    <p>Quando um perfil responde a uma mensagem SMS enviada pelo Campaign, você pode configurar mensagens que são automaticamente enviadas de volta, bem como a ação a ser executada.Personalizando um tipo de mensagem de notificação local</br><a href="../../channels/using/managing-incoming-sms.md"><strong>Clique aqui para obter mais informações.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Relatório de SMS</strong></p>
    </div>
    <p>O relatório de SMS fornece detalhes sobre deliveries de SMS, como taxas de delivery e rejeição.</br><a href="../../reporting/using/sms-report.md"><strong>Clique aqui</strong></a> para obter mais informações.</p>
    <br>
  </td>
</tr>
</table>

## Solução de problemas de dispositivos móveis {#mobile-troubleshooting}

As páginas a seguir ajudarão você a resolver os problemas mais comuns que ocorrem ao usar o delivery móvel no Adobe Campaign Standard.

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Perguntas frequentes sobre notificação por push</strong></p>
    </div>
    <p><a href="../../channels/using/about-push-notifications.md#push-faq"><strong>Clique aqui para obter mais informações.</p>
  </td>
  <td>
    <div>
    <p><strong>Perguntas frequentes sobre a sincronização do Adobe Launch</strong></p>
    </div>
    <p><a href="../../channels/using/in-app-faq.md"><strong>Clique aqui para obter mais informações.</p>
  </td>
  <td>
    <div>
    <p><strong>Perguntas frequentes no aplicativo</strong></p>
    </div>
    <p><a href="../../administration/using/syncwithlaunch-faq.md"><strong>Clique aqui para obter mais informações.</p>
  </td>
</tr>
</table>
