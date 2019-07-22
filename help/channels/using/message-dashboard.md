---
title: Painel de mensagens
seo-title: Painel de mensagens
description: Painel de mensagens
seo-description: Descubra o que é constituído pelo painel de mensagens, incluindo a barra de ações e os diversos blocos funcionais.
page-status-flag: nunca ativado
uuid: 9 bb 44 ee 8-2 cf 6-43 ce -94 a 4-367 f 4 e 469713
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: about-communication-channels
discoiquuid: 90 a 78742-697 f -46 da -8 c 54-108048 e 57 b 67
context-tags: entrega, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 25d997b2e5aa41e29e49ab047398b3db811bd6b6

---


# Message dashboard{#message-dashboard}

O painel de mensagens é uma área de trabalho composta de ícones diferentes - reunidos em uma barra de ações - e vários blocos funcionais que permitem estabelecer os parâmetros da mensagem e enviá-los. Esses elementos são apresentados em seguida.

![](assets/delivery_dashboard_2.png)

## Gray bar {#gray-bar}

A barra cinza recupera vários ícones vinculados à sua mensagem.

* **[!UICONTROL Summary]**: mostra/oculta as principais informações relacionadas à mensagem.
* **[!UICONTROL Edit properties]**: permite editar os parâmetros [avançados da mensagem](../../administration/using/configuring-email-channel.md#list-of-email-properties).
* **[!UICONTROL Reports]**: fornece acesso aos relatórios relacionados à mensagem.

**Tópicos relacionados:**

* [Configuração de canais](../../administration/using/about-channel-configuration.md)
* [Acessar relatórios](../../reporting/using/about-dynamic-reports.md)

## Action bar {#action-bar}

A barra de ações tem ícones diferentes que permitem interagir com a sua mensagem.

![](assets/delivery_dashboard_4.png)

Dependendo dos parâmetros que foram configurados e do progresso realizado, alguns ícones podem não estar disponíveis.

* **[!UICONTROL Show proofs]**: mostra/oculta a lista de testes que foram enviados, se existirem. Esse botão só é ativado depois que você enviou provas.

   For more on proofs, see [Managing test profiles and sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md).

* **[!UICONTROL Send a test]**: permite que você selecione o modo de aprovação a ser usado: **[!UICONTROL Email rendering]** ou **[!UICONTROL Proof]** ambos para um email. For more on test profiles, see [Sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).

   Esse botão só é ativado depois que você estabeleceu perfis de teste.

   >[!NOTE]
   >
   >For an SMS message, there is no other choice: it is automatically a **[!UICONTROL Proof]**.

* **[!UICONTROL Prepare send]**: começa a preparar o envio. **[!UICONTROL Deployment]** O bloco é exibido e exibe o resultado da preparação. Esse botão só aparece quando o destino foi inserido. Você pode interromper a preparação a qualquer momento usando o botão correspondente.

   For more on message preparation, [Preparing the send](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**: confirmar o envio da mensagem. The sending statistics appear in the **[!UICONTROL Deployment]** block. Esse botão só aparece depois que o envio foi preparado. You can stop or pause the send at any time using the **Stop send** and **[!UICONTROL Pause]** buttons.

   For more on confirming sending, see [Sending messages](../../sending/using/confirming-the-send.md).

## Blocks {#blocks}

A tela principal é composta de blocos diferentes. Clique em dentro de um bloco para acessar a tela de parâmetro correspondente:

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**: permite rastrear o progresso da preparação ou do envio da mensagem. Clique no botão encontrado na seção inferior direita deste bloco para acessar os logs de envio e análise. Esse bloco só será exibido depois que o envio for preparado. Para mais informações sobre isso. See [Confirming send](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**: permite estabelecer o destino principal da mensagem e os perfis de teste. See [Creating audiences](../../audiences/using/creating-audiences.md).
* **[!UICONTROL Schedule]**: permite especificar a data em que a mensagem será enviada. See [Scheduling](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**: permite que você defina o conteúdo da mensagem e a visualize. See [Defining content](../../designing/using/designing-content-in-adobe-campaign.md).

