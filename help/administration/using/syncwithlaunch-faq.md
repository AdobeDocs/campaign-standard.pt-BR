---
title: Perguntas frequentes sobre sincronização com o workflow técnico do Launch
description: Perguntas comuns sobre o fluxo de trabalho técnico do Adobe Launch
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 1%

---

# Perguntas frequentes sobre tags na sincronização do Adobe Experience Platform {#syncwithlaunch-faq}

É possível importar propriedades móveis de tags para o Adobe Campaign Standard por meio do **[!UICONTROL Sync with Launch]** fluxo de trabalho técnico dedicado. Para obter mais informações, consulte esta [página](../../administration/using/technical-workflows.md)

A seção abaixo lista perguntas comuns sobre essa sincronização.

## Criei uma propriedade de tag (não administrador da unidade organizacional ALL). Meu aplicativo está no estado Pronto para configurar no Adobe Campaign, mas não consigo abri-lo/configurá-lo. {#configuring-property}

Somente o administrador da unidade organizacional ALL pode configurar aplicativos móveis no Adobe Campaign Standard. Depois de configurado, somente os usuários da unidade organizacional atribuída poderão editar o aplicativo. Para obter mais informações sobre a unidade organizacional, consulte esta seção [página](../../administration/using/organizational-units.md).

## Não consigo editar um aplicativo móvel configurado no Adobe Campaign Standard e os aplicativos móveis estão somente no modo de leitura. {#read-mode-mobile-app}

Verifique a unidade organizacional do aplicativo móvel no **[!UICONTROL Access Authorization]** seção. Somente os usuários da unidade organizacional atribuída podem editar o aplicativo móvel.

Para obter mais informações sobre a unidade organizacional, consulte esta seção [página](../../administration/using/organizational-units.md).

## Sou um administrador com a unidade da organização ALL no Adobe Campaign Standard, mas não consigo configurar o aplicativo móvel. {#org-unit-mobile}

Um administrador com a unidade da organização definida como TODAS deve ter direitos para todas as propriedades móveis de tags para configurar o aplicativo móvel.

Para obter mais informações sobre a unidade organizacional, consulte esta seção [página](../../administration/using/organizational-units.md).

## Criei uma propriedade de tag para dispositivos móveis, mas minha propriedade não está visível no Adobe Campaign Standard. {#visibility-mobile-property}

1. Verifique se a extensão Adobe Campaign Standard está instalada na propriedade móvel na interface do usuário da coleta de dados.

1. Verifique se os pontos de extremidade da instância estão configurados corretamente na extensão .

1. Verifique se &#39;Launch_URL_Campaign&#39; ou &#39;NmsServer_URL&#39; estão corretos.

1. Em seguida, verifique se a sincronização foi concluída com o **[!UICONTROL syncWithLaunch]** fluxo de trabalho técnico.

## Como verificar se a sincronização entre o Adobe Campaign e as Tags no Adobe Experience Platform foi concluída? {#sync-campaign-launch}

1. No Adobe Campaign Standard, no menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Abra o **[!UICONTROL syncWithLaunch]** fluxo de trabalho.

1. Verifique se o workflow terminou sem erro.

1. Verifique nos logs se a sincronização do workflow está habilitada e concluída com êxito.

## Redefino a chave para um aplicativo móvel de tag configurado. Como reconfigurar a chave novamente na interface do usuário da coleta de dados? {#configuring-pkey}

1. Abra a propriedade móvel na interface do usuário da Coleta de dados.

1. Defina um novo URL na extensão do Adobe Campaign Standard para a qual a chave de privacidade foi redefinida.

1. Salve-o e permita a sincronização do workflow.

1. Após concluir a sincronização, abra a propriedade móvel na interface do usuário da coleta de dados.

1. Defina o URL correto na extensão Adobe Campaign Standard para a qual PKey foi redefinido.

1. Salve-o e permita que a sincronização do workflow seja executada novamente.

1. Somente então a propriedade aparecerá em **[!UICONTROL Ready to Configure]** no Adobe Campaign e agora pode ser configurado.

## Quero configurar uma propriedade móvel no Adobe Campaign. Terei que aguardar a sincronização do fluxo de trabalho técnico entre Tags no Adobe Experience Platform e no Adobe Campaign?

Você pode executar imediatamente o workflow:

1. No Adobe Campaign Standard, no menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Abra o **[!UICONTROL syncWithLaunch]** fluxo de trabalho.

1. Clique no botão **[!UICONTROL Scheduler]** e selecione **[!UICONTROL Immediate execution]**.
