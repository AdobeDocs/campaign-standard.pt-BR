---
title: Introdução à integração com o Microsoft Dynamics 365
description: Saiba mais sobre como começar a integração com o Microsoft Dynamics 365
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: fe5d40235abc33c0ea7e929cd2e69b7030cea0b1
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 5%

---


# Introdução à integração com o Microsoft Dynamics 365

Ative seus dados do CRM na comunicação entre canais: saiba como repassar contatos do Microsoft Dynamics 365 para a Adobe Campaign e compartilhar dados de desempenho da campanha (envios, aberturas, cliques e rejeições) da Adobe Campaign para o Microsoft Dynamics 365.

Essa integração exige as seguintes versões de software:

* Microsoft Dynamics 365 para Vendas Online apenas, versão mais recente

* Adobe Campaign Standard, versão mais recente

>[!CAUTION]
>
>Esse recurso não está disponível para uso imediato como parte do produto. A implementação exige o engajamento da Adobe Consulting. Entre em contato com seu representante da Adobe para obter mais detalhes.


## Princípios

A integração do Adobe Campaign Standard com o Microsoft Dynamics 365 permite a sincronização de todos os dados de contato disponíveis no sistema CRM, disponibilizando todos os dados de contato relevantes para o campanha atividade.

Por outro lado, à medida que os perfis no Adobe Campaign Standard interagem com mensagens, esses dados (por exemplo: envia, abre, clica e salta) automaticamente para o Microsoft Dynamics 365 para manter os registros de contato concluídos com a atividade de marketing também.

A integração também oferece suporte para permitir que [entidades personalizadas](../../integrating/using/d365-acs-self-service-app-settings.md) no Dynamics 365 sejam sincronizadas com os **recursos personalizados** correspondentes na Campanha.

Essa integração foi projetada para suportar quatro casos principais de uso:

1. Sincronizar contatos do Dynamics 365 para a Campaign para que possam ser direcionados para o Marketing campanha
1. Sincronizar entidades personalizadas do Dynamics 365 para a Campanha para que possam ser usadas para segmentação e personalização
1. Envio de eventos de marketing por email (envia, abre, clica, salta) da Campanha para o Dynamics 365 para exibição no repositório de vendas na interface do Dynamics 365
1. Sincronizar status de recusa (por exemplo, não enviar por email) entre o Dynamics 365 e a Campanha para manter as preferências de privacidade do cliente.

Os principais benefícios são:

* Mensagens consistentes entre vendas e marketing: a integração do Adobe Campaign Standard com a integração do Dynamics 365 dá aos dois sistemas acesso ao conhecimento do cliente e ao histórico de marketing de e-mail, permitindo que todas as mensagens do cliente compartilhem as mesmas mensagens consistentes.

* Visualização holística de todos os dados do prospecto e do cliente: ao integrar o Adobe Campaign Standard ao Dynamics 365, é possível compartilhar e acessar históricos de marketing de e-mail em cada contato a partir do sistema CRM.

* Ative os dados do Dynamics 365 em qualquer canal: com dados de contato sincronizados com a Adobe Campaign, as comunicações podem ser enviadas em qualquer canal online ou offline com Campanha, incluindo push móvel, no aplicativo, email ou mala direta. Campanha &quot;você cobriu&quot; independentemente do canal preferencial de cada contato.

>[!CAUTION]
>
>Essa integração considera o Dynamics 365 como a fonte da verdade para a sincronização de contatos e entidades personalizadas.  Quaisquer alterações nos atributos sincronizados devem ser feitas no Dynamics 365, não no Adobe Campaign Standard.  Se as alterações forem feitas na Campanha, elas poderão eventualmente ser substituídas durante a sincronização.


## Etapas principais para implementar a integração do Microsoft Dynamics 365{#request-and-implement-this-integration}

Para provisionar essa integração, é necessário seguir as etapas abaixo.

Siga os detalhes do fluxograma e do fluxograma abaixo para solicitar e configurar a integração.

![](assets/provisioning-wf.png)

Detalhes do fluxograma (mapeia para as etapas acima):

* **Etapa 1**  - Pressupõe-se que você já tenha ou esteja em processo de adquirir uma licença para o Microsoft Dynamics 365 para Vendas e para Adobe Campaign Standard.
* **Etapa 2**  - A oferta de integração padrão é gratuita para todos os clientes. no entanto, podem ser aplicados custos adicionais, dependendo de suas necessidades. Saiba mais sobre [Práticas recomendadas e limitações](../../integrating/using/d365-acs-notices-and-recommendations.md). Uma nova ordem de venda (SO) deverá ser assinada para aproveitar a integração se não tiver sido incluída na CO original.
* **Etapa 3**  - Complete as etapas de pré-integração para o Dynamics 365 e a Campanha. Consulte [Configurar esta integração](#configure-this-integration).
* **Etapa 4**  - A equipe de onboard do Adobe fornece acesso à interface do usuário do aplicativo de integração (UI).
* **Etapa 5**  - Você poderá configurar seus mapeamentos de dados, substituições, filtros etc. e teste sua integração na interface do usuário do aplicativo de integração.

   >[!IMPORTANT]
   >
   > Se você exigir a configuração bidirecional ou a Campanha para a opção de não participação do Dynamics 365, será necessário fazer a solicitação ao contato técnico do Adobe para que os workflows de não participação sejam configurados na instância da Campanha. [Saiba mais](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

### Configurar esta integração {#configure-this-integration}

Três sistemas precisam ser provisionados e configurados para essa integração:

* **Adobe Campaign Standard**: é necessário configurar o acesso à API e uma nova integração para a ferramenta de integração. Para conseguir isso, consulte [este artigo](../../integrating/using/d365-acs-configure-adobe-io.md).
* **Microsoft Dynamics 365**: é necessário criar um novo registro do aplicativo e permitir que o usuário do aplicativo use a integração.  Para configurar o Microsoft Dynamics 365 para essa integração, consulte [este artigo](../../integrating/using/d365-acs-configure-d365.md).
* **Integração do Adobe Campaign Standard com o aplicativo** Self-Service do Microsoft Dynamics 365: você precisará seguir as etapas  [deste artigo](../../integrating/using/d365-acs-self-service-app-control-access.md).

>[!IMPORTANT]
>
>Para cada sistema, essas etapas precisam ser executadas por um **administrador**.
>
>As etapas desta documentação o guiarão pela criação de integrações/registros que envolvam a atribuição de permissões e/ou acesso administrativo.  É sua responsabilidade garantir que essas etapas estejam em conformidade com suas políticas de empresa antes de serem executadas e executá-las cuidadosamente.


### Solicitar suporte

Os tíquetes de suporte podem ser registrados no Atendimento ao cliente do Adobe.

Para quaisquer problemas com fluxos de dados de integração, certifique-se de incluir o conjunto de relatórios como parte da descrição da edição, bem como as seguintes informações:

* **Proprietário** do processo: Arquitetos de engenharia
* **ID** do processo ES: Fornecido durante o processo de integração
* **Título** do processo: Integração Microsoft Dynamics 365 / Adobe Campaign Standard
* **Descrição** do problema: Descrição do problema

A cobertura de suporte de integração está disponível 24 horas por dia, 5 dias por semana (disponível de segunda a sexta-feira, exceto feriados de Adobe e períodos de pausa).
