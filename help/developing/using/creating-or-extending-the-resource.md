---
title: Criação ou extensão do recurso
description: Descubra como definir um recurso do zero.
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Data Model
role: Developer
level: Experienced
exl-id: b8731088-a675-4070-9036-bf2b5254e4e8
TQID: 'https://experienceleague.adobe.com/hdn9Hj-zHdqoD2fKbv5Rl-GcV5EpH-L8p95e7W0ouzA'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: a1681cd8-6b2e-4955-9113-33b5f7a22b8c
    internal-label: Data model architecture
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 11%
---
# Criação ou extensão do recurso{#creating-or-extending-the-resource}

Os administradores podem criar um novo recurso do zero ou criar uma extensão de um recurso existente se você precisar trabalhar em dados que não fazem parte do modelo de dados integrado.

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

1. Em **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**, clique no botão **[!UICONTROL Create]**.
1. Escolha a ação que deseja executar:

   * **[!UICONTROL Create a new resource]**: Insira os campos **[!UICONTROL Label]** e **[!UICONTROL ID]**. O campo **[!UICONTROL ID]** é obrigatório. Se você deixar o campo Label vazio, ele será automaticamente preenchido a partir da ID.

     ![](assets/schema_extension_2.png)

     >[!NOTE]
     >
     >Use no máximo 30 caracteres.

   * **[!UICONTROL Extend an existing resource]**: Selecione o recurso que deseja estender.

     ![](assets/schema_extension_10.png)

1. Clique em **[!UICONTROL Create]** para criar o recurso, que assumirá o status **[!UICONTROL Draft]** no caso de um novo recurso ou o status **[!UICONTROL Editing]** no caso de uma extensão.

O novo recurso é criado e agora pode ser configurado. Para obter mais informações sobre a configuração de recursos, consulte [Configurando a estrutura de dados do recurso](../../developing/using/configuring-the-resource-s-data-structure.md).
