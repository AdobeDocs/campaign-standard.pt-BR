---
title: Visualização de mensagens
description: Saiba como visualizar uma mensagem no editor de conteúdo ou no Designer de email.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Seed Address
role: User
level: Intermediate
exl-id: ac8c1265-f530-4438-ab2d-3ca17615ca85
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 16%

---

# Pré-visualização de entregas {#previewing-messages}

## Pré-visualização de emails {#previewing-emails}

O Campaign Standard permite que você visualize as mensagens antes do envio, a fim de verificar a personalização e como os recipients as verão.

A pré-visualização de mensagens é executada usando **Perfis de teste** que você adiciona ao público-alvo da mensagem.

Para **email** O Campaign Standard permite pré-visualizar mensagens usando perfis direcionados em vez de perfis de teste. Isso permite obter uma representação exata da mensagem que um perfil específico receberá. Para mais informações, consulte [Testar mensagens de email usando perfis segmentados](../../sending/using/testing-messages-using-target.md).

Para visualizar uma mensagem usando perfis de teste, siga estas etapas:

1. No [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md), clique no link **[!UICONTROL Preview]** botão.

   ![](assets/sending_preview.png)

   Uma visualização da área de trabalho e uma visualização móvel responsiva do seu email são exibidas lado a lado.

1. Uma verificação automática de antispam é executada durante cada pré-visualização. Clique em **[!UICONTROL Anti-spam analysis]** botão para saber mais sobre o aviso.

   ![](assets/sending_anti-spam_analysis.png)

1. Selecione o **[!UICONTROL Change profile]** botão para escolher o perfil de teste no qual deseja testar os elementos de personalização.

   ![](assets/sending_test-profile.png)

1. Para sair do **[!UICONTROL Preview]** , clique no link **[!UICONTROL Edit]** no canto superior esquerdo da tela.

   ![](assets/sending_preview_edit.png)

**Tópicos relacionados**

* [Gerenciamento de perfis de teste](../../audiences/using/managing-test-profiles.md)
* [Teste de mensagens de email usando perfis direcionados](../../sending/using/testing-messages-using-target.md)
* [Envio de provas](../../sending/using/sending-proofs.md)

## Pré-visualização de mensagens SMS {#previewing-sms}

Para **SMS** O Campaign Standard permite pré-visualizar mensagens usando perfis de teste. Isso permite obter uma representação exata da mensagem que um perfil específico receberá. Para mais informações, consulte [Gerenciamento de perfis de teste](../../audiences/using/managing-test-profiles.md).

Para visualizar uma mensagem SMS usando perfis de teste, siga estas etapas:

1. Depois de preencher o **[!UICONTROL Properties]** da mensagem SMS e dos públicos selecionados, você pode personalizar o delivery. Para obter mais informações, consulte [seção](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_preview.png)

1. Após personalizar o conteúdo, clique em **[!UICONTROL Create]** para acessar o **[!UICONTROL Summary]** janela.

1. No **[!UICONTROL Summary]** clique em **[!UICONTROL Content]** para começar a pré-visualização do delivery.

   ![](assets/sms_preview_2.png)

1. Clique em **[!UICONTROL Preview]** na barra de ferramentas.

   ![](assets/sms_preview_3.png)

1. Clique em **[!UICONTROL Change profile]** para selecionar o perfil de teste, então **[!UICONTROL Confirm]**.

   ![](assets/sms_preview_4.png)

Agora é possível ver a representação exata da mensagem, dependendo dos perfis de teste selecionados.

**Tópicos relacionados**

* [Sobre mensagens SMS](../../channels/using/about-sms-messages.md)
* [Criação de uma mensagem SMS](../../channels/using/creating-an-sms-message.md)
* [Personalização de mensagens SMS](../../channels/using/personalizing-sms-messages.md)

## Visualização de notificações por push {#previewing-push}

Para **Notificação por push**, Campaign Standard permite visualizar mensagens usando perfis de teste. Isso permite obter uma representação exata da mensagem que um perfil específico receberá. Para mais informações, consulte [Gerenciamento de perfis de teste](../../audiences/using/managing-test-profiles.md).

Para visualizar uma notificação por push usando perfis de teste, siga estas etapas:

1. Depois de preencher o **[!UICONTROL Properties]** da sua notificação por push e dos públicos selecionados, você pode personalizar o delivery. Para obter mais informações, consulte [Personalização de uma notificação por push](../../channels/using/customizing-a-push-notification.md).

1. Depois de personalizar o conteúdo, você pode verificar diretamente a renderização das notificações por push, dependendo dos dispositivos e do SO na janela de pré-visualização.

   ![](assets/push_preview.png)

1. Para visualizar sua notificação por push usando perfis de teste, clique em **[!UICONTROL Preview with test profile]**.

   ![](assets/push_preview_2.png)

1. Selecione o perfil de teste e **[!UICONTROL Confirm]**.

Agora é possível ver a representação exata da mensagem, dependendo dos perfis de teste selecionados.

![](assets/push_preview_3.png)

**Tópicos relacionados**

* [Sobre notificações por push](../../channels/using/about-push-notifications.md)
* [Preparação e envio de uma notificação por push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Personalização de uma notificação por push](../../channels/using/customizing-a-push-notification.md)

## Visualização de mensagens no aplicativo {#previewing-in-app}

Para **No aplicativo**, Campaign Standard permite visualizar mensagens usando perfis de teste. Isso permite obter uma representação exata da mensagem que um perfil específico receberá. Para mais informações, consulte [Gerenciamento de perfis de teste](../../audiences/using/managing-test-profiles.md).

Para visualizar uma mensagem no aplicativo usando perfis de teste, siga estas etapas:

1. Depois de preencher o **[!UICONTROL Properties]** da mensagem no aplicativo, selecionou os públicos e definiu as **[!UICONTROL Triggers]**, você pode personalizar o delivery. Para obter mais informações, consulte [Personalização de mensagem no aplicativo](../../channels/using/customizing-an-in-app-message.md).

1. Depois de personalizar o conteúdo, você pode verificar diretamente a renderização da mensagem no aplicativo, dependendo dos dispositivos e do sistema operacional na janela de pré-visualização.

   ![](assets/in_app_preview.png)

1. Para visualizar sua mensagem no aplicativo usando perfis de teste, clique em **[!UICONTROL Preview]**.

   ![](assets/in_app_preview_2.png)

1. Selecione o perfil de teste e **[!UICONTROL Confirm]**.

Agora é possível ver a representação exata da mensagem, dependendo dos perfis de teste selecionados.

![](assets/in_app_preview_3.png)

**Tópicos relacionados**

* [Sobre mensagens no aplicativo](../../channels/using/about-in-app-messaging.md)
* [Preparação e envio de uma mensagem no aplicativo](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [Personalização de mensagem no aplicativo](../../channels/using/customizing-an-in-app-message.md)
