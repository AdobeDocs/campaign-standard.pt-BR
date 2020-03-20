---
title: Painel de mensagens
description: Descubra do que o painel de mensagens é composto, incluindo a barra de ação e os vários blocos funcionais.
page-status-flag: never-activated
uuid: 9bb44ee8-2cf6-43ce-94a4-367f4e469713
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: about-communication-channels
discoiquuid: 90a78742-697f-46da-8c54-108048e57b67
context-tags: delivery,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 80f6a384e99a7cebbe5c570f3273eceb393fd9b0

---


# Painel de mensagens{#message-dashboard}

O painel de mensagens é um espaço de trabalho composto de ícones diferentes - agrupados em uma barra de ação - e vários blocos funcionais que permitem estabelecer os parâmetros da mensagem e enviá-la. Estes elementos são apresentados em seguida.

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

* **[!UICONTROL Show proofs]**: mostra/oculta a lista de provas enviadas, se existirem. Este botão só é ativado depois que você envia provas.

   Para obter mais informações, consulte [Enviar provas](../../sending/using/sending-proofs.md).

* **[!UICONTROL Send a test]**: permite que você selecione o modo de aprovação a ser usado: **[!UICONTROL Email rendering]**, **[!UICONTROL Proof]** ou ambos para um email. Para obter mais informações sobre perfis de teste, consulte [Enviar provas](../../sending/using/sending-proofs.md).

   Esse botão só é ativado depois que você tiver estabelecido os perfis de teste.

   >[!NOTE]
   >
   >Para uma mensagem SMS, não há outra opção: é automaticamente um **[!UICONTROL Proof]**.

* **[!UICONTROL Prepare send]**: começa a preparar o envio. O **[!UICONTROL Deployment]** bloco é exibido e exibe o resultado da preparação. Esse botão só é exibido depois que o destino é inserido. Pode interromper a preparação a qualquer momento usando o botão correspondente.

   Para obter mais informações sobre a preparação da mensagem, [Prepare o envio](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**: confirma o envio da mensagem. As estatísticas de envio são exibidas no **[!UICONTROL Deployment]** bloco. Esse botão só aparece depois que o envio é preparado. Você pode interromper ou pausar o envio a qualquer momento usando os botões **Parar envio** e **[!UICONTROL Pause]** .

   Para obter mais informações sobre como confirmar o envio, consulte [Enviar mensagens](../../sending/using/confirming-the-send.md).

## Blocos {#blocks}

A tela principal é composta por blocos diferentes. Clique dentro de um bloco para acessar a tela de parâmetros correspondente:

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**: permite que você rastreie o progresso da preparação ou envio da mensagem. Clique no botão encontrado na seção inferior direita deste bloco para acessar os logs de envio e análise. Este bloco só aparece depois que o envio é preparado. Para saber mais sobre isso. Consulte [Confirmação de envio](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**: permite estabelecer o destino principal da mensagem, bem como os perfis de teste. Consulte [Criação de públicos-alvo](../../audiences/using/creating-audiences.md).
* **[!UICONTROL Schedule]**: permite que você especifique a data em que sua mensagem será enviada. Consulte [Agendamento](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**: permite que você defina o conteúdo da mensagem e a visualize. See [Key steps to send a message](../../channels/using/key-steps-to-send-a-message.md).

## Avisos {#warnings}

Em alguns casos, um aviso pode aparecer em um banner amarelo na parte superior do painel de mensagens.

![](assets/delivery_dashboard_warnings.png)

Abaixo está uma lista das mensagens que podem ser exibidas:

* *&quot;A opção de modo de teste SMTP está ativada para este email: nenhuma mensagem será enviada.&quot;*

   For more on this, see [this section](../../administration/using/configuring-email-channel.md#smtp-test-mode).

* *&quot;A conta externa de roteamento foi desabilitada.&quot;*

   Para obter mais informações, consulte Contas [](../../administration/using/external-accounts.md)externas.

* *&quot;As mensagens não podem ser enviadas porque a afinidade IP atual não é tratada por nenhum processo de envio.&quot;*

   Se você vir essa mensagem, há um problema no nível de definição de afinidade IP ou no nível do processo de envio. Entre em contato com o administrador da Adobe.

* *&quot;Este é um modelo de mensagem transacional predefinido. Se quiser modificá-la, você deve duplicá-la e trabalhar na sua cópia.&quot;*

   Alguns desses modelos de mensagem transacional prontos são modelos incorporados de página inicial. For more on this, see [this section](../../channels/using/landing-page-templates.md).

* *&quot;Esta mensagem é um modelo técnico de mensagem transacional. Não é possível modificá-la ou publicá-la.&quot;*

   Este aviso é exibido em modelos de mensagem transacional vazios que não são editáveis. Para obter mais informações sobre mensagens transacionais, consulte [esta seção](../../channels/using/about-transactional-messaging.md).
