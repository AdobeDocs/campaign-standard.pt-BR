---
title: Versão mais recente
description: Esta página detalha o conteúdo da versão mais recente do Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: a8013bac719a45442e09d710db12df0abe721cc4
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 38%

---


# Versão mais recente{#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->

## Versão 24.1 – Versão do inverno de 2024 {#winter-24}

### Aprimoramentos {#e-rn-improvements}

* **Notificações por push do Android** - O Adobe Campaign Standard 24.1 usa as APIs HTTP v1 para enviar mensagens de notificação por push do Android, a fim de garantir a compatibilidade com as alterações futuras do FCM. Saiba mais nesta [nota técnica](../../administration/using/push-technote.md).

* **Notificações por push do iOS** - O Adobe Campaign Standard 24.1 agora é compatível com certificados de autenticação p8 para notificações por push do iOS. Sua implementação deve ser adaptada para ativar essas alterações. Saiba mais nesta [nota técnica](../../administration/using/push-technote.md).

* **Lista De Um Clique - Cancelar Inscrição** - A partir de 1 de junho de 2024, o Google e o Yahoo! exigirão que os remetentes cumpram o Cancelamento de inscrição na lista com um clique. O Campaign agora oferece suporte a esse recurso nativamente Saiba mais [nesta seção](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters).

* **Infraestrutura** - O banco de dados Postgres foi atualizado da versão 11.22 para a versão 12.17.

* **Rastreamento de CTA** - Quando os usuários abrem e clicam em um URL personalizado, o URL personalizado resolvido agora é rastreado em vez do URL personalizado codificado. Essa alteração não está habilitada por padrão. Para ativá-lo na instância do Campaign, entre em contato com o representante da Adobe.

* **Lista suspensa Campos de personalização** - Ao criar modelos de mensagem de email transacional no Adobe Experience Manager, agora é possível selecionar campos de personalização em uma lista suspensa. Essa alteração não está habilitada por padrão. Para ativá-lo na instância do Campaign, entre em contato com o representante da Adobe.

### Correções {#e-rn-fixes}

* Correção de um problema que impedia que os endereços de email rejeitados fossem removidos da quarentena após 30 dias. (CAMP-52977)
* Correção de um problema que interrompia o fluxo de trabalho de Alertas de entrega com o seguinte erro: `division by zero`. (CAMP-49786)

