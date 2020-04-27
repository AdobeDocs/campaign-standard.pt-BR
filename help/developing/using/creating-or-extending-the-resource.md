---
title: Criação ou extensão do recurso
description: Descubra como definir um recurso do zero.
page-status-flag: never-activated
uuid: 7c26b63d-9587-472b-804f-cde5c45dfb3c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 8dc45c37-6908-407e-8e41-4a4188cba2b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# Criação ou extensão do recurso{#creating-or-extending-the-resource}

Os administradores podem criar um novo recurso do zero ou criar uma extensão de um recurso existente se você precisar trabalhar em dados que não façam parte do modelo de dados incorporado.

Somente os seguintes recursos incorporados podem ser estendidos:

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

1. Em **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**, clique no **[!UICONTROL Create]** botão.
1. Escolha a ação que deseja executar:

   * **[!UICONTROL Create a new resource]**: Insira os campos **[!UICONTROL Label]** e **[!UICONTROL ID]** . O **[!UICONTROL ID]** campo é obrigatório. Se você deixar o campo Rótulo vazio, ele será automaticamente preenchido a partir da ID.

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >Use no máximo 30 caracteres.

   * **[!UICONTROL Extend an existing resource]**: Selecione o recurso que deseja estender.

      ![](assets/schema_extension_10.png)

1. Clique **[!UICONTROL Create]** para criar o recurso, que assumirá o **[!UICONTROL Draft]** status no caso de um novo recurso ou o **[!UICONTROL Editing]** status no caso de extensão.

O novo recurso é criado e agora pode ser configurado. Para obter mais informações sobre a configuração de recursos, consulte [Configuração da estrutura](../../developing/using/configuring-the-resource-s-data-structure.md)de dados do recurso.
