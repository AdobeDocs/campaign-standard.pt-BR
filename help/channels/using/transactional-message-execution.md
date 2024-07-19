---
title: Execução e monitoramento de mensagens transacionais
description: Saiba mais sobre a execução de mensagens transacionais e descubra como monitorar mensagens transacionais.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 4cea7207-469c-46c5-9921-ae2f8f12d141
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 61%

---

# Execução e monitoramento de mensagens transacionais {#transactional-messaging-execution}

## Entrega de execução de mensagem transacional {#transactional-message-execution-delivery}

Quando a mensagem for publicada e a integração do site estiver concluída, quando um evento for acionado, ele será atribuído a um delivery de execução.

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

Uma **entrega de execução** é uma mensagem técnica não acionável e não funcional criada uma vez por mês para cada mensagem transacional e cada vez que uma mensagem transacional é editada e publicada novamente.

**Tópicos relacionados**:
* [Publicação de mensagem transacional](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)
* [Integrar o acionamento de eventos](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)

## Processo de nova tentativa de mensagem transacional {#transactional-message-retry-process}

Uma mensagem transacional temporariamente não entregue está sujeita a tentativas automáticas que são executadas até que o delivery expire. Para mais informações sobre a duração da entrega, consulte [Parâmetros do período de validade](../../administration/using/configuring-email-channel.md#validity-period-parameters).

Quando uma mensagem transacional não é enviada, há dois sistemas de repetição:

* No nível de mensagens transacionais, uma mensagem transacional pode falhar antes de ser atribuída a uma entrega de execução, ou seja, entre a recepção do evento e a preparação da entrega. Consulte [Processo de nova tentativa de processamento de eventos](#event-processing-retry-process).
* No nível do processo de envio, depois que o evento é atribuído a uma entrega de execução, a mensagem transacional pode falhar devido a um erro temporário. Consulte [Processo de nova tentativa de envio de mensagens](#message-sending-retry-process).

### Processo de nova tentativa de processamento de evento {#event-processing-retry-process}

Quando um evento é acionado, ele é atribuído a um delivery de execução. Se o evento não puder ser atribuído a uma entrega de execução, o processamento do evento será adiado. As tentativas são executadas até que sejam atribuídas a uma nova entrega de execução.

>[!NOTE]
>
>Um evento adiado não é exibido nos logs de envio da mensagem transacional, pois ela ainda não foi atribuída a uma entrega de execução.

Por exemplo, o evento não pôde ser atribuído a uma entrega de execução porque seu conteúdo não estava correto. Houve um problema com direitos de acesso ou marca, um erro foi detectado ao aplicar regras de tipologia etc. Nesse caso, você pode pausar a mensagem, editá-la para corrigir o problema e publicá-la novamente. O sistema de nova tentativa a atribuirá a uma nova entrega de execução.

### Processo de nova tentativa de envio de mensagem {#message-sending-retry-process}

Depois que o evento tiver sido atribuído a uma entrega de execução, a mensagem transacional poderá falhar devido a um erro temporário, se a caixa de correio do destinatário estiver cheia, por exemplo. Para obter mais informações, consulte [Tentativas após uma falha temporária de entrega](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>Quando um evento é atribuído a uma entrega de execução, ele é exibido nos logs de envio dessa entrega de execução e apenas no momento. Os deliveries com falha são exibidos na guia **[!UICONTROL Execution list]** dos logs de envio da mensagem transacional.

### Limitações do processo de repetição {#limitations}

**Envio de atualização de logs**

No processo de repetição, os logs de envio da nova entrega de execução não são atualizados imediatamente (a atualização é executada por meio de um fluxo de trabalho programado). Isso significa que a mensagem pode estar em status **[!UICONTROL Pending]** mesmo se o evento transacional tiver sido processado pela nova entrega de execução.

**Entrega de execução com falha**

Não é possível interromper uma entrega de execução. No entanto, se a entrega de execução atual falhar, uma nova será criada assim que um novo evento for recebido, e todos os novos eventos serão processados por essa nova entrega de execução. Nenhum novo evento é processado pela entrega de execução com falha.

Se alguns eventos já atribuídos a um delivery de execução tiverem sido adiados como parte do processo de nova tentativa e esse delivery falhar, o sistema de nova tentativa não atribuirá os eventos adiados ao novo delivery de execução, o que significa que esses eventos são perdidos. Verifique os [logs do delivery](#monitoring-transactional-message-delivery) para ver os destinatários que podem ter sido afetados.

## Monitorar mensagens transacionais {#monitoring-transactional-message-delivery}

Para monitorar uma mensagem transacional, você precisa acessar os [deliveries de execução](#transactional-message-execution-delivery) correspondentes.

1. Para exibir o log de entrega da mensagem, clique no ícone na parte inferior direita do bloco **[!UICONTROL Deployment]**.

   ![](assets/message-center_access_logs.png)

1. Clique na guia **[!UICONTROL Execution list]**.

   ![](assets/message-center_execution_tab.png)

1. Selecione o delivery de execução de sua escolha.

   ![](assets/message-center_execution_delivery.png)

1. Clique novamente no ícone na parte inferior direita do bloco **[!UICONTROL Deployment]**.

   ![](assets/message-center_execution_access_logs.png)

   Para cada delivery de execução, você pode consultar os logs do delivery da mesma forma que faria para um delivery padrão. Para obter mais informações sobre como acessar e usar os logs, consulte [Monitoramento de uma entrega](../../sending/using/monitoring-a-delivery.md).

### Especificidades de mensagem transacional baseada em perfil {#profile-transactional-message-monitoring}

Para mensagens transacionais baseadas em perfil, é possível monitorar as seguintes informações de perfil.

Selecione a guia **[!UICONTROL Sending logs]**. Na coluna **[!UICONTROL Status]**, **[!UICONTROL Sent]** indica que um perfil foi aceito.

![](assets/message-center_marketing_sending_logs.png)

Selecione a guia **[!UICONTROL Exclusions logs]** para exibir os destinatários que foram excluídos do público-alvo da mensagem, como endereços na inclui na lista de bloqueios.

![](assets/message-center_marketing_exclusion_logs.png)

Para os perfis recusados, a regra de tipologia **[!UICONTROL Address on denylist]** exclui o destinatário correspondente.

Essa regra faz parte de uma tipologia específica aplicável a todas as mensagens transacionais baseadas na tabela **[!UICONTROL Profile]**.

![](assets/message-center_marketing_typology.png)

**Tópicos relacionados**:

* [Sobre tipologias e regras de tipologia](../../sending/using/about-typology-rules.md)
* [Monitoramento de uma entrega](../../sending/using/monitoring-a-delivery.md)
