---
title: Painel de mensagens
description: Descubra do que o painel de mensagem é composto, incluindo a barra de ação e os vários blocos funcionais.
page-status-flag: never-activated
uuid: 9bb44ee8-2cf6-43ce-94a4-367f4e469713
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: about-communication-channels
discoiquuid: 90a78742-697f-46da-8c54-108048e57b67
context-tags: delivery,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 6%

---


# Painel de mensagens{#message-dashboard}

O painel de mensagem é um espaço de trabalho composto de ícones diferentes - agrupados em uma barra de ação - e vários blocos funcionais que permitem estabelecer os parâmetros da mensagem e enviá-la. Estes elementos são apresentados em seguida.

![](assets/delivery_dashboard_2.png)

## Barra cinza {#gray-bar}

A barra cinza agrupa vários ícones vinculados à sua mensagem.

* **[!UICONTROL Summary]**: mostra/oculta as principais informações relacionadas à mensagem.
* **[!UICONTROL Edit properties]**: permite que você edite os parâmetros [](../../administration/using/configuring-email-channel.md#list-of-email-properties)avançados da mensagem.
* **[!UICONTROL Reports]**: fornece acesso aos relatórios relacionados à mensagem.

**Tópicos relacionados:**

* [Configuração de canais](../../administration/using/about-channel-configuration.md)
* [Acesso ao relatórios](../../reporting/using/about-dynamic-reports.md)

## Barra de ação {#action-bar}

A barra de ação tem ícones diferentes que permitem interagir com sua mensagem.

![](assets/delivery_dashboard_4.png)

Dependendo dos parâmetros que foram configurados e do progresso feito, alguns ícones podem não estar disponíveis.

* **[!UICONTROL Show proofs]**: mostra/oculta a lista de provas que foram enviadas, se elas existirem. Esse botão só é ativado depois que você envia o prova.

   Para obter mais informações sobre o prova, consulte [Enviar provas](../../sending/using/sending-proofs.md).

* **[!UICONTROL Send a test]**: permite que você selecione o modo de aprovação a ser usado: **[!UICONTROL Email rendering]** (somente email), **[!UICONTROL Proof]** ou ambos. Para obter mais informações sobre perfis de teste, consulte [Envio de provas](../../sending/using/sending-proofs.md). Esse botão só é ativado depois que você cria perfis de teste.

* **[!UICONTROL Prepare send]**: start para preparar o envio. O **[!UICONTROL Deployment]** bloco é exibido e exibe o resultado da preparação. Este botão só é exibido depois que o público alvo é inserido. Pode interromper a preparação a qualquer momento usando o botão correspondente. For more on message preparation, refer to [Preparing the send](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**: confirma o envio da mensagem. As estatísticas de envio são exibidas no **[!UICONTROL Deployment]** bloco. Esse botão só aparece depois que o envio é preparado. Você pode interromper ou pausar o envio a qualquer momento usando os botões **Parar envio** e **[!UICONTROL Pause]** . Para obter mais informações sobre como confirmar o envio, consulte [Enviar mensagens](../../sending/using/confirming-the-send.md).

## Blocos {#blocks}

A tela principal é composta por blocos diferentes. Clique dentro de um bloco para acessar a tela de parâmetros correspondente:

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**: permite que você rastreie o progresso da preparação ou envio da mensagem. Clique no botão localizado na seção inferior direita deste bloco para acessar os registros de envio e análise. Este bloco só aparece depois que o envio é preparado. Para saber mais sobre isso. See [Confirming send](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**: permite estabelecer o público alvo principal da mensagem, bem como os perfis de teste. Consulte [Criação de públicos-alvo](../../audiences/using/creating-audiences.md).
* **[!UICONTROL Schedule]**: permite que você especifique a data em que sua mensagem será enviada. Consulte [Agendamento](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**: permite que você defina o conteúdo da mensagem e a pré-visualização. See [Key steps to send a message](../../channels/using/key-steps-to-send-a-message.md).

## Avisos {#warnings}

Em alguns casos, um aviso pode aparecer em um banner amarelo na parte superior do painel da mensagem.

![](assets/delivery_dashboard_warnings.png)

Abaixo está uma lista das mensagens que podem ser exibidas:

* *&quot;A opção de modo de teste SMTP está ativada para este email: nenhuma mensagem será enviada.&quot;*

   Para obter mais informações, consulte [esta seção](../../administration/using/configuring-email-channel.md#smtp-test-mode).

* *&quot;A conta externa do Roteamento foi desativada.&quot;*

   For more on this, see [External accounts](../../administration/using/external-accounts.md).

* *&quot;As mensagens não podem ser enviadas porque a afinidade IP atual não é tratada por nenhum processo de envio.&quot;*

   Se você vir essa mensagem, há um problema no nível de definição da afinidade IP ou no nível do processo de envio. Entre em contato com o administrador do Adobe 

* *&quot;Este é um template de mensagem transacional pronto para usar. Se quiser modificá-la, você deve duplicado-la e trabalhar na sua cópia.&quot;*

   Alguns desses templates de mensagem transacionais prontos para uso são modelos de landing page integrados. Para obter mais informações, consulte [esta seção](../../channels/using/landing-page-templates.md).

* *&quot;Essa mensagem é um template de mensagem transacional técnico. Não é possível modificá-la ou publicá-la.&quot;*

   Esse aviso é exibido em templates de mensagem transacionais vazios que não são editáveis. For more on transactional messages, see [this section](../../channels/using/getting-started-with-transactional-msg.md).
