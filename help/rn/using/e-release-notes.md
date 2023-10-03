---
title: Notas de versão anteriores
description: Notas de versão anteriores
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 46c5454ad712910c88bfda7c067fda0337b043d9
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 22%

---


# Notas de versão anteriores {#e-new-release}

Esta página descreve as melhorias e correções incluídas na próxima versão do Campaign Standard.

>[!CAUTION]
>
> Esse conteúdo está sujeito a alterações sem aviso prévio até a data de atualização dos ambientes de estágio. Saiba mais na [página de planejamento de versão](../../rn/using/release-planning.md).

## Versão 23.2 - Versão de outono/inverno de 2023 {#fall-23}

>[!AVAILABILITY]
>
>Esta versão está disponível somente para algumas organizações (disponibilidade limitada). Para obter mais informações, entre em contato com o representante da Adobe.

### Aprimoramentos {#e-rn-improvements}

* **Integração com o Adobe Experience Manager**. Ao criar um template de delivery personalizado para mensagens transacionais no Adobe Experience Manager, agora é possível selecionar e usar os campos de personalização definidos em Campaign Standard em uma lista suspensa.

* **Expiração de cookie** - As expirações padrão do cookie agora estão definidas como 6 meses, para se alinhar às recomendações da Agência de Proteção de Dados (CNIL) da França.

* **Aprimoramento da pesquisa de perfil** - A pesquisa de perfil foi otimizada para que os cenários de tempo limite de pesquisa possam ser reduzidos

* **Localização** - As traduções do termo &quot;público-alvo&quot; ao se referirem a um grupo de perfis direcionados para receber uma mensagem foram harmonizadas em todos os produtos da Digital Experience para os seguintes idiomas:

   * Alemão: Zielgruppe
   * Português (Brasil): público-alvo
   * Espanhol: público-destino

  Essas alterações serão implementadas gradualmente com as próximas versões da interface do usuário e da documentação.

### Outras alterações {#e-rn-other-changes}

* As mensagens transacionais agora são compatíveis com o uso de várias afinidades separadas por vírgulas.

### Correções {#e-rn-fixes}

* Correção de uma regressão que poderia causar problemas de desempenho ao usar workflows grandes. (CAMP-53369)
* Correção de um problema que impedia que o link do email em um alerta ou notificação do workflow funcionasse. (CAMP-51874)
