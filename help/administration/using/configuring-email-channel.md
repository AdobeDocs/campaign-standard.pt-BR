---
title: Configuração do canal de e-mail no Adobe Campaign Standard
description: Saiba como configurar o canal de email no Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 9fddb655-b445-41f3-9b02-5d356fc88aa1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 3752d41f-8c59-4fad-b30f-e98e09cd74a8
context-tags: extAccountEmail,overview;emailConfig,main;ruleSet,overview;delivery,properties,open
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3cd089751423d9e165b1d44425b1fdfd20b62546

---


# Configuração do canal de email{#configuring-email-channel}

Como [administrador](../../administration/using/users-management.md#functional-administrators)da Campanha, você pode definir as configurações de canal de email. Essas configurações avançadas incluem parâmetros gerais de canal de email, contas de roteamento de email, regras de processamento de email e propriedades de email. Nesta página, você aprenderá a editar os valores padrão para o email geral e os parâmetros de envio.

Observe que algumas configurações de e-mail agora são gerenciadas pela MTA aprimorada do Adobe Campaign. Por conseguinte:
* Algumas configurações na interface do usuário da Campanha não são mais aplicadas:
   * As **[!UICONTROL Retries]** configurações no menu [](#email-channel-parameters) Configuração e nos parâmetros [de](#retries-parameters) envio das propriedades de email.
   * As regras **[!UICONTROL MX management]** e **[!UICONTROL Domain management]** no menu [Regras de processamento de](#email-processing-rules)email.

* Outros parâmetros agora são parcialmente gerenciados pelo MTA aprimorado, enquanto algumas configurações ainda podem ser feitas dentro da Campanha. As configurações impactadas são as seguintes:
   * O **[!UICONTROL Message delivery duration]** parâmetro no **[!UICONTROL Configuration]** menu. Para obter mais informações, consulte [esta seção](#email-channel-parameters).
   * O parâmetro **[!UICONTROL Delivery duration]** ou **[!UICONTROL Validity limit for sending messages]** na **[!UICONTROL Validity period]** seção. Para obter mais informações, consulte [esta seção](#validity-period-parameters).
   * As **[!UICONTROL Bounce mails]** regras no **[!UICONTROL Email processing rules]**. Para obter mais informações, consulte [esta seção](#email-processing-rules).

## Parâmetros de canal de email {#email-channel-parameters}

A tela de configuração de email permite definir os parâmetros do canal de email. Os administradores podem acessar essas configurações no menu **[!UICONTROL Administration]>[!UICONTROL Channels]>[!UICONTROL Email]>[!UICONTROL Configuration]**.

![](assets/channels_1.png)

* **Parâmetros de cabeçalho de emails enviados**

   Nesta seção, você pode especificar o endereço autorizado **[!UICONTROL masks]** para o remetente e o endereço de erro. Se forem usadas várias máscaras, elas devem ser separadas por vírgulas. Quando esses campos forem preenchidos, o Adobe Campaign verifica se os endereços digitados são válidos durante a fase de preparação da mensagem. Esse modo operacional garante que não sejam usados endereços que possam causar problemas de entrega. O remetente e os endereços de erro são configurados pela Adobe. É necessário entrar em contato com a equipe de Atendimento ao cliente da Adobe para atualizá-los.

* **Disponibilidade**

   Essa ID é fornecida pela equipe de Atendimento ao cliente da Adobe. É obrigatório que os relatórios de entrega funcionem corretamente.

* **Parâmetros do Delivery**

   O Adobe Campaign envia as mensagens que começam na data do start. O **[!UICONTROL Message delivery duration]** campo permite especificar a duração durante a qual as mensagens podem ser enviadas.

   >[!IMPORTANT]
   >
   >**Esse parâmetro na Campanha agora só é usado se definido para 3,5 dias ou menos.** Se você definir um valor superior a 3,5 dias, ele não será considerado, pois agora é gerenciado pela MTA aprimorada do Adobe Campaign.

   The **[!UICONTROL Online resources validity duration]** field is used for uploaded resources, mainly for the mirror page and images. Os recursos desta página são válidos por um tempo limitado (para economizar espaço em disco).

* **Tentativas**

   As mensagens temporariamente não entregues estão sujeitas a uma nova tentativa automática. For more on this, see [Retries after a delivery temporary failure](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

   >[!NOTE]
   >
   >O número máximo de tentativas a serem executadas e o atraso mínimo entre tentativas agora são gerenciados pelo Adobe Campaign Enhanced MTA, com base no desempenho histórico e atual de um IP em um determinado domínio. As configurações do **Tentativas** no Campaign serão ignoradas.

   <!--This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**). By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.-->

* **Parâmetros de quarentena de email**

   No **[!UICONTROL Time between two significant errors]** campo, digite um valor para definir o tempo que o aplicativo aguarda antes de incrementar o contador de erros em caso de falha. O valor padrão é **&quot;1d&quot;**, por 1 dia.

   Quando o **[!UICONTROL Maximum number of errors before quarantine]** valor é atingido, o endereço de email é colocado em quarentena. O valor padrão é **&quot;5&quot;**: o endereço será colocado em quarentena no quinto erro. Isso significa que o contato será automaticamente excluído dos delivery subsequentes.

   Para obter mais informações sobre o quarentena, consulte [Entendendo o gerenciamento](../../sending/using/understanding-quarantine-management.md)de quarentenas.

## Contas de roteamento de email {#email-routing-accounts}

A **[!UICONTROL Integrated email routing]** conta externa é fornecida por padrão. Ele contém os parâmetros técnicos que permitem ao aplicativo enviar emails.

![](assets/channels_2.png)

O tipo de conta deve ser sempre definido como **[!UICONTROL Routing]**, o canal como **[!UICONTROL Email]** e o modo delivery como **[!UICONTROL Bulk delivery]**.

**Tópicos relacionados**:

[Contas externas](../../administration/using/external-accounts.md)

## Regras de processamento de email {#email-processing-rules}

Os administradores **[!UICONTROL Email processing rules]** podem acessá-los pelo **[!UICONTROL Administration > Channels > Email]** menu.

Observe que os domínios de email e as regras MX agora são gerenciados pelo MTA aprimorado do Adobe Campaign:
* **A assinatura de autenticação de email DKIM (DomainKeys Identified Mail)** é feita pelo MTA aprimorado para todas as mensagens com todos os domínios. Ele não faz logon com a ID **do** remetente, **DomainKeys** ou **S/MIME** , a menos que especificado de outra forma no nível MTA aprimorado.
* O MTA aprimorado usa suas próprias regras MX que permitem personalizar sua throughput por domínio com base na sua própria reputação histórica de email e no feedback em tempo real proveniente dos domínios em que você está enviando emails.

### Mensagens de rejeição {#bounce-mails}

As rejeições assíncronas ainda são qualificadas pelo processo de Campanha inMail por meio da **[!UICONTROL Bounce mails]** regra.

This rule contains the list of character strings which can be returned by remote servers and which let you qualify the error (**Hard**, **Soft** or **Ignored**).

>[!NOTE]
>
>Para mensagens de erro de falha síncrona de delivery, o MTA aprimorado Adobe Campaign determina o tipo de rejeição e a qualificação e envia essas informações para a Campanha.

Para obter mais informações sobre qualificação de envio de e-mails, consulte esta [seção](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

<!--Because they are now managed by the Enhanced MTA, the bounce qualifications in the Campaign **[!UICONTROL Message qualification]** table are no longer used. For more on bounce mail qualification, see this [section](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

### Management of email domains {#managing-email-domains}

The email domains are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL Domain management]** rules are no longer used.

**DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.

### MX management {#mx-management}

The MX rules are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL MX management]** delivery throughput rules are no longer used.

The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

## Lista de propriedades de e-mail {#list-of-email-properties}

Esta seção detalha a lista de parâmetros disponíveis na tela de propriedades de um modelo de email ou de email.

>[!NOTE]
>
>Alguns parâmetros estão disponíveis somente em modelos. Os parâmetros que você pode acessar [dependem de suas permissões](../../administration/using/users-management.md).

Para editar as propriedades de um email ou modelo de email, use o **[!UICONTROL Edit properties]** botão.

![](assets/delivery_options_1.png)

### Parâmetros gerais {#general-parameters}

Na parte superior da tela de parâmetros de email, identifique o email usando os campos **[!UICONTROL Label]** e **[!UICONTROL ID]** . Essas informações aparecem na interface, mas não são visíveis para os recipient de mensagem.

![](assets/delivery_options_2.png)

>[!IMPORTANT]
>
>A ID deve ser exclusiva.

O **[!UICONTROL Brand]** campo permite selecionar a marca vinculada ao delivery. Para obter mais informações sobre como usar e configurar marcas, consulte a seção [Marcas](../../administration/using/branding.md) .

O **[!UICONTROL Campaign]** campo permite que você insira a campanha vinculada ao email.

Você também pode adicionar uma imagem **[!UICONTROL Description]** no campo correspondente e editar a imagem exibida na miniatura do email nas listas.

### Enviando parâmetros {#sending-parameters}

A **[!UICONTROL Send]** seção está disponível somente para modelos de e-mail. Ele contém os seguintes parâmetros:

#### Parâmetros do Tentativas {#retries-parameters}

As mensagens temporariamente não entregues estão sujeitas a uma nova tentativa automática. For more on this, see [Retries after a delivery temporary failure](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>O atraso mínimo entre o tentativas e o número máximo de tentativas a serem executadas agora são gerenciados pelo Adobe Campaign Enhanced MTA, com base no desempenho histórico e atual de um IP em um determinado domínio. As configurações do Campaign **Tentativas** serão ignoradas.

<!--This section indicates how many retries should be performed the day after the send is started ( **[!UICONTROL Max. number of retries]** ) and the minimum delay between retries ( **[!UICONTROL Retry period]** ).

By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the [Validity period parameters](#validity-period-parameters) section.

The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template.-->

A configuração **de duração do** delivery (definida na seção Parâmetros [do período de](#validity-period-parameters) validade) **configurada na Campanha ainda será respeitada, mas somente até 3,5 dias**. Nesse ponto, qualquer mensagem na fila de tentativas será removida da fila e enviada de volta como uma rejeição. Para obter mais informações sobre falhas de delivery, consulte esta [seção](../../sending/using/understanding-delivery-failures.md#about-delivery-failures).

#### Parâmetros do Formato do email {#email-format-parameters}

Você pode configurar o formato dos emails a serem enviados. Há três opções disponíveis:

* **Usar preferências** de recipient (modo padrão): o formato de mensagem é definido de acordo com os dados armazenados no perfil do recipient e armazenado por padrão no campo **Formato do email** (@emailFormat). Se um recipient deseja receber mensagens em determinado formato, esse será o formato enviado. Se o campo não estiver concluído, uma mensagem de multipart-alternative será enviada (veja abaixo).
* **Permitir que o cliente de e-mail do recipient escolha o formato mais apropriado (multipart-alternative)**: a mensagem contém ambos os formatos: text e HTML. O formato exibido após a recepção depende da configuração do software de e-mail do recipient.

   >[!IMPORTANT]
   >
   >Essa opção inclui ambas as versões da mensagem. Portanto, isso afeta o throughput do delivery, porque o tamanho da mensagem é maior.

* **Enviar todas as mensagens no formato** de texto: a mensagem é enviada em formato de texto. O formato HTML não será enviado, mas usado para o mirror page somente quando o recipient clicar no link na mensagem.

#### Modo de teste SMTP {#smtp-test-mode}

A **[!UICONTROL Enable SMTP test mode]** opção permite que você teste o envio de emails por uma conexão SMTP sem realmente enviar mensagens.
As mensagens são processadas até que a conexão com o servidor SMTP seja alcançada, mas não são enviadas.

![](assets/smtp-test-mode.png)

Esta opção está disponível para e-mails e modelos de e-mail.

Se você ativar a opção de modo de teste SMTP para um modelo de email, todas as mensagens de email criadas a partir desse modelo terão essa opção ativada.

>[!IMPORTANT]
>
>Quando esta opção estiver ativada para um email, nenhuma mensagem será enviada até que ela seja desmarcada.
>Um aviso será exibido no painel de e-mail ou modelo de e-mail.

Para obter mais informações sobre como configurar o SMTP, consulte a seção [Lista de parâmetros](#list-of-email-smtp-parameters) SMTP de email.

### Parâmetros do período de validade {#validity-period-parameters}

A **[!UICONTROL Validity period]** seção contém os seguintes parâmetros:

![](assets/delivery-validity-period.png)

* **[!UICONTROL Explicitly set validity dates]**: quando essa caixa está desmarcada, é necessário inserir uma duração nos campos **[!UICONTROL Delivery duration]** e **[!UICONTROL Resource validity limit]** .

   Marque essa caixa se desejar definir datas e horários específicos.

   ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]** / **[!UICONTROL Validity limit for sending messages]**: O Adobe Campaign envia as mensagens que começam na data do start. Esse campo permite especificar a duração durante a qual as mensagens podem ser enviadas.

   >[!IMPORTANT]
   >
   >Esse parâmetro agora é gerenciado pelo Adobe Campaign Enhanced MTA. **É necessário definir um valor de até 3,5 dias.** Se você definir um valor superior a 3,5 dias, ele não será considerado.

* **[!UICONTROL Resource validity duration]** / **[!UICONTROL Validity limit date for resources]**: este campo é usado para recursos carregados, principalmente para o mirror page e imagens. Os recursos desta página são válidos por um tempo limitado (para economizar espaço em disco).
* **[!UICONTROL Mirror page management]**: o mirror page é uma página HTML acessível on-line através de um navegador da Web. Seu conteúdo é idêntico ao conteúdo do email. Por padrão, o mirror page é gerado se o link for inserido no conteúdo do email. Este campo permite modificar a forma como esta página é gerada:

   >[!IMPORTANT]
   >
   >O conteúdo HTML deve ter sido definido para o email do mirror page a ser criado.

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** (modo padrão): o mirror page é gerado se o link for inserido no conteúdo do email.
   * **Forçar a geração do mirror page**: mesmo se nenhum link para o mirror page for inserido nas mensagens, o mirror page será criado.
   * **Não gerar o mirror page**: nenhum mirror page é gerado, mesmo se o link estiver nas mensagens.
   * **Gerar um mirror page acessível usando apenas a ID** da mensagem: essa opção permite acessar o conteúdo do mirror page, com informações de personalização, na janela do log de delivery.

>[!NOTE]
>
>O **[!UICONTROL Delivery duration]** parâmetro não se aplica a mensagens transacionais. For more on transactional messaging, see [this section](../../channels/using/about-transactional-messaging.md).

### Parâmetros de rastreamento {#tracking-parameters}

A **[!UICONTROL Tracking]** seção contém os seguintes parâmetros:

* **[!UICONTROL Activate tracking]**: permite ativar/desativar o rastreamento de URL da mensagem. Para gerenciar o rastreamento de cada URL de mensagem, use o **[!UICONTROL Links]** ícone na barra de ação do Designer de email. Consulte [Sobre URLs](../../designing/using/links.md#about-tracked-urls)acompanhados.
* **[!UICONTROL Tracking validity limit]**: permite definir a duração para a qual o rastreamento será ativado nos URLs.
* **[!UICONTROL Substitution URL for expired URLs]**: você pode inserir um URL para uma página da Web que será exibida depois que o rastreamento expirar.

### Parâmetros avançados {#advanced-parameters}

A **[!UICONTROL Advanced parameters]** seção contém vários parâmetros.

Os primeiros campos permitem que você insira as informações necessárias para elaborar cabeçalhos de mensagens de email. É possível gerenciar aqui o endereço de resposta e o texto, bem como o endereço do remetente (que preenche o campo &quot;De:&quot;). Essas informações podem ser personalizadas.

Clique no botão à direita do campo que será alterado e, em seguida, adicione o campo de personalização, o bloco de conteúdo ou o texto dinâmico.

![](assets/advancedparameters.png)

A inserção e o uso do conteúdo de personalização são detalhados na documentação [Personalização do conteúdo](../../designing/using/personalization.md) de email.

#### contexto do Público alvo {#target-context}

O contexto de definição de metas permite definir um conjunto de tabelas que serão usadas para definição de metas de email (na tela de definição de audiência) e personalização (definindo campos de personalização no editor de conteúdo HTML).

#### Roteamento {#routing}

Este campo indica o modo de roteamento usado. Ela faz referência a uma conta externa. Por exemplo, isso pode ser usado se você quiser usar uma conta externa contendo configurações específicas de marca.

>[!NOTE]
>
>O Conta externa pode ser acessado por meio do menu **Administração** > Configurações **** do aplicativo > **Conta externa** .

#### Preparação {#preparation}

A preparação de mensagens é detalhada na seção [Aprovando mensagens](../../sending/using/preparing-the-send.md) .

* **[!UICONTROL Typology]**: antes de qualquer envio, as mensagens devem ser preparadas para validar o conteúdo e a configuração. The verification rules applied during the preparation phase are defined in a **typology**. Por exemplo, para emails, a preparação envolve a verificação do assunto, URLs e imagens etc. Selecione a tipologia a ser aplicada neste campo.

   >[!NOTE]
   >
   >As tipologias, que podem ser acessadas pelo menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** , são apresentadas [nesta seção](../../sending/using/about-typology-rules.md).

* **[!UICONTROL Compute the label during delivery preparation]**: permite calcular o valor do rótulo do email durante a fase de preparação da mensagem usando campos de personalização, blocos de conteúdo e texto dinâmico.

   Também é possível personalizar o rótulo do delivery com variáveis de eventos que foram declaradas para a atividade de sinal externo do fluxo de trabalho. Para obter mais informações, consulte [esta seção](../../automating/using/calling-a-workflow-with-external-parameters.md).

* **[!UICONTROL Save SQL queries in the log]**: essa opção permite que você adicione logs de query SQL no journal durante a fase de preparação.

#### Configurações de Prova {#proof-settings}

Esta seção permite que você configure o prefixo padrão a ser usado na linha de assunto do prova. For more in this, refer to [this section](../../sending/using/sending-proofs.md).

### Lista de parâmetros SMTP de email {#list-of-email-smtp-parameters}

A **[!UICONTROL SMTP]** seção contém os seguintes parâmetros:

* **[!UICONTROL Character encoding]**: marque a **[!UICONTROL Force encoding]** caixa se desejar forçar a codificação de mensagens e selecione a codificação que deseja usar.
* **[!UICONTROL Bounce mails]**: por padrão, os e-mails de rejeição são recebidos na caixa de entrada de erro da plataforma (definida na tela **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Configuration]** ). Para definir um endereço de erro específico para um email, insira o endereço no **[!UICONTROL Error address]** campo.
* **[!UICONTROL Additional SMTP headers]**: essa opção permite que cabeçalhos SMTP adicionais sejam adicionados às suas mensagens. The script entered in the **[!UICONTROL Headers]** field must reference one header per line, in the form of **name:value**. Os valores são codificados automaticamente se necessário.

   >[!IMPORTANT]
   >
   >Adicionar um script para inserir cabeçalhos SMTP adicionais é apenas para usuários avançados. A sintaxe desse script deve estar em conformidade com os requisitos desse tipo de conteúdo: não há espaço não utilizado, nenhuma linha vazia, etc.

### Lista dos parâmetros de autorização de acesso {#list-of-access-authorization-parameters}

A **[!UICONTROL Access authorization]** seção contém os seguintes parâmetros:

* O **[!UICONTROL Organizational unit]** campo permite que você restrinja o acesso a esse email a determinados usuários. Os usuários associados à unidade especificada ou às unidades pai terão acesso de leitura e gravação a este email. Os usuários associados às unidades filhas terão acesso de leitura somente a este email.

   >[!NOTE]
   >
   >Você pode configurar unidades organizacionais por meio do menu **Administração** > **Usuários e segurança** .

* Os campos **[!UICONTROL Created by]**, **[!UICONTROL Created]** e **[!UICONTROL Modified by]** e **[!UICONTROL Last modified]** são automaticamente concluídos.
