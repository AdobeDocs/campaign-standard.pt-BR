---
solution: Campaign Standard
product: campaign
title: Noções básicas sobre falhas de delivery
description: Saiba mais sobre como gerenciar falhas de delivery com o Campaign.
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Capacidade de delivery
role: User
level: Intermediate
exl-id: 92a83400-447a-4d23-b05c-0ea013042ffa
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 74%

---

# Compreensão de falhas de entrega{#understanding-delivery-failures}

## Sobre falhas de delivery {#about-delivery-failures}

Quando um delivery não pode ser enviado a um perfil, o servidor remoto envia automaticamente uma mensagem de erro, que é recebida pela plataforma do Adobe Campaign, que determina se o endereço de email ou o número de telefone deve ir para a quarentena. Consulte [Qualificação de email de devolução](#bounce-mail-qualification).

>[!NOTE]
>
>Mensagens de erro de **email** (ou &quot;rejeições&quot;) são qualificadas pelo MTA aprimorado (rejeições síncronas) ou pelo processo inMail (rejeições assíncronas).
>
>**Mensagens de erro de SMS (ou &quot;SR&quot; para &quot;Relatório de Status&quot;) são qualificadas pelo processo MTA.**

As mensagens também podem ser excluídas durante a preparação do delivery se um endereço estiver em quarentena ou se um perfil estiver na lista de bloqueios. As mensagens excluídas são listadas na guia **[!UICONTROL Exclusion logs]** do painel de delivery (consulte [esta seção](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**Tópicos relacionados:**

* [Compreensão do gerenciamento de quarentena](../../sending/using/understanding-quarantine-management.md)
* [Sobre aceitação e recusa no Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
* [Rejeições](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#metrics-for-deliverability)

## Identificação de falhas de delivery para uma mensagem {#identifying-delivery-failures-for-a-message}

Quando um delivery é enviado, a guia **[!UICONTROL Sending logs]** (consulte [esta seção](../../sending/using/monitoring-a-delivery.md#sending-logs)) permite visualizar o status do delivery para cada perfil e o tipo e motivo da falha associados (consulte [Tipos e motivos de falha de delivery](#delivery-failure-types-and-reasons)).

![](assets/sending_logs.png)

Um relatório pronto para uso dedicado também está disponível. Esse relatório detalha os erros gerais de hardware e software encontrados durante os deliveries, bem como o processamento automático de rejeições. Para obter mais informações, consulte [esta seção](../../reporting/using/bounce-summary.md).

## Tipos e motivos de falha de entrega {#delivery-failure-types-and-reasons}

Há três tipos de erros quando um delivery falha:

* **Hard**: um erro &quot;grave&quot; indica um endereço inválido. Isto envolve uma mensagem de erro que declara explicitamente que o endereço é inválido, como &quot;Unknown user&quot;.
* **Soft**: pode ser um erro temporário ou que não pode ser categorizado, como: &quot;Domínio inválido&quot; ou &quot;Caixa de entrada cheia&quot;.
* **Ignored**: é um erro que é conhecido como temporário, como &quot;Out of office&quot;, ou um erro técnico, por exemplo, se o tipo de remetente for &quot;postmaster&quot;.

Os possíveis motivos para uma falha de delivery são:

| Rótulo de erro | Tipo de erro | Descrição |
| ---------|----------|---------|
| **[!UICONTROL User unknown]** | Grave | O endereço não existe. Não haverá mais tentativas de delivery para esse perfil. |
| **[!UICONTROL Quarantined address]** | Grave | O endereço foi colocado em quarentena. |
| **[!UICONTROL Unreachable]** | Suave/Grave | Ocorreu um erro na cadeia de delivery de mensagens (como domínio temporariamente inacessível). De acordo com o erro retornado pelo provedor, o endereço será enviado diretamente para a quarentena, ou o delivery será tentado novamente até que o Campaign receba um erro que justifique o status Quarantine ou até que o número de erros atinja 5. |
| **[!UICONTROL Address empty]** | Grave | O endereço não está definido. |
| **[!UICONTROL Mailbox full]** | Suave | A caixa de entrada deste usuário está cheia e não pode receber mais mensagens. Esse endereço pode ser removido da lista da quarentena para outra tentativa. Ele será removido automaticamente após 30 dias. Para que o endereço seja removido automaticamente da lista de endereços em quarentena, o workflow técnico de **[!UICONTROL Database cleanup]** deve ser iniciado. |
| **[!UICONTROL Refused]** | Suave/Grave | O endereço foi colocado em quarentena devido a um feedback de segurança como um relatório de spam. De acordo com o erro retornado pelo provedor, o endereço será enviado diretamente para a quarentena, ou o delivery será tentado novamente até que o Campaign receba um erro que justifique o status Quarantine ou até que o número de erros atinja 5. |
| **[!UICONTROL Duplicate]** | Ignorado | O endereço já foi detectado na segmentação. |
| **[!UICONTROL Not defined]** | Suave | o endereço está em qualificação porque os erros não foram aumentados. | ainda. Esse tipo de erro ocorre quando uma nova mensagem de erro é enviada pelo servidor: pode ser um erro isolado, mas se ocorrer novamente, o contador de erros aumentará, o que alertará as equipes técnicas. |
| **[!UICONTROL Error ignored]** | Ignorado | O endereço está em lista de permissões e um email será enviado para ele em qualquer caso. |
| **[!UICONTROL Address on denylist]** | Grave | O endereço foi adicionado à lista de bloqueios no momento do envio. |
| **[!UICONTROL Account disabled]** | Suave/Grave | Quando o Provedor de Acesso à Internet (IAP) detecta um longo período de inatividade, ele pode fechar a conta do usuário: os deliveries ao endereço do usuário serão impossíveis. O tipo Temporário ou Permanente depende do tipo de erro recebido: se a conta estiver temporariamente desativada devido a seis meses de inatividade e ainda puder ser ativada, o status **[!UICONTROL Erroneous]** será atribuído, e o delivery será repetido. Se o erro indicar que a conta está desativada permanentemente, ela será enviada diretamente para Quarentena. |
| **[!UICONTROL Not connected]** | Ignorado | O telefone celular do perfil está desligado ou não está conectado à rede quando a mensagem é enviada. |
| **[!UICONTROL Invalid domain]** | Suave | O domínio do endereço de email está incorreto ou não existe mais. Este perfil será alvo novamente até que a contagem de erros chegue a 5. Após isso, o registro será definido como Status de Quarentena e não haverá nenhuma tentativa nova. |
| **[!UICONTROL Text too long]** | Ignorado | O número de caracteres na mensagem SMS excede o limite. Para obter mais informações, consulte [Codificação, comprimento e transliteração de SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration). |
| **[!UICONTROL Character not supported by encoding]** | Ignorado | A mensagem SMS contém um ou mais caracteres que não são compatíveis pela codificação. Para obter mais informações, consulte [Tabela de caracteres - GSM padrão](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard). |


**Tópicos relacionados:**
* [Devoluções permanentes](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces)
* [Devoluções temporárias](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#soft-bounces)

## Tentativas após uma falha temporária de delivery {#retries-after-a-delivery-temporary-failure}

Se uma mensagem falhar devido a um erro temporário do tipo **Ignorado**, as tentativas serão executadas durante a duração do delivery. Para obter mais informações sobre os tipos de erros, consulte [Tipos e motivos de falha de delivery](#delivery-failure-types-and-reasons).

O número de tentativas (quantas tentativas devem ser executadas no dia seguinte ao início do envio) e o atraso mínimo entre as tentativas agora são<!--managed by the Adobe Campaign Enhanced MTA,--> com base no desempenho histórico e atual de um IP em um determinado domínio. As configurações de **Tentativas** no Campaign são ignoradas.

<!--Please note that Adobe Campaign Enhanced MTA is not available for the Push channel.-->

Para modificar a duração de um delivery, vá para os parâmetros avançados do delivery ou do template do delivery e edite o campo **[!UICONTROL Delivery duration]** da seção [Validity period](../../administration/using/configuring-email-channel.md#validity-period-parameters).

>[!IMPORTANT]
>
>**O parâmetro **[!UICONTROL Delivery duration]**nos deliveries do Campaign agora apenas será usado se definido para 3,5 dias ou menos.** Se você definir um valor superior a 3,5 dias, ele não será considerado.

Por exemplo, se você quiser que as tentativas de um delivery parem depois de um dia, poderá definir a duração do delivery como **1d**, e as mensagens na fila de tentativas serão removidas após um dia.

>[!NOTE]
>
>Quando uma mensagem estiver na fila de tentativas por um máximo de 3,5 dias e não for entregue, o tempo limite expirará, e seu status será atualizado<!--from **[!UICONTROL Sent]**--> para **[!UICONTROL Failed]** nos [logs do delivery](../../sending/using/monitoring-a-delivery.md#delivery-logs).

<!--MOVED TO configuring-email-channel.md > LEGACY SETTINGS
The default configuration allows five retries at one-hour intervals, followed by one retry per day for four days. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).-->

## Erros síncronos e assíncronos {#synchronous-and-asynchronous-errors}

Um delivery pode falhar imediatamente (erro síncrono), ou posteriormente, após ser enviado (erro assíncrono).

* **Erro síncrono**: o servidor remoto contatado pelo servidor de entrega do Adobe Campaign retornou imediatamente uma mensagem de erro, o delivery não tem permissão para ser enviado ao servidor do perfil.
* **Erro assíncrono**: um email de devolução ou um Relatório de Status foi reenviado posteriormente pelo servidor receptor. Podem ocorrer erros assíncronos até uma semana depois do envio.

## Qualificação de email de rejeição {#bounce-mail-qualification}

Para mensagens de erro de falha síncrona de delivery, o MTA aprimorado do Adobe Campaign (Message Transfer Agent) determina o tipo de rejeição e a qualificação e envia essas informações para o Campaign.

>[!NOTE]
>
>As qualificações de rejeição na tabela **[!UICONTROL Message qualification]** do Campaign não são mais usadas.

As rejeições assíncronas ainda são qualificadas pelo processo do InMail por meio das regras **[!UICONTROL Inbound email]**. Para acessar essas regras, clique no logotipo **[!UICONTROL Adobe Campaign]**, na parte superior esquerda, selecione **[!UICONTROL Administration > Channels > Email > Email processing rules]** e depois selecione **[!UICONTROL Bounce mails]**. Para obter mais informações sobre essa regra, consulte [esta seção](../../administration/using/configuring-email-channel.md#email-processing-rules).

Para obter mais informações sobre devoluções e os diferentes tipos de devoluções, consulte [esta seção](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#metrics-for-deliverability).

<!--MOVED TO configuring-email-channel.md > LEGACY SETTINGS

Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## Otimização da capacidade de fornecimento de email com o mecanismo de participação dupla {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

O mecanismo de participação dupla é uma prática recomendada para enviar emails. Ele protege a plataforma contra endereços de email incorretos ou inválidos e spambots, além de evitar possíveis reclamações de spam.

O princípio é enviar um email para confirmar o contrato do visitante antes de armazená-lo como &quot;perfis&quot; no banco de dados do Campaign: o visitante preenche uma landing page online, recebe um email e precisa clicar no link de confirmação para finalizar a assinatura.

Para obter mais informações, consulte [esta seção](../../channels/using/setting-up-a-double-opt-in-process.md).
