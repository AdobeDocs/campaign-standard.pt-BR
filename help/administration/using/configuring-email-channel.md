---
solution: Campaign Standard
product: campaign
title: Configuração do canal de email no Adobe Campaign Standard
description: Saiba como configurar o canal de email no Adobe Campaign Standard.
audience: administration
content-type: reference
topic-tags: configuring-channels
context-tags: extAccountEmail,overview;emailConfig,main;ruleSet,overview;delivery,properties,open
feature: Configurações de instância
role: Administrador
level: Experiente
exl-id: 76d70fd1-dd93-4a6d-b18c-96ebe5a27a7d
translation-type: tm+mt
source-git-commit: b899d1926526fccb2fe1fa42db7a4e4317ddb1cb
workflow-type: tm+mt
source-wordcount: '2602'
ht-degree: 76%

---

# Configuração do canal de email{#configuring-email-channel}

Como [administrador](../../administration/using/users-management.md#functional-administrators) do Campaign, você pode definir as configurações de canal de email. Essas configurações avançadas incluem parâmetros gerais de canal de email, contas de roteamento de email, regras de processamento de email e propriedades de email. Nesta página, você aprenderá a editar os valores padrão para o email geral e os parâmetros de envio.

## Parâmetros de canal de email {#email-channel-parameters}

A tela de configuração de email permite definir os parâmetros do canal de email. Os administradores podem acessar essas configurações no menu **[!UICONTROL Administration]> [!UICONTROL Channels] > [!UICONTROL Email] >[!UICONTROL Configuration]**.

![](assets/channels_1.png)

* **Campos de máscaras autorizados**

   A seção **[!UICONTROL Header parameters of sent emails]** lista os endereços de email autorizados que você pode usar para enviar emails para os seus recipients (endereço do remetente) e permitir que eles enviem respostas automatizadas, como rejeições assíncronas, respostas fora do escritório etc. (endereço de erro).  O Adobe Campaign verifica se os endereços inseridos são válidos durante a fase de preparação da mensagem. Esse modo operacional garante que não sejam usados endereços que possam causar problemas de entrega.
   * O endereço de remetente e de erro são configurados pela Adobe. Esses campos não podem estar vazios.
   * Não é possível editar esses campos. Para atualizar um endereço, entre em contato com a equipe de Atendimento ao cliente da Adobe.
   * Para adicionar outro endereço, use o [Painel de controle do Campaign](https://docs.adobe.com/content/help/pt-BR/control-panel/using/subdomains-and-certificates/setting-up-new-subdomain.html) para configurar um novo subdomínio ou entre em contato com a equipe de Atendimento ao cliente da Adobe. Observe que, se forem usadas várias máscaras, elas serão separadas por vírgulas.
   * É uma boa prática definir endereços usando uma estrela, como *@yourdomain.com. Ela permite que você use qualquer endereço que termine com seu nome de subdomínio.

* **Avaliação do delivery**

   A **[!UICONTROL Delivery reports ID]** é fornecida pela equipe de Atendimento ao cliente da Adobe. Ela identifica cada instância com uma ID de avaliação do delivery, usada nos relatórios técnicos de avaliação do delivery.
   <!--The Technical Deliverability report is not accessible through the UI in ACS. It will be replaced with 250ok in the future (project starting).-->

* **Parâmetros do delivery**

   O Adobe Campaign envia as mensagens começando pela data inicial.

   O campo **[!UICONTROL Message delivery duration]** permite especificar o período no qual qualquer mensagem no delivery que encontre um erro temporário ou uma rejeição temporária será repetida.

   >[!IMPORTANT]
   >
   >**Esse parâmetro no Campaign agora só é usado se for definido para 3,5 dias ou menos.** Se você definir um valor superior a 3,5 dias, ele não será considerado.

   O campo **[!UICONTROL Online resources validity duration]** é usado para recursos dos quais foram feitos upload, principalmente para mirror pages e imagens. Os recursos desta página são válidos por um tempo limitado (para economizar espaço em disco).

* **Tentativas**

   As mensagens temporariamente não entregues estão sujeitas a uma nova tentativa automática. Para obter mais informações, consulte [Tentativas após uma falha temporária de delivery](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

   >[!IMPORTANT]
   >
   >O número máximo de tentativas a serem executadas e o atraso mínimo entre tentativas agora se baseiam no desempenho histórico e atual de um IP em um determinado domínio. As configurações **[!UICONTROL Retry period]** e **[!UICONTROL Number of retries]** no Campaign serão ignoradas.

   <!--This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**). By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.-->

* **Parâmetros de quarentena de emails**

   No campo **[!UICONTROL Time between two significant errors]**, insira um valor para definir o tempo que o aplicativo aguarda antes de incrementar o contador de erros, no caso de uma falha provocada por rejeição temporária. O valor padrão é **&quot;1d&quot;**, para 1 dia.

   Quando o valor **[!UICONTROL Maximum number of errors before quarantine]** é atingido, o endereço de email é colocado em quarentena. O valor padrão é **&quot;5&quot;**: o endereço será colocado em quarentena no quinto erro. Isso significa que o contato será automaticamente excluído dos próximos deliveries.
   <!--Actually the way ACS works is that the address is already on the quarantine list on the first bounce, but with a different status meaning that the error count has started.-->

   Para obter mais informações sobre quarentena, consulte [Entendendo o gerenciamento de quarentenas](../../sending/using/understanding-quarantine-management.md).

## Contas de roteamento de emails {#email-routing-accounts}

A conta externa de **[!UICONTROL Integrated email routing]** é fornecida por padrão. Ela contém os parâmetros técnicos que permitem ao aplicativo enviar emails.

![](assets/channels_2.png)

O tipo de conta deve ser sempre definido como **[!UICONTROL Routing]**, o canal, como **[!UICONTROL Email]** e o modo de delivery, como **[!UICONTROL Bulk delivery]**.

**Tópicos relacionados**:

[Contas externas](../../administration/using/external-accounts.md)

## Regras de processamento de emails {#email-processing-rules}

As **[!UICONTROL Email processing rules]** podem ser acessadas pelos administradores pelo menu **[!UICONTROL Administration > Channels > Email]**.

>[!IMPORTANT]
>
>Os domínios de email e as regras MX agora são gerenciados automaticamente<!--by the Adobe Campaign Enhanced MTA (Message Transfer Agent)--> e não podem ser alterados.

* **A assinatura de autenticação de email DKIM (DomainKeys Identified Mail)**  é feita para todas as mensagens com todos os domínios. Ele não faz logon com **ID do remetente**, **DomainKeys** ou **S/MIME**.
* As regras MX personalizam automaticamente sua taxa de transferência por domínio com base em sua própria reputação histórica de email e no feedback em tempo real proveniente dos domínios em que você está enviando emails.

<!--Note that the email domains and the MX rules are now managed by the Adobe Campaign Enhanced MTA:
* **DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.
* The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

### Mensagens de rejeição {#bounce-mails}

As rejeições assíncronas ainda são qualificadas pelo processo de InMail do Campaign por meio das regras de **[!UICONTROL Bounce mails]**.

Essas regras contêm a lista de cadeias de caracteres que podem ser retornadas por servidores remotos e que permitem qualificar o erro (**Definitivo**, **Temporário** ou **Ignorado**).

>[!IMPORTANT]
>
>As mensagens de erro de falha síncrona do delivery agora são qualificadas pelo MTA aprimorado do Adobe Campaign, que determina o tipo de rejeição e a qualificação, e envia essas informações para o Campaign.

Para obter mais informações sobre qualificação de emails rejeitados, consulte esta [seção](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

<!--Because they are now managed by the Enhanced MTA, the bounce qualifications in the Campaign **[!UICONTROL Message qualification]** table are no longer used. For more on bounce mail qualification, see this [section](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

### Management of email domains {#managing-email-domains}

The email domains are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL Domain management]** rules are no longer used.

**DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.

### MX management {#mx-management}

The MX rules are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL MX management]** delivery throughput rules are no longer used.

The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

## Lista de propriedades de email {#list-of-email-properties}

Esta seção detalha a lista de parâmetros disponíveis na tela de propriedades de um template de email ou de um email.

>[!NOTE]
>
>Alguns parâmetros estão disponíveis somente em templates. Os parâmetros que você pode acessar [dependem das suas permissões](../../administration/using/users-management.md).

Para editar as propriedades de um email ou de um modelo de email, use o botão **[!UICONTROL Edit properties]**.

![](assets/delivery_options_1.png)

### Parâmetros gerais {#general-parameters}

Na parte superior da tela de parâmetros de email, identifique o email usando os campos **[!UICONTROL Label]** e **[!UICONTROL ID]**. Essas informações aparecem na interface, mas não estão visíveis para os recipients da mensagem.

![](assets/delivery_options_2.png)

>[!IMPORTANT]
>
>A ID deve ser exclusiva.

O campo **[!UICONTROL Brand]** permite selecionar a marca vinculada ao delivery. Para obter mais informações sobre como usar e configurar marcas, consulte a seção [Branding](../../administration/using/branding.md).

O campo **[!UICONTROL Campaign]** permite inserir a campanha vinculada ao email.

Você também pode adicionar uma **[!UICONTROL Description]** no campo correspondente e editar a imagem exibida na miniatura do email nas listas.

### Envio de parâmetros {#sending-parameters}

A seção **[!UICONTROL Send]** está disponível somente para modelos de email. Ela contém as seguintes parâmetros:

#### Parâmetros de tentativas {#retries-parameters}

As mensagens temporariamente não entregues estão sujeitas a uma nova tentativa automática. Para obter mais informações, consulte [Tentativas após uma falha temporária de delivery](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!IMPORTANT]
>
>O atraso mínimo entre as tentativas e o número máximo de tentativas a serem executadas agora se baseia no desempenho histórico e atual de um IP em um determinado domínio. As configurações **[!UICONTROL Retry period]** e **[!UICONTROL Max. number of retries]** no Campaign serão ignoradas.

A **configuração de duração do delivery** (definida na seção [Parâmetros do período de validade](#validity-period-parameters)) **configurada no Campaign ainda será respeitada, mas somente até 3,5 dias**. A essa altura, qualquer mensagem na fila de tentativas será removida e enviada de volta como uma rejeição. Para obter mais informações, consulte esta [seção](../../sending/using/understanding-delivery-failures.md#about-delivery-failures).

#### Parâmetros de formato do email {#email-format-parameters}

Você pode configurar o formato de emails que serão enviados. Há três opções disponíveis:

* **Usar preferências do recipient** (modo padrão): o formato da mensagem é definido de acordo com os dados armazenados no perfil do recipient e armazenado por padrão no campo **Formato do email** (@emailFormat). Se um recipient quiser receber mensagens em um determinado formato, esse será o formato enviado. Se o campo não estiver finalizado, uma mensagem multipart-alternative será enviada (veja abaixo).
* **Permitir que o cliente de email do recipient escolha o formato mais apropriado (multipart-alternative)**: a mensagem contém ambos os formatos: texto e HTML. O formato exibido no recebimento depende da configuração do software de email do recipient (multipart-alternative).

   >[!IMPORTANT]
   >
   >Essa opção inclui ambas as versões da mensagem. Portanto, isso afeta a taxa de delivery, pois o tamanho da mensagem é maior.

* **Enviar todas as mensagens no formato de texto**: a mensagem é enviada em formato de texto. O formato HTML não será enviado, mas usado somente para a mirror page quando o recipient clicar na mensagem.

#### Modo de teste SMTP {#smtp-test-mode}

A opção **[!UICONTROL Enable SMTP test mode]** permite testar o envio de emails por uma conexão SMTP sem realmente enviar mensagens.
As mensagens são processadas até que a conexão com o servidor SMTP seja alcançada, mas não são enviadas.

![](assets/smtp-test-mode.png)

Esta opção está disponível para emails e templates de email.

Se você ativar a opção de modo de teste SMTP para um template de email, todas as mensagens de email criadas diretamente desse template terão essa opção ativada.

>[!IMPORTANT]
>
>Quando essa opção estiver ativada para um email, nenhuma mensagem será enviada até que ela seja desmarcada.
>Um aviso será exibido no painel do email ou do template de email.

Para obter mais informações sobre como configurar o SMTP, consulte a seção [Lista de parâmetros SMTP de email](#list-of-email-smtp-parameters).

### Parâmetros do período de validade {#validity-period-parameters}

A seção **[!UICONTROL Validity period]** contém os seguintes parâmetros:

![](assets/delivery-validity-period.png)

* **[!UICONTROL Explicitly set validity dates]**: quando essa caixa estiver desmarcada, você deve inserir uma duração nos campos **[!UICONTROL Delivery duration]** e **[!UICONTROL Resource validity limit]**.

   Marque essa caixa se desejar definir datas e horários específicos.

   ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]** / **[!UICONTROL Validity limit for sending messages]**: o Adobe Campaign envia as mensagens que começam na data inicial. Esse campo permite especificar a duração em que as mensagens podem ser enviadas.

   >[!IMPORTANT]
   >
   >**É necessário definir um valor de até 3,5 dias.** Se você definir um valor superior a 3,5 dias, ele não será considerado.

* **[!UICONTROL Resource validity duration]****[!UICONTROL Validity limit date for resources]**: esse campo é usado para recursos dos quais foi feito upload, principalmente para a mirror page e imagens. Os recursos desta página são válidos por um tempo limitado (para economizar espaço em disco).
* **[!UICONTROL Mirror page management]**: a mirror page é uma página HTML acessível online por um navegador da Web. Seu conteúdo é idêntico ao conteúdo do email. Por padrão, a mirror page é gerada se o link for inserido no conteúdo do email. Este campo permite modificar como essa página é gerada:

   >[!IMPORTANT]
   >
   >Um conteúdo HTML deve ter sido definido para o email da mirror page que será criada.

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** (modo padrão): a mirror page é gerada se o link for inserido no conteúdo do email.
   * **Forçar a geração da mirror page**: mesmo se nenhum link para a mirror page for inserido nas mensagens, a mirror page será criada.
   * **Não gerar a mirror page**: nenhuma mirror page é gerada, mesmo se o link estiver presente nas mensagens.
   * **Gerar uma mirror page acessível usando somente a ID de mensagem**: essa opção permite acessar o conteúdo da mirror page, com informações de personalização, na janela de log do delivery.

>[!NOTE]
>
>O parâmetro **[!UICONTROL Delivery duration]** não se aplica a mensagens transacionais. Para obter mais informações, consulte [esta seção](../../channels/using/getting-started-with-transactional-msg.md).

### Parâmetros de rastreamento {#tracking-parameters}

A seção **[!UICONTROL Tracking]** contém os seguintes parâmetros:

* **[!UICONTROL Activate tracking]**: permite ativar/desativar o rastreamento de URL da mensagem. Para gerenciar o rastreamento de cada URL de mensagem, use o ícone **[!UICONTROL Links]** na barra de ação do Designer de email. Consulte [Sobre URLs rastreados](../../designing/using/links.md#about-tracked-urls).
* **[!UICONTROL Tracking validity limit]**: permite definir a duração para a qual o rastreamento será ativado nos URLs.
* **[!UICONTROL Substitution URL for expired URLs]**: você pode inserir um URL para uma página da Web que será exibida depois que o rastreamento expirar.

### Parâmetros avançados {#advanced-parameters}

A seção **[!UICONTROL Advanced parameters]** contém vários parâmetros.

Os primeiros campos permitem inserir as informações necessárias para elaborar cabeçalhos de mensagens de email. É possível gerenciar aqui o endereço de resposta e o texto, bem como o endereço do remetente (que preenche o campo &quot;De:&quot;). Essas informações podem ser personalizadas.

Clique no botão à direita do campo que será alterado e, em seguida, adicione o campo de personalização, o bloco de conteúdo ou o texto dinâmico.

![](assets/advancedparameters.png)

A inserção e o uso do conteúdo de personalização estão detalhados na documentação [Personalização de conteúdo de email](../../designing/using/personalization.md).

#### Contexto do público-alvo {#target-context}

O contexto de direcionamento permite definir um conjunto de tabelas que serão usadas para direcionamento de emails (na tela de definição de público) e personalização (definindo campos de personalização no editor de conteúdo HTML).

#### Roteamento {#routing}

Este campo indica o modo de roteamento usado. Ele faz referência a uma conta externa. Por exemplo, pode ser usado se você quiser usar uma conta externa contendo configurações específicas de marca.

>[!NOTE]
>
>Contas externas podem ser acessadas pelo menu **Administração** > **Configurações de aplicativo** > **Contas externas**.

#### Preparação {#preparation}

A preparação de mensagens está detalhada na seção [Aprovação de mensagens](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Typology]**: antes de qualquer envio, as mensagens devem ser preparadas para validar o conteúdo e a configuração. As regras de verificação aplicadas durante a fase de preparação são definidas em uma **tipologia**. Por exemplo, para emails, a preparação envolve a verificação do assunto, URLs e imagens etc. Selecione a tipologia que será aplicada neste campo.

   >[!NOTE]
   >
   >As tipologias, que podem ser acessadas pelo menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]**, são apresentadas [nesta seção](../../sending/using/about-typology-rules.md).

* **[!UICONTROL Compute the label during delivery preparation]**: permite calcular o valor do rótulo do email durante a fase de preparação da mensagem usando campos de personalização, blocos de conteúdo e texto dinâmico.

   Também é possível personalizar o rótulo do delivery com variáveis de eventos que foram declaradas para a atividade de sinal externo do fluxo de trabalho. Para obter mais informações, consulte [esta seção](../../automating/using/calling-a-workflow-with-external-parameters.md).

* **[!UICONTROL Save SQL queries in the log]**: essa opção permite adicionar logs de consultas SQL no journal durante a fase de preparação.

#### Configurações de prova {#proof-settings}

Esta seção possibilita configurar o prefixo padrão a ser usado na linha de assunto da prova. Para obter mais informações, consulte [esta seção](../../sending/using/sending-proofs.md).

### Lista de parâmetros SMTP de email {#list-of-email-smtp-parameters}

A seção **[!UICONTROL SMTP]** contém os seguintes parâmetros:

* **[!UICONTROL Character encoding]**: marque a caixa **[!UICONTROL Force encoding]** se desejar forçar a codificação de mensagens e selecione a codificação que deseja usar.
* **[!UICONTROL Bounce mails]**: por padrão, os emails de rejeição são recebidos na caixa de entrada de erro da plataforma (definida na tela **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Configuration]**). Para definir um endereço de erro específico para um email, insira o endereço no campo **[!UICONTROL Error address]**.
* **[!UICONTROL Additional SMTP headers]**: essa opção permite que cabeçalhos SMTP adicionais sejam adicionados às suas mensagens. O script inserido no campo **[!UICONTROL Headers]** deve referenciar um cabeçalho por linha no formato de **name:value**. Os valores são codificados automaticamente se necessário.

   >[!IMPORTANT]
   >
   >Adicionar um script para inserir cabeçalhos SMTP adicionais é apenas para usuários avançados. A sintaxe desse script deve estar em conformidade com os requisitos desse tipo de conteúdo: não há espaço não utilizado, nenhuma linha vazia etc.

### Lista dos parâmetros de autorização de acesso {#list-of-access-authorization-parameters}

A seção **[!UICONTROL Access authorization]** contém os seguintes parâmetros:

* O campo **[!UICONTROL Organizational unit]** permite restringir o acesso a esse email a determinados usuários. Os usuários associados à unidade especificada ou às unidades principais terão acesso de leitura e gravação a este email. Os usuários associados às unidades secundárias terão acesso de leitura somente a este email.

   >[!NOTE]
   >
   >Você pode configurar unidades organizacionais por meio do menu **Administração** > **Usuários e Segurança**.

* Os campos **[!UICONTROL Created by]**, **[!UICONTROL Created]**, **[!UICONTROL Modified by]** e **[!UICONTROL Last modified]** são automaticamente preenchidos.

## Configurações herdadas {#legacy-settings}

Se você estiver **NOT** executando a versão mais recente do Campaign, os parâmetros e as seções da interface do usuário descritas abaixo ainda se aplicam a você.

### Tentativas {#legacy-retries}

As configurações **[!UICONTROL Retries]** no menu de [Configuração](#email-channel-parameters) e no [Envio de parâmetros](#retries-parameters) das propriedades de email indicam quantas repetições deverão ser executadas no dia seguinte ao início do envio (**[!UICONTROL Number of retries]** / **[!UICONTROL Max. number of retries]**) e o atraso mínimo entre as tentativas (**[!UICONTROL Retry period]**).

O número de tentativas pode ser alterado globalmente (entre em contato com o administrador técnico do Adobe) ou para cada delivery ou template de delivery.

Por padrão, cinco tentativas são agendadas para o primeiro dia com um intervalo mínimo de uma hora, distribuídas pelas 24 horas do dia. Uma nova tentativa por dia é programada depois disso e até o prazo do delivery, que é definido globalmente na seção **[!UICONTROL Delivery parameters]** do menu **[!UICONTROL Configuration]**, ou na seção **[!UICONTROL Validity period]** no nível do delivery (consulte a seção [Delivery duration](#legacy-delivery-duration) abaixo).

### Duração do delivery {#legacy-delivery-duration}

O parâmetro **[!UICONTROL Message delivery duration]** no menu [Configuração](#email-channel-parameters) permite especificar o período no qual qualquer mensagem no delivery que encontre um erro temporário ou uma rejeição temporária será repetida.

O parâmetro **[!UICONTROL Delivery duration]** ou **[!UICONTROL Validity limit for sending messages]** na seção [Validity period parameters](#validity-period-parameters) permite especificar a duração durante a qual as mensagens podem ser enviadas.

### Regras de processamento de emails {#legacy-email-processing-rules}

As regras **[!UICONTROL MX management]**, **[!UICONTROL Bounce mails]** e **[!UICONTROL Domain management]** podem ser acessadas e modificadas pelos administradores através do menu **[!UICONTROL Administration > Channels > Email > Email processing rules]** [](#email-processing-rules).

### Qualificação de email de rejeição {#legacy-bounce-mail-qualification}

Para listar as várias rejeições e seus tipos de erro associados e motivos, clique no logotipo **[!UICONTROL Adobe Campaign]**, na parte superior esquerda, e selecione **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

As rejeições podem ter os seguintes status de qualificação:

* **[!UICONTROL To qualify]**: o email de devolução precisa ser qualificado. A qualificação deve ser feita pela equipe de Deliverability para garantir que a capacidade de delivery da plataforma funcione corretamente. Contanto que não esteja qualificado, o email de devolução não é usado para enriquecer a lista de regras de processamento de email.
* **[!UICONTROL Keep]**: o email de devolução foi qualificado e será usado pelo workflow  **Update for** deliverability para ser comparado às regras de processamento de email existentes e enriquecer a lista.
* **[!UICONTROL Ignore]**: o email de devolução foi qualificado, mas não será usado pelo workflow  **Update for** deliverability . Portanto, ele não será enviado para as instâncias do cliente.

>[!NOTE]
>
>No caso de uma interrupção de um ISP, os emails enviados pelo Campaign serão marcados incorretamente como rejeições. Para corrigir isso, você precisa atualizar a qualificação de devolução. Para obter mais informações, consulte [esta seção](../../administration/using/update-bounce-qualification.md).

<!--Bounces are qualified through the **[!UICONTROL Bounce mails]** processing rule. For more on accessing this rule, refer to this [section](#legacy-bounce-mail-qualification).-->

### Relatório do indicador entregue {#legacy-delivered-status-report}

Na visualização **[!UICONTROL Summary]** de cada mensagem, a porcentagem **[!UICONTROL Delivered]** aumentará progressivamente durante todo o período de validade do delivery, à medida que as devoluções temporárias e permanentes forem relatadas de volta.

As mensagens de rejeição temporária serão exibidas como **[!UICONTROL Failed]** após o dia do delivery e serão repetidas em cada dia adicional do período de validade do delivery.
