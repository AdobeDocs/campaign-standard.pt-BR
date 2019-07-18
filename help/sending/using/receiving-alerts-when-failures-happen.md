---
title: Recebimento de alertas quando ocorrerem falhas
seo-title: Recebimento de alertas quando ocorrerem falhas
description: Recebimento de alertas quando ocorrerem falhas
seo-description: Saiba como usar o sistema de gerenciamento de alertas.
page-status-flag: nunca ativado
uuid: a 3 ab 733 a-e 3 db -4 adc-b 930-cd 4064 b 6 dc 1 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviando
content-type: reference
topic-tags: monitoramento-mensagens
discoiquuid: 0766 bd 57-c 5 f 1-4 f 56-ac 84-e 5 a 04 d 3819 ec
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Receiving alerts when failures happen{#receiving-alerts-when-failures-happen}

## About delivery alerting {#about-delivery-alerting}

The **Delivery alerting** feature is an alert management system that enables a group of users to automatically receive notifications containing information on the execution of their deliveries.

As notificações enviadas contêm um relatório baseado por padrão nos seguintes critérios:

* Falha de entregas
* Entregas com falha de preparação
* Entregas com uma taxa de erro de rejeição suave ruim
* Entregas com uma taxa de erro de rejeição incorreta
* Entregas com status pendente mais longas do que o normal
* Entregas com baixa produtividade
* Entregas em andamento

Os destinatários dos alertas podem monitorar as entregas que estão sendo processadas pelo Adobe Campaign e tomar as medidas apropriadas quando há problemas na execução.

Essas notificações de alertas podem ser personalizadas dependendo dos critérios de alertas específicos definidos por um painel na interface do Adobe Campaign.

>[!NOTE]
>
>As notificações de alertas são fornecidas por email apenas.

As notificações enviadas contêm:

* A **[!UICONTROL Summary]** displaying the number of deliveries meeting the criteria that you defined and the label/color that you chose for each criterion.
* A **[!UICONTROL Details]** section listing all of the delivery criteria defined for the corresponding dashboard and all of the deliveries for each criterion.

![](assets/delivery-alerting_notification.png)

## Delivery alerting dashboards {#delivery-alerting-dashboards}

### About delivery alerting dashboards {#about-delivery-alerting-dashboards}

Para gerenciar destinatários de notificações, defina os critérios de alertas e acesse o histórico dos alertas, você precisa usar painéis.

>[!NOTE]
>
>To access and configure the dashboards and the alerting criteria, you must have administration rights or appear in the **Delivery supervisors** security group. Os usuários padrão não podem acessar os painéis na interface do Adobe Campaign. Eles só podem receber notificações de alertas. For more on users and security in Adobe Campaign, see [Types of users](../../administration/using/types-of-users.md) and [About security groups](../../administration/using/managing-groups-and-users.md#about-security-groups).

Na interface do Adobe Campaign, você pode:

* Criar e gerenciar painéis de alertas de entrega. See [Creating a delivery alerting dashboard](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-dashboard).
* Defina e gerencie os critérios de alertas de entrega para cada painel. Por exemplo, você pode criar alertas com base em entregas com falhas ou entregas com falhas apenas com baixo desempenho. See [About alerting criteria](../../sending/using/receiving-alerts-when-failures-happen.md#about-alerting-criteria).
* Modifique os parâmetros de critérios para cada painel. See [Criteria parameters](../../sending/using/receiving-alerts-when-failures-happen.md#criteria-parameters).
* Defina um grupo de destinatários para cada painel.

   Por exemplo, você deseja informar aos usuários apenas os direitos de administração das entregas que falharam. No entanto, você deseja que os usuários de marketing recebam informações sobre as entregas com uma taxa de erro incorreta incorreta. Portanto, você precisa criar dois painéis diferentes e definir os critérios que deseja para cada grupo de destinatários.

* Acesse o histórico de todos os alertas enviados para cada painel.

   Ao selecionar um painel, o último alerta enviado para este painel é exibido por padrão. Todos os alertas enviados são listados à esquerda da tela. Click an item in the **[!UICONTROL History]** list to access the corresponding alerts.

![](assets/delivery-alerting_dashboard.png)

### Creating a delivery alerting dashboard {#creating-a-delivery-alerting-dashboard}

Se desejar enviar notificações com base em critérios específicos a grupos diferentes de usuários, você precisa usar vários painéis. Para criar um novo painel:

1. Go to **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]**.
1. Select **[!UICONTROL Delivery alerting dashboards]** and click **[!UICONTROL Create]**.
1. Check the **[!UICONTROL Enabled]** box to activate the current dashboard.

   Se essa opção estiver desativada, as notificações vinculadas a esse painel não serão mais enviadas. Essa opção está desativada por padrão.

   ![](assets/delivery-alerting_dashboard_general.png)

1. Select the group of recipients that you want to notify from the **[!UICONTROL Alert group]** drop-down list. To modify or create a group, see [Creating a security group and assigning users](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users).
1. From the **[!UICONTROL Delivery alerting criteria]** section, click **[!UICONTROL Create element]** to add criteria. See [About alerting criteria](../../sending/using/receiving-alerts-when-failures-happen.md#about-alerting-criteria).
1. Select the **[!UICONTROL Edit properties]** button. In the **[!UICONTROL Criteria parameters]** tab, define how the criteria will be applied. See [Criteria parameters](../../sending/using/receiving-alerts-when-failures-happen.md#criteria-parameters).
1. Click **[!UICONTROL Create]** to save the dashboard.

Agora, cada vez que uma entrega atender aos critérios definidos nesse painel, uma notificação de alerta será enviada para o grupo especificado de usuários.

## Delivery alerting criteria {#delivery-alerting-criteria}

### About alerting criteria {#about-alerting-criteria}

To access the delivery alerting criteria, go to **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]** and select **[!UICONTROL Delivery alerting criteria]**.

![](assets/delivery-alerting_criteria.png)

Os seguintes critérios podem ser usados nos painéis de alertas de entrega:

* **[!UICONTROL Deliveries failed]**: Qualquer entrega programada dentro de um intervalo definido, com um status errôneo.
* **[!UICONTROL Deliveries with preparation failed]**: Qualquer entrega modificada em um intervalo definido, para a qual a etapa de preparação (cálculo de meta e geração de conteúdo) falhou. For more on this, see [Preparing the send](../../sending/using/preparing-the-send.md).
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**: Qualquer entrega programada dentro de um intervalo definido, com um status pelo menos **[!UICONTROL In progress]**, com uma proporção de erro de rejeição suave maior que uma porcentagem definida.
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**: Qualquer entrega programada dentro de um intervalo definido, com um status pelo menos **[!UICONTROL In progress]**, com uma proporção de erro de rejeição intensa maior que uma porcentagem definida.
* **[!UICONTROL Deliveries with long start pending]**: Qualquer entrega programada dentro de um intervalo definido, com **[!UICONTROL Start pending]** um status por mais do que uma duração definida, **[!UICONTROL Start pending]** significa que as mensagens ainda não foram consideradas pelo sistema.
* **[!UICONTROL Deliveries with low throughput]**: Qualquer entrega iniciada por mais do que uma duração definida, com menos do que uma porcentagem definida de mensagens processadas, com um valor inferior a um valor definido.
* **[!UICONTROL Deliveries in progress]**: Qualquer entrega programada dentro de um intervalo definido, com **[!UICONTROL In progress]** o status.

>[!NOTE]
>
>Todos os parâmetros que se aplicam aos critérios acima têm valores padrão. These values can be changed in the **[!UICONTROL Criteria parameters]** tab of the delivery alerting dashboards. See [Criteria parameters](../../sending/using/receiving-alerts-when-failures-happen.md#criteria-parameters).

You can select any item from the **[!UICONTROL Delivery alerting criteria]** list to access its details.

![](assets/delivery-alerting_criteria_definition.png)

Para cada critério, é possível definir as seguintes configurações:

* **[!UICONTROL Indicators to add in alerts]**, o que significa que as colunas aparecerão na **[!UICONTROL Details]** seção da notificação para as entregas correspondentes ao critério selecionado.

   ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**, o que significa que o rótulo e a cor aparecerão ao lado do critério de entrega no resumo da notificação.

   ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**: Se um critério for cumprido para uma entrega, ele será repetido em cada notificação enviada dentro do período de monitoramento. Caso contrário, apenas um alerta será enviado por um dia (na primeira ocorrência) por um critério de alerta para uma entrega.

   Por padrão, essa opção é definida como uma vez por dia para todos os critérios.

**Tópicos relacionados:**

* [Envio de logs](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [Frequência de alertas](../../sending/using/receiving-alerts-when-failures-happen.md#alerting-frequency)
* [Ícones e status de atividade de marketing](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### Creating a delivery alerting criterion {#creating-a-delivery-alerting-criterion}

Você pode criar novos critérios de alerta de entrega para melhor atender às suas necessidades.

For example, you can create a new criterion enabling to send a notification listing all deliveries with a **[!UICONTROL Finished]** status.

To do this, you first need to extend the **Delivery** resource and add a new filter allowing you to select only the deliveries with a **[!UICONTROL Finished]** status.

1. Go to **Adobe Campaign** &gt; **Administration** &gt; **Development** &gt; **Custom resources** and click **[!UICONTROL Create]**.
1. Select **[!UICONTROL Extend an existing resource]**, select the **[!UICONTROL Delivery]** resource from the drop-down list and click **[!UICONTROL Create]** to edit it.

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   For more on extending an existing resource, see [Define the resource](../../developing/using/creating-or-extending-the-resource.md).

1. In the **[!UICONTROL Delivery]** resource, go to the **[!UICONTROL Filter definition]** tab and click **[!UICONTROL Add an element]** to create a filter.

   ![](assets/delivery-alerting_new-filter.png)

1. Edit the new filter definition: in the **[!UICONTROL Filter definition]** window, drag and drop the **[!UICONTROL Status]** item into the workspace and select **[!UICONTROL Finished]** as the filter condition.

   ![](assets/delivery-alerting_filter-status.png)

   For more on creating and editing custom filters, see [Define filters](../../developing/using/configuring-filter-definition.md).

1. Salve suas alterações e publique seus recursos. For more on this, see [Publishing a custom resource](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   O filtro é criado e agora pode ser selecionado em um novo critério de alerta de entrega.

1. Go to **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]**, select **[!UICONTROL Delivery alerting criteria]** and click **[!UICONTROL Create]**.
1. In the **[!UICONTROL Delivery filter applied by this criterion]** drop-down list, select the filter that you just created.

   ![](assets/delivery-alerting_cus-filter.png)

   É possível definir as configurações do critério da mesma forma que para os critérios padrão. See [About alerting criteria](../../sending/using/receiving-alerts-when-failures-happen.md#about-alerting-criteria).

Depois de criados, esses critérios podem ser adicionados a um painel de alertas de entrega, bem como a outros critérios. See [About delivery alerting dashboards](../../sending/using/receiving-alerts-when-failures-happen.md#about-delivery-alerting-dashboards).

![](assets/delivery-alerting_new-criterion.png)

**Tópico relacionado:**

[Adicionar ou estender um recurso](../../developing/using/key-steps-of-adding-a-resource.md)

## Delivery alerting parameters {#delivery-alerting-parameters}

### Criteria parameters {#criteria-parameters}

In the **[!UICONTROL Criteria parameters]** tab of a [delivery alerting dashboard](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-dashboard), you can define the settings that apply to the criteria selected in this dashboard.

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**: Por exemplo, se você inserir 100 neste campo, uma notificação será enviada apenas para entregas com um destino igual ou maior que 100 destinatários. Esse parâmetro se aplica a todos os critérios.
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**: Número de horas antes e depois da hora atual. Somente as entregas que têm uma data de contato neste intervalo de tempo são consideradas. Esse parâmetro se aplica a todos os critérios. Por padrão, o valor desse campo é definido como 24 horas.

   For more information on the contact date, see [About the scheduling](../../sending/using/about-scheduling-messages.md).

* **[!UICONTROL Maximum ratio of soft bounce errors]**: Uma notificação é enviada para todas as entregas com uma proporção de erro de rejeição suave maior que o valor especificado. Por padrão, o valor desse campo é definido como 0.05 (5%).

   For more on soft bounce errors, see [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) and [List of delivery failure types](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Maximum ratio of hard bounce errors]**: Uma notificação é enviada para todas as entregas com uma taxa de erro de rejeição intensa maior que o valor especificado. Por padrão, o valor desse campo é definido como 0.05 (5%).

   For more on hard bounce errors, see [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) and [List of delivery failure types](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**: Uma notificação é enviada para todas as entregas com **[!UICONTROL Start pending]** um status por um período maior que a duração especificada neste campo, **[!UICONTROL Start pending]** o que significa que as mensagens ainda não foram consideradas pelo sistema.
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**: Somente as entregas iniciadas (com **[!UICONTROL In progress]** status) para mais do que a duração especificada são consideradas para o **[!UICONTROL Deliveries with low throughput]** critério.
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**: Somente as entregas com uma porcentagem de mensagens processadas inferiores à porcentagem especificada são consideradas para o **[!UICONTROL Deliveries with low throughput]** critério.
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**: Somente as entregas com saídas inferiores ao valor especificado são consideradas para o **[!UICONTROL Deliveries with low throughput]** critério.
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**: Somente as entregas com uma porcentagem de mensagens processadas superiores à porcentagem especificada são consideradas.

### Alerting frequency {#alerting-frequency}

The **[!UICONTROL Frequency of delivery alerting]** option allows to define the delay between two alert sendings. Por padrão, é definido como 10 minutos.

You can change this setting through the **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]** menu.

>[!NOTE]
>
>Essa opção se aplica a todos os painéis definidos no Adobe Campaign. Não é possível definir uma frequência específica para cada painel.

## Delivery alerting reasons {#delivery-alerting-reasons}

The **Delivery alerting** feature keeps all of your involved Adobe Campaign users automatically informed about the delivery execution status, via email and dashboard.

Agora, ao receber uma notificação de alerta de entrega, veja algumas dicas sobre o que você pode fazer.

First of all, check the delivery's **Log** tab to view all information relating to the delivery and proofs. Os ícones vermelho e amarelo permitem identificar erros ou avisos. O ícone vermelho indica um erro crítico que impede a execução da entrega.

To view the history of every occurrence of a delivery, select the **[!UICONTROL Sending logs]** tab. Ele contém a lista de mensagens enviadas e seus status. There you can check the delivery status for each recipient ( **[!UICONTROL Sent]**, **[!UICONTROL Pending]**, **[!UICONTROL Failed]**, etc.). For more on this, see [Sending logs](../../sending/using/monitoring-a-delivery.md#sending-logs).

Aqui estão alguns possíveis motivos para receber notificações de alertas de acordo com os critérios que são atendidos para uma entrega.

* **[!UICONTROL Deliveries failed]**: Este critério informa a você de todas as entregas com um status errôneo. Pode ser decorrente de:

   * Um problema com o servidor de entrega (MTA, Agente de transferência de mensagens)
   * Um tempo limite de conexão entre o servidor de entrega do Adobe Campaign e o servidor de recebimento
   * Um problema de entrega
   * Um fluxo de trabalho errôneo
   Se a entrega for acionada com um fluxo de trabalho, verifique se o fluxo de trabalho foi iniciado corretamente. For more on this, see [Executing a workflow](../../automating/using/executing-a-workflow.md). Caso contrário, entre em contato com o administrador do Adobe Campaign para resolver o problema.

* **[!UICONTROL Deliveries with preparation failed]**: Pode ocorrer um erro durante a preparação da entrega nos seguintes casos:

   * A entrega está sem um assunto.
   * Há uma sintaxe incorreta nos campos de personalização.
   * O destino está ausente.
   * A entrega excede o limite de tamanho.
   For more on this, see [Preparing the send](../../sending/using/preparing-the-send.md). No entanto, esses erros geralmente são destacados durante a análise de mensagens. See [Control rules](../../administration/using/control-rules.md).

* The possible causes for a **[!UICONTROL Delivery with bad error ratio for soft bounces]** alert can be:

   * O servidor do destinatário está inativo.
   * A caixa de entrada do destinatário está cheia.
   For more information, check the **[!UICONTROL Exclusion logs]** and **[!UICONTROL Exclusion causes]** tabs of the delivery logs. See [Exclusion logs](../../sending/using/monitoring-a-delivery.md#exclusion-logs).

   The possible causes for a **[!UICONTROL Delivery with bad error ratio for hard bounces]** alert can be:

   * O destinatário está na lista negra, o que significa que não quer mais ser contatado.
   * O endereço de email do destinatário não existe.
   * O domínio do destinatário não existe.
   * O servidor do destinatário está bloqueando a entrega.
   Para evitar erros de rejeição suave e difícil, siga as práticas recomendadas abaixo:

   * Construa regras de filtragem de filtragem para excluir uma parte do destino da mensagem durante a análise de entrega, como destinatários cercados. See [Creating a filtering rule](../../administration/using/filtering-rules.md).
   * Atualize regularmente o banco de dados do cliente para manter bons processos de gerenciamento de quarentena. See [About quarantines](../../sending/using/understanding-quarantine-management.md#about-quarantines).
   * Geralmente, melhore a capacidade de entrega o melhor possível. See the Adobe Campaign v7 [Managing deliverability](http://docs.campaign.adobe.com/doc/AC/getting_started/EN/deliverability.html) detailed guide and contact your Adobe Campaign administrator for assistance.



* **[!UICONTROL Deliveries with long start pending]**: Normalmente, isso significa que há um problema no nível do MTA (Message Transfer Agent). O processo de execução está aguardando a disponibilidade de alguns recursos. A MTA não foi iniciada.

   **[!UICONTROL Deliveries with low throughput]**: Novamente, esse é um problema de entrega que significa que a MTA é muito lenta.

   Para saber mais sobre esses problemas, entre em contato com o administrador do Adobe Campaign.

**Tópicos relacionados:**

* [Compreensão das falhas de entrega](../../sending/using/understanding-delivery-failures.md)
* [Noções básicas sobre o gerenciamento de quarentena](../../sending/using/understanding-quarantine-management.md)
* [Gerenciamento de lista negra no Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

