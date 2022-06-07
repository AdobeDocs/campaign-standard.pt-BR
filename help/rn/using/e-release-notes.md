---
title: Notas de versão anteriores
description: Notas de versão anteriores
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: b00a0b9e4536d388ccfef3cca0315cabd0d99670
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 30%

---

# Notas de versão anteriores {#new-release}

Esta página descreve novos recursos, melhorias e correções incluídos na próxima versão do Campaign Standard.

>[!CAUTION]
>
> Esse conteúdo está sujeito a alterações sem aviso prévio até a data de atualização dos ambientes de estágio. Saiba mais na [página de planejamento de versão](../../rn/using/release-planning.md).

## Versão 22.2 — junho de 2022 {#rn-2022}

**Aprimoramentos**

* **Serviço de notificação da Adobe** - o Campaign vem com o Serviço de notificação da Adobe, que permite que as soluções da Experience Cloud alertem os usuários sobre atividades que são importantes para eles. A experiência do usuário foi aprimorada a partir da versão 22.2: as notificações foram priorizadas e as notificações geradas por produtos foram separadas dos avisos de status da Adobe. Além disso, quando a notificação se refere a um fluxo de trabalho específico, agora é possível acessar o fluxo de trabalho correspondente diretamente do email ou da notificação no produto.  Para obter mais informações sobre notificações do Adobe Campaign, consulte [Notificações do Adobe Campaign](../../administration/using/sending-internal-notifications.md).

* **Otimização na inicialização do fluxo de trabalho** - o Adobe adicionou um novo recurso que pode ajustar o número de fluxos de trabalho que começam ao mesmo tempo. Isso ajudaria a evitar picos da CPU que poderiam levar a interrupções do serviço ou tempo de inatividade. O Adobe o ativaria após a versão 2.2. Não há mais nenhum item de ação no cliente em relação ao mesmo.

* **Acessibilidade** - O Adobe fez muitas correções de acessibilidade para melhorar a facilidade geral de uso do aplicativo. Esses recursos estão ativados no momento apenas para um conjunto de participantes iniciais e serão implantados em todos os clientes na versão ACS 2.3. Exemplos de melhorias de acessibilidade incluem:

   * Garantia de que haja um indicador de foco visível para elementos focalizáveis em cada tela
   * Criação de marcos de página para navegação mais fácil
   * Adicionar o nome, a função, o valor e o estado para muitos controles
   * Correção de problemas encontrados com a ordem de foco dinâmico nas telas principais

**Atualização de segurança**

* O Apache Tomcat foi atualizado da versão 7 para a versão 8.5.

**Correções**

* Correção de um problema no workflow técnico Faturamento devido a um erro de chave duplicada. (CAMP-51029)
* Adição da categoria ausente do navegador Microsoft Edge em Relatórios de rastreamento. Eles foram categorizados anteriormente com aberturas do Microsoft Chrome. (CAMP-51165)
* Correção de um problema com solicitações do GDPR que não excluíam dados de tabelas secundárias. (CAMP-48276)
* Correção de um problema no Designer de email que fazia com que a condição de visibilidade de um fragmento não fosse salva em um modelo de mensagem transacional. (CAMP-50338)
* Correção de um problema nos Relatórios de campanha que fazia com que o intervalo de datas não fosse considerado. (CAMP-50991)
* Correção de um erro que causava a falha de emails agendados: a análise de delivery não pôde ser iniciada, pois o delivery ainda estava no status &quot;Retry pending&quot;. (CAMP-50302)
* Correção de um problema no Designer de email ao visualizar um email com uma substituição de perfil. (CAMP-49312)
* Correção de um problema com valor vazio em enumerações personalizadas: ao criar um recurso personalizado com um campo que é uma enumeração de texto e contém apenas um valor, esse valor é definido agora por padrão, para que você possa criar uma consulta nesse campo como uma solicitação simples. (CAMP-50606)
