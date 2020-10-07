---
title: Receber alertas quando ocorrerem falhas
description: Saiba como usar o sistema de gerenciamento de alertas.
page-status-flag: never-activated
uuid: a3ab733a-e3db-4adc-b930-cd4064b6dc1c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: 0766bd57-c5f1-4f56-ac84-e5a04d3819ec
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '2031'
ht-degree: 3%

---


# Receber alertas quando ocorrerem falhas{#receiving-alerts-when-failures-happen}

## Sobre alertas de delivery {#about-delivery-alerting}

The **Delivery alerting** feature is an alert management system that enables a group of users to automatically receive notifications containing information on the execution of their deliveries.

As notificações enviadas contêm um relatório com base, por padrão, nos seguintes critérios:

* Delivery com falha
* Delivery com falha na preparação
* Delivery com uma taxa de erro de rejeição suave incorreta
* Delivery com uma taxa de erro de rejeição em disco rígido
* Delivery com status pendente maior que o normal
* Delivery com baixa throughput
* Delivery em andamento

Os recipient dos alertas podem monitorar os delivery que estão sendo processados pela Adobe Campaign e tomar as medidas apropriadas quando houver problemas na execução.

Essas notificações de alerta podem ser personalizadas dependendo de critérios de alerta específicos definidos por meio de um painel na interface do Adobe Campaign.

>[!NOTE]
>
>As notificações de alerta são entregues somente por email.

As notificações enviadas contêm:

* Uma **[!UICONTROL Summary]** exibição do número de delivery que atendem aos critérios definidos e do rótulo/cor escolhido para cada critério.
* Uma **[!UICONTROL Details]** seção que lista todos os critérios de delivery definidos para o painel correspondente e todos os delivery para cada critério.

![](assets/delivery-alerting_notification.png)

## Painéis de alerta do delivery {#delivery-alerting-dashboards}

### Sobre painéis de alerta de delivery {#about-delivery-alerting-dashboards}

Para gerenciar os recipient das notificações, definir os critérios de alerta e acessar o histórico dos alertas, é necessário usar painéis.

