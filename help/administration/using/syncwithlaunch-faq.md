---
title: Sincronizar com perguntas frequentes do fluxo de trabalho técnico do Launch
description: Perguntas frequentes sobre o fluxo de trabalho técnico do Launch.
page-status-flag: never-activated
uuid: 4f538452-cc67-4e03-9e2f-2d9eecc081c7
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 54028f63-c9ca-4397-a079-e27e0cfdebf6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95a7397092f6e07c84967d90908469f630f7a170
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 1%

---


# Perguntas frequentes sobre sincronização de inicialização de Adobe {#syncwithlaunch-faq}

É possível importar as propriedades do Adobe Launch para o Adobe Campaign Standard por meio do fluxo de trabalho técnico **[!UICONTROL Sync with Launch]** dedicado. Para obter mais informações, consulte esta [página](../../administration/using/technical-workflows.md)

A seção abaixo lista perguntas comuns sobre essa sincronização.

>[!NOTE]
>
>You will need to submit a ticket to Adobe Customer Care (either directly or through your Adobe contact) to have the **[!UICONTROL syncWithLaunch]** technical workflow enabled in your Campaign instance.

## Criei uma propriedade em [!DNL Launch] (não administrador da unidade organizacional ALL). Meu aplicativo está no estado Pronto para configurar no Adobe Campaign, mas não consigo abri-lo/configurá-lo. {#configuring-property}

Somente o administrador da unidade organizacional ALL pode configurar aplicativos móveis no Adobe Campaign Standard. Depois de configurado, somente os usuários da unidade organizacional atribuída podem editar o aplicativo. For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## Não consigo editar um aplicativo móvel configurado no Adobe Campaign Standard e os aplicativos móveis estão somente no modo de Leitura. {#read-mode-mobile-app}

Verifique a unidade organizacional do aplicativo móvel na **[!UICONTROL Access Authorization ]** seção. Somente os usuários da unidade organizacional atribuída podem editar o aplicativo móvel.

For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## Sou um administrador com a unidade da organização ALL no Adobe Campaign Standard, mas não posso configurar o aplicativo móvel. {#org-unit-mobile}

Um administrador com a unidade da organização definida como ALL deve ter direitos para todas as propriedades móveis para configurar [!DNL Launch] o aplicativo móvel.

For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## Criei uma propriedade móvel no [!DNL Launch] , mas minha propriedade não está visível no Adobe Campaign Standard. {#visibility-mobile-property}

1. Verifique se a extensão Adobe Campaign Standard está instalada na propriedade móvel em [!DNL Launch].

1. Verifique se os pontos de extremidade da instância estão configurados corretamente na extensão.

1. Verifique se &#39;Launch_URL_Campanha&#39; ou &#39;NmsServer_URL&#39; estão corretos.

1. Em seguida, verifique se a sincronização entre o [!DNL Launch] Adobe Campaign e o foi concluída com o fluxo de trabalho **[!UICONTROL syncWithLaunch]** técnico.

## Como verificar se a sincronização entre o Adobe Campaign e o Launch foi concluída? {#sync-campaign-launch}

1. No Adobe Campaign Standard, no menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Abra o **[!UICONTROL syncWithLaunch]** fluxo de trabalho.

1. Verifique se o fluxo de trabalho terminou sem erro.

1. Verifique nos registros se a sincronização do fluxo de trabalho está ativada e concluída com êxito.

## Redefino a chave para um aplicativo móvel configurado no Launch. Como reconfigurar a chave novamente no Launch? {#configuring-pkey}

1. Abra a propriedade mobile no Adobe Launch.

1. Defina um novo URL na extensão do Adobe Campaign Standard para a qual o PKey foi redefinido.

1. Salve-o e permita que o fluxo de trabalho seja sincronizado entre o Adobe Campaign e o [!DNL Launch].

1. Depois que a sincronização for concluída, abra a propriedade mobile em [!DNL Launch].

1. Defina o URL correto na extensão Adobe Campaign Standard para a qual PKey foi redefinido.

1. Salve-o e permita que a sincronização do fluxo de trabalho seja executada novamente.

1. Somente então a propriedade aparecerá no **[!UICONTROL Ready to Configure]** estado no Adobe Campaign e poderá ser configurada.

## Quero configurar uma propriedade móvel no Adobe Campaign. Terei que aguardar a sincronização do fluxo de trabalho técnico entre o Adobe Launch e o Adobe Campaign?

Você pode executar imediatamente o fluxo de trabalho:

1. No Adobe Campaign Standard, no menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Abra o **[!UICONTROL syncWithLaunch]** fluxo de trabalho.

1. Click on the **[!UICONTROL Scheduler]** activity and select **[!UICONTROL Immediate execution]**.
