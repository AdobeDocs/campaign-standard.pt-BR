---
title: Relatório de notificação por push
description: With the Push notification out-of-the-box report, learn about the success of your push notifications.
audience: reporting
content-type: reference
topic-tags: list-of-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: acfe0b9c-77a4-46ad-8151-7bf9c21fa4b0
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 1%

---

# Relatório de notificação por push{#push-notification-report}

>[!CAUTION]
>
>Observe que você precisa arrastar e soltar a variável **[!UICONTROL Message type]** para suas tabelas para dividir seus dados dependendo dos tipos de delivery, nesse caso, os deliveries de notificação por push.

O **Notificação por push** fornece detalhes do desempenho de marketing das notificações por push no Adobe Campaign. Esse relatório pronto para uso ajuda você a entender como os usuários interagem com notificações por push, aplicativos móveis e deliveries.

Algumas configurações são necessárias no aplicativo móvel para implementar o rastreamento por push; consulte esta seção [página](../../administration/using/push-tracking.md) para as etapas detalhadas.

![](assets/dynamic_report_push.png)

Each table is represented by summary numbers and charts. You can change how the details are shown in their respective visualization settings.

A primeira tabela **Resumo de Envolvimento da Notificação por Push** divide-se em três categorias: por dia, por aplicativo móvel e por delivery. Ele contém os dados disponíveis para a reatividade do recipient no delivery:

* **[!UICONTROL Processed/sent]**: Número total de notificações por push enviadas.
* **[!UICONTROL Delivered]**: Number of push notifications successfully sent, in relation to the total number of sent push notifications.
* **[!UICONTROL Impressions]**: Número de vezes que uma notificação por push foi entregue ao dispositivo e deixou-o intocado no centro de notificações. Na maioria dos casos, o número de impressões deve ser semelhante ao número entregue. This ensures that the device got the message and relayed that information back to the server.
* **[!UICONTROL Unique impressions]**: Number of impressions by recipient.
* **[!UICONTROL Click through rate]**: Porcentagem de usuários que interagiram com a notificação por push.
* **[!UICONTROL Open rate]**: Porcentagem de notificações por push abertas.

![](assets/dynamic_report_push_2.png)

The second table **Push notification Clicks &amp; opens** is split into three categories: by day, by mobile app and by delivery. Ele contém os dados disponíveis para o comportamento do recipient por delivery:

* **[!UICONTROL Impressions]**: Total de notificações por push vistas pelos recipients.
* **[!UICONTROL Unique impressions]**: Número de impressões por recipient.
* **[!UICONTROL Click]**: Número de vezes que uma notificação por push foi entregue ao dispositivo e clicada pelo usuário. O usuário deseja exibir a notificação, que será movida para o rastreamento Push Open ou ignorá-la.
* **[!UICONTROL Unique clicks]**: Número de vezes que um usuário único interage com a notificação por push, por exemplo, cliques na notificação ou no botão.
* **[!UICONTROL Open]**: Número total de notificações por push enviadas ao dispositivo e clicadas pelos usuários, abrindo o aplicativo. Isso é semelhante ao Clique de push, exceto que a opção Abrir por push não será acionada se a notificação for descartada.
* **[!UICONTROL Unique Opens]**: Número de recipients que abriram o delivery.
