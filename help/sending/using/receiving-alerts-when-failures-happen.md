---
title: Recebimento de alertas quando ocorrerem falhas
description: Saiba como usar o sistema de gerenciamento de alertas.
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Proofs
role: User
level: Beginner
exl-id: dc8bd1d3-e199-4901-9b1f-7b485879897d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '2038'
ht-degree: 2%

---

# Recebimento de alertas quando ocorrerem falhas{#receiving-alerts-when-failures-happen}

## Sobre alertas de delivery {#about-delivery-alerting}

O recurso **Alerta de entrega** é um sistema de gerenciamento de alertas que permite que um grupo de usuários receba automaticamente notificações contendo informações sobre a execução de suas entregas.

As notificações enviadas contêm um relatório com base nos seguintes critérios por padrão:

* Entregas com falha
* Entregas com falha na preparação
* Entregas com uma taxa de erro de rejeição temporária incorreta
* Entregas com uma taxa de erro de rejeição permanente ruim
* Entregas com um status pendente mais longo que o normal
* Deliveries com baixo throughput
* Entregas em andamento

Os recipients dos alertas podem monitorar os deliveries que estão sendo processados pelo Adobe Campaign e tomar as medidas apropriadas quando houver problemas em sua execução.

Essas notificações de alerta podem ser personalizadas dependendo de critérios de alerta específicos que são definidos por meio de um painel na interface do Adobe Campaign.

>[!NOTE]
>
>As notificações de alerta são entregues somente por email.

As notificações enviadas contêm:

* Uma **[!UICONTROL Summary]** que exibe o número de entregas que atendem aos critérios definidos e o rótulo/cor escolhido para cada critério.
* Uma seção **[!UICONTROL Details]** listando todos os critérios de entrega definidos para o painel correspondente e todas as entregas para cada critério.

![](assets/delivery-alerting_notification.png)

## Painéis de alertas de entrega {#delivery-alerting-dashboards}

### Sobre os painéis de alerta do delivery {#about-delivery-alerting-dashboards}

Para gerenciar os destinatários das notificações, definir os critérios de alerta e acessar o histórico dos alertas, é necessário usar painéis.

