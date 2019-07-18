---
title: Uso de dados de fluxo de trabalho
seo-title: Uso de dados de fluxo de trabalho
description: Uso de dados de fluxo de trabalho
seo-description: Saiba mais sobre as diferentes possibilidades de consumir os dados importados ou direcionados.
page-status-flag: nunca ativado
uuid: 3 dd 66 aeb -3 a 26-4214-b 6 a 0-242 c 2 b 7 fbc 49
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: fluxo de trabalho-geral-operação
discoiquuid: 90 b 250 f 1-f 32 d -4256-83 ea -4 c 0627628610
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Using workflow data{#using-workflow-data}

Depois que os dados forem identificados e preparados, eles poderão ser usados nos seguintes contextos:

* The **[!UICONTROL Update data]** activity allows you to perform a mass update on fields in the database.
* The **[!UICONTROL Save audience]** activity allows you to update an existing audience or create a new audience from the population computed upstream in a workflow. The audiences created or updated from this activity are **List** or **File** audiences. Essa atividade também permite exportar perfis como públicos-alvo/segmentos da Adobe Experience Cloud.
* The **[!UICONTROL Subscription Services]** activity allows you to take profiles in mass and subscribe them to a service or unsubscribe them from a service.
* The **[!UICONTROL Extract file]** activity allows you to export data from Adobe Campaign in the form of an external file.

Após definir uma meta de perfil, você pode usar várias atividades para criar e enviar entregas:

* The **[!UICONTROL Email delivery]** activity allows you to configure sending an email in a workflow. This can be a **single send** email and sent just once, or it can be a **recurring** email.
* The **[!UICONTROL SMS delivery]** activity allows you to configure sending an SMS in a workflow. This can be a **single send** SMS and sent just once, or it can be a **recurring** SMS.
* The **[!UICONTROL Mobile app delivery]** activity allows you to configure sending a push notification in a workflow. This can be a **single send** notification and sent just once, or it can be a **recurring** notification.

