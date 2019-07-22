---
title: Conceitos do modelo de dados
seo-title: Conceitos do modelo de dados
description: Conceitos do modelo de dados
seo-description: Saiba mais sobre o modelo de dados do Adobe Campaign e como modificá-lo.
page-status-flag: nunca ativado
uuid: cacd 563 f -6936-4 b 3 e -83 e 3-5 d 4 ae 31 d 44 e 8
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 4 e 0468 da -3052-4 ce 5-8174-45 aba 1 f 5 c 4 ed
context-tags: Cusresource, overview; Eventcusresource, visão geral
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4d95fe00c1958399ff4d22d5f0e7762f895b4032

---


# Data model concepts{#data-model-concepts}

O Adobe Campaign vem com um modelo de dados predefinido. This data model can be modified by [administrators](../../administration/using/users-management.md#functional-administrators) who are able to add new resources or extensions to existing resources.

>[!CAUTION]
>
>A criação e modificação de recursos são operações sigilosas que devem ser executadas apenas por usuários de especialistas.

The **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** menu, accessed via the Adobe Campaign logo, allows you to manage your **custom resources**, **publish** them, and **access the diagnostic tools**.

Os dados usados pelo Adobe Campaign são definidos por meio de recursos diferentes.

You can **enrich the data template** that is provided by creating your own custom resources, such as purchase or product tables.

Recursos prontos para uso (como campanhas, emails ou públicos-alvo) não podem ser modificados. No entanto, os recursos personalizados podem ser estendidos para adicionar novos campos.

>[!NOTE]
>
>You can find a datamodel representation for the out-of-the-box resources [here](https://docs.campaign.adobe.com/doc/standard/en/datamodel/datamodel.html).

You can also **configure the navigation** in the screens corresponding to the resource created.

Os campos de extensão são gerados com um prefixo para que nunca entrem em conflito com os campos prontos para uso.
