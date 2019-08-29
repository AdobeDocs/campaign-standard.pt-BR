---
title: Como criar ou estender o recurso
seo-title: Como criar ou estender o recurso
description: Como criar ou estender o recurso
seo-description: Descobrir como definir um recurso do zero.
page-status-flag: nunca ativado
uuid: 7 c 26 b 63 d -9587-472 b -804 f-cde 5 c 45 dfb 3 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adição ou extensão-a-resource
discoiquuid: 8 dc 45 c 37-6908-407 e -8 e 41-4 a 4188 cba 2 b 3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 50620788c05b76cc2f69c19c26f968ca15a02048

---


# Como criar ou estender o recurso{#creating-or-extending-the-resource}

Os administradores podem criar um novo recurso do zero ou criar uma extensão de um recurso existente se você precisar trabalhar em dados que não façam parte do modelo de dados out-of-box.

Apenas os seguintes recursos prontos para uso podem ser estendidos:

* **[!UICONTROL Campaign (campaign)]**
* **[!UICONTROL Deliveries (delivery)]**
* **[!UICONTROL Landing page (Landingpage)]**
* **[!UICONTROL Profiles (profile)]**
* **[!UICONTROL Program (program)]**
* **[!UICONTROL Service (service)]**
* **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**
* **[!UICONTROL Test profiles (seedMember)]**
* **[!UICONTROL Workflow (workflow)]**

Para criar ou estender um recurso:

1. Em **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom Resources]**, clique no **[!UICONTROL Create]** botão.
1. Escolha a ação que deseja executar:

   * **[!UICONTROL Create a new resource]**: Insira os campos **[!UICONTROL Label]** e **[!UICONTROL ID]** os campos. **[!UICONTROL ID]** O campo é obrigatório. Se você deixar o campo Rótulo vazio, ele será preenchido automaticamente da ID.

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >Recomendamos usar o máximo de 30 caracteres.

   * **[!UICONTROL Extend an existing resource]**: Selecione o recurso que deseja estender.

      ![](assets/schema_extension_10.png)

1. Clique **[!UICONTROL Create]** em para criar o recurso, que assume o **[!UICONTROL Draft]** status em caso de novo recurso ou o **[!UICONTROL Editing]** status no caso da extensão.

O novo recurso é criado e agora pode ser configurado. Para obter mais informações sobre a configuração de recursos, consulte [Configuração da estrutura de dados do recurso](../../developing/using/configuring-the-resource-s-data-structure.md).
