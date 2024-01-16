---
title: Versão mais recente
description: Esta página detalha o conteúdo da versão mais recente do Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: d6421cda301eed85fddf2df7b2d6fc2cf1db96b3
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 100%

---


# Versão mais recente{#latest-release}

![Painel de controle](assets/do-not-localize/cp-icon.png) **Nova versão do Painel de controle**. [Saiba mais](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=pt-BR){target="_blank"}.

## Versão 24.1 - Versão do 1º trimestre de 2024 {#winter-24}

### Aprimoramentos {#e-rn-improvements}

O Adobe Campaign Standard 24.1 usa as APIs HTTP v1 para enviar notificações por push no Android, a fim de garantir a compatibilidade com as alterações futuras do FCM. Saiba mais nesta [nota técnica](../../administration/using/push-technote.md).

O Adobe Campaign Standard 24.1 agora é compatível com certificados de autenticação p8 para notificações por push do iOS. Sua implementação deve ser adaptada para ativar essas alterações. Saiba mais nesta [nota técnica](../../administration/using/push-technote.md).


### Correções {#e-rn-fixes}

* Correção de um problema que impedia que os endereços de email rejeitados fossem removidos da quarentena após 30 dias. (CAMP-52977)
* Correção de um problema que interrompia o fluxo de trabalho de Alertas de entrega com o seguinte erro: `division by zero`. (CAMP-49786)

