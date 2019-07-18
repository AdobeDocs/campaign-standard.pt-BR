---
title: Configuração do canal de email
seo-title: Configuração do canal de email
description: Configuração do canal de email
seo-description: Saiba como configurar o canal de email.
page-status-flag: nunca ativado
uuid: 9 fddb 655-b 445-41 f 3-9 b 02-5 d 356 fc 88 aa 1
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuração-canais
discoiquuid: 3752 d 41 f -8 c 59-4 fad-b 30 f-e 98 e 09 cd 74 a 8
context-tags: Extaccountemail, visão geral; Emailconfig, main; Ruleset, overview; entrega, propriedades, abrir
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Configuring email channel{#configuring-email-channel}

## Email channel parameters {#email-channel-parameters}

A tela de configuração de email permite definir os parâmetros para o canal de email.

![](assets/channels_1.png)

* **Parâmetros de cabeçalho de emails enviados**

   In this section, you can specify the **[!UICONTROL masks]** authorized for the sender address and the error address. Se necessário, essas máscaras podem ser separadas usando vírgulas. Essa configuração é opcional. Quando esses campos forem inseridos, o Adobe Campaign verificará se os endereços digitados são válidos. Esse modo operacional garante que nenhum endereço seja usado que possa acionar problemas de entrega. Os endereços de entrega devem ser configurados no servidor de entrega.

* **Entregabilidade**

   Essa ID é fornecida pelo suporte. É necessário que os relatórios de disponibilização funcionem corretamente.

* **Parâmetros de entrega**

   O Adobe Campaign envia as mensagens que começam na data inicial. **[!UICONTROL Message delivery duration]** O campo permite especificar a duração durante a qual as mensagens podem ser enviadas.

   **[!UICONTROL Online resources validity duration]** O campo é usado para recursos carregados, principalmente para a página espelhada e imagens. Os recursos nesta página são válidos por um tempo limitado (para economizar espaço em disco).

* **Tentativas**

   As mensagens não entregues temporariamente estão sujeitas a uma tentativa automática. This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**).

   Por padrão, cinco tentativas são programadas para o primeiro dia com um intervalo mínimo de uma hora, espalhadas pelas 24 horas do dia. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.

* **Parâmetros de quarentena por email**

   In the **[!UICONTROL Time between two significant errors]** field, enter a value to define the time the application waits before incrementing the error counter in case of failure. Defaut value: **"1d"**, for 1 day.

   When the **[!UICONTROL Maximum number of errors before quarantine]** value is reached, the email address is then quarantined. Default value: **"5"**: the address will be quarantined on the sixth error. Isso significa que o contato será excluído automaticamente das entregas subsequentes.

**Tópico relacionado**:

[Noções básicas sobre o gerenciamento de quarentena](../../sending/using/understanding-quarantine-management.md)

## Email routing accounts {#email-routing-accounts}

The **[!UICONTROL Integrated email routing]** external account is provided by default. Ele contém os parâmetros técnicos que permitem ao aplicativo enviar emails.

![](assets/channels_2.png)

The account type must always be set to **[!UICONTROL Routing]**, the channel to **[!UICONTROL Email]** and the delivery mode set to **[!UICONTROL Bulk delivery]**.

**Tópico relacionado**:

[Contas externas](../../administration/using/external-accounts.md)

## Email processing rules {#email-processing-rules}

These rules contain the list of character strings which can be returned by remote servers and which let you qualify the error (**Hard**, **Soft** or **Ignored**).

As regras padrão são as seguintes:

**Mails de rejeição**

Quando um email falhar, o servidor de mensagem remota retornará uma mensagem de erro para o endereço especificado nas configurações do aplicativo. O Adobe Campaign compara o conteúdo de cada email de rejeição para as sequências de caracteres na lista de regras e a atribui um dos três tipos de erros.

O usuário pode criar suas próprias regras.

>[!CAUTION]
>
>When importing a package and when updating data via the **Update for deliverability** workflow, the user-created rules are overwritten.

**Gerenciamento de domínios de email**

As regras de gerenciamento de domínio são usadas para regular o fluxo de emails enviados para um domínio específico. Eles analisam as mensagens de rejeição e bloqueiam o envio quando apropriado. O servidor de mensagens do Adobe Campaign aplica regras específicas aos domínios e, em seguida, as regras para o caso geral representado por um asterisco na lista de regras. As regras para os domínios Hotmail e MSN estão disponíveis por padrão no Adobe Campaign.

Para configurar regras de gerenciamento de domínio, basta definir um limite e selecionar determinados parâmetros SMTP. A **threshold** is a limit calculated as an error percentage beyond which all messages towards a specific domain are blocked.

Por exemplo, no caso geral, para um mínimo de 300 mensagens, o envio de emails é bloqueado por três horas se a taxa de erro atingir 90%.

