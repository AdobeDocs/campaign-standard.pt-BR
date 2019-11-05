---
title: Relatório de notificação por push
description: Com a notificação por push pronta para uso, saiba mais sobre o sucesso de suas notificações por push.
page-status-flag: nunca ativado
uuid: 5b121a37-1c09-4749-a409-6989978dc4c
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: relatório
content-type: referência
topic-tags: lista de relatórios
discoiquuid: a425cd59-edfd-42c5-a6bd-38773c353ff0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Relatório de notificação por push{#push-notification-report}

>[!CAUTION]
>
>Observe que é necessário arrastar e soltar as **[!UICONTROL Message type]** métricas nas tabelas para dividir os dados dependendo dos tipos de entrega, nesse caso, as entregas de notificação por push.

O relatório de notificação **por** push fornece detalhes do desempenho de marketing das notificações por push no Adobe Campaign. Esse relatório pronto para uso ajudará você a entender como os usuários interagem com notificações por push, aplicativos móveis e entregas.

Algumas configurações são necessárias no aplicativo móvel para implementar o rastreamento de push. Consulte esta [página](https://helpx.adobe.com/campaign/kb/push-tracking.html) para obter as etapas detalhadas.

![](assets/dynamic_report_push.png)

Cada tabela é representada por números de resumo e gráficos. Você pode alterar a forma como os detalhes são exibidos em suas respectivas configurações de visualização.

A primeira tabela **Notificações por push Resumo** do envolvimento é dividida em três categorias: por dia, por aplicativo móvel e por entrega. Ele contém os dados disponíveis para a reatividade do destinatário na entrega:

* **[!UICONTROL Processed/sent]**:Número total de notificações por push enviadas.
* **[!UICONTROL Delivered]**:Número de notificações por push enviadas com êxito, em relação ao número total de notificações por push enviadas.
* **[!UICONTROL Impressions]**:Número de vezes que uma notificação por push foi entregue ao dispositivo e deixada inalterada no centro de notificações. Na maioria dos casos, o número de impressões deve ser semelhante ao número fornecido. Isso garante que o dispositivo recebeu a mensagem e repassou essas informações para o servidor.
* **[!UICONTROL Unique impressions]**:Número de impressões por destinatário.
* **[!UICONTROL Click through rate]**:Porcentagem de usuários que interagiram com a notificação por push.
* **[!UICONTROL Open rate]**:Porcentagem de notificações por push abertas.

![](assets/dynamic_report_push_2.png)

A segunda tabela **Notificações por push Cliques e abertos** é dividida em três categorias: por dia, por aplicativo móvel e por entrega. Ele contém os dados disponíveis para o comportamento do destinatário por entrega:

* **[!UICONTROL Impressions]**: Total de notificações por push vistas pelos destinatários.
* **[!UICONTROL Unique impressions]**:Número de impressões por destinatário.
* **[!UICONTROL Click]**: Número de vezes que uma notificação por push foi entregue ao dispositivo e clicada pelo usuário. O usuário deseja exibir a notificação, que será movida para o rastreamento Push Open ou ignorá-la.
* **[!UICONTROL Unique clicks]**:Número de vezes que um usuário único interage com a notificação por push, por exemplo, clica na notificação ou botão.
* **[!UICONTROL Open]**:O número total de notificações por push entregues ao dispositivo e clicadas pelos usuários, abrindo o aplicativo. Isso é semelhante ao clique de push, exceto que a opção Abrir push não será acionada se a notificação for descartada.
* **[!UICONTROL Unique Opens]**:Número de destinatários que abriram a entrega.

