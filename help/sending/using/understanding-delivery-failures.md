---
title: Compreensão das falhas de entrega
seo-title: Compreensão das falhas de entrega
description: Compreensão das falhas de entrega
seo-description: Saiba como gerenciar falhas de entrega com a Campanha.
page-status-flag: nunca ativado
uuid: 2735 aa 05-7 b 6 f -47 c 9-98 c 4-a 15 cc 33 be 39 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviando
content-type: reference
topic-tags: monitoramento-mensagens
discoiquuid: 38452841-4 cd 4-4 f 92-a 5 c 3-1 dfdd 54 ff 6 f 4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Understanding delivery failures{#understanding-delivery-failures}

## About delivery failures {#about-delivery-failures}

Quando não é possível enviar uma entrega a um perfil, o servidor remoto envia automaticamente uma mensagem de erro, que é selecionada pela plataforma do Adobe Campaign e qualificada para determinar se o endereço de email ou número de telefone deve ser cercado. See [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

>[!NOTE]
>
>**As mensagens** de erro de e-mail (ou "rejeições") são qualificadas pelo processo do inmail. **As mensagens** de erro SMS (ou "SR" para "Relatório de status") são qualificadas pelo processo MTA.

As mensagens também podem ser excluídas durante a preparação de entrega se um endereço estiver em quarentena ou se um perfil estiver na lista negra. Excluded messages are listed in the **[!UICONTROL Exclusion logs]** tab of the delivery dashboard (see [this section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**Tópicos relacionados:**

* [Noções básicas sobre o gerenciamento de quarentena](../../sending/using/understanding-quarantine-management.md)
* [Gerenciamento de lista negra no Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Identifying delivery failures for a message {#identifying-delivery-failures-for-a-message}

Once a delivery is sent, the **[!UICONTROL Sending logs]** tab (see [this section](../../sending/using/monitoring-a-delivery.md#sending-logs)) allows you to view the delivery status for each profile and the associated failure type and reason (see [Delivery failure types and reasons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)).

![](assets/sending_logs.png)

Um relatório dedicado também está disponível. Este relatório detalha os erros internos e internos gerais encontrados durante as entregas, bem como o processamento automático das rejeições. For more on this, refer to [this section](../../reporting/using/bounce-summary.md).

## Delivery failure types and reasons {#delivery-failure-types-and-reasons}

Há três tipos de erros quando uma entrega falha:

* **Difícil**: Um erro "difícil" indica um endereço inválido. Isso envolve uma mensagem de erro que declara explicitamente que o endereço é inválido, como: " Usuário desconhecido ".
* **Suave**: Isso pode ser um erro temporário ou um que não pôde ser categorizado, como: " Domínio inválido "ou" Mailbox full ".
* **Ignorado**: Este é um erro conhecido por ser temporário, como "Fora do escritório" ou um erro técnico, por exemplo, se o tipo de remetente for "postmaster".

Os possíveis motivos para uma falha de entrega são:

* **[!UICONTROL User unknown]** (Tipo fixo): o endereço não existe. Não haverá mais entregas para este perfil.
* **[!UICONTROL Quarantined address]** (Tipo fixo): o endereço foi colocado em quarentena.
* **[!UICONTROL Unreachable]** (Tipo suave/sólido): ocorreu um erro na cadeia de entrega de mensagens (incidente em RELTP SMTP, domínio temporariamente inatingível, etc.). De acordo com o erro retornado pelo provedor, o endereço será enviado para quarentena diretamente ou a entrega será tentada novamente até que a Campanha receba um erro que justifique o status da Quarentena ou até que o número de erros atinja 5.
* **[!UICONTROL Address empty]** (Tipo fixo): o endereço não está definido.
* **[!UICONTROL Mailbox full]** (Tipo condicional): a caixa de entrada deste usuário está cheia e não pode aceitar mais mensagens. Esse endereço pode ser removido da lista de quarentena para fazer outra tentativa. É removida automaticamente após 30 dias.

   Para que o endereço seja removido automaticamente da lista de endereços em quarentena, o fluxo de trabalho técnico de **[!UICONTROL Database cleanup]** deve ser iniciado.

* **[!UICONTROL Refused]** (Tipo suave/sólido): o endereço foi colocado em quarentena devido a um feedback de segurança como um relatório de spam. De acordo com o erro retornado pelo provedor, o endereço será enviado para quarentena diretamente ou a entrega será tentada novamente até que a Campanha receba um erro que justifique o status da Quarentena ou até que o número de erros atinja 5.
* **[!UICONTROL Duplicate]**: o endereço já foi detectado na segmentação.
* **[!UICONTROL Not defined]** (Tipo condicional): o endereço está na qualificação, pois os erros ainda não foram aumentados.

   Esse tipo de erro ocorre quando uma nova mensagem de erro é enviada pelo servidor: pode ser um erro isolado, mas se ocorrer novamente, o contador de erro aumentará, o que alertará as equipes técnicas.

* **[!UICONTROL Error ignored]**: o endereço está na lista de permissões e um e-mail será enviado a ele em qualquer caso.
* **[!UICONTROL Blacklisted address]**: o endereço foi bloqueado no momento do envio.
* **[!UICONTROL Account disabled]** (Tipo suave/sólido): quando o Provedor de acesso à Internet (IAP) detecta um período longo de inatividade, ele pode fechar a conta do usuário: as entregas ao endereço do usuário serão impossíveis. The Soft or Hard type depends upon the type of error received: if the account is temporarily disabled due to six months of inactivity and can still be activated, the status **[!UICONTROL Erroneous]** will be assigned and the delivery will be tried again. Se o erro recebido receber sinais de que a conta é desativada permanentemente, ela será enviada diretamente para Quarentena.
* **[!UICONTROL Not connected]**: o telefone celular do perfil é desligado ou não está conectado à rede quando a mensagem é enviada.
* **[!UICONTROL Invalid domain]** (Tipo condicional): o domínio do endereço de email está incorreto ou não existe mais. Esse perfil será novamente direcionado até que a contagem de erro atinja 5. Depois disso, o registro será definido como status de Quarentena e nenhuma nova tentativa será seguida.
* **[!UICONTROL Text too long]**: o número de caracteres na mensagem SMS excede o limite. For more on this, see [SMS encoding, length and transliteration](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).
* **[!UICONTROL Character not supported by encoding]**: a mensagem SMS contém um ou mais caracteres que não são suportados pela codificação. &amp;For more on this, see [Table of characters - GSM Standard](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard).

## Retries after a delivery temporary failure {#retries-after-a-delivery-temporary-failure}

If a message fails due to a temporary error of the **Ignored** type, retries will be performed during the delivery duration. For more on the types of errors, see [Delivery failure types and reasons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

Para modificar a duração de uma entrega, vá para os parâmetros avançados do modelo de entrega ou entrega e especifique a duração desejada no campo correspondente. The advanced delivery properties are presented in [this section](../../administration/using/configuring-email-channel.md#validity-period-parameters).

A configuração padrão permite cinco tentativas em intervalos de uma hora, seguida por uma nova tentativa por dia por quatro dias. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).

## Synchronous and asynchronous errors {#synchronous-and-asynchronous-errors}

Uma entrega pode falhar imediatamente (erro síncrono) ou mais recente, após o envio (erro assíncrono).

* **Erro síncrono**: o servidor remoto contatado pelo servidor de entrega do Adobe Campaign imediatamente retornava uma mensagem de erro, não permitia que o envio fosse enviado para o servidor do perfil.
* **Erro assíncrono**: um email de rejeição ou uma SR foi reenviada posteriormente pelo servidor de recebimento. Erros assíncronos podem ocorrer até uma semana depois que uma entrega é enviada.

## Bounce mail qualification {#bounce-mail-qualification}

As mensagens de erro de entrega de entrega (ou "rejeições") são escolhidas pela plataforma do Adobe Campaign e qualificadas pelo processo do inmail para aprimorar a lista de regras de gerenciamento de e-mail.

Essa lista está disponível somente para administradores e contém todas as regras usadas pelo Adobe Campaign para qualificar as falhas de entrega.

To access it, click the **[!UICONTROL Adobe Campaign]** logo, at the top left, then select **[!UICONTROL Administration > Channels > Email > Email processing rules]**.

For more on this, refer to this [section](../../administration/using/configuring-email-channel.md#email-processing-rules).

As rejeições podem ter os seguintes status de qualificação:

* **[!UICONTROL To qualify]**: a rejeição precisa ser qualificada. A qualificação deve ser feita pela equipe de Entrega para garantir que a função de entrega da plataforma funcione corretamente. Desde que não esteja qualificada, o email de rejeição não é usado para aprimorar a lista de regras de processamento de email.
* **[!UICONTROL Keep]**: a rejeição de rejeição foi qualificada e será usada pela **atualização para que** o fluxo de trabalho de disponibilização seja comparado às regras de processamento de email existentes e aprimore a lista.
* **[!UICONTROL Ignore]**: o email de rejeição era qualificado, mas não será usado pela **Atualização para** o fluxo de trabalho de envio. Portanto, ele não será enviado para as instâncias do cliente.

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)

## Optimizing mail deliverability with double opt-in mechanism {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

O mecanismo de opção dupla é uma prática recomendada ao enviar emails. Ele protege a plataforma de endereços de email incorretos ou inválidos, spâmbios e evita possíveis reclamações de spam.

O princípio é enviar um email para confirmar o contrato do visitante antes de armazená-lo como "perfis" no banco de dados da Campanha: o visitante preenche uma página de aterrissagem online, depois recebe um e-mail e precisa clicar no link de confirmação para finalizar sua assinatura.

For more on this, refer to [this section](../../channels/using/setting-up-a-double-opt-in-process.md).
