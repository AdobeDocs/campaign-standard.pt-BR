---
solution: Campaign Standard
product: campaign
title: Problema de assinatura de URLs rastreados
description: Problema de assinatura de URLs rastreados
hidefromtoc: true
hide: true
source-git-commit: 65c81f2f9e4fc80e7b2f7c0bdc0302e90f068b1e
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 100%

---


# Problema de assinatura de URLs rastreados {#tracked-urls}

Após alterações recentes, os URLs rastreados enviados pelo Campaign podem falhar. Algumas caixas de correio podem ser mais afetadas do que outras, já que algumas empresas têm ferramentas de segurança específicas que podem afetar links e alterar o mecanismo de assinatura do URL.

Como consequência, a Adobe decidiu desativar o mecanismo de assinatura para links de rastreamento. Esse procedimento corrige todos os links de rastreamento.

Observe que os links de unsubscription podem falhar como qualquer outro link, a frequência é variável de host para host, mas é inferior a 1%.

**Você será afetado?**

Alguns usuários do Campaign Standard são afetados, pois o mecanismo de assinatura para rastrear links em emails foi introduzido no [Campaign Standard 20.4](release-notes-2020.md#release-20-4---october-2020) — outubro de 2020 — e é ativado por padrão para todos os clientes.

**Como atualizar?**

A Adobe estará trabalhando com você para atualizar sua configuração em breve. Você receberá uma notificação por email com a linha do tempo da atualização.

**Qual é o impacto?**

A manutenção requer no máximo 25 minutos de inatividade, e durante esse período todos os deliveries, links de rastreamento e chamadas de API não funcionarão.

Quando a atualização estiver concluída, todos os links funcionarão conforme esperado.

>[!NOTE]
>
>Em caso de dúvidas sobre essas alterações, entre em contato com o [Atendimento ao cliente da Adobe](https://helpx.adobe.com/br/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).

