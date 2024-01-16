---
title: Notas de versão anteriores
description: Notas de versão anteriores
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: d6421cda301eed85fddf2df7b2d6fc2cf1db96b3
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 100%

---


# Notas de versão anteriores {#e-new-release}

Esta página descreve as melhorias e correções incluídas na próxima versão do Campaign Standard.

>[!CAUTION]
>
> Esse conteúdo está sujeito a alterações sem aviso prévio até a data de atualização dos ambientes de estágio. Saiba mais na [página de planejamento de versão](../../rn/using/release-planning.md).

## Versão 24.1 - Versão do 1º trimestre de 2024 {#winter-24}

### Aprimoramentos {#e-rn-improvements}

O Adobe Campaign Standard 24.1 usa as APIs HTTP v1 para enviar notificações por push no Android, a fim de garantir a compatibilidade com as alterações futuras do FCM. Saiba mais nesta [nota técnica](../../administration/using/push-technote.md).

O Adobe Campaign Standard 24.1 agora é compatível com certificados de autenticação p8 para notificações por push do iOS. Sua implementação deve ser adaptada para ativar essas alterações. Saiba mais nesta [nota técnica](../../administration/using/push-technote.md).


### Correções {#e-rn-fixes}

* Correção de um problema que impedia que os endereços de email rejeitados fossem removidos da quarentena após 30 dias. (CAMP-52977)
* Correção de um problema que interrompia o fluxo de trabalho de Alertas de entrega com o seguinte erro: `division by zero`. (CAMP-49786)