The **SMTP parameters** act as filters applied for a blocking rule.

* You can choose whether or not to activate certain identification standards and encryption keys to check the domain name, such as **Sender ID**, **DomainKeys**, **DKIM**, and **S/MIME**.
* **Título SMTP**: permite configurar o endereço IP e a porta de um servidor de rell para um domínio específico.

**Gerenciamento MX**

Cada regra define uma máscara de endereço para o MX. Portanto, qualquer MX cujo nome corresponda a essa máscara é elegível. A máscara pode conter " *" e "?" caracteres genéricos.

Por exemplo, os seguintes endereços:

* a.mx.ya hoo.com
* b.mx.ya hoo.com
* c.mx.ya hoo.com

são compatíveis com as seguintes máscaras:

* *.yahoo.com
* ? .mx.yahoo.com

Essas regras são aplicadas em sequência: a primeira regra cuja máscara MX é compatível com o MX alvo é aplicada.

Os seguintes parâmetros estão disponíveis para cada regra:

* **[!UICONTROL Range of IDs]**: esta opção permite indicar os intervalos de identificadores (publicicid) para os quais a regra se aplica. Você pode especificar:

   * Um número: a regra será aplicada somente a esta publicação.
   * Um intervalo de números (número 1-número 2): a regra será aplicada a todas as publicidades entre esses dois números.
   Se o campo estiver vazio, a regra se aplica a todas as IDs.

* **[!UICONTROL Shared]**: esta opção indica que o maior número de mensagens por hora e conexões se aplicam a todos os mxs vinculados a esta regra.
* **[!UICONTROL Maximum number of connections]**: número máximo de conexões simultâneas a um MX a partir de um determinado endereço.
* **Número máximo de mensagens**: número máximo de mensagens que podem ser enviadas por uma conexão. Após essa quantia, a conexão é fechada e uma nova é reaberta.
* **[!UICONTROL Messages per hour]**: número máximo de mensagens que podem ser enviadas em uma hora para um MX por um determinado endereço.

>[!CAUTION]
>
>* O servidor de entrega (MTA) deve ser reiniciado se os parâmetros tiverem sido alterados.
>* A modificação ou a criação de regras de gerenciamento são apenas para usuários especializados.
>



## List of email properties {#list-of-email-properties}

This section details the list of parameters available in the properties screen of an email or [email template](../../start/using/about-templates.md).

>[!NOTE]
>
>Alguns parâmetros só estão disponíveis em modelos. Parameters you can access [depend on your permissions](../../administration/using/types-of-users.md).

To edit the properties of an email or an email template, use the **[!UICONTROL Edit properties]** button.

![](assets/delivery_options_1.png)

### General parameters {#general-parameters}

On the top of the email parameter screen, identify the email using the **[!UICONTROL Label]** and **[!UICONTROL ID]** fields. Essas informações aparecem na interface, mas não estão visíveis para os destinatários da mensagem.

![](assets/delivery_options_2.png)

>[!CAUTION]
>
>A ID deve ser exclusiva.

**[!UICONTROL Brand]** O campo permite que você selecione a marca vinculada à entrega. For more information on using and configuring brands, refer to the [Branding](../../administration/using/branding.md) section.

**[!UICONTROL Campaign]** O campo permite que você insira a campanha vinculada ao e-mail.

You can also add a **[!UICONTROL Description]** in the corresponding field and edit the image displayed on the email thumbnail in the lists.

### Sending parameters {#sending-parameters}

The **[!UICONTROL Send]** section is only available for email templates. Ele contém os seguintes parâmetros:

#### Retries parameters {#retries-parameters}

As mensagens não entregues temporariamente estão sujeitas a uma tentativa automática. This section indicates how many retries should be performed the day after the send is started ( **[!UICONTROL Max. number of retries]** ) and the minimum delay between retries ( **[!UICONTROL Retry period]** ).

