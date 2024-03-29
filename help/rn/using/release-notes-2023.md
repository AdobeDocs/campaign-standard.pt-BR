---
title: Notas de versão de 2023
description: Essa página lista todas as versões de 2023 do Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: 5817c4d2-4788-4695-bf9a-ec04cc042190
source-git-commit: 30e96494dd7fa3313601e48deeec8ef98dcdce85
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 100%

---

# Notas de versão de 2023 {#release-notes-2023}

## Versão 23.2 - Versão de outono/inverno de 2023 {#fall-23}

>[!AVAILABILITY]
>
>Esta versão está disponível somente para algumas organizações (disponibilidade limitada). Para mais informações, entre em contato com o seu representante da Adobe.

### Aprimoramentos {#fall-23-rn-improvements}

* **Integração com o Adobe Experience Manager**. Ao criar um template de entrega personalizado para mensagens transacionais no Adobe Experience Manager, agora é possível selecionar e usar os campos de personalização definidos no Campaign Standard em um menu suspenso. [Saiba mais](../../integrating/using/creating-email-experience-manager.md)

* **Expiração de cookies**: a expiração padrão de cookies agora é definida como seis meses, de acordo com as recomendações da Agência de Proteção de Dados (CNIL) da França.

* **Aprimoramento da pesquisa de perfil**: a pesquisa de perfil foi otimizada para reduzir os casos de tempo-limite esgotado

* **Localização**: as traduções do termo &quot;público-alvo&quot;, em referência a um grupo de perfis direcionados para receber uma mensagem, foram harmonizadas em todos os produtos da Digital Experience nos seguintes idiomas:

   * Alemão: Zielgruppe
   * Português (Brasil): público-alvo
   * Espanhol: público destinatario

  Essas alterações serão implementadas gradualmente com as próximas versões da interface e da documentação.


### Outras alterações {#fall-23-rn-other-changes}

* As mensagens transacionais agora são compatíveis com o uso de várias afinidades separadas por vírgulas. [Saiba mais](../../sending/using/managing-typologies.md)

### Correções {#fall-23-rn-fixes}

* Correção de uma regressão que poderia causar problemas de desempenho ao usar workflows grandes. (CAMP-53369)
* Correção de um problema que impedia que o link nos alertas ou notificações por email do workflow funcionasse. (CAMP-51874)

## Versão 23.1 - Versão de primavera/verão de 2023 {#apr-23}

### Aprimoramentos {#e-rn-improvements}

* O serviço de mensagens por push foi modernizado para melhorar o suporte. (CAMP-47959)
* O serviço de mensagens SMS foi aprimorado para proporcionar mais estabilidade. (CAMP-52217)
* A Adobe fez várias correções de acessibilidade para melhorar a facilidade de uso geral do aplicativo. Estes são alguns exemplos de melhorias da acessibilidade:
   * A acessibilidade do teclado da interface foi otimizada em várias telas.
   * O aplicativo foi aprimorado para usuários de telas sensíveis ao toque.
   * A cor de vários itens da interface foi alterada para melhorar a visibilidade.

### Outras alterações {#e-rn-changes}

* O **fluxo de trabalho de criação do enriquecimento de relatórios** pronto para uso foi adicionado. Após importar um target mapping de uma instância para outra, basta executar o fluxo de trabalho para importar as entradas de enriquecimento de relatório correspondentes. (CAMP-52452)

### Problemas corrigidos{#e-rn-patches}

* Correção de um problema que poderia resultar em um erro de tempo limite ao exibir o relatório **Hot click**. (CAMP-51582)
* Correção de um problema que poderia impedir o uso da integração com o serviço **Places**. (CAMP-51923)
* Correção de um problema que poderia impedir o funcionamento adequado do Scheduler de fluxos de trabalho. (CAMP-52003)
* Correção de um problema que impedia a exibição do detalhamento ao visualizar a versão PDF de um relatório dinâmico personalizado com um grande volume de dados. (CAMP-52178)
* Correção de um problema que poderia exibir um erro ao acessar relatórios. (CAMP-52500)
* Correção de um problema que aplicava incorretamente o parâmetro do conector SMS **Limitar instâncias de MTA desta conta** para todos os canais em vez de aplicar somente ao de SMS. (CAMP-52640)
