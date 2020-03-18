---
title: Noções básicas sobre gestão de quarentena
description: Saiba como otimizar sua capacidade de entrega com o gerenciamento de quarentena.
page-status-flag: never-activated
uuid: 3c287865-1ada-4351-b205-51807ff9f7ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: de3a50b6-ea8f-4521-996b-c49cc1f3c946
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7e361d10d039718c421a3684c518347af2be951

---


# Noções básicas sobre gestão de quarentena{#understanding-quarantine-management}

## Sobre a quarentena {#about-quarantines}

Um endereço de email ou um número de telefone podem ser colocados em quarentena, por exemplo, quando a caixa de correio está cheia ou se o endereço não existe.

In any case, the quarantine procedure complies with specific rules described in this [section](#conditions-for-sending-an-address-to-quarantine).

### Otimização do seu delivery por meio da quarentena {#optimizing-your-delivery-through-quarantines}

The profiles whose email addresses or phone number are in quarantine are automatically excluded during message preparation (see [Identifying quarantined addresses for a delivery](#identifying-quarantined-addresses-for-a-delivery)). Isso irá acelerar os deliveries, pois a taxa de erro tem um efeito significativo na velocidade do delivery.

Alguns provedores de acesso à Internet consideram automaticamente emails como spam se a taxa de endereços inválidos for muito alta. A quarentena permite evitar a inclusão na blacklist por esses provedores.

Além disso, a quarentena ajuda a reduzir os custos de envio do SMS, excluindo números de telefone incorretos dos deliveries.

Para obter mais informações sobre as práticas recomendadas para proteger e otimizar seus deliveries, consulte [esta página](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).

### Quarentena versus blacklist {#quarantine-vs-blacklisting}

A **quarentena** se aplica somente a um endereço, não ao próprio perfil. Isso significa que, se dois perfis tiverem o mesmo endereço de email, eles serão afetados se o endereço estiver em quarentena.

Da mesma forma, um perfil cujo endereço de email está em quarentena poderia atualizar seu perfil e inserir um novo endereço e pode ser alvo de ações de delivery novamente.

A inclusão na **Blacklist**, por outro lado, resultará no perfil não sendo mais alvo por qualquer delivery, por exemplo, depois de unsubscription (recusa). Para obter mais informações sobre o processo de inclusão na lista negra, consulte [Gerenciamento de listas negras no Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!NOTE]
>
>Quando um usuário responde a uma mensagem SMS com uma palavra-chave como &quot;PARAR&quot; para não participar dos deliveries de SMS, seu perfil não é incluído na blacklist como no processo de recusa de email. O número de telefone do perfil é enviado para quarentena com o **[!UICONTROL Blacklisted]** status. Esse status se refere apenas ao número de telefone, o perfil não está na lista negra para que o usuário continue recebendo mensagens de email. Para obter mais informações, consulte [esta seção](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

## Identificação de endereços em quarentena {#identifying-quarantined-addresses}

Os endereços em quarentena podem ser listados para um delivery específico ou para a plataforma inteira.

>[!NOTE]
>
>Se precisar remover um endereço da quarentena, entre em contato com o administrador técnico.

### Identificação de endereços em quarentena para um delivery {#identifying-quarantined-addresses-for-a-delivery}

Quarantined addresses for a specific delivery are listed during the delivery preparation phase, in the **[!UICONTROL Exclusion logs]** tab of the delivery dashboard (see [this section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). For more on delivery preparation, refer to [this section](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Identificação de endereços em quarentena para toda a plataforma {#identifying-quarantined-addresses-for-the-entire-platform}

Os administradores podem listar os endereços em quarentena para a plataforma inteira no **[!UICONTROL Administration > Channels > Quarantines > Addresses]** menu.

>[!NOTE]
>
>Este menu lista os elementos colocados em quarentena para os canais de **email**, **SMS** e **notificação por push** .

![](assets/quarantines1.png)

>[!NOTE]
>
>O aumento no número de quarantinas é um efeito normal, relacionado ao &quot;desgaste&quot; do banco de dados. Por exemplo, se a duração de um endereço de email for considerada como sendo de três anos e a tabela do destinatário aumentar 50% a cada ano, o aumento de quarenta pode ser calculado da seguinte forma: Fim do Ano 1: (1*0.33)/(1+0.5)=22%. Fim do Ano 2: ((1.22*0.33)+0.33)/(1.5+0.75)=32.5%.

## Condições para colocar um endereço na quarentena {#conditions-for-sending-an-address-to-quarantine}

O Adobe Campaign gerencia a quarentena de acordo com o tipo de falha de entrega e o motivo atribuído durante a qualificação de mensagens de erro (consulte Tipos e motivos [de falha de](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) entrega e qualificação [de](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)Rejeição de mensagens).

* **Erro ignorado**: os erros ignorados não enviam um endereço para quarentena.
* **Erro grave**: o endereço de email correspondente é enviado imediatamente para quarentena.
* **Erro suave**: erros suaves não enviam um endereço imediatamente para quarentena, mas incrementam um contador de erros. Quando o contador de erros atinge o limite da cota, o endereço vai para a quarentena. Na configuração padrão, a cota é definida em cinco erros, onde dois erros são significativos se ocorrerem pelo menos em 24 horas de distância. O endereço é colocado em quarentena no quinto erro. O limite do contador de erros pode ser modificado. Para obter mais informações, consulte esta [página](../../administration/using/configuring-email-channel.md#email-channel-parameters).

   Quando um delivery é bem-sucedido após uma tentativa, o contador de erros do endereço anterior à quarentena é reinicializado. The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.

If a user qualifies an email as a spam (**Feedback loop**), the message is automatically redirected towards a technical mailbox managed by Campaign. The user&#39;s email address is then automatically sent to quarantine with the **[!UICONTROL Blacklisted]** status. Esse status se refere apenas ao endereço, o perfil não está na lista negra, de modo que o usuário continua recebendo mensagens SMS e notificações por push.

>[!NOTE]
A quarentena no Adobe Campaign diferencia maiúsculas de minúsculas. Certifique-se de importar endereços de email em letras minúsculas, para que não sejam redirecionados posteriormente.

Na lista de endereços em quarentena (consulte [Identificação de endereços em quarentena para a plataforma](#identifying-quarantined-addresses-for-the-entire-platform)inteira), o **[!UICONTROL Error reason]** campo indica por que o endereço selecionado foi colocado em quarentena.

![](assets/quarantines2.png)

