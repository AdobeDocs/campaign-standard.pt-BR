---
title: Introdução à integração com o Microsoft Dynamics 365
description: Saiba como começar a integração com o Microsoft Dynamics 365
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: fa0f790d-6a4d-4b83-a51f-f565e9545a1a
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 4%

---

# Introdução à integração com o Microsoft Dynamics 365

Ativar os dados do CRM na comunicação entre canais: saiba como transmitir contatos do Microsoft Dynamics 365 para o Adobe Campaign e compartilhar dados de desempenho da campanha (envios, aberturas, cliques e rejeições) do Adobe Campaign para o Microsoft Dynamics 365.

Essa integração exige as seguintes versões de software:

* Microsoft Dynamics 365 apenas para vendas on-line, versão mais recente

* Adobe Campaign Standard, versão mais recente

>[!CAUTION]
>
>Esse recurso não está disponível para uso imediato como parte do produto. A implementação exige o engajamento da Adobe Consulting. Entre em contato com seu representante da Adobe para obter mais detalhes.
>

## Princípios

A integração do Adobe Campaign Standard com o Microsoft Dynamics 365 permite a sincronização de todos os dados de contato disponíveis no sistema CRM, disponibilizando todos os dados de contato relevantes para atividades de campanha.

Por outro lado, como os perfis no Adobe Campaign Standard interagem com mensagens, esses dados (por exemplo: envios, aberturas, cliques e rejeições) fluem automaticamente para o Microsoft Dynamics 365 para manter os registros de contato completos com a atividade de marketing também.

A integração também permite que [entidades personalizadas](../../integrating/using/d365-acs-self-service-app-settings.md) do Dynamics 365 sejam sincronizadas com os **recursos personalizados** correspondentes no Campaign.

Essa integração foi projetada para atender a quatro casos de uso principais:

1. Sincronização de contatos do Dynamics 365 com o Campaign para que possam ser direcionados em campanhas de marketing
1. Sincronização de entidades personalizadas do Dynamics 365 para o Campaign para que possam ser usadas para segmentação e personalização
1. Enviar eventos de marketing por email (envios, aberturas, cliques, rejeições) do Campaign para o Dynamics 365 para exibir ao repositório de vendas na interface do Dynamics 365
1. Sincronização de status de recusa (por exemplo, não enviar email) entre o Dynamics 365 e o Campaign para manter as preferências de privacidade do cliente.

Os principais benefícios são:

* Mensagens consistentes entre vendas e marketing: a integração do Adobe Campaign Standard com a integração do Dynamics 365 fornece aos dois sistemas acesso ao insight do cliente e ao histórico de marketing por email, permitindo que todas as mensagens para o cliente compartilhem a mesma mensagem consistente.

* Visualização integral de todos os dados de clientes potenciais e de clientes: ao integrar o Adobe Campaign Standard ao Dynamics 365, é possível compartilhar e acessar o histórico de marketing por email em cada contato no sistema de CRM.

* Ativar dados do Dynamics 365 em qualquer canal: com dados de contato sincronizados com o Adobe Campaign, as comunicações podem ser enviadas em qualquer canal online ou offline com o Campaign, incluindo push móvel, no aplicativo, email ou correspondência direta. A campanha &quot;você cobriu&quot; independentemente do canal preferido de cada contato.

>[!CAUTION]
>
>Essa integração considera o Dynamics 365 como a fonte da verdade para a sincronização de contatos e entidades personalizadas.  Quaisquer alterações nos atributos sincronizados devem ser feitas no Dynamics 365, não no Adobe Campaign Standard.  Se forem feitas alterações no Campaign, elas poderão ser substituídas durante a sincronização.
>

## Etapas principais para implementar a integração com o Microsoft Dynamics 365{#request-and-implement-this-integration}

Para provisionar essa integração, é necessário seguir as etapas abaixo.

Siga os detalhes do fluxograma e do fluxograma abaixo para solicitar e configurar a integração.

![](assets/provisioning-wf.png)

Detalhes do fluxograma (mapeia para as etapas acima):

* **Etapa 1** - Presume-se que você já tenha ou esteja em processo de aquisição de uma licença do Microsoft Dynamics 365 para Vendas e para Adobe Campaign Standard.
* **Etapa 2** - A oferta de integração padrão é gratuita para todos os clientes; no entanto, podem ser aplicados custos adicionais, dependendo de suas necessidades. Saiba mais sobre [Práticas recomendadas e limitações](../../integrating/using/d365-acs-notices-and-recommendations.md). Uma nova ordem de venda precisará ser assinada para aproveitar a integração se não tiver sido incluída na OC original.
* **Etapa 3** - Conclua as etapas de pré-integração do Dynamics 365 e do Campaign. Consulte [Configurar esta integração](#configure-this-integration).
* **Etapa 4** - A equipe de integração do Adobe fornecerá acesso à interface do usuário (UI) do aplicativo de integração.
* **Etapa 5** - Você poderá configurar mapeamentos de dados, substituições, filtros etc. e teste sua integração na interface do usuário do aplicativo de integração.

  >[!IMPORTANT]
  >
  > Se você precisar da configuração de recusa bidirecional ou do Campaign para o Dynamics 365, será necessário fazer a solicitação ao contato técnico da Adobe para que os workflows de recusa sejam configurados na instância do Campaign. [Saiba mais](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

### Configurar esta integração {#configure-this-integration}

Três sistemas precisam ser provisionados e configurados para essa integração:

* **Adobe Campaign Standard**: é necessário configurar o acesso à API e configurar uma nova integração para a ferramenta de integração. Para isso, consulte [este artigo](../../integrating/using/d365-acs-configure-adobe-io.md).
* **Microsoft Dynamics 365**: é necessário criar um novo registro de aplicativo e habilitar um usuário do aplicativo para usar a integração.  Para configurar o Microsoft Dynamics 365 para essa integração, consulte [este artigo](../../integrating/using/d365-acs-configure-d365.md).
* **Integração do Adobe Campaign Standard com o Aplicativo de Autoatendimento do Microsoft Dynamics 365**: você precisará seguir as etapas em [este artigo](../../integrating/using/d365-acs-self-service-app-control-access.md).

>[!IMPORTANT]
>
>Para cada sistema, essas etapas precisam ser executadas por um **administrador**.
>
>As etapas desta documentação guiarão você pela criação de integrações/registros que envolvem a atribuição de permissões e/ou acesso de administrador.  É sua responsabilidade garantir que essas etapas estejam em conformidade com as políticas de sua empresa antes de executar o, e executá-las com cuidado.
>

### Solicitar suporte

Os tíquetes de suporte podem ser registrados no Atendimento ao cliente da Adobe.

Para quaisquer problemas com fluxos de dados de integração, inclua as seguintes informações:

* **Proprietário do Processo**: Arquitetos de Engenharia
* **ES Process ID**: fornecido durante o processo de integração
* **Título do Processo**: Integração do Microsoft Dynamics 365/Adobe Campaign Standard
* **Descrição do problema**: Descrição do problema

Atualmente, a cobertura do suporte à integração é 24x5 (disponível de segunda a sexta-feira, exceto feriados e períodos de interrupção do Adobe).
