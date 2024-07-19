---
title: Notas de versão mais recentes
description: Esta página detalha o conteúdo da versão mais recente do Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 44c436a74a0a4aa688427bfb36d506566d57ac3a
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 100%

---


# Notas de versão mais recentes {#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->


## Notas de versão antecipadas {#e-new-release}

Esta seção lista as melhorias e alterações incluídas na próxima versão do Campaign Standard.

>[!CAUTION]
>
>Esse conteúdo está sujeito a alterações sem aviso prévio até a data de atualização dos ambientes de preparo. Saiba mais na [página de planejamento de versão](../../rn/using/release-planning.md).

**Versão 24.2 – Versão do verão de 2024**

* **Data de lançamento**: agosto de 2024 (disponibilidade limitada) – [Saiba mais](../../rn/using/release-planning.md).

* **Migração para as credenciais OAuth de servidor para servidor**

  A partir desta versão, com a credencial de conta de serviço (JWT) sendo descontinuada pela Adobe, as integrações de saída do Campaign com soluções e aplicativos Adobe agora dependem da credencial de servidor para servidor do OAuth. A Adobe executará a migração de JWT para OAuth em suas integrações de saída, como a integração do Campaign-Analytics ou a integração dos Acionadores da Experience Cloud.

  Se você implementou integrações de entrada com o Campaign e está usando [APIs do Campaign](../../api/using/get-started-apis.md), é necessário migrar sua conta técnica conforme detalhado [nesta documentação](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. As credenciais da Conta de serviço (JWT) deixarão de funcionar em **27 de janeiro de 2025**.


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

