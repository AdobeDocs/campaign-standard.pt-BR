---
title: União em duas audiências refinadas
description: Este caso de uso mostra a união de duas atividades de audiência de leitura.
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 0%

---


# União em duas audiências refinadas {#example--union-on-two-refined-audiences}

O fluxo de trabalho definido neste exemplo mostra a união de duas **[!UICONTROL Read audience]** atividades. O objetivo deste fluxo de trabalho é enviar um email para membros Gold ou Silver com idade entre 18 e 30 anos. audiências específicas já foram criadas no sistema para rastrear os membros Gold e Silver.

O fluxo de trabalho é projetado da seguinte forma:

![](assets/readaudience_activity_example1.png)

* Uma primeira atividade de audiência [de](../../automating/using/read-audience.md) leitura que recupera a audiência dos membros Gold e a refina selecionando apenas perfis com idade entre 18 e 30 anos.
* Uma segunda **[!UICONTROL Read audience]** atividade que recupera a audiência dos membros da Prata e a refina selecionando apenas perfis com idade entre 18 e 30 anos.
* Uma atividade [União](../../automating/using/union.md) que une populações de ambas as **[!UICONTROL Read audiences]** atividades em uma população final.
* Uma atividade de delivery [de email que envia o email para a população proveniente da](../../automating/using/email-delivery.md) **[!UICONTROL Union]** atividade.
