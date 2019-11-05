---
title: Criação ou extensão do recurso
description: Descubra como definir um recurso do zero.
page-status-flag: nunca ativado
uuid: 7c26b63d-9587-472b-804f-cde5c45dfb3c
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: desenvolvimento
content-type: referência
topic-tags: adição ou extensão de um recurso
discoiquuid: 8dc45c37-6908-407e-8e41-4a4188cba2b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Criação ou extensão do recurso{#creating-or-extending-the-resource}

Os administradores podem criar um novo recurso do zero ou criar uma extensão de um recurso existente se você precisar trabalhar em dados que não façam parte do modelo de dados predefinido.

Somente os seguintes recursos prontos para uso podem ser estendidos:

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

   * **[!UICONTROL Create a new resource]**: Insira os campos **[!UICONTROL Label]** e **[!UICONTROL ID]** . O **[!UICONTROL ID]** campo é obrigatório. Se você deixar o campo Rótulo vazio, ele será automaticamente preenchido a partir da ID.

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >Recomendamos o uso do máximo de 30 caracteres.

   * **[!UICONTROL Extend an existing resource]**: Selecione o recurso que deseja estender.

      ![](assets/schema_extension_10.png)

1. Clique **[!UICONTROL Create]** para criar o recurso, que assumirá o **[!UICONTROL Draft]** status no caso de um novo recurso ou o **[!UICONTROL Editing]** status no caso de extensão.

O novo recurso é criado e agora pode ser configurado. Para obter mais informações sobre a configuração de recursos, consulte [Configuração da estrutura](../../developing/using/configuring-the-resource-s-data-structure.md)de dados do recurso.
