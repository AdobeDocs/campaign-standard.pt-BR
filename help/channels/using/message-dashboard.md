---
solution: Campaign Standard
product: campaign
title: Painel de mensagens
description: Descubra de que o painel de mensagens é composto, incluindo a barra de ação e os vários blocos funcionais.
audience: channels
content-type: reference
topic-tags: about-communication-channels
context-tags: delivery,main
feature: Visão geral
role: Profissional
level: Iniciante
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 6%

---


# Painel de mensagens{#message-dashboard}

O painel de mensagens é um espaço de trabalho composto de ícones diferentes - reagrupados em uma barra de ação - e vários blocos funcionais que permitem estabelecer os parâmetros da mensagem e enviá-la. Estes elementos são apresentados em seguida.

![](assets/delivery_dashboard_2.png)

## Barra cinza {#gray-bar}

A barra cinza agrupa vários ícones vinculados à sua mensagem.

* **[!UICONTROL Summary]**: mostra/oculta as informações principais relacionadas à mensagem.
* **[!UICONTROL Edit properties]**: permite editar os parâmetros  [avançados](../../administration/using/configuring-email-channel.md#list-of-email-properties) da mensagem.
* **[!UICONTROL Reports]**: permite o acesso aos relatórios relacionados à mensagem.

**Tópicos relacionados:**

* [Configuração de canais](../../administration/using/about-channel-configuration.md)
* [Acesso ao relatórios](../../reporting/using/about-dynamic-reports.md)

## Barra de ação {#action-bar}

A barra de ação tem ícones diferentes que permitem interagir com a mensagem.

![](assets/delivery_dashboard_4.png)

Dependendo dos parâmetros que foram configurados e do progresso realizado, alguns ícones podem não estar disponíveis.

* **[!UICONTROL Show proofs]**: mostra/oculta a lista de provas que foram enviadas, caso existam. Esse botão só será ativado depois que você enviar provas.

   Para obter mais informações, consulte [Enviar provas](../../sending/using/sending-proofs.md).

* **[!UICONTROL Send a test]**: permite selecionar o modo de aprovação a ser usado:  **[!UICONTROL Email rendering]** (somente email),  **[!UICONTROL Proof]** ou ambos. Para obter mais informações sobre perfis de teste, consulte [Enviar provas](../../sending/using/sending-proofs.md). Esse botão só será ativado depois que você tiver criado perfis de teste.

* **[!UICONTROL Prepare send]**: começa a preparar o envio. O bloco **[!UICONTROL Deployment]** é exibido e exibe o resultado da preparação. Esse botão só aparecerá depois que o target for inserido. Você pode interromper a preparação a qualquer momento usando o botão correspondente. Para obter mais informações sobre a preparação da mensagem, consulte [Preparação do envio](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**: confirma o envio da mensagem. As estatísticas de envio aparecem no bloco **[!UICONTROL Deployment]** . Esse botão só aparecerá depois que o envio tiver sido preparado. Você pode interromper ou pausar o envio a qualquer momento usando os botões **Stop send** e **[!UICONTROL Pause]**. Para obter mais informações sobre confirmação de envio, consulte [Envio de mensagens](../../sending/using/confirming-the-send.md).

## Bloqueios {#blocks}

A tela principal é composta por blocos diferentes. Clique dentro de um bloco para acessar a tela de parâmetro correspondente:

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**: permite rastrear o progresso da preparação ou envio da mensagem. Clique no botão localizado na seção inferior direita deste bloco para acessar os logs de envio e análise. Esse bloco só aparecerá depois que o envio for preparado. Para saber mais sobre isso. Consulte [Confirmação do envio](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**: O permite estabelecer o público-alvo principal da mensagem e os perfis de teste. Consulte [Criação de públicos-alvo](../../audiences/using/creating-audiences.md).
* **[!UICONTROL Schedule]**: permite especificar a data em que a mensagem será enviada. Consulte [Agendamento](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**: permite definir o conteúdo da mensagem e visualizá-la. Consulte [Etapas principais para enviar uma mensagem](../../channels/using/key-steps-to-send-a-message.md).

## Avisos {#warnings}

Em alguns casos, um aviso pode aparecer em um banner amarelo na parte superior do painel da mensagem.

![](assets/delivery_dashboard_warnings.png)

Abaixo está uma lista das mensagens que podem ser exibidas:

* *&quot;A opção SMTP test mode está habilitada para este email: nenhuma mensagem será enviada.&quot;*

   Para obter mais informações, consulte [esta seção](../../administration/using/configuring-email-channel.md#smtp-test-mode).

* *&quot;A conta externa de roteamento foi desabilitada.&quot;*

   Para obter mais informações, consulte [Contas externas](../../administration/using/external-accounts.md).

* *&quot;As mensagens não podem ser enviadas porque a afinidade IP atual não é tratada por nenhum processo de envio.&quot;*

   Se você vir esta mensagem, há um problema no nível de definição de afinidade IP ou no nível do processo de envio. Entre em contato com o administrador do Adobe 

* *&quot;Este é um template de mensagem transacional pronto para uso. Se quiser modificá-lo, você deve duplicá-lo e trabalhar em sua cópia.&quot;*

   Alguns desses templates de mensagem transacional prontos são templates de página de aterrissagem integrados. Para obter mais informações, consulte [esta seção](../../channels/using/landing-page-templates.md).

* *&quot;Essa mensagem é um template de mensagem transacional técnica. Não é possível modificá-lo ou publicá-lo.&quot;*

   Esse aviso é exibido em templates de mensagem transacional vazios que não são editáveis. Para obter mais informações sobre mensagens transacionais, consulte [esta seção](../../channels/using/getting-started-with-transactional-msg.md).