>[!NOTE]
>
>Para acessar e configurar os painéis e os critérios de alerta, você deve ter direitos administrativos ou aparecer no grupo de segurança **Supervisores de entrega**. Usuários padrão não podem acessar os painéis na interface do Adobe Campaign. Eles só podem receber as notificações de alerta. Para obter mais informações sobre usuários e segurança no Adobe Campaign, consulte [Tipos de usuários](../../administration/using/users-management.md) e [Sobre grupos de segurança](../../administration/using/managing-groups-and-users.md#about-security-groups).

Na interface do Adobe Campaign, é possível:

* Crie e gerencie painéis de alerta de delivery. Consulte [Criando um painel de alertas de entrega](#creating-a-delivery-alerting-dashboard).
* Defina e gerencie os critérios de alerta de delivery para cada painel. Por exemplo, você pode criar alertas com base em deliveries com falha de preparação ou deliveries com baixa taxa de transferência apenas. Consulte [Sobre os critérios de alerta](#about-alerting-criteria).
* Modifique os parâmetros de critérios para cada painel. Consulte [Parâmetros de critérios](#criteria-parameters).
* Defina um grupo de recipients para cada painel.

  Por exemplo, você deseja informar os usuários com direitos administrativos somente sobre os deliveries com falha. No entanto, você deseja que os usuários de marketing recebam informações sobre os deliveries com uma taxa de erro leve de rejeição. Portanto, é necessário criar dois painéis diferentes e definir os critérios que deseja para cada grupo de recipients.

* Acesse o histórico de todos os alertas enviados para cada painel.

  Ao selecionar um painel, o último alerta enviado para esse painel é exibido por padrão. Todos os alertas enviados são listados à esquerda da tela. Clique em um item na lista **[!UICONTROL History]** para acessar os alertas correspondentes.

![](assets/delivery-alerting_dashboard.png)

### Criação de um painel de alerta de delivery {#creating-a-delivery-alerting-dashboard}

Para enviar notificações com base em critérios específicos para diferentes grupos de usuários, é necessário usar vários painéis. Para criar um novo painel:

1. Vá para **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**.
1. Selecione **[!UICONTROL Delivery alerting dashboards]** e clique em **[!UICONTROL Create]**.
1. Marque a caixa **[!UICONTROL Enabled]** para ativar o painel atual.

   Se essa opção estiver desativada, as notificações vinculadas a esse painel não serão mais enviadas. Essa opção está desabilitada por padrão.

   ![](assets/delivery-alerting_dashboard_general.png)

1. Selecione o grupo de destinatários que deseja notificar na lista suspensa **[!UICONTROL Alert group]**. Para modificar ou criar um grupo, consulte [Criação de um grupo de segurança e atribuição de usuários](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users).
1. Na seção **[!UICONTROL Delivery alerting criteria]**, clique em **[!UICONTROL Create element]** para adicionar critérios. Consulte [Sobre os critérios de alerta](#about-alerting-criteria).
1. Selecione o botão **[!UICONTROL Edit properties]**. Na guia **[!UICONTROL Criteria parameters]**, defina como os critérios serão aplicados. Consulte [Parâmetros de critérios](#criteria-parameters).
1. Clique em **[!UICONTROL Create]** para salvar o painel.

Agora, sempre que um delivery atender aos critérios definidos nesse painel, uma notificação de alerta será enviada para o grupo especificado de usuários.

## Critérios de alertas de entrega {#delivery-alerting-criteria}

### Sobre os critérios de alerta {#about-alerting-criteria}

Para acessar os critérios de alerta de entrega, vá para **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]** e selecione **[!UICONTROL Delivery alerting criteria]**.

![](assets/delivery-alerting_criteria.png)

Os seguintes critérios podem ser usados nos painéis de alerta de delivery:

* **[!UICONTROL Deliveries failed]**: Qualquer entrega agendada dentro de um intervalo definido, com status incorreto.
* **[!UICONTROL Deliveries with preparation failed]**: Qualquer entrega modificada dentro de um intervalo definido, para a qual a etapa de preparação (cálculo de destino e geração de conteúdo) falhou. Para obter mais informações, consulte [Preparação do envio](../../sending/using/preparing-the-send.md).
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**: Qualquer entrega agendada dentro de um intervalo definido, com um status de pelo menos **[!UICONTROL In progress]**, com uma taxa de erro de rejeição temporária maior que uma porcentagem definida.
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**: Qualquer entrega agendada dentro de um intervalo definido, com um status de pelo menos **[!UICONTROL In progress]**, com uma taxa de erro de rejeição permanente maior que uma porcentagem definida.
* **[!UICONTROL Deliveries with long start pending]**: Qualquer entrega agendada dentro de um intervalo definido, com um status **[!UICONTROL Start pending]** por mais tempo do que uma duração definida, status **[!UICONTROL Start pending]** significando que as mensagens ainda não foram consideradas pelo sistema.
* **[!UICONTROL Deliveries with low throughput]**: Qualquer entrega iniciada por mais de uma duração definida, com menos de uma porcentagem definida de mensagens processadas, com uma taxa de transferência inferior a um valor definido.
* **[!UICONTROL Deliveries in progress]**: Qualquer entrega agendada dentro de um intervalo definido, com o status **[!UICONTROL In progress]**.

>[!NOTE]
>
>Todos os parâmetros que se aplicam aos critérios acima têm valores padrão. Esses valores podem ser alterados na guia **[!UICONTROL Criteria parameters]** dos painéis de alertas de entrega. Consulte [Parâmetros de critérios](#criteria-parameters).

Você pode selecionar qualquer item da lista **[!UICONTROL Delivery alerting criteria]** para acessar seus detalhes.

![](assets/delivery-alerting_criteria_definition.png)

Para cada critério, você pode definir as seguintes configurações:

* **[!UICONTROL Indicators to add in alerts]**, o que significa que as colunas que aparecerão na seção **[!UICONTROL Details]** da notificação para as entregas correspondentes ao critério selecionado.

  ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**, que significa o rótulo e a cor que aparecerão ao lado do critério de entrega no resumo da notificação.

  ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**: se um critério for atendido para uma entrega, ele será repetido em cada notificação enviada dentro do período de monitoramento. Caso contrário, somente um alerta será enviado por dia (na primeira ocorrência) por critério de alerta para um delivery.

  Por padrão, essa opção é definida para uma vez por dia para todos os critérios.

**Tópicos relacionados:**

* [Logs de envio](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [Frequência de alerta](#alerting-frequency)
* [Ícones e status de atividades de marketing](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### Criação de um critério de alerta de delivery {#creating-a-delivery-alerting-criterion}

Você pode criar novos critérios de alerta de delivery para melhor atender às suas necessidades.

Por exemplo, você pode criar um novo critério que permita enviar uma notificação listando todos os deliveries com um status **[!UICONTROL Finished]**.

Para fazer isso, primeiro é necessário estender o recurso **Delivery** e adicionar um novo filtro que permita selecionar apenas as entregas com status **[!UICONTROL Finished]**.

1. Vá para **Adobe Campaign** > **Administração** > **Desenvolvimento** > **Recursos personalizados** e clique em **[!UICONTROL Create]**.
1. Selecione **[!UICONTROL Extend an existing resource]**, selecione o recurso **[!UICONTROL Delivery]** na lista suspensa e clique em **[!UICONTROL Create]** para editá-lo.

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   Para obter mais informações sobre a extensão de um recurso existente, consulte [Definir o recurso](../../developing/using/creating-or-extending-the-resource.md).

1. No recurso **[!UICONTROL Delivery]**, vá para a guia **[!UICONTROL Filter definition]** e clique em **[!UICONTROL Add an element]** para criar um filtro.

   ![](assets/delivery-alerting_new-filter.png)

1. Edite a nova definição de filtro: na janela **[!UICONTROL Filter definition]**, arraste e solte o item **[!UICONTROL Status]** no espaço de trabalho e selecione **[!UICONTROL Finished]** como condição de filtro.

   ![](assets/delivery-alerting_filter-status.png)

   Para obter mais informações sobre como criar e editar filtros personalizados, consulte [Definir filtros](../../developing/using/configuring-filter-definition.md).

1. Salve as alterações e publique os recursos. Para obter mais informações, consulte [Publicação de um recurso personalizado](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   O filtro é criado e agora pode ser selecionado em um novo critério de alerta de delivery.

1. Vá para **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**, selecione **[!UICONTROL Delivery alerting criteria]** e clique em **[!UICONTROL Create]**.
1. Na lista suspensa **[!UICONTROL Delivery filter applied by this criterion]**, selecione o filtro que você acabou de criar.

   ![](assets/delivery-alerting_cus-filter.png)

   Você pode definir as configurações dos seus critérios da mesma forma que os critérios padrão. Consulte [Sobre os critérios de alerta](#about-alerting-criteria).

Depois de criados, esses critérios podem ser adicionados a um painel de alerta de delivery, bem como a outros critérios. Consulte [Sobre painéis de alertas de entrega](#about-delivery-alerting-dashboards).

![](assets/delivery-alerting_new-criterion.png)

**Tópicos relacionados:**

[Adição ou extensão de um recurso](../../developing/using/key-steps-to-add-a-resource.md)

## Parâmetros de alerta de entrega {#delivery-alerting-parameters}

### Parâmetros de critérios {#criteria-parameters}

Na guia **[!UICONTROL Criteria parameters]** de um [painel de alertas de entrega](#creating-a-delivery-alerting-dashboard), você pode definir as configurações que se aplicam aos critérios selecionados neste painel.

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**: por exemplo, se você inserir 100 neste campo, uma notificação será enviada somente para deliveries com um público alvo igual ou maior que 100 recipients. Esse parâmetro se aplica a todos os critérios.
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**: Número de horas antes e depois da hora atual. Somente os deliveries com uma data de contato nesse intervalo de tempo são considerados. Esse parâmetro se aplica a todos os critérios. Por padrão, o valor desse campo é definido como 24 horas.

  Para obter mais informações sobre a data de contato, consulte [Sobre o agendamento](../../sending/using/about-scheduling-messages.md).

* **[!UICONTROL Maximum ratio of soft bounce errors]**: uma notificação é enviada para todas as entregas com uma taxa de erro de rejeição temporária maior que o valor especificado. Por padrão, o valor desse campo é definido como 0,05 (5%).

  Para obter mais informações sobre erros de rejeição temporária, consulte [Qualificação de email de rejeição](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) e [Lista de tipos de falha de entrega](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Maximum ratio of hard bounce errors]**: uma notificação é enviada para todas as entregas com uma taxa de erro de rejeição permanente maior que o valor especificado. Por padrão, o valor desse campo é definido como 0,05 (5%).

  Para obter mais informações sobre erros de rejeição permanente, consulte [Qualificação de email de rejeição](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) e [Lista de tipos de falha de entrega](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**: uma notificação é enviada para todas as entregas com status **[!UICONTROL Start pending]** por mais tempo do que a duração especificada neste campo, status **[!UICONTROL Start pending]** significando que as mensagens ainda não foram consideradas pelo sistema.
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**: Somente entregas iniciadas (com status **[!UICONTROL In progress]**) por mais tempo do que a duração especificada são consideradas para o critério **[!UICONTROL Deliveries with low throughput]**.
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**: Somente entregas com uma porcentagem de mensagens processadas inferior à porcentagem especificada são consideradas para o critério **[!UICONTROL Deliveries with low throughput]**.
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**: Somente entregas com uma taxa de transferência menor que o valor especificado são consideradas para o critério **[!UICONTROL Deliveries with low throughput]**.
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**: Somente entregas com uma porcentagem de mensagens processadas maior que a porcentagem especificada são consideradas.

### Frequência de alerta {#alerting-frequency}

A opção **[!UICONTROL Frequency of delivery alerting]** permite definir o atraso entre dois envios de alerta. Por padrão, é definido como 10 minutos.

Você pode alterar essa configuração no menu **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.

>[!NOTE]
>
>Essa opção se aplica a todos os painéis definidos no Adobe Campaign. Não é possível definir uma frequência específica para cada painel.

## Motivos de alerta de delivery {#delivery-alerting-reasons}

O recurso **Alertas de entrega** mantém todos os usuários do Adobe Campaign envolvidos informados automaticamente sobre o status de execução da entrega, por email e pelo painel.

Agora, quando você receber uma notificação de alerta de delivery, veja algumas dicas sobre o que você pode fazer.

Primeiro, verifique a guia **Log** do delivery para exibir todas as informações relacionadas ao delivery e às provas. Os ícones vermelho e amarelo permitem identificar erros ou avisos. O ícone vermelho indica um erro crítico que impede que o delivery seja iniciado.

Para exibir o histórico de cada ocorrência de uma entrega, selecione a guia **[!UICONTROL Sending logs]**. Ela contém a lista de mensagens enviadas e seus status. Você pode verificar o status de entrega de cada destinatário ( **[!UICONTROL Sent]**, **[!UICONTROL Pending]**, **[!UICONTROL Failed]** etc.). Para obter mais informações, consulte [Enviar logs](../../sending/using/monitoring-a-delivery.md#sending-logs).

Estes são alguns motivos possíveis para receber notificações de alerta de acordo com os critérios que são atendidos para um delivery.

* **[!UICONTROL Deliveries failed]**: este critério informa sobre todas as entregas com status incorreto. Pode ser devido a:

   * Um problema com o servidor de entrega (MTA, Agente de transferência de mensagem)
   * Um tempo limite de conexão entre o servidor de entrega do Adobe Campaign e o servidor de recebimento
   * Um problema da capacidade de entrega
   * Um workflow incorreto

  Se o delivery for acionado com um workflow, verifique se esse workflow foi iniciado corretamente. Para obter mais informações, consulte [Executando um fluxo de trabalho](../../automating/using/about-workflow-execution.md). Caso contrário, entre em contato com o administrador do Adobe Campaign para resolver o problema.

* **[!UICONTROL Deliveries with preparation failed]**: um erro pode ocorrer durante a preparação da entrega nos seguintes casos:

   * Falta um assunto na entrega.
   * Há uma sintaxe incorreta nos campos de personalização.
   * O destino está ausente.
   * A entrega excede o limite de tamanho.

  Para obter mais informações, consulte [Preparação do envio](../../sending/using/preparing-the-send.md). No entanto, esses erros geralmente são identificados durante a análise da mensagem. Consulte [Regras de controle](../../sending/using/control-rules.md).

* As possíveis causas para um alerta **[!UICONTROL Delivery with bad error ratio for soft bounces]** podem ser:

   * O servidor do destinatário está inativo.
   * A caixa de correio do destinatário está cheia.

  Para obter mais informações, verifique as guias **[!UICONTROL Exclusion logs]** e **[!UICONTROL Exclusion causes]** dos logs de entrega. Consulte [Logs de exclusão](../../sending/using/monitoring-a-delivery.md#exclusion-logs).

  As possíveis causas para um alerta **[!UICONTROL Delivery with bad error ratio for hard bounces]** podem ser:

   * O recipient é adicionado ao incluo na lista de bloqueios, o que significa que ele não deseja mais ser contatado.
   * O endereço de email do destinatário não existe.
   * O domínio do destinatário não existe.
   * O servidor do destinatário está bloqueando a entrega.

  Para evitar erros de devolução temporária e permanente, siga as práticas recomendadas abaixo:

   * Crie regras de tipologia de filtragem para excluir uma parte do público-alvo da mensagem durante a análise de entrega, como destinatários em quarentena. Consulte [Criando uma regra de filtragem](../../sending/using/filtering-rules.md).
   * Atualize regularmente o banco de dados do cliente para manter bons processos de gerenciamento de quarentena. Consulte [Sobre quarentenas](../../sending/using/understanding-quarantine-management.md#about-quarantines).
   * De modo geral, melhore a capacidade de delivery da melhor maneira possível. Consulte a documentação detalhada da [Capacidade de entrega](../../sending/using/about-deliverability.md) do Adobe Campaign e entre em contato com o administrador do Adobe Campaign para obter assistência.

* **[!UICONTROL Deliveries with long start pending]**: Geralmente significa que há um problema no nível do MTA (Agente de Transferência de Mensagem). O processo de execução está aguardando a disponibilidade de alguns recursos. O MTA pode não ter sido iniciado.

  **[!UICONTROL Deliveries with low throughput]**: Novamente, esse é um problema de capacidade de entrega, o que significa que o MTA é muito lento.

  Para obter mais informações sobre esses problemas, entre em contato com o administrador do Adobe Campaign.

**Tópicos relacionados:**

* [Noções básicas sobre falhas de entrega](../../sending/using/understanding-delivery-failures.md)
* [Compreensão do gerenciamento de quarentena](../../sending/using/understanding-quarantine-management.md)
* [Sobre aceitação e recusa no Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
