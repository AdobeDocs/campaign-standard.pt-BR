---
title: Mensagens de acompanhamento
seo-title: Mensagens de acompanhamento
description: Mensagens de acompanhamento
seo-description: Saiba como criar e publicar uma mensagem de acompanhamento.
page-status-flag: nunca ativado
uuid: d2a17da2-e935-420a-8531-78ed6a1fe68b
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: canais
content-type: referência
topic-tags: mensagens transacionais
discoiquuid: 9615e369-754f-4f6a-a1b1-14462f94666
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fad149d30d06f285a89f13e4c8bff20932297695

---


# Mensagens de acompanhamento{#follow-up-messages}

Você pode enviar uma mensagem de acompanhamento aos clientes que receberam uma mensagem de transação específica. Para fazer isso, é necessário configurar um fluxo de trabalho direcionado ao evento correspondente.

Vamos reutilizar o exemplo descrito na seção do princípio [operacional de mensagens](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) transacionais: um e-mail de abandono de carrinho é enviado para os usuários do site que adicionaram produtos ao carrinho, mas deixaram o site sem precisar fazer compras.

Você deseja enviar um lembrete amigável a todos os clientes que receberam a notificação de abandono do carrinho, mas que não a abriram após três dias.

Cada cliente em questão receberá uma mensagem de acompanhamento com base nos mesmos dados que foram usados no primeiro email enviado.

## Acessar as mensagens de acompanhamento {#accessing-the-follow-up-messages}

Depois que você criar e publicar um evento (o abandono do carrinho, conforme o [exemplo](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) acima), a mensagem transacional e a mensagem de acompanhamento correspondentes são criadas automaticamente.

As etapas de configuração são apresentadas na seção [Configuração de um evento para enviar uma mensagem](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) de acompanhamento.

Para lidar com um evento em um fluxo de trabalho, um modelo de entrega é necessário. No entanto, ao publicar o evento, a mensagem [](../../channels/using/event-transactional-messages.md) transacional criada não pode ser usada como modelo. Portanto, é necessário criar um modelo de entrega de acompanhamento específico projetado para suportar esse tipo de evento e ser usado como modelo em um fluxo de trabalho.

Para acessar este modelo:

1. Clique no **[!UICONTROL Adobe Campaign]** logotipo, no canto superior esquerdo.
1. Selecione **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]**.
1. Marque a **[!UICONTROL Follow-up messages]** caixa no painel esquerdo.

   ![](assets/message-center_follow-up-search.png)

Somente as mensagens de acompanhamento são exibidas.

>[!NOTE]
>
>Para acessar mensagens transacionais, você deve fazer parte do grupo de **[!UICONTROL Administrators (all units)]** segurança.

## Envio de uma mensagem de acompanhamento {#sending-a-follow-up-message}

Depois de criar o modelo de entrega de acompanhamento, você pode usá-lo em um fluxo de trabalho para enviar uma mensagem de acompanhamento.

1. Acesse a lista de atividades de marketing e crie um novo fluxo de trabalho.

   Consulte [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. Arraste e solte uma **[!UICONTROL Scheduler]** atividade em seu fluxo de trabalho e abra-a. Defina a frequência de execução como uma vez por dia.

   A atividade do Agendador é apresentada na seção [Agendador](../../automating/using/scheduler.md) .

1. Arraste e solte uma **[!UICONTROL Query]** atividade em seu fluxo de trabalho e abra-a.

   A atividade Consulta é apresentada na seção [Consulta](../../automating/using/query.md) .

1. Para executar a consulta em um recurso diferente do recurso de perfil, vá para a guia da atividade **[!UICONTROL Properties]** e clique na lista **[!UICONTROL Resource]** suspensa.

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >Por padrão, a atividade é pré-configurada para procurar perfis.

1. Selecione o evento que deseja direcionar para que você acesse apenas os dados desse evento.

   ![](assets/message-center_follow-up-query-resource.png)

1. Vá para a **[!UICONTROL Target]** guia da atividade e arraste e solte o **[!UICONTROL Delivery logs (logs)]** elemento da **[!UICONTROL Email]** seção na área de trabalho.

   ![](assets/message-center_follow-up-delivery-logs.png)

   Selecione **[!UICONTROL Exists]** para direcionar todos os clientes que receberam o email.

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. Mova o **[!UICONTROL Tracking logs (tracking)]** elemento da paleta para o espaço de trabalho e selecione **[!UICONTROL Does not exist]** para direcionar todos os clientes que não abriram o email.

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. Arraste e solte o evento direcionado (abandono **do** carrinho neste exemplo) da **[!UICONTROL Email]** seção na área de trabalho. Em seguida, defina uma regra para direcionar todas as mensagens enviadas há três dias.

   ![](assets/message-center_follow-up-created.png)

   Isso significa que todos os destinatários que receberam a mensagem transacional três dias antes da execução do fluxo de trabalho e ainda não a abriram são direcionados.

   Clique em **[!UICONTROL Confirm]** para salvar a consulta.

1. Arraste e solte uma atividade de entrega **de** email em seu fluxo de trabalho.

   A atividade de entrega de email é apresentada na seção de entrega [de](../../automating/using/email-delivery.md) email.

   ![](assets/message-center_follow-up-workflow.png)

   Você também pode usar uma entrega [de](../../automating/using/sms-delivery.md) SMS ou uma atividade de entrega [de aplicativo](../../automating/using/push-notification-delivery.md) móvel. Nesse caso, selecione o canal **[!UICONTROL Mobile (SMS)]** ou **[!UICONTROL Mobile application]** ao criar a configuração do evento. Consulte [Criação de um evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).

1. Open the **Email delivery** activity. No assistente de criação, marque a **[!UICONTROL Follow-up messages]** caixa e selecione o modelo de entrega de acompanhamento criado após a publicação do evento.

   ![](assets/message-center_follow-up-template.png)

1. No conteúdo da mensagem de acompanhamento, você pode aproveitar o conteúdo do seu evento adicionando campos de personalização.

   ![](assets/message-center_follow-up-content.png)

1. Encontre os campos que você definiu ao criar seu evento selecionando **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]**. Consulte [Personalizando uma mensagem](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)transacional.

   ![](assets/message-center_follow-up-personalization.png)

   Isso significa que você pode aproveitar o mesmo conteúdo, incluindo dados enriquecidos, que foi usado na primeira vez que o evento foi enviado, para criar um lembrete personalizado.

1. Salve a atividade e inicie o fluxo de trabalho.

Quando o fluxo de trabalho for iniciado, todos os clientes que tiverem recebido sua notificação de abandono do carrinho três dias atrás, mas não a tiverem aberto, receberão uma mensagem de acompanhamento com base nos mesmos dados.

>[!NOTE]
>
>Se você tiver selecionado a dimensão de **[!UICONTROL Profile]** definição de metas ao criar a configuração do evento, a mensagem de acompanhamento também impulsionará o banco de dados de marketing do Adobe Campaign. Consulte Mensagens [transacionais de](../../channels/using/profile-transactional-messages.md)perfil.

