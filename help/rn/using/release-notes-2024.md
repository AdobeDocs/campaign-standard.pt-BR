---
title: Notas de versão de 2024
description: Essa página lista todas as versões de 2024 do Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
source-git-commit: c70e3058f75ba2b11a8311628198e5c02d489964
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 100%

---

# Notas de versão de 2024 {#release-notes-2024}

## Versão 24.1 – Versão do inverno de 2024 {#winter-24}

### Aprimoramentos {#e-rn-improvements}

* **Notificações por push no Android**: o Adobe Campaign Standard 24.1 usa as APIs HTTP v1 para enviar notificações por push no Android, a fim de garantir a compatibilidade com as alterações futuras do FCM. Saiba mais nesta [nota técnica](../../administration/using/push-technote.md).

* **Notificações por push no iOS**: o Adobe Campaign Standard 24.1 agora é compatível com certificados de autenticação p8 para notificações por push no iOS. Sua implementação deve ser adaptada para ativar essas alterações. Saiba mais nesta [nota técnica](../../administration/using/push-technote.md).

* **Cancelar inscrição com um clique**: a partir de 1º de junho de 2024, o Google e o Yahoo! exigirão que os remetentes cumpram o Cancelamento de inscrição na lista com um clique. O Campaign agora oferece suporte a esse recurso nativamente Saiba mais [nesta seção](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters).

* **Infraestrutura**: o banco de dados Postgres foi atualizado da versão 11.22 para a versão 12.17.

* **Rastreamento de CTA**: quando as pessoas abrem e clicam em um URL personalizado, o URL personalizado resolvido agora é rastreado em vez do URL personalizado codificado. Essa alteração não está habilitada por padrão. Para habilitá-la na instância do Campaign, entre em contato com o seu representante da Adobe.

* **Lista suspensa de campos de personalização**: ao criar modelos de mensagem de email transacional no Adobe Experience Manager, agora é possível selecionar campos de personalização em uma lista suspensa. Essa alteração não está habilitada por padrão. Para habilitá-la na instância do Campaign, entre em contato com o seu representante da Adobe.

### Correções {#e-rn-fixes}

* Correção de um problema que impedia que os endereços de email rejeitados fossem removidos da quarentena após 30 dias. (CAMP-52977)
* Correção de um problema que interrompia o fluxo de trabalho de Alertas de entrega com o seguinte erro: `division by zero`. (CAMP-49786)

