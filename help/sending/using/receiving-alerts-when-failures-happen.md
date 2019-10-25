---
title: Recebendo alertas quando ocorrem falhas
seo-title: Recebendo alertas quando ocorrem falhas
description: Recebendo alertas quando ocorrem falhas
seo-description: Saiba como usar o sistema de gerenciamento de alertas.
page-status-flag: nunca ativado
uuid: a3ab733a-e3db-4adc-b930-cd4064b6dc1c
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: envio
content-type: referência
topic-tags: mensagens de monitoramento
discoiquuid: 0766bd57-c5f1-4f56-ac84-e5a04d3819ec
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Recebendo alertas quando ocorrem falhas{#receiving-alerts-when-failures-happen}

## Sobre os avisos de entrega {#about-delivery-alerting}

O recurso de alerta **de** Entrega é um sistema de gerenciamento de alertas que permite que um grupo de usuários receba automaticamente notificações contendo informações sobre a execução de suas entregas.

As notificações enviadas contêm um relatório com base, por padrão, nos seguintes critérios:

* Entregas com falha
* Entregas com falha na preparação
* Entregas com uma taxa de erro de rejeição suave
* Entregas com uma taxa de erro de rejeição em disco rígido
* Entregas com status pendente maior do que o normal
* Ofertas com baixa throughput
* Entregas em andamento

Os destinatários dos alertas podem monitorar as entregas que estão sendo processadas pelo Adobe Campaign e tomar as ações apropriadas quando houver problemas na execução.

Essas notificações de alerta podem ser personalizadas dependendo de critérios de alerta específicos definidos por meio de um painel na interface do Adobe Campaign.

>[!NOTE]
>
>As notificações de alerta são entregues somente por email.

As notificações enviadas contêm:

* Uma **[!UICONTROL Summary]** exibição do número de entregas que atendem aos critérios definidos e do rótulo/cor escolhido para cada critério.
* Uma **[!UICONTROL Details]** seção que lista todos os critérios de entrega definidos para o painel correspondente e todas as entregas para cada critério.

![](assets/delivery-alerting_notification.png)

## Painéis de alerta de entrega {#delivery-alerting-dashboards}

### Sobre painéis de aviso de entrega {#about-delivery-alerting-dashboards}

Para gerenciar os destinatários das notificações, definir os critérios de alerta e acessar o histórico dos alertas, é necessário usar painéis.

>[!NOTE]
>
>Para acessar e configurar os painéis e os critérios de alerta, é necessário ter direitos administrativos ou aparecer no grupo de segurança **de supervisores** de entrega. Os usuários padrão não podem acessar os painéis na interface do Adobe Campaign. Eles só podem receber as notificações de alerta. Para obter mais informações sobre usuários e segurança no Adobe Campaign, consulte [Tipos de usuários](../../administration/using/users-management.md) e [Sobre grupos](../../administration/using/managing-groups-and-users.md#about-security-groups)de segurança.

Na interface do Adobe Campaign, é possível:

* Crie e gerencie painéis de aviso de entrega. Consulte [Criação de um painel](#creating-a-delivery-alerting-dashboard)de alertas de entrega.
* Defina e gerencie os critérios de aviso de entrega para cada painel. Por exemplo, você pode criar alertas com base em entregas com falhas de preparação ou entregas com baixa taxa de transferência. Consulte [Sobre critérios](#about-alerting-criteria)de alerta.
* Modifique os parâmetros de critérios para cada painel. Consulte Parâmetros [de critérios](#criteria-parameters).
* Defina um grupo de destinatários para cada painel.

   Por exemplo, você deseja informar os usuários com direitos administrativos somente sobre as entregas com falha. No entanto, você deseja que os usuários de marketing recebam informações sobre as entregas com uma taxa de erro de rejeição suave. Portanto, você precisa criar dois painéis diferentes e definir os critérios que deseja para cada grupo de destinatários.

* Acesse o histórico de todos os alertas enviados para cada painel.

   Ao selecionar um painel, o último alerta enviado para esse painel é exibido por padrão. Todos os alertas enviados são listados à esquerda da tela. Clique em um item na **[!UICONTROL History]** lista para acessar os alertas correspondentes.

![](assets/delivery-alerting_dashboard.png)

### Criar um painel de alertas de entrega {#creating-a-delivery-alerting-dashboard}

Se você quiser enviar notificações com base em critérios específicos para grupos diferentes de usuários, é necessário usar vários painéis. Para criar um novo painel:

1. Vá até **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]**.
1. Selecione **[!UICONTROL Delivery alerting dashboards]** e clique em **[!UICONTROL Create]**.
1. Marque a **[!UICONTROL Enabled]** caixa para ativar o painel atual.

   Se essa opção estiver desativada, as notificações vinculadas a esse painel não serão mais enviadas. Essa opção está desabilitada por padrão.

   ![](assets/delivery-alerting_dashboard_general.png)

1. Selecione o grupo de destinatários que deseja notificar na lista **[!UICONTROL Alert group]** suspensa. Para modificar ou criar um grupo, consulte [Criar um grupo de segurança e atribuir usuários](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users).
1. Na **[!UICONTROL Delivery alerting criteria]** seção, clique **[!UICONTROL Create element]** para adicionar critérios. Consulte [Sobre critérios](#about-alerting-criteria)de alerta.
1. Selecione o **[!UICONTROL Edit properties]** botão. Na **[!UICONTROL Criteria parameters]** guia, defina como os critérios serão aplicados. Consulte Parâmetros [de critérios](#criteria-parameters).
1. Clique em **[!UICONTROL Create]** para salvar o painel.

Agora, cada vez que uma entrega atender aos critérios definidos neste painel, uma notificação de alerta será enviada para o grupo especificado de usuários.

## Critérios de alerta de entrega {#delivery-alerting-criteria}

### Sobre os critérios de alerta {#about-alerting-criteria}

Para acessar os critérios de aviso de entrega, vá até **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]** e selecione **[!UICONTROL Delivery alerting criteria]**.

![](assets/delivery-alerting_criteria.png)

Os seguintes critérios podem ser usados nos painéis de aviso de entrega:

* **[!UICONTROL Deliveries failed]**: Qualquer entrega programada em um intervalo definido, com um status incorreto.
* **[!UICONTROL Deliveries with preparation failed]**: Qualquer entrega modificada em um intervalo definido, para a qual a etapa de preparação (cálculo de destino e geração de conteúdo) falhou. Para obter mais informações, consulte [Preparação do envio](../../sending/using/preparing-the-send.md).
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**: Qualquer entrega programada em um intervalo definido, com um status pelo menos **[!UICONTROL In progress]**, com uma relação de erro de rejeição suave maior que uma porcentagem definida.
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**: Qualquer entrega agendada dentro de um intervalo definido, com um status pelo menos **[!UICONTROL In progress]**, com uma relação de erro de rejeição forçada maior que uma porcentagem definida.
* **[!UICONTROL Deliveries with long start pending]**: Qualquer entrega agendada dentro de um intervalo definido, com um **[!UICONTROL Start pending]** status maior que uma duração definida, **[!UICONTROL Start pending]** status que significa que as mensagens ainda não foram levadas em conta pelo sistema.
* **[!UICONTROL Deliveries with low throughput]**: Qualquer entrega iniciada por mais tempo que uma duração definida, com menos de uma porcentagem definida de mensagens processadas, com uma saída menor que um valor definido.
* **[!UICONTROL Deliveries in progress]**: Qualquer entrega programada em um intervalo definido, com o **[!UICONTROL In progress]** status.

>[!NOTE]
>
>Todos os parâmetros que se aplicam aos critérios acima têm valores padrão. Esses valores podem ser alterados na **[!UICONTROL Criteria parameters]** guia dos painéis de aviso de entrega. Consulte Parâmetros [de critérios](#criteria-parameters).

Você pode selecionar qualquer item na **[!UICONTROL Delivery alerting criteria]** lista para acessar seus detalhes.

![](assets/delivery-alerting_criteria_definition.png)

Para cada critério, é possível definir as seguintes configurações:

* **[!UICONTROL Indicators to add in alerts]**, ou seja, as colunas que aparecerão na **[!UICONTROL Details]** seção da notificação para as entregas correspondentes ao critério selecionado.

   ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**, que significa o rótulo e a cor que aparecerão ao lado do critério de entrega no resumo da notificação.

   ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**: Se um critério for cumprido para uma entrega, repete-se em cada notificação enviada durante o período de monitorização. Caso contrário, somente um alerta será enviado por dia (na primeira ocorrência) por critério de alerta para uma entrega.

   Por padrão, essa opção é definida como uma vez por dia para todos os critérios.

**Tópicos relacionados:**

* [Envio de logs](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [Frequência de alerta](#alerting-frequency)
* [Ícones e status da atividade de marketing](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### Criando um critério de aviso de entrega {#creating-a-delivery-alerting-criterion}

Você pode criar novos critérios de aviso de entrega para melhor atender às suas necessidades.

Por exemplo, você pode criar um novo critério que permite enviar uma notificação listando todas as entregas com um **[!UICONTROL Finished]** status.

Para fazer isso, é necessário estender o recurso **Entrega** e adicionar um novo filtro que permita selecionar apenas as entregas com um **[!UICONTROL Finished]** status.

1. Acesse **Adobe Campaign** &gt; **Administração** &gt; **Desenvolvimento** &gt; Recursos **** personalizados e clique em **[!UICONTROL Create]**.
1. Selecione **[!UICONTROL Extend an existing resource]**, selecione o **[!UICONTROL Delivery]** recurso na lista suspensa e clique **[!UICONTROL Create]** para editá-lo.

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   Para obter mais informações sobre como estender um recurso existente, consulte [Definir o recurso](../../developing/using/creating-or-extending-the-resource.md).

1. No **[!UICONTROL Delivery]** recurso, vá para a **[!UICONTROL Filter definition]** guia e clique **[!UICONTROL Add an element]** para criar um filtro.

   ![](assets/delivery-alerting_new-filter.png)

1. Edite a nova definição de filtro: na **[!UICONTROL Filter definition]** janela, arraste e solte o **[!UICONTROL Status]** item no espaço de trabalho e selecione **[!UICONTROL Finished]** a condição de filtro.

   ![](assets/delivery-alerting_filter-status.png)

   Para obter mais informações sobre como criar e editar filtros personalizados, consulte [Definir filtros](../../developing/using/configuring-filter-definition.md).

1. Salve as alterações e publique os recursos. Para obter mais informações, consulte [Publicação de um recurso](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)personalizado.

   O filtro é criado e pode ser selecionado em um novo critério de alerta de entrega.

1. Vá até **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]**, selecione **[!UICONTROL Delivery alerting criteria]** e clique em **[!UICONTROL Create]**.
1. Na lista **[!UICONTROL Delivery filter applied by this criterion]** suspensa, selecione o filtro que você acabou de criar.

   ![](assets/delivery-alerting_cus-filter.png)

   Você pode definir as configurações do seu critério da mesma forma que para os critérios padrão. Consulte [Sobre critérios](#about-alerting-criteria)de alerta.

Depois de criados, esses critérios podem ser adicionados a um painel de alertas de entrega, bem como a outros critérios. Consulte [Sobre painéis](#about-delivery-alerting-dashboards)de aviso de entrega.

![](assets/delivery-alerting_new-criterion.png)

**Tópico relacionado:**

[Adicionar ou estender um recurso](../../developing/using/key-steps-to-add-a-resource.md)

## Parâmetros de alerta de entrega {#delivery-alerting-parameters}

### Parâmetros de critérios {#criteria-parameters}

Na **[!UICONTROL Criteria parameters]** guia de um painel [de alertas de](#creating-a-delivery-alerting-dashboard)entrega, é possível definir as configurações que se aplicam aos critérios selecionados neste painel.

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**: Por exemplo, se você digitar 100 neste campo, uma notificação será enviada somente para entregas com um destino igual ou superior a 100 destinatários. Esse parâmetro se aplica a todos os critérios.
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**: Número de horas antes e depois da hora atual. Só são tidas em conta as entregas com data de contato neste intervalo de tempo. Esse parâmetro se aplica a todos os critérios. Por padrão, o valor desse campo é definido como 24 horas.

   Para obter mais informações sobre a data do contato, consulte [Sobre o agendamento](../../sending/using/about-scheduling-messages.md).

* **[!UICONTROL Maximum ratio of soft bounce errors]**: Uma notificação é enviada para todas as entregas com uma taxa de erro de rejeição suave maior que o valor especificado. Por padrão, o valor desse campo é definido como 0,05 (5%).

   Para obter mais informações sobre erros de rejeição em modo suave, consulte Qualificação [de](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) rejeição de mensagens e [Lista de tipos](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)de falha de entrega.

* **[!UICONTROL Maximum ratio of hard bounce errors]**: Uma notificação é enviada para todas as entregas com uma taxa de erro de rejeição em disco maior que o valor especificado. Por padrão, o valor desse campo é definido como 0,05 (5%).

   Para obter mais informações sobre erros de rejeição, consulte [Rejeitar qualificação](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) de mensagens e [Lista de tipos](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)de falha de entrega.

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**: Uma notificação é enviada para todas as entregas com um **[!UICONTROL Start pending]** status superior à duração especificada neste campo, o que significa que **[!UICONTROL Start pending]** o sistema ainda não tomou em consideração as mensagens.
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**: Apenas as entregas iniciadas (com **[!UICONTROL In progress]** estatuto) para além da duração especificada são tidas em conta para o **[!UICONTROL Deliveries with low throughput]** critério.
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**: Apenas as entregas com uma percentagem de mensagens processadas inferior à percentagem especificada são tidas em conta para o **[!UICONTROL Deliveries with low throughput]** critério.
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**: Apenas as entregas com um rendimento inferior ao valor especificado são consideradas para o **[!UICONTROL Deliveries with low throughput]** critério.
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**: Somente as entregas com uma porcentagem de mensagens processadas superior à porcentagem especificada são consideradas.

### Frequência de alerta {#alerting-frequency}

A **[!UICONTROL Frequency of delivery alerting]** opção permite definir o atraso entre dois envios de alerta. Por padrão, é definido como 10 minutos.

É possível alterar essa configuração pelo menu **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]** .

>[!NOTE]
>
>Essa opção se aplica a todos os painéis definidos no Adobe Campaign. Não é possível definir uma frequência específica para cada painel.

## Motivos de alerta de entrega {#delivery-alerting-reasons}

O recurso de alerta **de** entrega mantém todos os usuários envolvidos do Adobe Campaign informados automaticamente sobre o status de execução da entrega, por email e painel.

Agora, quando você receber uma notificação de aviso de entrega, veja algumas dicas sobre o que você pode fazer.

Primeiro, verifique a guia **Log** da entrega para exibir todas as informações relacionadas à entrega e às provas. Os ícones vermelho e amarelo permitem identificar erros ou avisos. O ícone vermelho indica um erro crítico que impede que a entrega seja iniciada.

Para exibir o histórico de cada ocorrência de uma entrega, selecione a **[!UICONTROL Sending logs]** guia. Contém a lista de mensagens enviadas e seus status. Lá, você pode verificar o status de entrega de cada destinatário ( **[!UICONTROL Sent]**, **[!UICONTROL Pending]**, **[!UICONTROL Failed]**, etc.). Para obter mais informações, consulte [Enviar logs](../../sending/using/monitoring-a-delivery.md#sending-logs).

Estes são alguns motivos possíveis para receber notificações de alerta de acordo com os critérios que são atendidos para uma entrega.

* **[!UICONTROL Deliveries failed]**: Este critério informa todas as entregas com um status incorreto. Pode ser devido a:

   * Um problema com o servidor de entrega (MTA, Agente de Transferência de Mensagens)
   * Tempo limite de conexão entre o servidor de entrega do Adobe Campaign e o servidor de recebimento
   * Um problema de entrega
   * Um fluxo de trabalho incorreto
   Se a entrega for acionada com um fluxo de trabalho, verifique se esse fluxo de trabalho foi iniciado corretamente. Para obter mais informações, consulte [Executar um fluxo de trabalho](../../automating/using/executing-a-workflow.md). Caso contrário, entre em contato com o administrador do Adobe Campaign para resolver o problema.

* **[!UICONTROL Deliveries with preparation failed]**: Um erro pode ocorrer durante a preparação da entrega nos seguintes casos:

   * Falta um assunto na entrega.
   * Há uma sintaxe incorreta nos campos de personalização.
   * O alvo está faltando.
   * A entrega excede o limite de tamanho.
   Para obter mais informações, consulte [Preparação do envio](../../sending/using/preparing-the-send.md). No entanto, esses erros são geralmente detectados durante a análise de mensagens. Consulte Regras [de controle](../../administration/using/control-rules.md).

* As possíveis causas de um **[!UICONTROL Delivery with bad error ratio for soft bounces]** alerta podem ser:

   * O servidor do destinatário está inativo.
   * A caixa de correio do destinatário está cheia.
   Para obter mais informações, verifique as guias **[!UICONTROL Exclusion logs]** e **[!UICONTROL Exclusion causes]** os registros de entrega. Consulte Logs [de exclusão](../../sending/using/monitoring-a-delivery.md#exclusion-logs).

   As possíveis causas de um **[!UICONTROL Delivery with bad error ratio for hard bounces]** alerta podem ser:

   * O destinatário está na lista negra, o que significa que ele não quer mais ser contatado.
   * O endereço de email do destinatário não existe.
   * O domínio do destinatário não existe.
   * O servidor do destinatário está bloqueando a entrega.
   Para evitar erros de rejeição em modo suave e rígido, siga as práticas recomendadas abaixo:

   * Crie regras de tipologia de filtragem para excluir uma parte do destino da mensagem durante a análise de entrega, como destinatários em quarentena. See [Creating a filtering rule](../../administration/using/filtering-rules.md).
   * Atualize regularmente o banco de dados do cliente para manter bons processos de gerenciamento de quarentena. Consulte [Sobre quarentena](../../sending/using/understanding-quarantine-management.md#about-quarantines).
   * Em geral, melhore o melhor possível a capacidade de entrega. Consulte o guia detalhado do Adobe Campaign v7 [Gerenciar entrega](http://docs.campaign.adobe.com/doc/AC/getting_started/EN/deliverability.html) e entre em contato com o administrador do Adobe Campaign para obter ajuda.



* **[!UICONTROL Deliveries with long start pending]**: Normalmente, isso significa que há um problema no nível do MTA (Agente de transferência de mensagens). O processo de execução está aguardando a disponibilidade de alguns recursos. O MTA pode não ter sido iniciado.

   **[!UICONTROL Deliveries with low throughput]**: Mais uma vez, este é um problema de entrega, o que significa que o MTA é muito lento.

   Para obter mais informações sobre esses problemas, entre em contato com o administrador do Adobe Campaign.

**Tópicos relacionados:**

* [Noções básicas sobre falhas de delivery](../../sending/using/understanding-delivery-failures.md)
* [Noções básicas sobre gestão de quarentena](../../sending/using/understanding-quarantine-management.md)
* [Gerenciamento de listas negras no Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

