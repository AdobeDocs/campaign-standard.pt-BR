---
title: Noções básicas sobre gestão de quarentena
description: Saiba como otimizar sua capacidade de entrega com o gerenciamento de quarentenas.
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
source-git-commit: 121ec37cef6193d3a7085b6d0296b6a2e7cafa06
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 45%

---


# Noções básicas sobre gestão de quarentena{#understanding-quarantine-management}

## Sobre a quarentena {#about-quarantines}

Um endereço de email ou um número de telefone podem ser colocados em quarentena, por exemplo, quando a caixa de correio está cheia ou se o endereço não existe.

In any case, the quarantine procedure complies with specific rules described in this [section](#conditions-for-sending-an-address-to-quarantine).

### Otimização do seu delivery por meio da quarentena {#optimizing-your-delivery-through-quarantines}

Os perfis cujos endereços de email ou número de telefone estão em quarentena são excluídos automaticamente durante a preparação da mensagem (consulte [Identificação de endereços em quarentena para um delivery](#identifying-quarantined-addresses-for-a-delivery)). Isso irá acelerar os deliveries, pois a taxa de erro tem um efeito significativo na velocidade do delivery.

Alguns provedores de acesso à Internet consideram automaticamente emails como spam se a taxa de endereços inválidos for muito alta. A Quarentena, portanto, permite evitar que você seja adicionado a uma lista de blocos por esses provedores.

Além disso, a quarentena ajuda a reduzir os custos de envio do SMS, excluindo números de telefone incorretos dos deliveries.

Para obter mais informações sobre as práticas recomendadas para proteger e otimizar seus deliveries, consulte [esta página](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).

### Quarentena vs lista de blocos {#quarantine-vs-block-list}

A **quarentena** se aplica somente a um endereço, não ao próprio perfil. Isso significa que, se dois perfis tiverem o mesmo endereço de email, eles serão afetados se o endereço estiver em quarentena.

Da mesma forma, um perfil cujo endereço de email está em quarentena poderia atualizar seu perfil e inserir um novo endereço e pode ser alvo de ações de delivery novamente.

Being on the **block list**, on the other hand, will result in the profile no longer being targeted by any delivery, for example after an unsubscription (opt-out). Para obter mais informações sobre o processo de lista de blocos, consulte [Sobre aceitação e não participação na Campanha](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!NOTE]
>
>Quando um usuário responde a uma mensagem SMS com uma palavra-chave como &quot;PARAR&quot; para recusar delivery SMS, seu perfil não é adicionado à lista de bloqueios como no processo de recusa por email. O número de telefone do perfil é enviado para a quarentena com o **[!UICONTROL On block list]** status. Esse status se refere apenas ao número de telefone, o perfil não está na lista de bloqueios para que o usuário continue recebendo mensagens de email. Para obter mais informações, consulte [esta seção](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

## Identificação de endereços em quarentena {#identifying-quarantined-addresses}

Os endereços em quarentena podem ser listados para um delivery específico ou para a plataforma inteira.

>[!NOTE]
>
>Se precisar remover um endereço da quarentena, entre em contato com o administrador técnico.

### Identificação de endereços em quarentena para um delivery {#identifying-quarantined-addresses-for-a-delivery}

Quarantined addresses for a specific delivery are listed during the delivery preparation phase, in the **[!UICONTROL Exclusion logs]** tab of the delivery dashboard (see [this section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). For more on delivery preparation, refer to [this section](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Identificação de endereços em quarentena para toda a plataforma {#identifying-quarantined-addresses-for-the-entire-platform}

Administrators can list the addresses in quarantine for the entire platform from the **[!UICONTROL Administration > Channels > Quarantines > Addresses]** menu.

>[!NOTE]
>
>Este menu lista os elementos colocados em quarentena para os canais de **email**, **SMS** e **notificação por push** .

![](assets/quarantines1.png)

>[!NOTE]
>
>O aumento no número de quarentenas é um efeito normal, relacionado ao &quot;desgaste&quot; do banco de dados. Por exemplo, se a duração de um endereço de email for considerada de três anos e a tabela do recipient aumentar 50% a cada ano, o aumento nas quarentenas pode ser calculado da seguinte forma: Fim do Ano 1: (1*0.33)/(1+0.5)=22%. Fim do Ano 2: ((1.22*0.33)+0.33)/(1.5+0.75)=32.5%.

## Condições para colocar um endereço na quarentena {#conditions-for-sending-an-address-to-quarantine}

O Adobe Campaign gerencia a quarentena de acordo com o tipo de falha do delivery e o motivo atribuído durante a qualificação de mensagens de erro (consulte Tipos e motivos [de falha do](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) Delivery e qualificação [de](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)Rejeição de mensagens).

* **Erro ignorado**: os erros ignorados não enviam um endereço para quarentena.
* **Erro grave**: o endereço de email correspondente é enviado imediatamente para quarentena.
* **Erro suave**: erros suaves não enviam um endereço imediatamente para quarentena, mas incrementam um contador de erros. Quando o contador de erros atinge o limite da cota, o endereço vai para a quarentena. Na configuração padrão, a cota é definida em cinco erros, onde dois erros são significativos se ocorrerem pelo menos em 24 horas de distância. O endereço é colocado em quarentena no quinto erro. O limite do contador de erros pode ser modificado. Para obter mais informações, consulte esta [página](../../administration/using/configuring-email-channel.md#email-channel-parameters).

   Quando um delivery é bem-sucedido após uma tentativa, o contador de erros do endereço anterior à quarentena é reinicializado. The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.

If a user qualifies an email as a spam (**Feedback loop**), the message is automatically redirected towards a technical mailbox managed by Campaign. The user&#39;s email address is then automatically sent to quarantine with the **[!UICONTROL On block list]** status. Esse status se refere apenas ao endereço, o perfil não está na lista de blocos, de modo que o usuário continua recebendo mensagens SMS e notificações por push.

>[!NOTE]
A quarentena no Adobe Campaign diferencia maiúsculas de minúsculas. Certifique-se de importar endereços de email em letras minúsculas, para que não sejam redirecionados posteriormente.

Na lista de endereços em quarentena (consulte [Identificação de endereços em quarentena para a plataforma](#identifying-quarantined-addresses-for-the-entire-platform)inteira), o **[!UICONTROL Error reason]** campo indica por que o endereço selecionado foi colocado na quarentena.

![](assets/quarantines2.png)

