---
title: Notas de versão de 2024
description: Essa página lista todas as versões de 2024 do Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: 26616ecc-a009-485c-b13d-d4e0c23969f2
TQID: https://experienceleague.adobe.com/L1RnV5WNdVWVn8oRUtFp4BDW-GzuP6xWZXpFYgupbQs
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2id: d5ef99fa-df0c-4153-bf94-105ad0724167
subfeature_v2: id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0id: cbcf4d90-26be-46e2-b16a-aebc529dc41e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 516
ht-degree: 94%

---

# Notas de versão de 2024 {#release-notes-2024}


## Versão 24.2 – Versão do verão de 2024 (LA) {#summer-24}

### Melhoria {#summer-24-rn-improvements}

**Migração para as credenciais OAuth de servidor para servidor**

A partir desta versão, com a credencial de conta de serviço (JWT) sendo descontinuada pela Adobe, as integrações de saída do Campaign com soluções e aplicativos Adobe agora dependem da credencial de servidor para servidor do OAuth. A Adobe executará a migração de JWT para OAuth em suas integrações de saída, como a integração do Campaign-Analytics ou a integração dos Acionadores da Experience Cloud.

Se você implementou integrações de entrada com o Campaign e está usando [APIs do Campaign](../../api/using/get-started-apis.md), migre sua conta técnica conforme detalhada em [esta documentação](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. As credenciais da Conta de serviço (JWT) deixarão de funcionar em **27 de janeiro de 2025**.

### Correções {#summer-24-rn-fixes}

* Correção de um problema que fazia com que o scheduler de fluxos de trabalho iniciasse antes do horário agendado. (CAMP-55412)
* Correção de um problema que causava um erro ao duplicar campos personalizados em notificações por push transacionais. (CAMP-54459)
* Correção de problemas que afetavam a usabilidade do scheduler de hora e data para mensagens no aplicativo. (CAMP-54495)
* Correção de um problema que fazia com que o rastreamento não funcionasse ao utilizar o recurso de alias de rastreamento personalizado, e o link inteiro ser dinâmico. (CAMP-56044)
* Correção de um problema que fazia com que uma quantidade limitada de modelos fosse exibida ao usar a pesquisa para localizar modelos específicos. (CAMP-55273)
* Adição dos seguintes idiomas à lista suspensa de idiomas preferidos: en_kz (inglês – Cazaquistão) e en_ua (inglês – Ucrânia). (CAMP-55336)
* Correção de um problema que fazia com que os botões de ajuste de hora não funcionassem nas configurações do scheduler. (CAMP-53602)
* Correção de vários problemas da interface do usuário relacionados à barra de ajuste de hora nas configurações do scheduler. (CAMP-55291)


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
