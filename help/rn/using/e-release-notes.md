---
title: Notas de versão anteriores
description: Notas de versão anteriores
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 66aed3668dc0eb2041312dcbaebe7c36f54b13a5
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 100%

---

# Notas de versão anteriores {#new-release}

Esta página descreve novos recursos, melhorias e correções incluídos na próxima versão do Campaign Standard.

>[!CAUTION]
>
> Esse conteúdo está sujeito a alterações sem aviso prévio até a data de atualização dos ambientes de estágio. Saiba mais na [página de planejamento de versão](../../rn/using/release-planning.md).

## Versão 22.2 - junho de 2022 {#rn-2022}

**Aprimoramentos**

* **Serviço de notificação da Adobe** - o Campaign vem com o Serviço de notificação da Adobe, que permite que as soluções da Experience Cloud alertem os usuários sobre atividades que são importantes para eles. A experiência do usuário foi aprimorada a partir da versão 22.2: as notificações foram priorizadas e as notificações geradas por produtos foram separadas dos avisos de status da Adobe. Além disso, quando a notificação se refere a um fluxo de trabalho específico, agora é possível acessar o fluxo de trabalho correspondente diretamente do email ou da notificação no produto.  Para obter mais informações sobre notificações do Adobe Campaign, consulte [Notificações do Adobe Campaign](../../administration/using/sending-internal-notifications.md).

* **Otimização na inicialização do fluxo de trabalho** - A Adobe adicionou um novo recurso que pode ajustar o número de workflows que começam ao mesmo tempo. Isso ajudaria a evitar picos da CPU que poderiam levar a interrupções do serviço ou tempo de inatividade. A Adobe o ativaria após a versão 22.2. Não há mais nenhum item de ação no cliente em relação a isso.

* **Acessibilidade** - a Adobe fez muitas correções de acessibilidade para melhorar a facilidade geral de uso do aplicativo. No momento, esses recursos estão habilitados apenas para alguns participantes iniciais e serão implantados para todos os clientes na versão 22.3 do ACS. Exemplos de melhorias de acessibilidade:

   * Garantia de que haja um indicador de foco visível para elementos focalizáveis em cada tela
   * Criação de pontos de referência de página para facilitar a navegação
   * Adição de nome, função, valor e estado para diversos controles
   * Correção de problemas relacionados à ordem de foco dinâmico nas telas principais


**Correções**

* Correção de um problema no fluxo de trabalho técnico de faturamento devido a um erro de chave duplicada. (CAMP-51029)
* Adição da categoria ausente do navegador Microsoft Edge em Relatórios de rastreamento. Eles eram categorizados anteriormente como aberturas do Microsoft e Chrome. (CAMP-51165)
* Correção de um problema com solicitações do GDPR que não excluíam dados de tabelas secundárias. (CAMP-48276)
* Correção de um problema no Designer de email que fazia com que a condição de visibilidade de um fragmento não fosse salva em um template de mensagem transacional. (CAMP-50338)
* Correção de um problema nos Relatórios de campanha que fazia com que o intervalo de datas não fosse considerado. (CAMP-50991)
* Correção de um erro que causava a falha de emails agendados: a análise de entrega não podia ser iniciada, pois a entrega ainda estava no status “Nova tentativa pendente”. (CAMP-50302)
* Correção de um problema no Designer de email ao visualizar um email com uma substituição de perfil. (CAMP-49312)
* Correção de um problema com listas discriminadas personalizadas de valor vazio: ao criar um recurso personalizado com um campo que é uma lista discriminada de texto e contém apenas um valor, esse valor agora é definido por padrão, para que você possa criar uma consulta nesse campo como uma solicitação simples. (CAMP-50606)
