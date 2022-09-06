---
title: Versão mais recente
description: Esta página detalha o conteúdo da versão mais recente do Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 163cd5bf2091a4655bf1bc2c733fdaa4757b3f36
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---


# Versão mais recente{#latest-release}

![Painel de controle do Campaign](assets/do-not-localize/cp-icon.png) **Nova versão do Painel de controle do Campaign**. [Saiba mais](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=pt-BR){target=&quot;_blank&quot;}.


## Versão 22.2 - junho de 2022 {#june-2022}

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

