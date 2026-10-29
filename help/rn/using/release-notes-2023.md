---
title: Notas de versão de 2023
description: Essa página lista todas as versões de 2023 do Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: 5817c4d2-4788-4695-bf9a-ec04cc042190
TQID: 'https://experienceleague.adobe.com/YpZ3cQVh6CeVyCkOChGYLBUo1dMueoWh1AkFj3ycRwk'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e8d937ec-9046-41b5-834b-d22a624e0d37
    internal-label: Campaign overview
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
    internal-label: Accessibility
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: ht
source-wordcount: '463'
ht-degree: 100%
---
# Notas de versão de 2023 {#release-notes-2023}

## Versão 23.2 - Versão de outono/inverno de 2023 {#fall-23}

>[!AVAILABILITY]
>
>Esta versão está disponível somente para algumas organizações (disponibilidade limitada). Para mais informações, entre em contato com o seu representante da Adobe.

### Aprimoramentos {#fall-23-rn-improvements}

* **Integração com o Adobe Experience Manager**. Ao criar um modelo de entrega personalizado para mensagens transacionais no Adobe Experience Manager, agora é possível selecionar e usar os campos de personalização definidos no Campaign Standard em um menu suspenso. [Saiba mais](../../integrating/using/creating-email-experience-manager.md)

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

* Correção de uma regressão que poderia causar problemas de desempenho ao usar fluxos de trabalho grandes. (CAMP-53369)
* Correção de um problema que impedia que o link nos alertas ou notificações por email do fluxo de trabalho funcionasse. (CAMP-51874)

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

* Correção de um problema que poderia resultar em um erro de tempo-limite ao exibir o relatório **Hot click**. (CAMP-51582)
* Correção de um problema que poderia impedir o uso da integração com o serviço **Places**. (CAMP-51923)
* Correção de um problema que poderia impedir o funcionamento adequado do Scheduler de fluxos de trabalho. (CAMP-52003)
* Correção de um problema que impedia a exibição do detalhamento ao visualizar a versão PDF de um relatório dinâmico personalizado com um grande volume de dados. (CAMP-52178)
* Correção de um problema que poderia exibir um erro ao acessar relatórios. (CAMP-52500)
* Correção de um problema que aplicava incorretamente o parâmetro do conector SMS **Limitar instâncias de MTA desta conta** para todos os canais em vez de aplicar somente ao de SMS. (CAMP-52640)
