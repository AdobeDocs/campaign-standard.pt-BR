---
title: Noções básicas sobre o gerenciamento de quarentena
seo-title: Noções básicas sobre o gerenciamento de quarentena
description: Noções básicas sobre o gerenciamento de quarentena
seo-description: Saiba como otimizar sua entregabilidade com o gerenciamento de quarentena.
page-status-flag: nunca ativado
uuid: 3 c 287865-1 ado -4351-b 205-51807 ff 9 f 7 ed
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviando
content-type: reference
topic-tags: monitoramento-mensagens
discoiquuid: de 3 a 50 b 6-ea 8 f -4521-996 b-c 49 cc 1 f 3 c 946
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5b3ea982f08e1198e8c88f78a5faf8a80b935db4

---


# Understanding quarantine management{#understanding-quarantine-management}

## About quarantines {#about-quarantines}

Um endereço de email ou um número de telefone pode ser cercado, por exemplo, quando a caixa de entrada está cheia ou se o endereço não existe.

In any case, the quarantine procedure complies with specific rules described in this [section](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).

### Optimizing your delivery through quarantines {#optimizing-your-delivery-through-quarantines}

The profiles whose email addresses or phone number are in quarantine are automatically excluded during message preparation (see [Identifying quarantined addresses for a delivery](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-a-delivery)). Isso agiliza as entregas, pois a taxa de erro tem um efeito significativo na velocidade de entrega.

Alguns provedores de acesso à Internet consideram os emails como spam para serem spam se a taxa de endereços inválidos for muito alta. Dessa forma, a quarentena permite evitar a lista negra desses provedores.

Além disso, as quarentena ajudam a reduzir os custos de envio de SMS, excluindo números de telefone incorretos das entregas.

For more on best practices to secure and optimize your deliveries, refer to [this page](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).

### Quarantine vs blacklisting {#quarantine-vs-blacklisting}

**A quarentena** se aplica somente a um endereço, não ao próprio perfil. Isso significa que, se dois perfis tiverem o mesmo endereço de email, ambos serão afetados se o endereço estiver em quarentena.

Da mesma forma, um perfil cujo endereço de email é armazenado pode atualizar seu perfil e inserir um novo endereço, e pode ser direcionado para ações de entrega novamente.

**Por outro lado, a lista negra** resultará no perfil não sendo mais direcionado por qualquer entrega, por exemplo, após uma cancelação de assinatura (rejeitar). For more on the blacklisting process, refer to [Managing blacklisting in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!NOTE]
>
>Quando um usuário responde a uma mensagem SMS com uma palavra-chave como "STOP" para excluir entregas SMS, seu perfil não é listado como no processo de não participação por email. The profile phone number is sent to quarantine with the **[!UICONTROL Blacklisted]** status. Esse status se refere somente ao número de telefone, o perfil não é lista negra para que o usuário continue recebendo mensagens de email. For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

## Identifying quarantined addresses {#identifying-quarantined-addresses}

Os endereços em quarentena podem ser listados para uma entrega específica ou para a plataforma inteira.

>[!NOTE]
>
>Se precisar remover um endereço da quarentena, entre em contato com o administrador técnico.

### Identifying quarantined addresses for a delivery {#identifying-quarantined-addresses-for-a-delivery}

Quarantined addresses for a specific delivery are listed during the delivery preparation phase, in the **[!UICONTROL Exclusion logs]** tab of the delivery dashboard (see [this section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). For more on delivery preparation, refer to [this section](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Identifying quarantined addresses for the entire platform {#identifying-quarantined-addresses-for-the-entire-platform}

Administrators can list the addresses in quarantine for the entire platform from the **[!UICONTROL Administration > Channels > Quarantines > Addresses]** menu.

>[!NOTE]
>
>This menu lists quarantined elements for **email**, **SMS** and **Push notification** channels.

![](assets/quarantines1.png)

>[!NOTE]
>
>O aumento em número de quarentena é um efeito normal, relacionado ao "deslocamento e ao tear" do banco de dados. Por exemplo, se a duração de um endereço de email for considerada como três anos e a tabela do destinatário aumentar por 50% a cada ano, o aumento em quarentena pode ser calculado da seguinte maneira: Fim do ano 1: (1 * 0.33)/(1+0.5) = 22%. Fim do ano 2: ((1.22 * 0.33) +0.33)/(1.5+0.75) = 32.5%.

## Conditions for sending an address to quarantine {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign manages quarantine according to the delivery failure type and the reason assigned during error messages qualification (see [Delivery failure types and reasons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) and [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)).

* **Erro ignorado**: os erros ignorados não enviam um endereço para quarentena.
* **Erro grave**: o endereço de email correspondente é enviado imediatamente para quarentena.
* **Erro condicional**: erros de ortografia não enviam imediatamente um endereço para quarentena, mas incrementam um contador de erro. Quando o contador de erro atinge o limite de limite, o endereço entra em quarentena. Na configuração padrão, o limite é definido em cinco erros, onde dois erros são significativos se ocorrer pelo menos 24 horas entre si. O endereço é colocado em quarentena no sexto erro. O limite de contador de erro pode ser modificado. For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).

   Quando uma entrega é bem-sucedida após uma tentativa, o contador de erro do endereço que estava antes daquela quarentena é reinicializado. The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.

If a user qualifies an email as a spam (**Feedback loop**), the message is automatically redirected towards a technical mailbox managed by Campaign. The user's email address is then automatically sent to quarantine with the **[!UICONTROL Blacklisted]** status. Esse status se refere somente ao endereço, o perfil não é lista negra, para que o usuário continue recebendo mensagens SMS e notificações por push.

>[!NOTE]
A quarentena no Adobe Campaign diferencia maiúsculas e minúsculas. Certifique-se de importar endereços de email em letras minúsculas para que não sejam redirecionados posteriormente.

In the list of quarantined addresses (see [Identifying quarantined addresses for the entire platform](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)), the **[!UICONTROL Error reason]** field indicates why the selected address was placed in quarantine.

![](assets/quarantines2.png)

