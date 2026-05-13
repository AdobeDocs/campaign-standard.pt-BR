---
title: Perguntas frequentes sobre sincronização com o fluxo de trabalho técnico do Launch
description: Perguntas comuns sobre o fluxo de trabalho técnico do Adobe Launch
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
TQID: https://experienceleague.adobe.com/0ixw0iKTFcM1081kmmLNj0iPuH-XwWWKETDALpobe8k
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 497
ht-degree: 1%

---

# Perguntas frequentes sobre tags na sincronização da Adobe Experience Platform {#syncwithlaunch-faq}

Você pode importar propriedades de dispositivos móveis de tag para a Adobe Campaign Standard por meio do fluxo de trabalho técnico dedicado **[!UICONTROL Sync with Launch]**. Para obter mais informações, consulte esta [página](../../administration/using/technical-workflows.md)

A seção abaixo lista perguntas comuns sobre essa sincronização.

## Criei uma propriedade de tag (não administrador de ALL de unidade organizacional). Meu aplicativo está no estado Pronto para configurar no Adobe Campaign, mas não consigo abri-lo/configurá-lo. {#configuring-property}

Somente o administrador de TODAS as unidades organizacionais pode configurar aplicativos móveis no Adobe Campaign Standard. Depois de configurado, somente os usuários da unidade organizacional atribuída poderão editar a variável
aplicação. Para obter mais informações sobre a unidade organizacional, consulte esta [página](../../administration/using/organizational-units.md).

## Não consigo editar um aplicativo para dispositivos móveis configurado no Adobe Campaign Standard e os aplicativos para dispositivos móveis estão em modo de leitura apenas. {#read-mode-mobile-app}

Verifique a unidade organizacional do aplicativo móvel na seção **[!UICONTROL Access Authorization]**. Somente os usuários da unidade organizacional atribuída podem editar o aplicativo para dispositivos móveis.

Para obter mais informações sobre a unidade organizacional, consulte esta [página](../../administration/using/organizational-units.md).

## Sou um administrador com a unidade organizacional ALL na Adobe Campaign Standard, mas não posso configurar o aplicativo para dispositivos móveis. {#org-unit-mobile}

Um administrador com unidade organizacional definida como TODOS deve ter direitos a todas as propriedades móveis de tag para configurar o aplicativo móvel.

Para obter mais informações sobre a unidade organizacional, consulte esta [página](../../administration/using/organizational-units.md).

## Criei uma propriedade móvel de tag, mas minha propriedade não está visível no Adobe Campaign Standard. {#visibility-mobile-property}

1. Verifique se a extensão do Adobe Campaign Standard está instalada na propriedade móvel na interface da coleção de dados.

1. Verifique se os pontos de extremidade da instância estão configurados corretamente na extensão.

1. Verifique se &quot;Launch_URL_Campaign&quot; ou &quot;NmsServer_URL&quot; estão corretos.

1. Em seguida, verifique se a sincronização foi concluída com o fluxo de trabalho técnico **[!UICONTROL syncWithLaunch]**.

## Como verificar se a sincronização entre o Adobe Campaign e as tags no Adobe Experience Platform foi concluída? {#sync-campaign-launch}

1. No Adobe Campaign Standard, no menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Abra o fluxo de trabalho **[!UICONTROL syncWithLaunch]**.

1. Verifique se o fluxo de trabalho terminou sem erros.

1. Verifique nos logs se a sincronização do workflow está ativada e concluída com êxito.

## Redefini a pkey para um aplicativo móvel de tag configurado. Como reconfigurar a pkey novamente na interface da coleção de dados? {#configuring-pkey}

1. Abra a propriedade móvel na interface da Coleção de dados.

1. Defina um novo URL na extensão do Adobe Campaign Standard para o qual a PKey foi redefinida.

1. Salve-o e deixe o workflow sincronizar.

1. Após a conclusão da sincronização, abra a propriedade móvel no na interface da Coleção de dados.

1. Defina o URL correto na extensão do Adobe Campaign Standard para o qual o PKey foi redefinido.

1. Salve-o e deixe a sincronização do workflow ser executada novamente.

1. Somente então a propriedade aparecerá no estado **[!UICONTROL Ready to Configure]** no Adobe Campaign e poderá ser configurada.

## Quero configurar uma propriedade móvel no Adobe Campaign. Terei que aguardar o fluxo de trabalho técnico sincronizar entre as Tags no Adobe Experience Platform e no Adobe Campaign?

Você pode fazer a execução imediata do workflow:

1. No Adobe Campaign Standard, no menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Abra o fluxo de trabalho **[!UICONTROL syncWithLaunch]**.

1. Clique na atividade **[!UICONTROL Scheduler]** e selecione **[!UICONTROL Immediate execution]**.
