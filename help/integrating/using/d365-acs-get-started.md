---
title: Introdução à integração com o Microsoft Dynamics 365
description: Saiba como começar a usar a integração com o Microsoft Dynamics 365
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Integração do Microsoft CRM
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 5%

---


# Introdução à integração com o Microsoft Dynamics 365

Ative seus dados do CRM na comunicação entre canais: saiba como transmitir contatos do Microsoft Dynamics 365 para o Adobe Campaign e compartilhar dados de desempenho da campanha (envios, aberturas, cliques e devoluções) de volta do Adobe Campaign para o Microsoft Dynamics 365.

Essa integração exige as seguintes versões de software:

* Microsoft Dynamics 365 for Sales Online apenas, versão mais recente

* Adobe Campaign Standard, versão mais recente

>[!CAUTION]
>
>Esse recurso não está disponível para uso imediato como parte do produto. A implementação exige o engajamento da Adobe Consulting. Entre em contato com seu representante da Adobe para obter mais detalhes.


## Princípios

A integração do Adobe Campaign Standard com o Microsoft Dynamics 365 permite a sincronização de todos os dados de contato disponíveis no sistema CRM, disponibilizando todos os dados de contato relevantes para atividades de campanha.

Por outro lado, à medida que os perfis no Adobe Campaign Standard interagem com as mensagens, esses dados (por exemplo: envia, abre, clica e rejeita automaticamente o Microsoft Dynamics 365 para manter os registros de contato concluídos com a atividade de marketing também.

A integração também oferece suporte para habilitar [entidades personalizadas](../../integrating/using/d365-acs-self-service-app-settings.md) no Dynamics 365 para serem sincronizadas com os **recursos personalizados** correspondentes no Campaign.

Essa integração foi projetada para suportar quatro casos de uso principais:

1. Sincronizar contatos do Dynamics 365 para o Campaign para que possam ser direcionados em campanhas de marketing
1. Sincronização de entidades personalizadas do Dynamics 365 para o Campaign para que possam ser usadas para segmentação e personalização
1. Enviar eventos de marketing por email (envia, abre, clica, rejeições) do Campaign para o Dynamics 365 para exibir no repositório de vendas na interface do Dynamics 365
1. Sincronizar status de recusa (por exemplo, não enviar por email) entre o Dynamics 365 e o Campaign para manter as preferências de privacidade do cliente.

Os principais benefícios são:

* Mensagens consistentes entre vendas e marketing: a integração do Adobe Campaign Standard com o Dynamics 365 fornece aos dois sistemas acesso ao insight do cliente e ao histórico de marketing por email, permitindo que todas as mensagens do cliente compartilhem as mesmas mensagens consistentes.

* Visualização holística de todos os dados de cliente e prospecto: ao integrar o Adobe Campaign Standard ao Dynamics 365, é possível compartilhar e acessar o histórico de marketing por email em cada contato a partir do sistema CRM.

* Ative os dados do Dynamics 365 em qualquer canal: com dados de contato sincronizados com o Adobe Campaign, as comunicações podem ser enviadas em qualquer canal online ou offline com o Campaign, incluindo push móvel, no aplicativo, email ou mala direta. A campanha &quot;cobriu&quot; independentemente do canal preferencial de cada contato.

>[!CAUTION]
>
>Essa integração considera o Dynamics 365 como a fonte de verdade para a sincronização de contatos e entidades personalizadas.  Quaisquer alterações nos atributos sincronizados devem ser feitas no Dynamics 365, não no Adobe Campaign Standard.  Se as alterações forem feitas no Campaign, elas poderão ser substituídas durante a sincronização.


## Etapas principais para implementar a integração do Microsoft Dynamics 365{#request-and-implement-this-integration}

Para provisionar essa integração, você precisará seguir as etapas abaixo.

Siga os detalhes do fluxograma e do fluxograma abaixo para solicitar e configurar a integração.

![](assets/provisioning-wf.png)

Detalhes do Fluxograma (mapeia para as etapas acima):

* **Etapa 1**  - Pressupõe-se que você já tenha ou esteja em processo de adquirir uma licença do Microsoft Dynamics 365 para Vendas e para Adobe Campaign Standard.
* **Etapa 2**  - A oferta de integração padrão é gratuita para todos os clientes; no entanto, podem ser aplicados custos adicionais dependendo de suas necessidades. Saiba mais sobre [Práticas recomendadas e limitações](../../integrating/using/d365-acs-notices-and-recommendations.md). Será necessário assinar uma nova ordem de venda (SO) para tirar partido da integração se não tiver sido incluída na comunicação de objeções original.
* **Etapa 3**  - Conclua as etapas de pré-integração do Dynamics 365 e Campaign. Consulte [Configurar esta integração](#configure-this-integration).
* **Etapa 4**  - A equipe de integração do Adobe fornecerá acesso à interface do usuário do aplicativo de integração (UI).
* **Etapa 5**  - Você poderá configurar os mapeamentos de dados, substituições, filtros, etc. e teste sua integração na interface do usuário do aplicativo de integração.

   >[!IMPORTANT]
   >
   > Se você precisar da configuração de recusa bidirecional ou do Campaign para o Dynamics 365, será necessário fazer a solicitação para o contato técnico do Adobe para que os workflows de recusa sejam configurados na instância do Campaign. [Saiba mais](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

### Configurar essa integração {#configure-this-integration}

Três sistemas precisam ser provisionados e configurados para essa integração:

* **Adobe Campaign Standard**: é necessário configurar o acesso à API e configurar uma nova integração para a ferramenta de integração. Para fazer isso, consulte [este artigo](../../integrating/using/d365-acs-configure-adobe-io.md).
* **Microsoft Dynamics 365**: é necessário criar um novo registro de aplicativo e permitir que um usuário do aplicativo use a integração .  Para configurar o Microsoft Dynamics 365 para essa integração, consulte [este artigo](../../integrating/using/d365-acs-configure-d365.md).
* **Integração do Adobe Campaign Standard com o aplicativo** de autoatendimento do Microsoft Dynamics 365: você precisará seguir as etapas  [neste artigo](../../integrating/using/d365-acs-self-service-app-control-access.md).

>[!IMPORTANT]
>
>Para cada sistema, essas etapas precisam ser executadas por um **administrador**.
>
>As etapas nesta documentação guiarão você pela criação de integrações/registros que envolvam a atribuição de permissões e/ou acesso administrativo.  É sua responsabilidade garantir que essas etapas estejam em conformidade com as políticas de sua empresa antes de serem executadas e executá-las com cuidado.


### Solicitar suporte

Ingressos de suporte podem ser registrados no Atendimento ao cliente do Adobe.

Para qualquer problema com fluxos de dados de integração, inclua as seguintes informações:

* **Proprietário** do processo: Arquitetos de engenharia
* **ID** do processo ES: Fornecido durante o processo de integração
* **Título** do processo: Integração do Microsoft Dynamics 365 / Adobe Campaign Standard
* **Descrição** do problema: Descrição do problema

A cobertura de suporte de integração é atualmente 24x5 (disponível de segunda a sexta-feira, exceto feriados Adobe e períodos de pausa).
