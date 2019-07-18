---
title: Configuração da integração do Target-Target
seo-title: Configuração da integração do Target-Target
description: Configuração da integração do Target-Target
seo-description: Saiba como configurar a integração do Adobe Target para começar a usar conteúdo dinâmico no Adobe Campaign.
page-status-flag: nunca ativado
uuid: 0 df 5701 c-dc 26-4 c 30-9 af 9-ebf 92815 d 90 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: trabalho com campanha e destino
discoiquuid: f 7 fb 2084-dd 6 f -4 aa 2-940 f-e 48713146635
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Configuring the Campaign-Target integration{#configuring-the-campaign-target-integration}

A integração entre o Adobe Campaign e o Adobe Target permite que você insira conteúdo dinâmico na entrega.

Uma configuração é necessária primeiro no Adobe Campaign para usar as funcionalidades de integração com o Adobe Target e deve ser gerenciada pelo administrador funcional.

Os seguintes elementos são necessários para este procedimento:

* Um inquilino da Adobe Experience Cloud
* Um tenant do Adobe Target
* Um rawbox do Adobe Target especificado para estabelecer a conexão com o Adobe Campaign

1. From the advanced menu, via the Adobe Campaign logo in the top left corner, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]**.
1. Para configurar as opções do servidor e do locatário para o Adobe Target, preencha os seguintes campos de acordo:

   * **[!UICONTROL TNT_TenantName]**: nome do locatário do Adobe Target. This value corresponds to the name of the Adobe Target **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**: Servidor do Adobe Target usado para integração. Essa opção já está fornecida por padrão. This value corresponds to the Adobe Target **[!UICONTROL Server Domain]**, followed by the **/m2** value. For example: **tt.omtrdc.net/m2**.
   ![](assets/tar_options.png)

Os usuários agora podem adicionar imagens dinâmicas em uma entrega com o Adobe Target.
