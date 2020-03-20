---
title: Configuração de canal de email no Adobe Campaign Standard
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
source-git-commit: 130eaa44dc89a3b013038660d8e3790f05299136

---


# Configuração do canal de email{#configuring-email-channel}

## Parâmetros de canal de email {#email-channel-parameters}

A tela de configuração de email permite definir os parâmetros do canal de email.

![](assets/channels_1.png)

* **Parâmetros de cabeçalho de emails enviados**

   Nesta seção, você pode especificar o endereço autorizado **[!UICONTROL masks]** para o remetente e o endereço de erro. Se necessário, essas máscaras podem ser separadas por vírgulas. Essa configuração é opcional. Quando esses campos são inseridos, durante a fase de preparação da mensagem, o Adobe Campaign verifica se os endereços digitados são válidos. Esse modo operacional garante que não sejam usados endereços que possam causar problemas de entrega. Os endereços de entrega devem ser configurados no servidor de entrega.

* **Disponibilidade**

   Essa ID é fornecida pelo suporte. É necessário que os relatórios de entrega funcionem corretamente.

* **Parâmetros de entrega**

   O Adobe Campaign envia as mensagens que começam na data de início. O **[!UICONTROL Message delivery duration]** campo permite especificar a duração durante a qual as mensagens podem ser enviadas.

   The **[!UICONTROL Online resources validity duration]** field is used for uploaded resources, mainly for the mirror page and images. Os recursos desta página são válidos por um tempo limitado (para economizar espaço em disco).

* **Repetir**

   As mensagens temporariamente não entregues estão sujeitas a uma nova tentativa automática. Esta seção indica quantas tentativas devem ser executadas no dia seguinte ao início do envio (**Número de tentativas**) e o atraso mínimo entre as tentativas (período **de** novas tentativas).

   Por padrão, cinco tentativas são programadas para o primeiro dia com um intervalo mínimo de uma hora, distribuídas nas 24 horas do dia. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.

* **Parâmetros de quarentena de email**

   No **[!UICONTROL Time between two significant errors]** campo, digite um valor para definir o tempo que o aplicativo aguarda antes de incrementar o contador de erros em caso de falha. Valor padrão: **&quot;1d&quot;**, por 1 dia.

   Quando o **[!UICONTROL Maximum number of errors before quarantine]** valor é atingido, o endereço de email é colocado em quarentena. Valor padrão: **&quot;5&quot;**: o endereço será colocado em quarentena no sexto erro. Isso significa que o contato será automaticamente excluído das entregas subsequentes.

**Tópico** relacionado:

[Noções básicas sobre gestão de quarentena](../../sending/using/understanding-quarantine-management.md)

## Contas de roteamento de email {#email-routing-accounts}

A conta **[!UICONTROL Integrated email routing]** externa é fornecida por padrão. Ele contém os parâmetros técnicos que permitem ao aplicativo enviar emails.

![](assets/channels_2.png)

O tipo de conta deve ser sempre definido como **[!UICONTROL Routing]**, o canal como **[!UICONTROL Email]** e o modo de entrega definido como **[!UICONTROL Bulk delivery]**.

**Tópico** relacionado:

[Contas externas](../../administration/using/external-accounts.md)

## Regras de processamento de email {#email-processing-rules}

Os administradores **[!UICONTROL Email processing rules]** podem acessá-los pelo **[!UICONTROL Administration > Channels > Email]** menu.

Essas regras contêm a lista de cadeias de caracteres que podem ser retornadas por servidores remotos e que permitem que você qualifique o erro (**Grave**, **Suave** ou **Ignorado**).

As regras padrão são as seguintes:

### Mensagens de rejeição {#bounce-mails}