Por padrão, cinco tentativas são programadas para o primeiro dia com um intervalo mínimo de uma hora, espalhadas pelas 24 horas do dia. One retry per day is programmed after that and until the delivery deadline, which is defined in the [Validity period parameters](../../administration/using/configuring-email-channel.md#validity-period-parameters) section.

O número de tentativas pode ser alterado globalmente (entre em contato com seu administrador técnico da Adobe) ou para cada entrega ou modelo de entrega

The **[!UICONTROL Test SMTP delivery]** option allows you to test sending messages via SMTP. As mensagens são processadas até que a conexão com o servidor SMTP seja atingida, mas elas não são enviadas. For more information on configuring SMTP, refer to the [List of email SMTP parameters](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters) section.

#### Email format parameters {#email-format-parameters}

É possível configurar o formato de e-mails a serem enviados. Há três opções disponíveis:

* **Use preferências do destinatário** (modo padrão): o formato de mensagem é definido de acordo com os dados armazenados no perfil do destinatário e armazenados por padrão no campo **de formato** de email (@ emailformat). Se um destinatário quiser receber mensagens em um determinado formato, esse é o formato enviado. Se o campo não estiver concluído, uma mensagem multiativa é enviada (veja abaixo).
* **Permita que o cliente de email do destinatário escolha o formato mais adequado (multipart-alternativo)**: a mensagem contém ambos os formatos: texto e HTML. O formato exibido na recepção depende da configuração do software de email do destinatário (multipart-alternative).

   >[!CAUTION]
   >
   >Essa opção inclui ambas as versões da mensagem. Isso afeta a entrega, pois o tamanho da mensagem é maior.

* **Enviar todas as mensagens em formato de texto**: a mensagem é enviada em formato de texto. O formato HTML não será enviado, mas usado para a página espelhada apenas quando o destinatário clicar no link na mensagem.

### Validity period parameters {#validity-period-parameters}

**[!UICONTROL Validity]** A seção contém os seguintes parâmetros:

* **[!UICONTROL Explicitly set validity dates]**: quando essa caixa estiver desmarcada, você deve inserir uma duração nos campos **[!UICONTROL Delivery duration]** e nos **[!UICONTROL Resource validity limit]** campos. Marque essa caixa se desejar definir horas e datas específicas.
* **[!UICONTROL Delivery duration]**: O Adobe Campaign envia as mensagens que começam na data inicial. Esse campo permite especificar a duração durante a qual as mensagens podem ser enviadas.
* **[!UICONTROL Resource validity duration]**: este campo é usado para recursos carregados, principalmente para a página espelhada e imagens. Os recursos nesta página são válidos por um tempo limitado (para economizar espaço em disco).
* **[!UICONTROL Mirror page management]**: a página de espelho é uma página HTML acessível online por meio de um navegador da Web. Seu conteúdo é idêntico ao conteúdo de email. Por padrão, a página espelhada é gerada se o link for inserido no conteúdo de email. Esse campo permite modificar a forma como esta página é gerada:

   >[!CAUTION]
   >
   >Um conteúdo HTML deve ter sido definido para que o e-mail da página espelhada seja criado.

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** (modo padrão): a página espelhada é gerada se o link for inserido no conteúdo de email.
   * **Determine a geração da página de espelho**: mesmo se nenhum link para a página espelhada for inserido nas mensagens, a página espelhada será criada.
   * **Não gere a página de espelho**: nenhuma página espelhada é gerada, mesmo se o link estiver nas mensagens.
   * **Gere uma página de espelho acessível usando apenas a ID da mensagem**: essa opção permite acessar o conteúdo da página de espelho, com informações de personalização, na janela de log de entrega.

>[!NOTE]
>
>The **[!UICONTROL Explicitly set validity dates]** and **[!UICONTROL Delivery duration]** parameters do not apply to transactional messages. For more on transactional messaging, see [this section](../../channels/using/about-transactional-messaging.md).

### Tracking parameters {#tracking-parameters}

**[!UICONTROL Tracking]** A seção contém os seguintes parâmetros:

* **[!UICONTROL Activate tracking]**: permite ativar/desativar o rastreamento de URL da mensagem. To manage tracking for each message URL, use the **[!UICONTROL Links]** icon in the Email Designer action bar. See [About tracked URLs](../../designing/using/about-tracked-urls.md).
* **[!UICONTROL Tracking validity limit]**: permite definir a duração para a qual o rastreamento será ativado nos urls.
* **[!UICONTROL Substitution URL for expired URLs]**: você pode inserir um URL para uma página da Web que será exibida depois que o rastreamento tiver expirado.

### Advanced parameters {#advanced-parameters}

**[!UICONTROL Advanced parameters]** A seção contém vários parâmetros.

Os dois primeiros campos permitem inserir informações necessárias para descrever cabeçalhos de mensagem de email (endereço de resposta e texto de endereço de resposta). Essas informações podem ser personalizadas. Para fazer isso, clique no botão à direita do campo que será alterado e adicione os campos de personalização. Inserting and using the personalization fields is detailed in the [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md) section.

#### Target context {#target-context}

O contexto de definição de metas permite definir um conjunto de tabelas que serão usadas para direcionamento de email (na tela de definição do público-alvo) e personalização (definindo campos de personalização no editor de conteúdo HTML).

#### Routing {#routing}

Este campo indica o modo de roteamento usado. Ele faz referência a uma conta externa. Por exemplo, isso pode ser usado se você deseja usar uma conta externa contendo configurações de marca específicas.

>[!NOTE]
>
>External accounts are accessible via the **Administration** &gt; **Application settings** &gt; **External accounts** menu.

#### Preparation {#preparation}

Preparing messages is detailed in the [Approving messages](../../sending/using/preparing-the-send.md) section.

* **[!UICONTROL Typology]**: antes de qualquer envio, as mensagens devem ser preparadas para validar o conteúdo e a configuração. The verification rules applied during the preparation phase are defined in a **typology**. Por exemplo, para emails, a preparação envolve a verificação do assunto, urls e imagens, etc. Selecione a tipologia a ser aplicada neste campo.

   >[!NOTE]
   >
   >Typologies, which can be accessed via the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** menu, are presented in the [Typologies](../../administration/using/about-typology-rules.md) section.

* **[!UICONTROL Compute the label during delivery analysis]**: permite calcular o valor de rótulo do email durante a fase de preparação de mensagens.
* **[!UICONTROL Save SQL queries in the log]**: esta opção permite que você adicione logs de consulta SQL no diário durante a fase de preparação.

### List of email SMTP parameters {#list-of-email-smtp-parameters}

**[!UICONTROL SMTP]** A seção contém os seguintes parâmetros:

* **[!UICONTROL Character encoding]**: marque a **[!UICONTROL Force encoding]** caixa se desejar forçar a codificação de mensagens e selecione a codificação que deseja usar.
* **[!UICONTROL Bounce mails]**: por padrão, os emails de rejeição são recebidos na caixa de entrada de erro da plataforma (definida em **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Email]** &gt; &gt; **[!UICONTROL Configuration]** ). To define a specific error address for an email, enter the address in the **[!UICONTROL Error address]** field.
* **[!UICONTROL Additional SMTP headers]**: esta opção permite que cabeçalhos SMTP adicionais sejam adicionados às suas mensagens. The script entered in the **[!UICONTROL Headers]** field must reference one header per line, in the form of **name:value**. Os valores são codificados automaticamente, se necessário.

   >[!CAUTION]
   >
   >Adicionar um script para inserir cabeçalhos SMTP adicionais é reservado para usuários avançados. A sintaxe desse script deve atender aos requisitos deste tipo de conteúdo: nenhum espaço não usado, nenhuma linha vazia etc.

