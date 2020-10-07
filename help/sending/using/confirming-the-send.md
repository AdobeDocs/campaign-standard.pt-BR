---
title: Confirmação do envio
description: Saiba como finalizar a preparação da mensagem.
page-status-flag: never-activated
uuid: 1eaecb32-ffd2-45d0-a8b4-f97bee59a1bd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
discoiquuid: 8bb160b1-7de9-4c1f-bb89-b2e5fdafed41
context-tags: delivery,deployment,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 100%

---


# Confirmação do envio{#confirming-the-send}

Quando terminar de preparar as mensagens e as etapas de aprovação forem executadas, você poderá enviá-las. Para saber mais sobre a preparação de mensagens, consulte [Preparação do envio](../../sending/using/preparing-the-send.md).

Somente os usuários com a função **[!UICONTROL Start deliveries]** podem confirmar o envio. Para saber mais, consulte a seção [Lista de funções](../../administration/using/list-of-roles.md).

Os usuários sem essa função verão a seguinte mensagem:

![](assets/confirm_delivery_2.png)

Para enviar o delivery, clique no botão **[!UICONTROL Confirm send]** localizado na barra de ação da mensagem.

![](assets/confirm_delivery.png)

Você deverá finalizar o envio definitivamente clicando no botão **[!UICONTROL OK]**.

![](assets/confirm_delivery1.png)

A mensagem é enviada.

>[!NOTE]
>
>Se a mensagem estiver programada, ela será enviada no horário especificado. Para saber mais sobre como programar mensagens, consulte [esta seção](../../sending/using/about-scheduling-messages.md).

Se estiver usando um delivery recorrente sem nenhum período de agregação, você poderá solicitar uma confirmação antes de o delivery ser enviado. Para isso, abra o bloco **[!UICONTROL Schedule]** do painel de delivery e ative a opção dedicada.

![](assets/confirmation_recurring_deliveries.png)

O bloco **[!UICONTROL Deployment]** mostra o progresso do envio.

Depois que a mensagem é enviada aos contatos, a zona **[!UICONTROL Deployment]** mostra seus KPIs (indicadores principais de desempenho), inclusive:

* Número de mensagens para delivery
* Número de mensagens enviadas
* A porcentagem de mensagens entregues
* A porcentagem de rejeições e erros
* A porcentagem de mensagens abertas
* A porcentagem de cliques nas mensagens (para emails)

   >[!NOTE]
   >
   >A **[!UICONTROL Open rate]** e a **[!UICONTROL Click-through rate]** são atualizadas a cada hora.

![](assets/sending_delivery.png)

Se os KPIs demorarem para atualizar ou não levarem em conta os resultados dos logs de envio, clique no botão **[!UICONTROL Compute stats]** da janela **[!UICONTROL Deployment]**.

![](assets/sending_delivery7.png)

A mensagem pode ser exibida no histórico de um dos perfis de clientes que fazem parte do público-alvo. Consulte [Perfil de cliente integrado](../../audiences/using/integrated-customer-profile.md).

Depois que uma mensagem é enviada, você poderá rastrear o comportamento dos recipients e monitorá-la para medir o impacto. Para saber mais, consulte estas seções:

* [Rastreamento de mensagens](../../sending/using/tracking-messages.md)
* [Monitoramento de um delivery](../../sending/using/monitoring-a-delivery.md)

