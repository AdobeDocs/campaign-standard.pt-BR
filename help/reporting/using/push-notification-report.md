---
title: Relatório de notificação por push
seo-title: Relatório de notificação por push
description: Relatório de notificação por push
seo-description: Com o relatório de notificação por push out-of-the-box, saiba mais sobre o sucesso das notificações por push.
page-status-flag: nunca ativado
uuid: 5 b 121 a 37-1 c 09-4749-a 409-6989978 ddc 4 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: relatórios
content-type: reference
topic-tags: lista de relatórios
discoiquuid: a 425 cd 59-edfd -42 c 5-a 6 bd -38773 c 353 ff 0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7102ed308f94985f8924a13aab2583e50b6c68e4

---


# Push notification report{#push-notification-report}

>[!CAUTION]
>
>Please note that you have to drag and drop the **[!UICONTROL Message type]** metrics to your tables to split your data depending on your delivery types, in this case push notification deliveries.

The **Push notification** report provides details of marketing performance of push notifications in Adobe Campaign. Esse relatório externo ajudará você a entender como os usuários interagem com notificações por push, aplicativos móveis e entregas.

Some configuration is required in the mobile application to implement push tracking, refer to this [page](https://helpx.adobe.com/campaign/kb/push-tracking.html) for the detailed steps.

![](assets/dynamic_report_push.png)

Cada tabela é representada por números de resumo e gráficos. É possível alterar como os detalhes são mostrados nas respectivas configurações de visualização.

The first table **Push notification Engagement Summary** is split into three categories: by day, by mobile app and by delivery. Ele contém os dados disponíveis para a reatividade do destinatário na entrega:

* **[!UICONTROL Processed/sent]**: O número total de notificações por push enviadas.
* **[!UICONTROL Delivered]**: Número de notificações por push enviadas com sucesso, em relação ao número total de notificações por push enviadas.
* **[!UICONTROL Impressions]**: Número de vezes que uma notificação por push foi entregue ao dispositivo e à esquerda não é exibida na central de notificações. Na maioria dos casos, o número de impressões deve ser similar ao número fornecido. Isso garante que o dispositivo obtenha a mensagem e reviva essas informações de volta para o servidor.
* **[!UICONTROL Unique impressions]**: Número de impressões por destinatário.
* **[!UICONTROL Click through rate]**: Porcentagem de usuários que interagiram com a notificação por push.
* **[!UICONTROL Open rate]**: Porcentagem de notificações por push abertas.

![](assets/dynamic_report_push_2.png)

The second table **Push notification Clicks &amp; opens** is split into three categories: by day, by mobile app and by delivery. Ele contém os dados disponíveis para o comportamento do destinatário por entrega:

* **[!UICONTROL Impressions]**: Total de notificações por push vistas pelos destinatários.
* **[!UICONTROL Unique impressions]**: Número de impressões por destinatário.
* **[!UICONTROL Click]**: Número de vezes que uma notificação por push foi entregue ao dispositivo e clicada pelo usuário. O usuário deseja exibir a notificação, que será movida para o rastreamento de Push aberto ou para descartá-la.
* **[!UICONTROL Unique clicks]**: Número de vezes que um usuário único interage com a notificação por push, por exemplo, cliques na notificação ou no botão.
* **[!UICONTROL Open]**: O número total de notificações por push entregues ao dispositivo e clicado por usuários abrindo o aplicativo. Isso é semelhante ao clique em Push, exceto que um Push aberto não será acionado se a notificação tiver sido fechada.
* **[!UICONTROL Unique Opens]**: Número de destinatários que abriram a entrega.