### List of access authorization parameters {#list-of-access-authorization-parameters}

**[!UICONTROL Access authorization]** A seção contém os seguintes parâmetros:

* The **[!UICONTROL Organizational unit]** field allows you to restrict access to this email to certain users. Os usuários associados às unidades de unidade ou pai especificadas terão acesso de leitura e gravação a esse email. Os usuários associados a unidades secundárias terão somente acesso de leitura a esse email.

   >[!NOTE]
   >
   >You can configure organizational units via the **Administration** &gt; **Users &amp; Security** menu.

* The **[!UICONTROL Created by]**, **[!UICONTROL Created]**, **[!UICONTROL Modified by]** and **[!UICONTROL Last modified]** fields are automatically completed.

## Archiving emails {#archiving-emails}

Você pode configurar o Adobe Campaign para manter uma cópia de e-mails enviada de sua plataforma.

No entanto, o próprio Adobe Campaign não gerencia arquivos arquivados. Ele permite enviar as mensagens de sua escolha para um endereço dedicado, de onde elas podem ser processadas e arquivadas usando um sistema externo.

Quando ativado no modelo de entrega, esse recurso permite enviar uma cópia exata do correspondente enviado para um endereço de email CCO (invisível para os destinatários de entrega) que você deve especificar.

### Recommendations and limitations {#recommendations-and-limitations}

* Esse recurso é opcional. Verifique seu contrato de licença e entre em contato com seu executivo de contas para ativá-lo.
* Você só pode usar um endereço de email CCO.
* Somente emails enviados com êxito são tomados em conta. As rejeições não são.
* Por motivos de privacidade, os emails Cco devem ser processados por um sistema de arquivamento capaz de armazenar informações de identificação pessoal (PII) com segurança.
* Ao criar um novo modelo de entrega, o Email Cco não é ativado por padrão, mesmo se a opção foi adquirida. Você deve ativá-lo manualmente em cada modelo de entrega para o qual deseja usá-lo.

### Activating email archiving {#activating-email-archiving}

Email BCC is activated in the [email template](../../start/using/about-templates.md), through a dedicated option:

1. Go to **Resources** &gt; **Templates** &gt; **Delivery templates**.
1. Duplicate the out-of-the-box **[!UICONTROL Send via email]** template.
1. Selecione o modelo duplicado.
1. Click the **[!UICONTROL Edit properties]** button to edit the template's properties.
1. Expand the **[!UICONTROL Send]** section.
1. Check the **[!UICONTROL Archive emails]** box to keep a copy of all sent messages for each delivery based on this template.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>If the emails sent to the BCC address are opened and clicked through, this will be taken into account in the **[!UICONTROL Total opens]** and **[!UICONTROL Clicks]** from the send analysis, which could cause some miscalculations.

