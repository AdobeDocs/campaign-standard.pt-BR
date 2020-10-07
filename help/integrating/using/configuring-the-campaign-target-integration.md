---
title: Configuração da integração do Campaign com o Target
description: Saiba como configurar a integração do Adobe Target ao start usando conteúdo dinâmico no Adobe Campaign.
page-status-flag: never-activated
uuid: 0df5701c-dc26-4c30-9af9-ebf92815d90c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
discoiquuid: f7fb2084-dd6f-4aa2-940f-e48713146635
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 18%

---


# Configuração da integração do Campaign com o Target{#configuring-the-campaign-target-integration}

A integração entre o Adobe Campaign e o Adobe Target permite inserir conteúdo dinâmico em seu delivery.

Uma configuração é necessária no Adobe Campaign para usar as funcionalidades de integração com a Adobe Target e deve ser gerenciada pelo administrador funcional.

Para este procedimento, são necessários os seguintes elementos:

* Um locatário da Adobe Experience Cloud
* Um locatário da Adobe Target
* Um rawbox do Adobe Target especificado para estabelecer a conexão com o Adobe Campaign

1. No menu avançado, pelo logotipo Adobe Campaign no canto superior esquerdo, selecione **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.
1. Para configurar as opções de servidor e locatário para Adobe Target, preencha os seguintes campos de acordo:

   * **[!UICONTROL TNT_TenantName]**: nome do locatário do Adobe Target. Esse valor corresponde ao nome do **[!UICONTROL Client]** do Adobe Target.
   * **[!UICONTROL TNT_EdgeServer]**: Servidor Adobe Target usado para integração. Essa opção já é fornecida por padrão. This value corresponds to the Adobe Target **[!UICONTROL Server Domain]**, followed by the **/m2** value. Por exemplo: **tt.omtrdc.net/m2**.

   ![](assets/tar_options.png)

Seus usuários agora podem adicionar imagens dinâmicas em um delivery com o Adobe Target.
