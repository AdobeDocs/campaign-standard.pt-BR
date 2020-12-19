---
solution: Campaign Standard
product: campaign
title: União em dois públicos-alvo refinados
description: Este caso de uso mostra a união de duas atividades de audiência de leitura.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 58%

---


# União em dois públicos-alvo refinados {#example--union-on-two-refined-audiences}

O fluxo de trabalho definido neste exemplo mostra a união de duas atividades **[!UICONTROL Read audience]**. O objetivo desse fluxo de trabalho é enviar um email para os membros Gold ou Silver entre 18 e 30 anos. Já foram criados públicos-alvo específicos no sistema para rastrear esses membros.

O fluxo de trabalho de reconciliação foi criado deste modo:

![](assets/readaudience_activity_example1.png)

* Uma primeira atividade [Ler audiência](../../automating/using/read-audience.md) que recupera a audiência dos membros Gold e a refina selecionando apenas perfis com idade entre 18 e 30 anos.
* Uma primeira atividade **[!UICONTROL Read audience]** que recupera o público-alvo dos membros Silver e o refina selecionando apenas os perfis entre 18 e 30 anos.
* Uma atividade [União](../../automating/using/union.md) que une populações de ambas as atividades **[!UICONTROL Read audiences]** em uma população final.
* Uma atividade [delivery de email](../../automating/using/email-delivery.md) que envia o email para a população proveniente da atividade **[!UICONTROL Union]**.
