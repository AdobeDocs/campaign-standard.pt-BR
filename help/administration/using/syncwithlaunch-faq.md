---
solution: Campaign Standard
product: campaign
title: Perguntas frequentes sobre sincronização com o workflow técnico do Launch
description: Perguntas comuns sobre o workflow técnico do Launch.
audience: administration
content-type: reference
topic-tags: users-and-security
feature: Configurações de instância
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 2%

---

# Perguntas frequentes sobre a sincronização do Adobe Launch {#syncwithlaunch-faq}

Você pode importar propriedades móveis do Adobe Launch para o Adobe Campaign Standard por meio do fluxo de trabalho técnico dedicado **[!UICONTROL Sync with Launch]**. Para obter mais informações, consulte esta [página](../../administration/using/technical-workflows.md)

A seção abaixo lista perguntas comuns sobre essa sincronização.

## Criei uma propriedade em [!DNL Launch] (não administrador da unidade organizacional ALL). Meu aplicativo está no estado Pronto para configurar no Adobe Campaign, mas não consigo abri-lo/configurá-lo. {#configuring-property}

Somente o administrador da unidade organizacional ALL pode configurar aplicativos móveis no Adobe Campaign Standard. Após a configuração, somente os usuários da unidade organizacional atribuída poderão editar a variável
aplicativo. Para obter mais informações sobre a unidade organizacional, consulte esta [página](../../administration/using/organizational-units.md).

## Não consigo editar um aplicativo móvel configurado no Adobe Campaign Standard e os aplicativos móveis estão somente no modo de leitura. {#read-mode-mobile-app}

Verifique a unidade organizacional do aplicativo móvel na seção **[!UICONTROL Access Authorization]** . Somente os usuários da unidade organizacional atribuída podem editar o aplicativo móvel.

Para obter mais informações sobre a unidade organizacional, consulte esta [página](../../administration/using/organizational-units.md).

## Sou um administrador com a unidade da organização ALL no Adobe Campaign Standard, mas não consigo configurar o aplicativo móvel. {#org-unit-mobile}

Um administrador com a unidade da organização definida como TODAS deve ter direitos para todas as propriedades móveis em [!DNL Launch] para configurar o aplicativo móvel.

Para obter mais informações sobre a unidade organizacional, consulte esta [página](../../administration/using/organizational-units.md).

## Criei uma propriedade móvel em [!DNL Launch], mas minha propriedade não está visível no Adobe Campaign Standard. {#visibility-mobile-property}

1. Verifique se a extensão Adobe Campaign Standard está instalada na propriedade móvel em [!DNL Launch].

1. Verifique se os pontos de extremidade da instância estão configurados corretamente na extensão .

1. Verifique se &#39;Launch_URL_Campaign&#39; ou &#39;NmsServer_URL&#39; estão corretos.

1. Em seguida, verifique se a sincronização entre [!DNL Launch] e o Adobe Campaign foi concluída com o workflow técnico **[!UICONTROL syncWithLaunch]**.

## Como verificar se a sincronização entre o Adobe Campaign e o Launch foi concluída? {#sync-campaign-launch}

1. No Adobe Campaign Standard, no menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Abra o workflow **[!UICONTROL syncWithLaunch]** .

1. Verifique se o workflow terminou sem erro.

1. Verifique nos logs se a sincronização do workflow está habilitada e concluída com êxito.

## Redefino a chave de um aplicativo móvel configurado no Launch. Como reconfigurar a chave novamente no Launch? {#configuring-pkey}

1. Abra a propriedade móvel no Adobe Launch.

1. Defina um novo URL na extensão do Adobe Campaign Standard para a qual a chave de privacidade foi redefinida.

1. Salve-o e permita que o workflow sincronize entre Adobe Campaign e [!DNL Launch].

1. Após concluir a sincronização, abra a propriedade móvel em [!DNL Launch].

1. Defina o URL correto na extensão Adobe Campaign Standard para a qual PKey foi redefinido.

1. Salve-o e permita que a sincronização do workflow seja executada novamente.

1. Somente então a propriedade aparecerá no estado **[!UICONTROL Ready to Configure]** no Adobe Campaign e agora poderá ser configurada.

## Quero configurar uma propriedade móvel no Adobe Campaign. Terei que aguardar a sincronização do workflow técnico entre o Adobe Launch e o Adobe Campaign?

Você pode executar imediatamente o workflow:

1. No Adobe Campaign Standard, no menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Abra o workflow **[!UICONTROL syncWithLaunch]** .

1. Clique na atividade **[!UICONTROL Scheduler]** e selecione **[!UICONTROL Immediate execution]**.
