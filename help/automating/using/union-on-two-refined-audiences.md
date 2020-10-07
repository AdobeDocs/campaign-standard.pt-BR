---
title: União em dois públicos-alvo refinados
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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 58%

---


# União em dois públicos-alvo refinados {#example--union-on-two-refined-audiences}

O fluxo de trabalho definido neste exemplo mostra a união de duas atividades **[!UICONTROL Read audience]**. O objetivo desse fluxo de trabalho é enviar um email para os membros Gold ou Silver entre 18 e 30 anos. Já foram criados públicos-alvo específicos no sistema para rastrear esses membros.

O fluxo de trabalho de reconciliação foi criado deste modo:

![](assets/readaudience_activity_example1.png)

* A first [Read audience](../../automating/using/read-audience.md) activity that retrieves the Gold members audience and refines it by selecting only profiles that are between 18 and 30 years old.
* Uma primeira atividade **[!UICONTROL Read audience]** que recupera o público-alvo dos membros Silver e o refina selecionando apenas os perfis entre 18 e 30 anos.
* A [Union](../../automating/using/union.md) activity that unites populations from both **[!UICONTROL Read audiences]** activities into one final population.
* An [Email delivery](../../automating/using/email-delivery.md) activity that sends the email to the population coming from the **[!UICONTROL Union]** activity.
