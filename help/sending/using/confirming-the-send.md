---
title: Confirmar o envio
description: Saiba como finalizar a preparação da mensagem.
page-status-flag: nunca ativado
uuid: 1eaecb32-ffd2-45d0-a8b4-f97bee59a1bd
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: envio
content-type: referência
topic-tags: enviar e rastrear mensagens
discoiquuid: 8bb160b1-7de9-4c1f-bb89-b2e5fdafed41
context-tags: entrega,implantação,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Confirmar o envio{#confirming-the-send}

Quando terminar de preparar suas mensagens e as etapas de aprovação tiverem sido executadas, você poderá enviá-las. Para obter mais informações sobre a preparação de mensagens, consulte [Preparação do envio](../../sending/using/preparing-the-send.md).

Somente os usuários com a **[!UICONTROL Start deliveries]** função podem confirmar o envio. Para obter mais informações, consulte a seção [Lista de funções](../../administration/using/list-of-roles.md) .

Os usuários sem essa função verão a seguinte mensagem:

![](assets/confirm_delivery_2.png)

Para enviar sua entrega, clique no **[!UICONTROL Confirm send]** botão encontrado na barra de ação da mensagem.

![](assets/confirm_delivery.png)

Você será solicitado a finalizar o envio definitivamente clicando no **[!UICONTROL OK]** botão.

![](assets/confirm_delivery1.png)

A mensagem está sendo enviada.

>[!NOTE]
>
>Se a mensagem estiver programada, ela será enviada quando a hora de envio for atingida. For more on scheduling messages, refer to [this section](../../sending/using/about-scheduling-messages.md).

Se você estiver usando uma entrega recorrente sem período de agregação, poderá solicitar confirmação antes que a entrega seja enviada. Para fazer isso, abra o **[!UICONTROL Schedule]** bloco do painel de entrega e ative a opção dedicada.

![](assets/confirmation_recurring_deliveries.png)

O **[!UICONTROL Deployment]** bloco mostra o progresso do envio.

Depois que a mensagem é enviada aos contatos, a **[!UICONTROL Deployment]** zona mostra seus dados KPIs (Indicador-chave de desempenho), incluindo:

* O número de mensagens a serem entregues
* O número de mensagens enviadas
* A porcentagem de mensagens entregues
* A porcentagem de rejeições e erros
* A porcentagem de mensagens abertas
* A porcentagem de cliques nas mensagens (para emails)

   >[!NOTE]
   >
   >O **[!UICONTROL Open rate]** e **[!UICONTROL Click-through rate]** são atualizados a cada hora.

![](assets/sending_delivery.png)

Se os KPIs levarem muito tempo para atualizar ou não levarem em conta os resultados dos logs de envio, clique no **[!UICONTROL Compute stats]** botão na **[!UICONTROL Deployment]** janela.

![](assets/sending_delivery7.png)

A mensagem pode ser visualizada no histórico de um dos perfis do cliente que faz parte do público-alvo. See [Integrated customer profile](../../audiences/using/integrated-customer-profile.md).

Depois que uma mensagem é enviada, você pode rastrear o comportamento de seus destinatários e monitorá-la para medir seu impacto. Para obter mais informações, consulte essas seções.

* [Rastreamento de mensagens](../../sending/using/tracking-messages.md)
* [Monitoramento de uma entrega](../../sending/using/monitoring-a-delivery.md)

