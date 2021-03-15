---
solution: Campaign Standard
product: campaign
title: União em dois públicos-alvo refinados
description: Este caso de uso mostra a união de duas atividades Read audience .
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Fluxos de trabalho
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 57%

---


# União em dois públicos-alvo refinados {#example--union-on-two-refined-audiences}

O fluxo de trabalho definido neste exemplo mostra a união de duas atividades **[!UICONTROL Read audience]**. O objetivo desse fluxo de trabalho é enviar um email para os membros Gold ou Silver entre 18 e 30 anos. Já foram criados públicos-alvo específicos no sistema para rastrear esses membros.

O fluxo de trabalho de reconciliação foi criado deste modo:

![](assets/readaudience_activity_example1.png)

* Uma primeira atividade [Read audience](../../automating/using/read-audience.md) que recupera o público-alvo dos membros Gold e o refina selecionando apenas os perfis entre 18 e 30 anos.
* Uma primeira atividade **[!UICONTROL Read audience]** que recupera o público-alvo dos membros Silver e o refina selecionando apenas os perfis entre 18 e 30 anos.
* Uma atividade [Union](../../automating/using/union.md) que une as populações das duas atividades **[!UICONTROL Read audiences]** em uma população final.
* Uma atividade [Email delivery](../../automating/using/email-delivery.md) que envia o email para a população proveniente da atividade **[!UICONTROL Union]**.
