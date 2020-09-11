---
title: Introdução à integração com o Microsoft Dynamics 365
description: Saiba mais sobre como começar a integração com o Microsoft Dynamics 365
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3590fd42e4692df6bba21ac721568ae60dfcdd65
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 3%

---


# Introdução à integração com o Microsoft Dynamics 365

Ative seus dados do CRM na comunicação entre canais: saiba como repassar contatos do Microsoft Dynamics 365 para a Adobe Campaign e compartilhar dados de desempenho da campanha (envios, aberturas, cliques e rejeições) da Adobe Campaign para o Microsoft Dynamics 365.

As versões suportadas estão listadas [nesta seção](#support-software-versions).

>[!CAUTION]
>
>Esse recurso não está disponível para uso imediato como parte do produto. A implementação exige que a Adobe Consulting esteja envolvida. Entre em contato com seu representante de Adobe para saber mais.

## Princípios

A integração do Adobe Campaign e do Microsoft Dynamics 365 permite a sincronização de todos os dados de contato disponíveis no sistema CRM, disponibilizando todos os dados de contato relevantes para o campanha atividade.

Por outro lado, à medida que os perfis no Adobe Campaign interagem com mensagens, esses dados (por exemplo: envia, abre, clica e salta) automaticamente para o Microsoft Dynamics 365 para manter os registros de contato concluídos com a atividade de marketing também.

A integração também oferece suporte a entidades personalizadas, permitindo que as entidades [](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md) personalizadas no Dynamics 365 sejam sincronizadas com as entidades personalizadas correspondentes na Campanha.

Essa integração foi projetada para suportar quatro casos principais de uso:

1. Sincronizar contatos do Dynamics 365 para a Campaign para que possam ser direcionados para o Marketing campanha
1. Sincronizar entidades personalizadas do Dynamics 365 para a Campanha para que possam ser usadas para segmentação e personalização
1. Envio de eventos de marketing por email (envia, abre, clica, salta) da Campanha para o Dynamics 365 para exibição no repositório de vendas na interface do Dynamics 365
1. Sincronizar status de não participação (por exemplo, não enviar emails) entre o Dynamics 365 e o ACS para manter as preferências de privacidade do cliente.

## Principais benefícios

* Mensagens consistentes entre vendas e marketing

A integração entre o Adobe Campaign e o Microsoft Dynamics 365 dá aos dois sistemas acesso ao conhecimento do cliente e ao histórico de marketing de e-mail, permitindo que todas as mensagens do cliente compartilhem as mesmas mensagens consistentes.

* Visualização holística de todos os dados do prospecto e do cliente

Ao integrar o Adobe Campaign ao Dynamics 365, é possível compartilhar e acessar históricos de marketing de e-mail em cada contato a partir do sistema do CRM.

* Ativar dados do Dynamics 365 em qualquer canal

Com os dados de contato sincronizados com a Adobe Campaign, as comunicações podem ser enviadas em qualquer canal online ou offline com Campanha, incluindo push móvel, no aplicativo, email ou mala direta. Independentemente do canal preferencial de cada contato, a Campanha foi abordada.

>[!CAUTION]
>
>Para a sincronização de contatos e entidades personalizadas, essa integração considera o Dynamics 365 como a fonte da verdade.  Quaisquer alterações nos atributos sincronizados devem ser feitas no Dynamics 365, não na Campanha.  Se as alterações forem feitas na Campanha, elas poderão eventualmente ser substituídas durante a sincronização.

## Versões de software de suporte {#support-software-versions}

Essa integração exige as seguintes versões de software:

* Microsoft Dynamics 365 para Vendas Online apenas, versão mais recente

* Adobe Campaign Standard, versão mais recente
