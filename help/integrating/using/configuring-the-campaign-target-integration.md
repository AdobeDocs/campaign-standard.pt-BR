---
title: Configurar da integração do Campaign com oTarget
description: Saiba como configurar a integração do Adobe Target para começar a usar conteúdo dinâmico no Adobe Campaign.
page-status-flag: nunca ativado
uuid: 0df5701c-dc26-4c30-9af9-ebf92815d90c
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: integrando
content-type: referência
topic-tags: trabalhar com campanha e meta
discoiquuid: f7fb2084-dd6f-4aa2-940f-e4871314635
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Configurar da integração do Campaign com oTarget{#configuring-the-campaign-target-integration}

A integração entre o Adobe Campaign e o Adobe Target permite inserir conteúdo dinâmico em sua entrega.

Uma configuração é necessária no Adobe Campaign para usar as funcionalidades de integração com o Adobe Target e deve ser gerenciada pelo administrador funcional.

Os seguintes elementos são necessários para este procedimento:

* Um locatário da Adobe Experience Cloud
* Um locatário do Adobe Target
* Um rawbox do Adobe Target especificado para estabelecer a conexão com o Adobe Campaign

1. No menu avançado, pelo logotipo do Adobe Campaign no canto superior esquerdo, selecione **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]**.
1. Para configurar as opções de servidor e locatário para o Adobe Target, preencha os seguintes campos de acordo:

   * **[!UICONTROL TNT_TenantName]**: nome do locatário do Adobe Target. This value corresponds to the name of the Adobe Target **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**: Servidor do Adobe Target usado para integração. Essa opção já é fornecida por padrão. Esse valor corresponde ao Adobe Target **[!UICONTROL Server Domain]**, seguido pelo valor **/m2** .  Por exemplo: **tt.omtrdc.net/m2**.
   ![](assets/tar_options.png)

Seus usuários agora podem adicionar imagens dinâmicas em uma entrega com o Adobe Target.