Para mensagens de erro de falha de entrega síncrona, o MTA aprimorado determina o tipo de rejeição e a qualificação e envia essas informações para o Campaign. Para obter mais informações sobre o Adobe Campaign Enhanced MTA, consulte este [documento](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

As rejeições assíncronas ainda são qualificadas pelo processo Campanha no Mail pela **[!UICONTROL Bounce mails]** regra.

>[!IMPORTANT]
>
>Após a atualização para o MTA aprimorado, as qualificações de rejeição na tabela Campanha **[!UICONTROL Message qualification]** não são mais usadas. Para obter mais informações sobre qualificação de envio de e-mails, consulte esta [seção](../../sending/using/understanding-delivery-failures.md).

<!--The user can create his own rules.

>[!IMPORTANT]
>
>When importing a package and when updating data via the **Update for deliverability** workflow, the user-created rules are overwritten.-->

### Gerenciamento de domínios de email {#managing-email-domains}

<!--The Adobe Campaign messaging server applies rules specific to the domains, and then the rules for the general case represented by an asterisk in the list of rules.

The **SMTP parameters** act as filters applied for a blocking rule.

* You can choose whether or not to activate certain identification standards and encryption keys to check the domain name, such as **Sender ID**, **DomainKeys**, **DKIM**, and **S/MIME**.
* **SMTP relay**: lets you configure the IP address and the port of a relay server for a particular domain.-->

>[!IMPORTANT]
>
>Após a atualização para o MTA aprimorado, as **[!UICONTROL Domain management]** regras do Adobe Campaign não são mais usadas.

**A assinatura de autenticação de email DKIM (DomainKeys Identified Mail)** é feita pelo MTA aprimorado para todas as mensagens com todos os domínios. Ele não faz logon com a ID **do** remetente, **DomainKeys**, **DKIM** ou **S/MIME** , a menos que especificado de outra forma no nível MTA aprimorado.

Para obter mais informações sobre o Adobe Campaign Enhanced MTA, consulte este [documento](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

### MX management {#mx-management}

<!--The MX management rules are used to regulate the flow of outgoing emails for a specific domain. They sample the bounce messages and block sending where appropriate.

The Adobe Campaign messaging server applies rules specific to the domains, and then the rules for the general case represented by an asterisk in the list of rules.

To configure MX management rules, simply set a threshold and select certain SMTP parameters. A **threshold** is a limit calculated as an error percentage beyond which all messages towards a specific domain are blocked.-->

>[!IMPORTANT]
>
>Após a atualização para o MTA aprimorado, as regras de **[!UICONTROL MX management]** throughput de entrega do Adobe Campaign não são mais usadas.

O MTA aprimorado usa suas próprias regras MX que permitem personalizar sua throughput por domínio com base na sua própria reputação histórica de email e no feedback em tempo real proveniente dos domínios em que você está enviando emails.

Para obter mais informações sobre o Adobe Campaign Enhanced MTA, consulte este [documento](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

<!--Each rule defines an address mask for the MX. Any MX whose name matches this mask is therefore eligible. The mask can contain "&#42;" and "?" generic characters.

For example, the following addresses:

* a.mx.yahoo.com 
* b.mx.yahoo.com 
* c.mx.yahoo.com

are compatible with the following masks:

* &#42;.yahoo.com
* ?.mx.yahoo.com

These rules are applied in sequence: the first rule whose MX mask is compatible with the targeted MX is applied.

The following parameters are available for each rule:

* **[!UICONTROL Range of IDs]**: this option lets you indicate the ranges of identifiers (publicId) for which the rule applies. You can specify:

    * A number: the rule will only apply to this publicId.
    * A range of numbers (number1-number2): the rule will apply to all publicIds between these two numbers.

  If the field is empty, the rule applies to all IDs.

* **[!UICONTROL Shared]**: this option indicates that the highest number of messages per hour and of connections applies to all MXs linked to this rule. 
* **[!UICONTROL Maximum number of connections]**: maximum number of simultaneous connections to an MX from a given address. 
* **Maximum number of messages**: maximum number of messages that can be sent by one connection. After this amount, the connection is closed and a new one is reopened. 
* **[!UICONTROL Messages per hour]**: maximum number of messages that can be sent in one hour for an MX via a given address.

>[!IMPORTANT]
>
>* The delivery server (MTA) must be restarted if the parameters have been changed. 
>* The modification or creation of management rules is for expert users only. -->

## Lista de propriedades de email {#list-of-email-properties}

Esta seção detalha a lista de parâmetros disponíveis na tela de propriedades de um modelo de email ou de email.

>[!NOTE]
>
>Alguns parâmetros estão disponíveis somente em modelos. Os parâmetros que você pode acessar [dependem de suas permissões](../../administration/using/users-management.md).

Para editar as propriedades de um email ou modelo de email, use o **[!UICONTROL Edit properties]** botão.

![](assets/delivery_options_1.png)

### Parâmetros gerais {#general-parameters}

Na parte superior da tela de parâmetros de email, identifique o email usando os campos **[!UICONTROL Label]** e **[!UICONTROL ID]** . Essas informações aparecem na interface, mas não são visíveis para os destinatários da mensagem.

![](assets/delivery_options_2.png)

>[!IMPORTANT]
>
>A ID deve ser exclusiva.

O **[!UICONTROL Brand]** campo permite selecionar a marca vinculada à entrega. Para obter mais informações sobre como usar e configurar marcas, consulte a seção [Marcas](../../administration/using/branding.md) .

O **[!UICONTROL Campaign]** campo permite que você insira a campanha vinculada ao email.

Você também pode adicionar uma imagem **[!UICONTROL Description]** no campo correspondente e editar a imagem exibida na miniatura do email nas listas.

### Enviando parâmetros {#sending-parameters}

A **[!UICONTROL Send]** seção está disponível somente para modelos de e-mail. Ele contém os seguintes parâmetros:

#### Repetir parâmetros {#retries-parameters}

As mensagens temporariamente não entregues estão sujeitas a uma nova tentativa automática. Esta seção indica quantas tentativas devem ser executadas no dia seguinte ao início do envio ( **[!UICONTROL Max. number of retries]** ) e o atraso mínimo entre as tentativas ( **[!UICONTROL Retry period]** ).

Por padrão, cinco tentativas são programadas para o primeiro dia com um intervalo mínimo de uma hora, distribuídas nas 24 horas do dia. One retry per day is programmed after that and until the delivery deadline, which is defined in the [Validity period parameters](#validity-period-parameters) section.

O número de tentativas pode ser alterado globalmente (entre em contato com o administrador técnico da Adobe) ou para cada entrega ou modelo de entrega

#### Parâmetros de formato de email {#email-format-parameters}

Você pode configurar o formato dos emails a serem enviados. Há três opções disponíveis:

* **Usar preferências** do destinatário (modo padrão): o formato de mensagem é definido de acordo com os dados armazenados no perfil do destinatário e armazenado por padrão no campo de formato **de** email (@emailFormat). Se um recipient deseja receber mensagens em determinado formato, esse será o formato enviado. Se o campo não estiver concluído, uma mensagem multipart-alternativo será enviada (consulte abaixo).
* **Deixe que o cliente de email do destinatário escolha o formato mais apropriado (multipart-alternativo)**: a mensagem contém ambos os formatos: text e HTML. O formato exibido após a recepção depende da configuração do software de email do destinatário (multipart-alternativo).

   >[!IMPORTANT]
   >
   >Essa opção inclui ambas as versões da mensagem. Portanto, isso afeta o throughput de entrega, porque o tamanho da mensagem é maior.

* **Enviar todas as mensagens no formato** de texto: a mensagem é enviada em formato de texto. O formato HTML não será enviado, mas usado para a página espelhada somente quando o destinatário clicar no link na mensagem.

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

* **[!UICONTROL Explicitly set validity dates]**: quando essa caixa estiver desmarcada, você deve inserir uma duração nos campos **[!UICONTROL Delivery duration]** e **[!UICONTROL Resource validity limit]** . Marque essa caixa se desejar definir datas e horários específicos.

   ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]**: O Adobe Campaign envia as mensagens que começam na data de início. Esse campo permite especificar a duração durante a qual as mensagens podem ser enviadas.

   >[!IMPORTANT]
   >
   >Depois de atualizado para o MTA aprimorado, o **[!UICONTROL Delivery duration]** parâmetro nas entregas do Campaign é usado somente se definido para 3,5 dias ou menos. Se você definir um valor superior a 3,5 dias, ele não será considerado. Todos os impactos são detalhados no documento MTA [aprimorado do](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html) Adobe Campaign.

* **[!UICONTROL Resource validity duration]**: esse campo é usado para recursos carregados, principalmente para a página espelhada e imagens. Os recursos desta página são válidos por um tempo limitado (para economizar espaço em disco).
* **[!UICONTROL Mirror page management]**: a página espelhada é uma página HTML acessível on-line através de um navegador da Web. Seu conteúdo é idêntico ao conteúdo do email. Por padrão, a página espelhada é gerada se o link for inserido no conteúdo do email. Este campo permite modificar a forma como esta página é gerada:

   >[!IMPORTANT]
   >
   >Um conteúdo HTML deve ter sido definido para o email da página espelhada a ser criada.

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** (modo padrão): a página espelhada será gerada se o link for inserido no conteúdo do email.
   * **Forçar a geração da página** espelhada: mesmo se nenhum link para a página espelhada for inserido nas mensagens, a página espelhada será criada.
   * **Não gerar a página** espelhada: nenhuma página espelhada é gerada, mesmo se o link estiver nas mensagens.
   * **Gerar uma página espelhada acessível usando apenas a ID** da mensagem: essa opção permite acessar o conteúdo da página espelhada, com informações de personalização, na janela do log de entrega.

>[!NOTE]
>
>O **[!UICONTROL Delivery duration]** parâmetro não se aplica a mensagens transacionais. Para obter mais informações sobre mensagens transacionais, consulte [esta seção](../../channels/using/about-transactional-messaging.md).

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

#### Contexto de destino {#target-context}

O contexto de definição de metas permite definir um conjunto de tabelas que serão usadas para definição de metas de email (na tela de definição de público-alvo) e personalização (definindo campos de personalização no editor de conteúdo HTML).

#### Roteamento {#routing}

Este campo indica o modo de roteamento usado. Ele faz referência a uma conta externa. Por exemplo, isso pode ser usado se você quiser usar uma conta externa que contenha configurações específicas de marca.

>[!NOTE]
>
>As contas externas podem ser acessadas por meio do menu **Administração** > Configurações **de** aplicativo > Contas **** externas.

#### Preparação {#preparation}

A preparação de mensagens é detalhada na seção [Aprovando mensagens](../../sending/using/preparing-the-send.md) .

* **[!UICONTROL Typology]**: antes de qualquer envio, as mensagens devem ser preparadas para validar o conteúdo e a configuração. The verification rules applied during the preparation phase are defined in a **typology**. Por exemplo, para emails, a preparação envolve a verificação do assunto, URLs e imagens etc. Selecione a tipologia a ser aplicada neste campo.

   >[!NOTE]
   >
   >As tipologias, que podem ser acessadas pelo menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** , são apresentadas na seção [Tipologias](../../administration/using/about-typology-rules.md) .

* **[!UICONTROL Compute the label during delivery preparation]**: permite calcular o valor do rótulo do email durante a fase de preparação da mensagem usando campos de personalização, blocos de conteúdo e texto dinâmico.

   Também é possível personalizar o rótulo de entrega com variáveis de eventos que foram declaradas para a atividade de sinal externo do fluxo de trabalho. Para obter mais informações, consulte [esta seção](../../automating/using/calling-a-workflow-with-external-parameters.md).

* **[!UICONTROL Save SQL queries in the log]**: essa opção permite adicionar logs de consulta SQL no diário durante a fase de preparação.

#### Configurações de prova {#proof-settings}

Esta seção permite que você configure o prefixo padrão a ser usado na linha de assunto da prova. For more in this, refer to [this section](../../sending/using/sending-proofs.md).

### Lista de parâmetros SMTP de email {#list-of-email-smtp-parameters}

A **[!UICONTROL SMTP]** seção contém os seguintes parâmetros:

* **[!UICONTROL Character encoding]**: marque a **[!UICONTROL Force encoding]** caixa se desejar forçar a codificação de mensagens e selecione a codificação que deseja usar.
* **[!UICONTROL Bounce mails]**: por padrão, os e-mails de rejeição são recebidos na caixa de entrada de erro da plataforma (definida na tela **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Configuration]** ). Para definir um endereço de erro específico para um email, insira o endereço no **[!UICONTROL Error address]** campo.
* **[!UICONTROL Additional SMTP headers]**: essa opção permite que cabeçalhos SMTP adicionais sejam adicionados às suas mensagens. O script inserido no **[!UICONTROL Headers]** campo deve fazer referência a um cabeçalho por linha, na forma de **name:value**. Os valores são codificados automaticamente se necessário.

   >[!IMPORTANT]
   >
   >Adicionar um script para inserir cabeçalhos SMTP adicionais é apenas para usuários avançados. A sintaxe desse script deve estar em conformidade com os requisitos desse tipo de conteúdo: não há espaço não utilizado, nenhuma linha vazia, etc.

### Lista de parâmetros de autorização de acesso {#list-of-access-authorization-parameters}

A **[!UICONTROL Access authorization]** seção contém os seguintes parâmetros:

* O **[!UICONTROL Organizational unit]** campo permite que você restrinja o acesso a esse email a determinados usuários. Os usuários associados à unidade especificada ou às unidades pai terão acesso de leitura e gravação a este email. Os usuários associados às unidades filhas terão acesso de leitura somente a este email.

   >[!NOTE]
   >
   >Você pode configurar unidades organizacionais por meio do menu **Administração** > **Usuários e segurança** .

* Os campos **[!UICONTROL Created by]**, **[!UICONTROL Created]** e **[!UICONTROL Modified by]** e **[!UICONTROL Last modified]** são automaticamente concluídos.
