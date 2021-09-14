---
title: Relatório de notificação por push
description: Com o relatório de notificação por push pronto para uso, saiba mais sobre o sucesso das notificações por push.
audience: reporting
content-type: reference
topic-tags: list-of-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: acfe0b9c-77a4-46ad-8151-7bf9c21fa4b0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 1%

---

# Relatório de notificação por push{#push-notification-report}

>[!CAUTION]
>
>Observe que é necessário arrastar e soltar as métricas **[!UICONTROL Message type]** em suas tabelas para dividir os dados dependendo dos tipos de delivery, nesse caso, os deliveries de notificação por push.

O relatório **Notificação por push** fornece detalhes do desempenho de marketing das notificações por push no Adobe Campaign. Esse relatório pronto para uso ajudará você a entender como os usuários interagem com notificações por push, aplicativos móveis e deliveries.

Algumas configurações são necessárias no aplicativo móvel para implementar o rastreamento por push, consulte esta [página](../../administration/using/push-tracking.md) para obter as etapas detalhadas.

![](assets/dynamic_report_push.png)

Cada tabela é representada por números de resumo e gráficos. Você pode alterar como os detalhes são mostrados em suas respectivas configurações de visualização.

A primeira tabela **Resumo do envolvimento da notificação por push** é dividida em três categorias: por dia, por aplicativo móvel e por delivery. Ele contém os dados disponíveis para a reatividade do recipient no delivery:

* **[!UICONTROL Processed/sent]**: Número total de notificações por push enviadas.
* **[!UICONTROL Delivered]**: Número de notificações por push enviadas com êxito em relação ao número total de notificações por push enviadas.
* **[!UICONTROL Impressions]**: Número de vezes que uma notificação por push foi entregue ao dispositivo e deixou-o intocado no centro de notificações. Na maioria dos casos, o número de impressões deve ser semelhante ao número entregue. Isso garante que o dispositivo receba a mensagem e reenvie essas informações de volta para o servidor.
* **[!UICONTROL Unique impressions]**: Número de impressões por recipient.
* **[!UICONTROL Click through rate]**: Porcentagem de usuários que interagiram com a notificação por push.
* **[!UICONTROL Open rate]**: Porcentagem de notificações por push abertas.

![](assets/dynamic_report_push_2.png)

A segunda tabela **Push notification Clicks &amp; opens** é dividida em três categorias: por dia, por aplicativo móvel e por delivery. Ele contém os dados disponíveis para o comportamento do recipient por delivery:

* **[!UICONTROL Impressions]**: Total de notificações por push vistas pelos recipients.
* **[!UICONTROL Unique impressions]**: Número de impressões por recipient.
* **[!UICONTROL Click]**: Número de vezes que uma notificação por push foi entregue ao dispositivo e clicada pelo usuário. O usuário deseja exibir a notificação, que será movida para o rastreamento Push Open ou ignorá-la.
* **[!UICONTROL Unique clicks]**: Número de vezes que um usuário único interage com a notificação por push, por exemplo, cliques na notificação ou no botão.
* **[!UICONTROL Open]**: Número total de notificações por push enviadas ao dispositivo e clicadas pelos usuários, abrindo o aplicativo. Isso é semelhante ao Clique de push, exceto que a opção Abrir por push não será acionada se a notificação for descartada.
* **[!UICONTROL Unique Opens]**: Número de recipients que abriram o delivery.