>[!NOTE]
>
>Para acessar e configurar os painéis e os critérios de alerta, você deve ter direitos administrativos ou aparecer no grupo de supervisores **do** Delivery. Os usuários padrão não podem acessar os painéis na interface do Adobe Campaign. Eles só podem receber as notificações de alerta. Para obter mais informações sobre usuários e segurança no Adobe Campaign, consulte [Tipos de usuários](../../administration/using/users-management.md) e [Sobre grupos](../../administration/using/managing-groups-and-users.md#about-security-groups)de segurança.

Na interface do Adobe Campaign, é possível:

* Crie e gerencie painéis de alertas de delivery. Consulte [Criação de um painel](#creating-a-delivery-alerting-dashboard)de alerta de delivery.
* Defina e gerencie os critérios de alerta do delivery para cada painel. Por exemplo, você pode criar alertas com base em delivery com problemas de preparação ou delivery com baixa taxa de transferência. Consulte [Sobre critérios](#about-alerting-criteria)de alerta.
* Modifique os parâmetros de critérios para cada painel. Consulte Parâmetros [de critérios](#criteria-parameters).
* Defina um grupo de recipient para cada painel.

   Por exemplo, você deseja informar os usuários com direitos administrativos somente dos delivery que falharam. No entanto, você deseja que os usuários de marketing recebam informações sobre os delivery com uma taxa de erro de rejeição suave. Portanto, é necessário criar dois painéis diferentes e definir os critérios desejados para cada grupo de recipient.

* Acesse o histórico de todos os alertas enviados para cada painel.

   Ao selecionar um painel, o último alerta enviado para esse painel é exibido por padrão. Todos os alertas enviados são listados à esquerda da tela. Clique em um item na **[!UICONTROL History]** lista para acessar os alertas correspondentes.

![](assets/delivery-alerting_dashboard.png)

### Criação de um painel de alerta de delivery {#creating-a-delivery-alerting-dashboard}

Se desejar enviar notificações com base em critérios específicos para grupos diferentes de usuários, será necessário usar vários painéis. Para criar um novo painel:

1. Vá para **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**.
1. Selecione **[!UICONTROL Delivery alerting dashboards]** e clique em **[!UICONTROL Create]**.
1. Marque a **[!UICONTROL Enabled]** caixa para ativar o painel atual.

   Se essa opção estiver desativada, as notificações vinculadas a esse painel não serão mais enviadas. Essa opção está desabilitada por padrão.

   ![](assets/delivery-alerting_dashboard_general.png)

1. Selecione o grupo de recipient que deseja notificar na lista **[!UICONTROL Alert group]** suspensa. Para modificar ou criar um grupo, consulte [Criação de um grupo de segurança e atribuição de usuários](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users).
1. Na **[!UICONTROL Delivery alerting criteria]** seção, clique **[!UICONTROL Create element]** para adicionar critérios. Consulte [Sobre critérios](#about-alerting-criteria)de alerta.
1. Selecione o botão **[!UICONTROL Edit properties]**. Na **[!UICONTROL Criteria parameters]** guia, defina como os critérios serão aplicados. Consulte Parâmetros [de critérios](#criteria-parameters).
1. Click **[!UICONTROL Create]** to save the dashboard.

Agora, cada vez que um delivery atender aos critérios definidos nesse painel, uma notificação de alerta será enviada para o grupo especificado de usuários.

## Critérios de alerta do delivery {#delivery-alerting-criteria}

### Sobre os critérios de alerta {#about-alerting-criteria}

Para acessar os critérios de alerta do delivery, vá até **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]** e selecione **[!UICONTROL Delivery alerting criteria]**.

![](assets/delivery-alerting_criteria.png)

Os seguintes critérios podem ser usados nos painéis de alerta do delivery:

* **[!UICONTROL Deliveries failed]**: Qualquer delivery programado em um intervalo definido, com um status incorreto.
* **[!UICONTROL Deliveries with preparation failed]**: Qualquer delivery modificado em um intervalo definido, para o qual a etapa de preparação (cálculo do público alvo e geração de conteúdo) falhou. Para obter mais informações, consulte [Preparação do envio](../../sending/using/preparing-the-send.md).
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**: Qualquer delivery programado em um intervalo definido, com um status pelo menos **[!UICONTROL In progress]**, com uma relação de erro de rejeição suave maior que uma porcentagem definida.
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**: Qualquer delivery agendado dentro de um intervalo definido, com um status pelo menos **[!UICONTROL In progress]**, com uma taxa de erro de rejeição em massa superior a uma porcentagem definida.
* **[!UICONTROL Deliveries with long start pending]**: Qualquer delivery agendado dentro de um intervalo definido, com um **[!UICONTROL Start pending]** status maior que uma duração definida, **[!UICONTROL Start pending]** status que significa que as mensagens ainda não foram levadas em conta pelo sistema.
* **[!UICONTROL Deliveries with low throughput]**: Qualquer delivery iniciado por mais tempo do que uma duração definida, com menos de uma porcentagem definida de mensagens processadas, com uma saída menor do que um valor definido.
* **[!UICONTROL Deliveries in progress]**: Qualquer delivery programado dentro de um intervalo definido, com o **[!UICONTROL In progress]** status.

>[!NOTE]
>
>Todos os parâmetros que se aplicam aos critérios acima têm valores padrão. Esses valores podem ser alterados na **[!UICONTROL Criteria parameters]** guia dos painéis de alerta do delivery. Consulte Parâmetros [de critérios](#criteria-parameters).

Você pode selecionar qualquer item da **[!UICONTROL Delivery alerting criteria]** lista para acessar seus detalhes.

![](assets/delivery-alerting_criteria_definition.png)

Para cada critério, é possível definir as seguintes configurações:

* **[!UICONTROL Indicators to add in alerts]**, ou seja, as colunas que aparecerão na **[!UICONTROL Details]** seção da notificação para os delivery correspondentes ao critério selecionado.

   ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**, ou seja, o rótulo e a cor que aparecerão ao lado do critério do delivery no resumo da notificação.

   ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**: Se um critério for cumprido para um delivery, repete-se em cada notificação enviada durante o período de monitorização. Caso contrário, apenas um alerta será enviado por dia (na primeira ocorrência) por critério de alerta para um delivery.

   Por padrão, essa opção é definida como uma vez por dia para todos os critérios.

**Tópicos relacionados:**

* [Envio de logs](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [Frequência de alerta](#alerting-frequency)
* [Ícones e status da atividade de marketing](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### Criação de um critério de alerta de delivery {#creating-a-delivery-alerting-criterion}

Você pode criar novos critérios de alerta de delivery para melhor atender às suas necessidades.

Por exemplo, você pode criar um novo critério permitindo o envio de uma notificação listando todos os delivery com um **[!UICONTROL Finished]** status.

Para fazer isso, é necessário estender o recurso de **Delivery** e adicionar um novo filtro que permita selecionar apenas os delivery com um **[!UICONTROL Finished]** status.

1. Acesse **Adobe Campaign** > **Administração** > **Desenvolvimento** > Recursos **** personalizados e clique em **[!UICONTROL Create]**.
1. Selecione **[!UICONTROL Extend an existing resource]**, selecione o **[!UICONTROL Delivery]** recurso na lista suspensa e clique **[!UICONTROL Create]** para editá-lo.

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   Para obter mais informações sobre como estender um recurso existente, consulte [Definir o recurso](../../developing/using/creating-or-extending-the-resource.md).

1. No **[!UICONTROL Delivery]** recurso, vá para a **[!UICONTROL Filter definition]** guia e clique **[!UICONTROL Add an element]** para criar um filtro.

   ![](assets/delivery-alerting_new-filter.png)

1. Edite a nova definição de filtro: na **[!UICONTROL Filter definition]** janela, arraste e solte o **[!UICONTROL Status]** item no espaço de trabalho e selecione **[!UICONTROL Finished]** a condição de filtro.

   ![](assets/delivery-alerting_filter-status.png)

   Para obter mais informações sobre como criar e editar filtros personalizados, consulte [Definir filtros](../../developing/using/configuring-filter-definition.md).

1. Salve as alterações e publique os recursos. For more on this, see [Publishing a custom resource](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   O filtro é criado e agora pode ser selecionado em um novo critério de alerta de delivery.

1. Vá até **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**, selecione **[!UICONTROL Delivery alerting criteria]** e clique em **[!UICONTROL Create]**.
1. Na lista **[!UICONTROL Delivery filter applied by this criterion]** suspensa, selecione o filtro que você acabou de criar.

   ![](assets/delivery-alerting_cus-filter.png)

   Você pode definir as configurações do seu critério da mesma forma que para os critérios padrão. Consulte [Sobre critérios](#about-alerting-criteria)de alerta.

Depois de criados, esses critérios podem ser adicionados a um painel de alerta de delivery, bem como a outros critérios. Consulte [Sobre painéis](#about-delivery-alerting-dashboards)de alerta de delivery.

![](assets/delivery-alerting_new-criterion.png)

**Tópicos relacionados:**

[Adicionar ou estender um recurso](../../developing/using/key-steps-to-add-a-resource.md)

## Parâmetros de alerta do delivery {#delivery-alerting-parameters}

### Parâmetros de critérios {#criteria-parameters}

Na **[!UICONTROL Criteria parameters]** guia de um painel [de alerta de](#creating-a-delivery-alerting-dashboard)delivery, é possível definir as configurações que se aplicam aos critérios selecionados nesse painel.

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**: Por exemplo, se você digitar 100 nesse campo, uma notificação será enviada somente para delivery com um público alvo igual ou superior a 100 recipient. Esse parâmetro se aplica a todos os critérios.
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**: Número de horas antes e depois da hora atual. Somente os delivery com data de contato neste intervalo de tempo são considerados. Esse parâmetro se aplica a todos os critérios. Por padrão, o valor desse campo é definido como 24 horas.

   Para obter mais informações sobre a data do contato, consulte [Sobre o agendamento](../../sending/using/about-scheduling-messages.md).

* **[!UICONTROL Maximum ratio of soft bounce errors]**: Uma notificação é enviada para todos os delivery com uma taxa de erro de rejeição suave maior que o valor especificado. Por padrão, o valor desse campo é definido como 0,05 (5%).

   Para obter mais informações sobre erros de rejeição por mala direta, consulte Qualificação [de](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) rejeição de mensagens e [Lista de tipos](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)de falha de delivery.

* **[!UICONTROL Maximum ratio of hard bounce errors]**: Uma notificação é enviada para todos os delivery com uma taxa de erro de rejeição em disco maior que o valor especificado. Por padrão, o valor desse campo é definido como 0,05 (5%).

   Para obter mais informações sobre erros de rejeição, consulte [Rejeitar qualificação](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) de e-mail e [Lista de tipos](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)de falha de delivery.

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**: Uma notificação é enviada para todos os delivery com um **[!UICONTROL Start pending]** status por mais tempo do que a duração especificada neste campo, **[!UICONTROL Start pending]** status que significa que as mensagens ainda não foram levadas em conta pelo sistema.
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**: Somente delivery iniciados (com **[!UICONTROL In progress]** status) por mais do que a duração especificada são considerados para o **[!UICONTROL Deliveries with low throughput]** critério.
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**: Somente delivery com uma porcentagem de mensagens processadas inferior à porcentagem especificada são considerados para o **[!UICONTROL Deliveries with low throughput]** critério.
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**: Somente os delivery com um rendimento inferior ao valor especificado são considerados para o **[!UICONTROL Deliveries with low throughput]** critério.
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**: Somente delivery com uma porcentagem de mensagens processadas superior à porcentagem especificada são considerados.

### Frequência de alerta {#alerting-frequency}

A **[!UICONTROL Frequency of delivery alerting]** opção permite definir o atraso entre dois envios de alerta. Por padrão, é definido como 10 minutos.

É possível alterar essa configuração pelo menu **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** .

>[!NOTE]
>
>Essa opção se aplica a todos os painéis definidos no Adobe Campaign. Não é possível definir uma frequência específica para cada painel.

## Motivos de alerta do delivery {#delivery-alerting-reasons}

O recurso de alerta **do** Delivery mantém todos os usuários envolvidos do Adobe Campaign informados automaticamente sobre o status de execução do delivery, por email e painel.

Agora, quando você recebe uma notificação de alerta de delivery, veja algumas dicas sobre o que você pode fazer.

Primeiro, verifique a guia **Log** do delivery para visualização de todas as informações relacionadas ao delivery e provas. Os ícones vermelho e amarelo permitem identificar erros ou avisos. O ícone vermelho indica um erro crítico que impede que o delivery seja iniciado.

Para visualização do histórico de cada ocorrência de um delivery, selecione a **[!UICONTROL Sending logs]** guia. Ele contém a lista de mensagens enviadas e seus status. Lá, você pode verificar o status do delivery para cada recipient ( **[!UICONTROL Sent]**, **[!UICONTROL Pending]**, **[!UICONTROL Failed]**, etc.). For more on this, see [Sending logs](../../sending/using/monitoring-a-delivery.md#sending-logs).

Estes são alguns motivos possíveis para receber notificações de alerta de acordo com os critérios que são atendidos para um delivery.

* **[!UICONTROL Deliveries failed]**: Este critério informa todos os delivery com um status incorreto. Pode ser devido a:

   * Um problema com o servidor de delivery (MTA, Agente de Transferência de Mensagens)
   * Tempo limite de conexão entre o servidor do delivery Adobe Campaign e o servidor receptor
   * Um problema de entrega
   * Um fluxo de trabalho incorreto

   Se o delivery for acionado com um fluxo de trabalho, verifique se ele foi iniciado corretamente. Para obter mais informações, consulte [Executar um fluxo de trabalho](../../automating/using/about-workflow-execution.md). Caso contrário, entre em contato com o administrador do Adobe Campaign para resolver o problema.

* **[!UICONTROL Deliveries with preparation failed]**: Um erro pode ocorrer durante a preparação do delivery nos seguintes casos:

   * Falta um assunto ao delivery.
   * Há uma sintaxe incorreta nos campos de personalização.
   * O público alvo está faltando.
   * O delivery excede o limite de tamanho.

   Para obter mais informações, consulte [Preparação do envio](../../sending/using/preparing-the-send.md). No entanto, esses erros geralmente são detectados durante a análise da mensagem. Consulte Regras [de controle](../../sending/using/control-rules.md).

* As possíveis causas de um **[!UICONTROL Delivery with bad error ratio for soft bounces]** alerta podem ser:

   * O servidor do recipient está inativo.
   * A caixa de correio do recipient está cheia.

   Para obter mais informações, verifique as guias **[!UICONTROL Exclusion logs]** e **[!UICONTROL Exclusion causes]** os logs do delivery. Consulte Logs [de exclusão](../../sending/using/monitoring-a-delivery.md#exclusion-logs).

   As possíveis causas de um **[!UICONTROL Delivery with bad error ratio for hard bounces]** alerta podem ser:

   * O recipient é adicionado à lista de bloqueios, o que significa que não deseja mais ser contatado.
   * O endereço de email do recipient não existe.
   * O domínio do recipient não existe.
   * O servidor do recipient está bloqueando o delivery.

   Para evitar erros de rejeição em modo suave e rígido, siga as práticas recomendadas abaixo:

   * Crie regras de tipologia de filtragem para excluir uma parte do público alvo de mensagens durante a análise do delivery, como recipient em quarentena. See [Creating a filtering rule](../../sending/using/filtering-rules.md).
   * Atualize regularmente o banco de dados do cliente para manter bons processos de gerenciamento de quarentenas. Consulte [Sobre quarentenas](../../sending/using/understanding-quarantine-management.md#about-quarantines).
   * Em geral, melhore o melhor possível a capacidade de entrega. Consulte a documentação detalhada do Adobe Campaign [Deliverability](../../sending/using/about-deliverability.md) e entre em contato com o administrador da Adobe Campaign para obter assistência.



* **[!UICONTROL Deliveries with long start pending]**: Normalmente, isso significa que há um problema no nível do MTA (Agente de transferência de mensagens). O processo de execução está aguardando a disponibilidade de alguns recursos. O MTA pode não ter sido iniciado.

   **[!UICONTROL Deliveries with low throughput]**: Mais uma vez, este é um problema de entrega, o que significa que o MTA é muito lento.

   Para obter mais informações sobre esses problemas, entre em contato com o administrador da Adobe Campaign.

**Tópicos relacionados:**

* [Noções básicas sobre falhas de delivery](../../sending/using/understanding-delivery-failures.md)
* [Noções básicas sobre gestão de quarentena](../../sending/using/understanding-quarantine-management.md)
* [Sobre participação e não participação no Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

