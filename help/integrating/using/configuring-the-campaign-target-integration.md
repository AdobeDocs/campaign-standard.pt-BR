---
solution: Campaign Standard
product: campaign
title: Configuração da integração do Campaign com o Target
description: Saiba como configurar a integração do Adobe Target para começar a usar conteúdo dinâmico no Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 18%

---


# Configuração da integração do Campaign com o Target{#configuring-the-campaign-target-integration}

A integração entre o Adobe Campaign e o Adobe Target permite inserir conteúdo dinâmico no seu delivery.

Primeiro, uma configuração é necessária no Adobe Campaign para usar as funcionalidades de integração com o Adobe Target e deve ser gerenciada pelo administrador funcional.

Os seguintes elementos são necessários para este procedimento:

* Um locatário do Adobe Experience Cloud
* Um locatário do Adobe Target
* Um rawbox do Adobe Target especificado para estabelecer a conexão com o Adobe Campaign

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** pelo logotipo do Adobe Campaign no canto superior esquerdo.
1. Para configurar as opções do servidor e do locatário para o Adobe Target, preencha os seguintes campos de acordo:

   * **[!UICONTROL TNT_TenantName]**: nome do locatário do Adobe Target. Esse valor corresponde ao nome do **[!UICONTROL Client]** do Adobe Target.
   * **[!UICONTROL TNT_EdgeServer]**: Servidor Adobe Target usado para integração. Essa opção já é fornecida por padrão. Esse valor corresponde ao Adobe Target **[!UICONTROL Server Domain]**, seguido pelo valor **/m2**. Por exemplo: **tt.omtrdc.net/m2**.

   ![](assets/tar_options.png)

Seus usuários agora podem adicionar imagens dinâmicas em um delivery com o Adobe Target.
