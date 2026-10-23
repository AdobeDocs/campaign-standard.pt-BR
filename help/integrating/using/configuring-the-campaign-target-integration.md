---
title: Configuração da integração do Campaign com o Target
description: Saiba como configurar a integração do Adobe Target para começar a usar conteúdo dinâmico no Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: d382bfdd-418d-46c1-98dd-df8626f85cac
TQID: 'https://experienceleague.adobe.com/trfuEp6pEd2jFADsK6NMw6tx8ASi86ZFur56AjwnpWQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0
    internal-label: Triggers
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 19%
---
# Configuração da integração do Campaign com o Target{#configuring-the-campaign-target-integration}

A integração entre o Adobe Campaign e o Adobe Target permite inserir conteúdo dinâmico no seu delivery.

Uma configuração é necessária primeiro no Adobe Campaign para usar as funcionalidades de integração com o Adobe Target e deve ser gerenciada pelo administrador funcional.

Os seguintes elementos são necessários para esse procedimento:

* Um locatário da Adobe Experience Cloud
* Um locatário do Adobe Target
* Um rawbox do Adobe Target especificado para estabelecer a conexão com o Adobe Campaign

1. No menu avançado, no logotipo do Adobe Campaign, no canto superior esquerdo, selecione **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.
1. Para configurar as opções de servidor e locatário do Adobe Target, preencha os seguintes campos adequadamente:

   * **[!UICONTROL TNT_TenantName]**: nome do locatário do Adobe Target. Esse valor corresponde ao nome do **[!UICONTROL Client]** do Adobe Target.
   * **[!UICONTROL TNT_EdgeServer]**: servidor Adobe Target usado para integração. Essa opção já é fornecida por padrão. Este valor corresponde ao Adobe Target **[!UICONTROL Server Domain]**, seguido pelo valor **/m2**. Por exemplo: **tt.omtrdc.net/m2**.

   ![](assets/tar_options.png)

Seus usuários agora podem adicionar imagens dinâmicas em um delivery com o Adobe Target.
