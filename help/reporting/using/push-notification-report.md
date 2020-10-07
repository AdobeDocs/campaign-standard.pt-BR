---
title: Relatório de notificação por push
description: Com a notificação por push pronta para uso, saiba mais sobre o sucesso de suas notificações por push.
page-status-flag: never-activated
uuid: 5b121a37-1c09-4749-a409-6989978ddc4c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: list-of-reports
discoiquuid: a425cd59-edfd-42c5-a6bd-38773c353ff0
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 1%

---


# Relatório de notificação por push{#push-notification-report}

>[!CAUTION]
>
>Observe que é necessário arrastar e soltar as **[!UICONTROL Message type]** métricas em suas tabelas para dividir seus dados dependendo dos tipos de delivery, nesse caso, delivery de notificação por push.

O relatório de notificação **por** push fornece detalhes do desempenho de marketing das notificações por push no Adobe Campaign. Esse relatório pronto para uso ajudará você a entender como os usuários interagem com notificações por push, aplicativos móveis e delivery.

Algumas configurações são necessárias no aplicativo móvel para implementar o rastreamento de push. Consulte esta [página](../../administration/using/push-tracking.md) para obter as etapas detalhadas.

![](assets/dynamic_report_push.png)

Cada tabela é representada por números de resumo e gráficos. Você pode alterar a forma como os detalhes são exibidos em suas respectivas configurações de visualização.

A primeira tabela Resumo **do envolvimento da notificação por** push é dividida em três categorias: por dia, por aplicativo móvel e por delivery. Ele contém os dados disponíveis para a reatividade do recipient ao delivery:

* **[!UICONTROL Processed/sent]**: Número total de notificações por push enviadas.
* **[!UICONTROL Delivered]**: Número de notificações por push enviadas com êxito, em relação ao número total de notificações por push enviadas.
* **[!UICONTROL Impressions]**: Número de vezes que uma notificação por push foi entregue ao dispositivo e deixada inalterada no centro de notificações. Na maioria dos casos, o número de impressões deve ser semelhante ao número fornecido. Isso garante que o dispositivo recebeu a mensagem e repassou essas informações para o servidor.
* **[!UICONTROL Unique impressions]**: Número de impressões por recipient.
* **[!UICONTROL Click through rate]**: Porcentagem de usuários que interagiram com a notificação por push.
* **[!UICONTROL Open rate]**: Porcentagem de notificações por push abertas.

![](assets/dynamic_report_push_2.png)

A segunda tabela **Notificações por push Cliques e abertos** é dividida em três categorias: por dia, por aplicativo móvel e por delivery. Ele contém os dados disponíveis para o comportamento do recipient por delivery:

* **[!UICONTROL Impressions]**: Total de notificações por push vistas por recipient.
* **[!UICONTROL Unique impressions]**: Número de impressões por recipient.
* **[!UICONTROL Click]**: Número de vezes que uma notificação por push foi entregue ao dispositivo e clicada pelo usuário. O usuário desejou visualização na notificação, que será movida para o rastreamento Push Open ou ignorará.
* **[!UICONTROL Unique clicks]**: Número de vezes que um usuário único interage com a notificação por push, por exemplo, clica na notificação ou no botão.
* **[!UICONTROL Open]**: O número total de notificações por push entregues ao dispositivo e clicadas pelos usuários, abrindo o aplicativo. Isso é semelhante ao clique de push, exceto que a opção Abrir push não será acionada se a notificação for descartada.
* **[!UICONTROL Unique Opens]**: Número de recipient que abriram o delivery.

