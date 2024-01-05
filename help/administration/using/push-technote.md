---
title: Próximas alterações no Canal de notificação por push
description: Próximas alterações no Canal de notificação por push
audience: channels
feature: Push
role: Admin
level: Experienced
exl-id: e273b443-7c43-482b-8f86-60ada4b57cbf
source-git-commit: ac4a52263482557a6d5c370af6df5d54a42671b4
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 10%

---

# Próximas alterações no Canal de notificação por push {#push-upgrade}

Você pode usar o Campaign para enviar notificações por push em dispositivos Android e iOS. Para fazer isso, o Campaign depende de serviços de assinatura específicos. Algumas alterações importantes no serviço Android Firebase Cloud Messaging (FCM) serão lançadas com a versão 24.1 2024 do Winter e afetarão sua implementação do Adobe Campaign. Além disso, para aplicativos iOS, o Adobe está alterando a maneira de permitir que os administradores configurem certificados.

## O que mudou? {#push-changes}

### Android {#push-android}

Como parte do esforço contínuo do Google para melhorar seus serviços, as APIs herdadas do FCM serão descontinuadas em **20 de junho de 2024**. Saiba mais sobre o protocolo HTTP do Firebase Cloud Messaging em [Documentação do Google Firebase](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

Atualmente, a Adobe Campaign Standard está usando APIs HTTP herdadas para enviar mensagens de notificação por push do Android e fará alterações nos próximos meses para atualizar para as APIs HTTP v1.

### iOS {#push-ios}

O Adobe também atualizará o Adobe Campaign Standard para o Canal de notificação por push da iOS e alterará a maneira como permitimos que os administradores configurem certificados para seus aplicativos da iOS. A partir da versão 24.2 2024 do Winter, os administradores precisarão fazer upload dos certificados do iOS por meio da interface do usuário do Adobe Campaign Standard, em suas propriedades do aplicativo móvel.

## Você será afetado? {#push-impact}

Como usuário do Campaign Standard, se você estiver enviando mensagens de notificação por push para seus públicos-alvo, você será afetado.

## Como migrar? {#push-migration}

Essas atualizações exigem uma atualização da build Campaign Standard para a versão 24.1 2024 Winter, pois afetam a configuração do canal móvel e o gerenciamento de permissões.

Instruções detalhadas serão fornecidas em breve para facilitar um processo de transição suave.

Nossa equipe de suporte ao cliente estará disponível para ajudá-lo durante essa transição. Também podemos realizar webinários e sessões de capacitação para abordar os aspectos técnicos e as práticas recomendadas para a transição.

Enquanto isso, recomenda-se reservar esse tempo para revisar sua configuração e personalização atuais no Adobe Campaign Standard, de modo que você esteja preparado para fazer as alterações necessárias, se necessário.

Se você tiver dúvidas ou preocupações imediatas, entre em contato com nossa equipe de suporte.
