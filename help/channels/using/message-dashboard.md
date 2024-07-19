---
title: Painel de mensagens
description: Descubra do que o painel de mensagens é composto, incluindo a barra de ação e os vários blocos funcionais.
audience: channels
content-type: reference
topic-tags: about-communication-channels
context-tags: delivery,main
feature: Overview
role: User
level: Beginner
exl-id: 886aae39-2029-471c-b4d1-c6ca57d0e568
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 4%

---

# Painel de mensagens{#message-dashboard}

O painel de mensagens é um espaço de trabalho composto por diferentes ícones, reagrupados em uma barra de ação, e vários blocos funcionais que permitem estabelecer os parâmetros da mensagem e enviá-la. Esses elementos são apresentados a seguir.

![](assets/delivery_dashboard_2.png)

## Barra cinza {#gray-bar}

A barra cinza reagrupa vários ícones vinculados à mensagem.

* **[!UICONTROL Summary]**: mostra/oculta as informações principais relacionadas à mensagem.
* **[!UICONTROL Edit properties]**: permite editar os [parâmetros avançados](../../administration/using/configuring-email-channel.md#list-of-email-properties) da mensagem.
* **[!UICONTROL Reports]**: fornece acesso aos relatórios relacionados à mensagem.

**Tópicos relacionados:**

* [Configuração de canais](../../administration/using/about-channel-configuration.md)
* [Acesso a relatórios](../../reporting/using/about-dynamic-reports.md)

## Barra de ação {#action-bar}

A barra de ação tem ícones diferentes que permitem interagir com a mensagem.

![](assets/delivery_dashboard_4.png)

Dependendo dos parâmetros configurados e do progresso feito, alguns ícones podem não estar disponíveis.

* **[!UICONTROL Show proofs]**: mostra/oculta a lista de provas que foram enviadas, se existirem. Esse botão só será ativado depois que você enviar provas.

  Para obter mais informações, consulte [Envio de provas](../../sending/using/sending-proofs.md).

* **[!UICONTROL Send a test]**: permite selecionar o modo de aprovação a ser usado: **[!UICONTROL Email rendering]** (somente email), **[!UICONTROL Proof]** ou ambos. Para obter mais informações sobre perfis de teste, consulte [Enviar provas](../../sending/using/sending-proofs.md). Esse botão só será ativado depois que você criar perfis de teste.

* **[!UICONTROL Prepare send]**: começa a preparar o envio. O bloco **[!UICONTROL Deployment]** é exibido e exibe o resultado da preparação. Esse botão só será exibido depois que o target for inserido. É possível interromper a preparação a qualquer momento usando o botão correspondente. Para obter mais informações sobre a preparação da mensagem, consulte [Preparação do envio](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**: confirma o envio da mensagem. As estatísticas de envio aparecem no bloco **[!UICONTROL Deployment]**. Esse botão só aparece depois que o envio é preparado. Você pode interromper ou pausar o envio a qualquer momento usando os botões **Parar envio** e **[!UICONTROL Pause]**. Para obter mais informações sobre a confirmação do envio, consulte [Envio de mensagens](../../sending/using/confirming-the-send.md).

## Blocos {#blocks}

A tela principal é composta por blocos diferentes. Clique dentro de um bloco para acessar a tela de parâmetros correspondente:

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**: permite acompanhar o progresso da preparação ou envio da mensagem. Clique no botão encontrado na seção inferior direita deste bloco para acessar os logs de envio e análise. Esse bloco só será exibido depois que o envio tiver sido preparado. Para obter mais informações. Consulte [Confirmando envio](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**: permite estabelecer o destino principal da mensagem, bem como os perfis de teste. Consulte [Criação de públicos-alvo](../../audiences/using/creating-audiences.md).
* **[!UICONTROL Schedule]**: permite especificar a data em que a mensagem será enviada. Consulte [Agendando](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**: permite que você defina o conteúdo da mensagem e a visualize. Consulte [Etapas principais para enviar uma mensagem](../../channels/using/key-steps-to-send-a-message.md).

## Avisos {#warnings}

Em alguns casos, um aviso pode aparecer em um banner amarelo na parte superior do painel de mensagem.

![](assets/delivery_dashboard_warnings.png)

Abaixo está uma lista das mensagens que podem ser exibidas:

* *&quot;A opção de modo de teste SMTP está habilitada para este email: nenhuma mensagem será enviada.&quot;*

  Para obter mais informações, consulte [esta seção](../../administration/using/configuring-email-channel.md#smtp-test-mode).

* *&quot;A conta externa de roteamento foi desabilitada.&quot;*

  Para obter mais informações, consulte [Contas externas](../../administration/using/external-accounts.md).

* *&quot;As mensagens não podem ser enviadas porque a afinidade de IP atual não é tratada por nenhum processo de envio.&quot;*

  Se você vir essa mensagem, há um problema no nível de definição de afinidade de IP ou no nível do processo de envio. Entre em contato com o administrador do Adobe.

* *&quot;Este é um modelo de mensagem transacional pronto para uso. Se quiser modificá-la, duplique-a e trabalhe na sua cópia.&quot;*

  Alguns desses templates de mensagem transacional prontos para uso são templates de landing page incorporados. Para obter mais informações, consulte [esta seção](../../channels/using/landing-page-templates.md).

* *&quot;Esta mensagem é um modelo de mensagem técnica transacional. Não é possível modificá-lo ou publicá-lo.&quot;*

  Esse aviso é exibido em modelos de mensagem transacional vazios que não são editáveis. Para obter mais informações sobre mensagens transacionais, consulte [esta seção](../../channels/using/getting-started-with-transactional-msg.md).
