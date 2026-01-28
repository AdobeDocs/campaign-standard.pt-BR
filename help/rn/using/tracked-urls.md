---
title: Problema de assinatura de URLs rastreados
description: Problema de assinatura de URLs rastreados
hidefromtoc: true
hide: true
exl-id: 8c2725a8-2c3a-448a-8c04-c0c2a5950574
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: ht
source-wordcount: '196'
ht-degree: 100%

---

# Problema de assinatura de URLs rastreados {#tracked-urls}

Após alterações recentes, os URLs rastreados enviados pelo Campaign podem falhar. Algumas caixas de correio podem ser mais afetadas do que outras, já que algumas empresas têm ferramentas de segurança específicas que podem afetar links e alterar o mecanismo de assinatura do URL.

Como consequência, a Adobe decidiu desabilitar o mecanismo de assinatura para links de rastreamento. Esse procedimento corrige todos os links de rastreamento.

Observe que os links de unsubscription podem falhar como qualquer outro link, a frequência é variável de host para host, mas é inferior a 1%.

**Você será afetado?**

Alguns usuários do Campaign Standard são afetados, pois o mecanismo de assinatura para rastrear links em emails foi introduzido no [Campaign Standard 20.4](release-notes-2020.md#release-20-4---october-2020) — outubro de 2020 — e é habilitado por padrão para todos os clientes.

**Como atualizar?**

A Adobe estará trabalhando com você para atualizar sua configuração em breve. Você receberá uma notificação por email com a linha do tempo da atualização.

**Qual é o impacto?**

A manutenção requer no máximo 25 minutos de inatividade, e durante esse período todas as entregas, links de rastreamento e chamadas de API não funcionarão.

Quando a atualização estiver concluída, todos os links funcionarão conforme esperado.

>[!NOTE]
>
>Em caso de dúvidas sobre essas alterações, entre em contato com o [Atendimento ao cliente da Adobe](https://helpx.adobe.com/br/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).
>
