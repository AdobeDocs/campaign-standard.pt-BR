---
solution: Campaign Standard
product: campaign
title: Execução e monitoramento de mensagens transacionais
description: Saiba mais sobre a execução de mensagens transacionais e descubra como monitorar mensagens transacionais.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Mensagens transacionais
role: Profissional
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 63%

---


# Execução e monitoramento de mensagens transacionais {#transactional-messaging-execution}

## Delivery de execução de mensagem transacional {#transactional-message-execution-delivery}

Quando a mensagem é publicada e a integração do site é concluída, quando um evento é acionado, ele é atribuído a um delivery de execução.

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

Um **execution delivery** é uma mensagem técnica não acionável e não funcional criada uma vez por mês para cada mensagem transacional e cada vez que uma mensagem transacional é editada e publicada novamente.

**Tópicos relacionados**:
* [Publicação de mensagem transacional](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)
* [Integrar o acionamento do evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)

## Processo de nova tentativa de mensagens transacionais {#transactional-message-retry-process}

Uma mensagem transacional temporariamente não entregue está sujeita a tentativas automáticas que são executadas até que o delivery expire. Para mais informações sobre a duração do delivery, consulte [Parâmetros do período de validade](../../administration/using/configuring-email-channel.md#validity-period-parameters).

Quando uma mensagem transacional não é enviada, há dois sistemas de repetição:

* No nível de mensagens transacionais, uma mensagem transacional pode falhar antes de ser atribuída a um delivery de execução, ou seja, entre a recepção do evento e a preparação do delivery. Consulte [Processo de nova tentativa de processamento de eventos](#event-processing-retry-process).
* No nível do processo de envio, depois que o evento é atribuído a um delivery de execução, a mensagem transacional pode falhar devido a um erro temporário. Consulte [Processo de nova tentativa de envio de mensagens](#message-sending-retry-process).

### Processo de nova tentativa de processamento de eventos {#event-processing-retry-process}

Quando um evento é acionado, ele é atribuído a um delivery de execução. Se o evento não puder ser atribuído a um delivery de execução, o processamento do evento será adiado. As tentativas são executadas até que sejam atribuídas a um novo delivery de execução.

>[!NOTE]
>
>Um evento adiado não é exibido nos logs de envio da mensagem transacional, pois ela ainda não foi atribuída a um delivery de execução.

Por exemplo, o evento não pôde ser atribuído a um delivery de execução porque seu conteúdo não estava correto. Houve um problema com direitos de acesso ou marca, um erro foi detectado ao aplicar regras de tipologia etc. Nesse caso, você pode pausar a mensagem, editá-la para corrigir o problema e publicá-la novamente. O sistema de nova tentativa a atribuirá a um novo delivery de execução.

### Processo de nova tentativa de envio de mensagem {#message-sending-retry-process}

Depois que o evento tiver sido atribuído a um delivery de execução, a mensagem transacional poderá falhar devido a um erro temporário, se a caixa de correio do recipient estiver cheia, por exemplo. Para obter mais informações, consulte [Tentativas após uma falha temporária de delivery](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>Quando um evento é atribuído a um delivery de execução, ele é exibido nos logs de envio desse delivery de execução e apenas no momento. Os deliveries com falha são exibidos na guia **[!UICONTROL Execution list]** dos logs de envio de mensagem transacional.

### Repetir as limitações do processo {#limitations}

**Envio de atualização de logs**

No processo de repetição, os logs de envio do novo delivery de execução não são atualizados imediatamente (a atualização é executada por meio de um fluxo de trabalho programado). Isso significa que a mensagem pode estar em status **[!UICONTROL Pending]** mesmo se o evento transacional tiver sido processado pelo novo delivery de execução.

**Delivery de execução com falha**

Não é possível interromper um delivery de execução. No entanto, se o delivery de execução atual falhar, um novo será criado assim que um novo evento for recebido, e todos os novos eventos serão processados por esse novo delivery de execução. Nenhum novo evento é processado pelo delivery de execução com falha.

Se alguns eventos já atribuídos a um delivery de execução tiverem sido adiados como parte do processo de nova tentativa e esse delivery falhar, o sistema de nova tentativa não atribuirá os eventos adiados ao novo delivery de execução, o que significa que esses eventos são perdidos. Verifique os [logs do delivery](#monitoring-transactional-message-delivery) para ver os recipients que podem ter sido afetados.

## Monitoramento de mensagens transacionais {#monitoring-transactional-message-delivery}

Para monitorar uma mensagem transacional, é necessário acessar os [deliveries de execução](#transactional-message-execution-delivery) correspondentes.

1. Para exibir o log de delivery da mensagem, clique no ícone na parte inferior direita do bloco **[!UICONTROL Deployment]**.

   ![](assets/message-center_access_logs.png)

1. Clique na guia **[!UICONTROL Execution list]**.

   ![](assets/message-center_execution_tab.png)

1. Selecione o delivery de execução de sua escolha.

   ![](assets/message-center_execution_delivery.png)

1. Clique novamente no ícone na parte inferior direita do bloco **[!UICONTROL Deployment]**.

   ![](assets/message-center_execution_access_logs.png)

   Para cada delivery de execução, você pode consultar os logs de delivery como faria para um delivery padrão. Para obter mais informações sobre como acessar e usar os logs, consulte [Monitoring a delivery](../../sending/using/monitoring-a-delivery.md).

### Especificidades de mensagens transacionais baseadas em perfil {#profile-transactional-message-monitoring}

Para mensagens transacionais baseadas em perfil, você pode monitorar as seguintes informações de perfil.

Selecione a guia **[!UICONTROL Sending logs]**. Na coluna **[!UICONTROL Status]**, **[!UICONTROL Sent]** indica que um perfil foi aceito.

![](assets/message-center_marketing_sending_logs.png)

Selecione a guia **[!UICONTROL Exclusions logs]** para exibir os recipients que foram excluídos do público-alvo da mensagem, como endereços em lista de bloqueios.

![](assets/message-center_marketing_exclusion_logs.png)

Para os perfis recusados, a regra de tipologia **[!UICONTROL Address on denylist]** exclui o recipient correspondente.

Essa regra faz parte de uma tipologia específica aplicável a todas as mensagens transacionais baseadas na tabela **[!UICONTROL Profile]**.

![](assets/message-center_marketing_typology.png)

**Tópicos relacionados**:

* [Sobre tipologias e regras de tipologia](../../sending/using/about-typology-rules.md)
* [Monitorar um delivery](../../sending/using/monitoring-a-delivery.md)
