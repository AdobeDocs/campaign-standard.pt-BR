---
solution: Campaign Standard
product: campaign
title: Mensagens transacionais de evento
description: Saiba como criar e publicar uma mensagem transacional de evento.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 4e157a582de836fa325d95593491c756209b205e
workflow-type: tm+mt
source-wordcount: '1352'
ht-degree: 77%

---


# Ciclo de vida do mensagen transacional {#publishing-transactional-message}

Quando [mensagen transacional](../../channels/using/editing-transactional-message.md) estiver pronto para ser enviado, ele poderá ser publicado.

As etapas para testar, publicar, pausar, cancelar a publicação e excluir um evento estão detalhadas abaixo. Esta seção também descreve o processo de repetição de mensagens transacionais.

## Processo de publicação de mensagens transacionais {#transactional-messaging-pub-process}

O gráfico abaixo ilustra o processo geral de publicação de mensagens transacionais.

![](assets/message-center_pub-process.png)

Para obter mais informações sobre como publicar um mensagen transacional, consulte [esta seção](#publishing-a-transactional-message).
Para obter mais informações sobre como pausar um mensagen transacional, consulte [esta seção](#suspending-a-transactional-message-publication).
Para obter mais informações sobre como cancelar a publicação de um mensagen transacional, consulte [esta seção](#unpublishing-a-transactional-message).

Para obter mais informações sobre como publicar e desfazer a publicação de um evento, consulte [esta seção](../../channels/using/publishing-transactional-event.md).

## Teste de mensagem transacional {#testing-a-transactional-message}

Primeiro, é necessário criar um perfil de teste específico que permita verificar o mensagen transacional corretamente.

### Definição de um perfil de teste específico {#defining-specific-test-profile}

Defina um perfil de teste que será vinculado ao seu evento, o que permitirá que você pré-visualização sua mensagem e envie uma prova relevante.

1. No painel do mensagen transacional, clique no botão **[!UICONTROL Create test profile]**.

   ![](assets/message-center_test-profile.png)

1. Especifique as informações para enviar no formato JSON, na seção **[!UICONTROL Event data used for personalization]**. Esse é o conteúdo que será usado ao visualizar a mensagem e quando o perfil de teste receber a prova.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >Você também pode inserir as informações relacionadas à tabela do perfil. Consulte [Enriquecendo o evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)<!--and [Personalizing a transactional message](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)-->.

1. Depois de criado, o perfil de teste será pré-especificado no mensagen transacional. Clique no bloco **[!UICONTROL Test profiles]** da mensagem para verificar o público-alvo da prova.

   ![](assets/message-center_5.png)

Você também pode criar um novo perfil de teste ou usar um que já existe no menu **[!UICONTROL Test profiles]**. Para fazer isso:

1. Clique no logotipo **[!UICONTROL Adobe Campaign]**, no canto superior esquerdo, em seguida, selecione **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. Na seção **[!UICONTROL Event]**, selecione o evento que você acabou de criar. Neste exemplo, selecione &quot;Abandono de carrinho (EVTcartAbandonment)&quot;.
1. Especifique as informações para enviar no formato JSON na caixa de texto **[!UICONTROL Event data]**.

   ![](assets/message-center_3.png)

1. Salve as alterações.
1. Acesse a mensagem que você criou e selecione o perfil de teste atualizado.

**Tópicos relacionados:**

* [Gerenciamento de perfis de teste](../../audiences/using/managing-test-profiles.md)
* [Criação de públicos-alvo](../../audiences/using/creating-audiences.md)

### Envio de uma prova {#sending-proof}

Depois de criar um ou mais perfis de teste específicos e salvar seu mensagen transacional, você pode enviar uma prova para testá-lo.

![](assets/message-center_10.png)

As etapas para enviar uma prova estão detalhadas na seção [Enviar provas](../../sending/using/sending-proofs.md).

## Publicação de mensagem transacional {#publishing-a-transactional-message}

Depois de verificar a mensagem transacional, você pode publicá-la.

![](assets/message-center_12.png)

Agora, assim que o evento &quot;Abandono do carrinho&quot; for acionado, ele automaticamente solicitará uma mensagem contendo o título e sobrenome do recipient, o URL do carrinho, o último produto consultado ou uma lista de produtos, se você tiver definido uma lista de produtos, e o valor total do carrinho a ser enviado.

Para acessar os relatórios referentes à sua mensagem transacional, use o botão **[!UICONTROL Reports]**. Consulte [Relatórios dinâmicos](../../reporting/using/about-dynamic-reports.md).

![](assets/message-center_13.png)

### Suspensão de publicação de mensagem transacional {#suspending-a-transactional-message-publication}

Você pode suspender a publicação da mensagem transacional usando o botão **[!UICONTROL Pause]**, por exemplo, para modificar os dados contidos na mensagem. Portanto, os eventos não são mais processados, mas mantidos em fila no banco de dados do Adobe Campaign.

Os eventos em fila são mantidos durante um período definido na REST API (consulte a [documentação da REST API](../../api/using/managing-transactional-messages.md) ou no evento de disparo se você estiver usando o serviço principal Acionadores (consulte [Sobre os Acionadores da Adobe Experience Cloud](../../integrating/using/about-adobe-experience-cloud-triggers.md)).

![](assets/message-center_pause.png)

Ao clicar em **[!UICONTROL Resume]**, todos os eventos em fila (desde que não tenham expirado) são processados. Eles agora contêm todas as modificações efetuadas durante a suspensão da publicação do modelo.

### Cancelamento de publicação de uma mensagem transacional {#unpublishing-a-transactional-message}

Clicar em **[!UICONTROL Unpublish]** permite cancelar a publicação da mensagem transacional, mas também a publicação do evento correspondente, que exclui da API REST o recurso correspondente ao evento criado anteriormente.

![](assets/message-center_unpublish-template.png)

Agora, mesmo que o evento seja acionado pelo seu site, as mensagens correspondentes não serão mais enviadas e não serão armazenadas no banco de dados.

>[!NOTE]
>
>Para publicar a mensagem novamente, você precisa voltar para a configuração de evento correspondente, [publicar o evento](../../channels/using/publishing-transactional-event.md) e [publicar a mensagem](#publishing-a-transactional-message).

Se você cancelar a publicação de uma mensagem transacional pausada, talvez precise aguardar até 24 horas para poder publicá-la novamente. Isso permite que o fluxo de trabalho da **[!UICONTROL Database cleanup]** limpe todos os eventos enviados para a fila.

As etapas para pausar uma mensagem estão detalhadas na seção [Suspensão de publicação de mensagem transacional](#suspending-a-transactional-message-publication).

O fluxo de trabalho da **[!UICONTROL Database cleanup]**, que é executado todos os dias às 4h da manhã, pode ser acessado por meio de **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Workflows]**.

### Exclusão de uma mensagem transacional {#deleting-a-transactional-message}

Depois de cancelada a publicação de uma mensagem transacional, ou se uma mensagem transacional ainda não tiver sido publicada, você poderá excluí-la da lista de mensagens transacionais. Para fazer isso:

1. Clique no logotipo **[!UICONTROL Adobe Campaign]**, no canto superior esquerdo, em seguida selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.
1. Passe o mouse sobre a mensagem de sua escolha.
1. Clique no botão **[!UICONTROL Delete element]**.

![](assets/message-center_delete-template.png)

No entanto, a exclusão de uma mensagem transacional só pode ser feita sob certas condições:

* Verifique se a mensagem transacional tem o status **[!UICONTROL Draft]**; caso contrário, você não poderá excluí-la. O status **[!UICONTROL Draft]** se aplica a uma mensagem que ainda não foi publicada ou cuja [publicação foi cancelada](#unpublishing-a-transactional-message) (e não [pausada](#suspending-a-transactional-message-publication)).

* **Mensagens transacionais**: a menos que outra mensagem transacional esteja vinculada ao evento correspondente, se a publicação da mensagem transacional for cancelada, a publicação da configuração do evento também precisará ser cancelada para excluir com êxito a mensagem transacional. Para obter mais informações, consulte [Cancelamento de publicação de evento](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).

   >[!IMPORTANT]
   >
   >A exclusão de uma mensagem transacional que já enviou notificações também excluirá seus logs de rastreamento e envios.

* **Mensagens transacionais de um modelo de evento pronto para uso (mensagens transacionais internas)**: se uma mensagem transacional interna for a única associada ao evento interno correspondente, ela não poderá ser excluída. Primeiro, você precisa criar outra mensagem transacional duplicando-a, ou pelo menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Transactional message templates]**.

## Processo de nova tentativa de Mensagem transacional {#transactional-message-retry-process}

Uma mensagem transacional temporariamente não entregue está sujeita a tentativas automáticas que são executadas até que o delivery expire. Para mais informações sobre a duração do delivery, consulte [Parâmetros do período de validade](../../administration/using/configuring-email-channel.md#validity-period-parameters).

Quando uma mensagem transacional não é enviada, há dois sistemas de repetição:

* No nível de mensagens transacionais, uma mensagem transacional pode falhar antes de ser atribuída a um delivery de execução, ou seja, entre a recepção do evento e a preparação do delivery. Consulte [Processo de nova tentativa de processamento de eventos](#event-processing-retry-process).
* No nível do processo de envio, depois que o evento é atribuído a um delivery de execução, a mensagem transacional pode falhar devido a um erro temporário. Consulte [Processo de nova tentativa de envio de mensagens](#message-sending-retry-process).

### Processo de nova tentativa de processamento de eventos {#event-processing-retry-process}

Se o evento não puder ser atribuído a um delivery de execução, o processamento do evento será adiado. As tentativas são executadas até que sejam atribuídas a um novo delivery de execução.

>[!NOTE]
>
>Um evento adiado não é exibido nos logs de envio da mensagem transacional, pois ela ainda não foi atribuída a um delivery de execução.

Por exemplo, o evento não pôde ser atribuído a um delivery de execução porque seu conteúdo não estava correto. Houve um problema com direitos de acesso ou marca, um erro foi detectado ao aplicar regras de tipologia etc. Nesse caso, você pode pausar a mensagem, editá-la para corrigir o problema e publicá-la novamente. O sistema de nova tentativa a atribuirá a um novo delivery de execução.

### Processo de nova tentativa de envio de mensagem {#message-sending-retry-process}

Depois que o evento tiver sido atribuído a um delivery de execução, a mensagem transacional poderá falhar devido a um erro temporário, se a caixa de correio do recipient estiver cheia, por exemplo. Para obter mais informações, consulte [Tentativas após uma falha temporária de delivery](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>Quando um evento é atribuído a um delivery de execução, ele é exibido nos logs de envio desse delivery de execução e apenas no momento. Os delivery com falha são exibidos na guia **[!UICONTROL Execution list]** dos logs de envio de mensagens transacionais.

### Repetir limitações do processo {#limitations}

**Envio de atualização de logs**

No processo de repetição, os logs de envio do novo delivery de execução não são atualizados imediatamente (a atualização é executada por meio de um fluxo de trabalho programado). Isso significa que a mensagem pode estar em status **[!UICONTROL Pending]** mesmo se o evento transacional tiver sido processado pelo novo delivery de execução.

**Delivery de execução com falha**

Não é possível interromper um delivery de execução. No entanto, se o delivery de execução atual falhar, um novo será criado assim que um novo evento for recebido, e todos os novos eventos serão processados por esse novo delivery de execução. Nenhum novo evento é processado pelo delivery de execução com falha.

Se alguns eventos já atribuídos a um delivery de execução tiverem sido adiados e esse delivery falhar, o sistema de nova tentativa não atribuirá os eventos adiados ao novo delivery de execução, ou seja, esses eventos serão perdidos.
