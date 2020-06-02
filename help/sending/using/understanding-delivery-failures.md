---
title: Noções básicas sobre falhas de entrega
description: Saiba mais sobre como gerenciar falhas de delivery com a Campanha.
page-status-flag: never-activated
uuid: 2735aa05-7b6f-47c9-98c4-a15cc33be39d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: 38452841-4cd4-4f92-a5c3-1dfdd54ff6f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d05d2692607117e056c360e81d85b7d64c4077a3
workflow-type: tm+mt
source-wordcount: '1279'
ht-degree: 28%

---


# Noções básicas sobre falhas de entrega{#understanding-delivery-failures}

## Sobre falhas de delivery {#about-delivery-failures}

Quando um delivery não pode ser enviado para um perfil, o servidor remoto envia automaticamente uma mensagem de erro, que é coletada pela plataforma Adobe Campaign e qualificada para determinar se o endereço de email ou o número de telefone devem ser colocados em quarentena. Consulte [Qualificação de email de devolução](#bounce-mail-qualification).

>[!NOTE]
>
>**As mensagens de erro de e-mail** (ou &quot;rejeições&quot;) são qualificadas pelo MTA aprimorado (rejeições síncronas) ou pelo processo inMail (rejeições assíncronas).
>
>**Mensagens de erro de SMS (ou &quot;SR&quot; para &quot;Relatório de Status&quot;) são qualificadas pelo processo MTA.**

As mensagens também podem ser excluídas durante a preparação do delivery se um endereço estiver em quarentena ou se um perfil for incluído na blacklist. As mensagens excluídas são listadas na **[!UICONTROL Exclusion logs]** guia do painel do delivery (consulte [esta seção](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**Tópicos relacionados:**

* [Noções básicas sobre gestão de quarentena](../../sending/using/understanding-quarantine-management.md)
* [Gerenciamento de listas negras em Campanhas](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Como identificar falhas de delivery para uma mensagem {#identifying-delivery-failures-for-a-message}

Quando um delivery é enviado, a **[!UICONTROL Sending logs]** guia (consulte [esta seção](../../sending/using/monitoring-a-delivery.md#sending-logs)) permite que você visualização o status do delivery para cada perfil e o tipo e motivo da falha associados (consulte os tipos e motivos [da falha do](#delivery-failure-types-and-reasons)Delivery).

![](assets/sending_logs.png)

Um relatório pronto para uso dedicado também está disponível. Este relatório detalha os erros gerais de hardware e software encontrados durante os delivery, bem como o processamento automático de rejeições. Para obter mais informações, consulte [esta seção](../../reporting/using/bounce-summary.md).

## Tipos e motivos de falha de delivery {#delivery-failure-types-and-reasons}

Há três tipos de erros quando um delivery falha:

* **Hard**: um erro &quot;grave&quot; indica um endereço inválido. Isto envolve uma mensagem de erro que declara explicitamente que o endereço é inválido, como &quot;Unknown user&quot;.
* **Soft**: pode ser um erro temporário ou que não pode ser categorizado, como: &quot;Invalid domain&quot; ou &quot;Mailbox full&quot;.
* **Ignored**: é um erro que é conhecido como temporário, como &quot;Out of office&quot;, ou um erro técnico, por exemplo, se o tipo de remetente for &quot;postmaster&quot;.

Os possíveis motivos para uma falha de delivery são:

| Rótulo de erro | Tipo de erro | Descrição |
---------|----------|---------
| **[!UICONTROL User unknown]** | Grave | O endereço não existe. Não haverá mais tentativas de delivery para este perfil. |
| **[!UICONTROL Quarantined address]** | Grave | O endereço foi colocado em quarentena. |
| **[!UICONTROL Unreachable]** | Suave/Grave | Ocorreu um erro na cadeia de delivery de mensagens (como domínio temporariamente inacessível). De acordo com o erro retornado pelo provedor, o endereço será enviado diretamente para a quarentena ou o delivery será tentado novamente até que a Campanha receba um erro que justifique o status da Quarentena ou até que o número de erros atinja 5. |
| **[!UICONTROL Address empty]** | Grave | O endereço não está definido. |
| **[!UICONTROL Mailbox full]** | Suave | A caixa de entrada deste usuário está cheia e não pode receber mais mensagens. Esse endereço pode ser removido da lista da quarentena para tentar novamente. Ele é removido automaticamente após 30 dias. Para que o endereço seja removido automaticamente da lista de endereços em quarentena, o fluxo de trabalho técnico de **[!UICONTROL Database cleanup]** deve ser iniciado. |
| **[!UICONTROL Refused]** | Suave/Grave | O endereço foi colocado em quarentena devido a um feedback de segurança como um relatório de spam. De acordo com o erro retornado pelo provedor, o endereço será enviado diretamente para a quarentena ou o delivery será tentado novamente até que a Campanha receba um erro que justifique o status da Quarentena ou até que o número de erros atinja 5. |
| **[!UICONTROL Duplicate]** | Ignored | O endereço já foi detectado na segmentação. |
| **[!UICONTROL Not defined]** | Suave | o endereço está em qualificação porque os erros ainda não foram aumentados. Esse tipo de erro ocorre quando uma nova mensagem de erro é enviada pelo servidor: pode ser um erro isolado, mas se ocorrer novamente, o contador de erros aumentará, o que alertará as equipes técnicas. |
| **[!UICONTROL Error ignored]** | Ignored | O endereço está na lista de permissões e um e-mail será enviado para ele em qualquer caso. |
| **[!UICONTROL Blacklisted address]** | Grave | o endereço era incluído na blacklist no momento do envio. |
| **[!UICONTROL Account disabled]** | Suave/Grave | Quando o Provedor de Acesso à Internet (IAP) detecta um longo período de inatividade, ele pode fechar a conta do usuário: delivery para o endereço do usuário serão impossíveis. O tipo Soft ou Hard depende do tipo de erro recebido: se a conta estiver temporariamente desativada devido a seis meses de inatividade e ainda puder ser ativada, o status **[!UICONTROL Erroneous]** será atribuído e o delivery será tentado novamente. Se o erro recebido indicar que a conta está permanentemente desativada, então ela será enviada diretamente para a Quarentena. |
| **[!UICONTROL Not connected]** | Ignored | O telefone móvel do perfil é desligado ou não está conectado à rede quando a mensagem é enviada. |
| **[!UICONTROL Invalid domain]** | Suave | O domínio do endereço de email está incorreto ou não existe mais. Este perfil será alvo novamente até que a contagem de erros chegue a 5. Após isso, o registro será definido como Status de Quarentena e não haverá nenhuma tentativa nova. |
| **[!UICONTROL Text too long]** | Ignored | O número de caracteres na mensagem SMS excede o limite. Para obter mais informações, consulte codificação, comprimento e transliteração [de](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)SMS. |
| **[!UICONTROL Character not supported by encoding]** | Ignored | A mensagem SMS contém um ou mais caracteres que não são suportados pela codificação. &amp;Para obter mais informações, consulte [Tabela de caracteres - GSM Standard](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard). |

## Tentativas após uma falha temporária de delivery {#retries-after-a-delivery-temporary-failure}

Se uma mensagem falhar devido a um erro temporário do tipo **Ignorado** , as tentativas serão executadas durante a duração do delivery. Para obter mais informações sobre os tipos de erros, consulte Tipos de falha de [Delivery e motivos](#delivery-failure-types-and-reasons).

O número de tentativas (quantas tentativas devem ser executadas no dia seguinte ao início do envio) e o atraso mínimo entre as tentativas agora são gerenciados pelo Adobe Campaign Enhanced MTA, com base no desempenho histórico e atual de um IP em um determinado domínio. As configurações do **Tentativas** na Campanha são ignoradas.

Para modificar a duração de um delivery, vá para os parâmetros avançados do delivery ou template do delivery e edite o **[!UICONTROL Delivery duration]** campo da seção Período [de](../../administration/using/configuring-email-channel.md#validity-period-parameters) validade.

>[!IMPORTANT]
>
>**O **[!UICONTROL Delivery duration]**parâmetro em seus delivery de Campanha agora só é usado se definido para 3,5 dias ou menos.** Se você definir um valor superior a 3,5 dias, ele não será considerado, pois agora é gerenciado pela MTA aprimorada do Adobe Campaign.

Por exemplo, se você quiser que o tentativas de um delivery pare após um dia, é possível definir a duração do delivery como **1d**, e o MTA aprimorado vai seguir essa configuração removendo mensagens na fila de tentativas após um dia.

>[!NOTE]
>
>Quando uma mensagem estiver na fila MTA aprimorada por 3,5 dias e não for entregue, o tempo limite expirará e seu status será atualizado de **[!UICONTROL Sent]** para **[!UICONTROL Failed]** nos [logs do delivery](../../sending/using/monitoring-a-delivery.md#delivery-logs).

<!--The default configuration allows five retries at one-hour intervals, followed by one retry per day for four days. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).-->

## Erros síncronos e assíncronos {#synchronous-and-asynchronous-errors}

Um delivery pode falhar imediatamente (erro síncrono), ou posteriormente, depois de ter sido enviado (erro assíncrono).

* **Erro** síncrono: se o servidor remoto contatado pelo servidor de delivery de Adobe Campaign imediatamente retornar uma mensagem de erro, o delivery não poderá ser enviado para o servidor de perfil.
* **Erro** assíncrono: uma mensagem de rejeição ou um SR foi reenviado posteriormente pelo servidor destinatário. Podem ocorrer erros assíncronos até uma semana depois do envio.

## Qualificação de email de devolução {#bounce-mail-qualification}

Para mensagens de erro de falha síncrona de delivery, o MTA aprimorado determina o tipo de rejeição e a qualificação e envia essas informações para a Campanha.

As rejeições assíncronas ainda são qualificadas pelo processo do InMail por meio das regras **[!UICONTROL Inbound email]**. Para acessar essas regras, clique no **[!UICONTROL Adobe Campaign]** logotipo, na parte superior esquerda, selecione **[!UICONTROL Administration > Channels > Email > Email processing rules]** e selecione **[!UICONTROL Bounce mails]**. For more on this rule, refer to this [section](../../administration/using/configuring-email-channel.md#email-processing-rules).

>[!NOTE]
>
>A qualificação de e-mail de rejeição agora é gerenciada pelo MTA aprimorado do Adobe Campaign. As qualificações de rejeição na tabela de Campanha não são mais usadas. **[!UICONTROL Message qualification]**

<!--Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## Otimização da entrega de e-mails com o mecanismo de aceitação de duplos {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

O mecanismo de aceitação do Duplo é uma prática recomendada para enviar emails. Ela protege a plataforma contra endereços de email errados ou inválidos, spambots e evita possíveis reclamações de spam.

O princípio é enviar um e-mail para confirmar o contrato do visitante antes de armazená-lo como &quot;perfis na sua base de dados de Campanhas: o visitante preenche uma landing page on-line, recebe um email e precisa clicar no link de confirmação para finalizar a subscrição.

Para obter mais informações, consulte [esta seção](../../channels/using/setting-up-a-double-opt-in-process.md).
