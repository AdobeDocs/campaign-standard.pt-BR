---
title: Introdução à integração do Microsoft Dynamics 365
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
source-git-commit: 21135f27fd1d8297edd3dd067446d09c39de9f4f
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---


# Introdução à integração do Microsoft Dynamics 365

>[!IMPORTANT]
>
>No momento, essa integração não está disponível. Um novo conector está sendo desenvolvido e estará disponível no futuro. Para obter mais informações, entre em contato com seu representante de vendas da Adobe.

Ative seus dados do CRM na comunicação entre canais: saiba como repassar contatos do Microsoft Dynamics 365 para o Adobe Campaign e compartilhar dados de desempenho da campanha (envios, aberturas, cliques e rejeições) de volta do Adobe Campaign para o Microsoft Dynamics 365.

>[!NOTE]
>
>A integração do Microsoft Dynamics 365 / Adobe Campaign Standard oferece suporte somente ao aplicativo **de vendas do** Microsoft Dynamics 365.

## Princípios

A integração do Adobe Campaign e do Microsoft Dynamics 365 permite a sincronização de todos os dados de contato disponíveis no sistema CRM, disponibilizando todos os dados de contato relevantes para o campanha atividade.

Por outro lado, à medida que os perfis interagem com as mensagens, esses dados (por exemplo: envia, abre, clica e salta) automaticamente para o Microsoft Dynamics 365 para manter registros de Contato concluídos com a atividade de marketing também.

A versão mais recente da integração também adiciona suporte para entidades personalizadas, permitindo que as entidades personalizadas no Dynamics 365 sejam sincronizadas com as entidades personalizadas correspondentes na Campanha.

Essa integração foi projetada para suportar três casos principais de uso:

1. Sincronizar contatos do Dynamics 365 para a Campaign para que possam ser direcionados para o campanha de marketing
1. Envio de eventos de marketing por email (envia, abre, clica, salta) da Campanha para o Dynamics 365 para exibição no repositório de vendas na interface do Dynamics 365
1. Sincronizar entidades personalizadas do Dynamics 365 para a Campanha para que possam ser usadas para segmentação e personalização

## Principais benefícios

* Mensagens consistentes entre vendas e marketing

A integração do Adobe Campaign e do Microsoft Dynamics 365 dá aos dois sistemas acesso ao conhecimento do cliente e ao histórico de marketing de e-mail, permitindo que todas as mensagens do cliente compartilhem as mesmas mensagens consistentes.

* visualização holística de todos os dados do prospecto e do cliente

Ao integrar o Adobe Campaign ao Dynamics 365, é possível compartilhar e acessar históricos de marketing de e-mail em cada Contato a partir do sistema do CRM.

* Ativar dados do Dynamics 365 em qualquer canal

Com dados de contato sincronizados com o Adobe Campaign, as comunicações podem ser enviadas em qualquer canal online ou offline com Campanha, incluindo push móvel, no aplicativo, email ou mala direta. Independentemente do canal preferencial de cada Contatos, a Campanha foi coberta por você.

>[!CAUTION]
>
>Para sincronização de Contatos, essa integração considera o Dynamics 365 como a fonte da verdade.  Quaisquer alterações nos atributos de contato sincronizados devem ser feitas no Dynamics 365, não na Campanha.  Se as alterações forem feitas na Campanha, elas poderão eventualmente ser substituídas durante a sincronização.
