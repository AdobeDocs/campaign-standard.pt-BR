---
title: União em dois públicos-alvos refinados
description: Este caso de uso mostra a união de duas atividades Ler público.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 6261f800-11bd-4b02-a587-49ddb0da240f
TQID: https://experienceleague.adobe.com/NZA7DqSxrgPvNPfo4dgWvyJaOp-2Ma07MZJuHff3sAA
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 156
ht-degree: 43%

---

# União em dois públicos-alvos refinados {#example--union-on-two-refined-audiences}

O fluxo de trabalho definido neste exemplo mostra a união de duas atividades **[!UICONTROL Read audience]**. O objetivo desse fluxo de trabalho é enviar um email para os membros Gold ou Silver entre 18 e 30 anos. Já foram criados públicos-alvo específicos no sistema para rastrear esses membros.

O fluxo de trabalho de reconciliação foi criado deste modo:

![](assets/readaudience_activity_example1.png)

* Uma primeira atividade [Read audience](../../automating/using/read-audience.md) que recupera o público-alvo dos membros Gold e o refina selecionando apenas os perfis entre 18 e 30 anos.
* Uma primeira atividade **[!UICONTROL Read audience]** que recupera o público-alvo dos membros Silver e o refina selecionando apenas os perfis entre 18 e 30 anos.
* Uma atividade [Union](../../automating/using/union.md) que une as populações das duas atividades **[!UICONTROL Read audiences]** em uma única população.
* Uma atividade de [Entrega de email](../../automating/using/email-delivery.md) que envia o email para a população da atividade **[!UICONTROL Union]**.
