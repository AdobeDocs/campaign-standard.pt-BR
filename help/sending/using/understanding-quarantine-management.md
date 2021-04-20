---
solution: Campaign Standard
product: campaign
title: Noções básicas sobre gestão de quarentena
description: Saiba como otimizar sua capacidade de delivery com o gerenciamento de quarentenas.
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Deliverability
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 83%

---


# Noções básicas sobre gestão de quarentena{#understanding-quarantine-management}

## Sobre a quarentena {#about-quarantines}

Um endereço de email pode ser colocado em quarentena, por exemplo, quando a caixa de entrada estiver cheia ou se o endereço não existir.

Em qualquer caso, o procedimento de quarentena está em conformidade com as regras específicas descritas nesta [seção](#conditions-for-sending-an-address-to-quarantine).

### Otimização do seu delivery por meio da quarentena {#optimizing-your-delivery-through-quarantines}

Os perfis cujos endereços de email ou número de telefone estão em quarentena são excluídos automaticamente durante a preparação da mensagem (consulte [Identificação de endereços em quarentena para um delivery](#identifying-quarantined-addresses-for-a-delivery)). Isso irá acelerar os deliveries, pois a taxa de erro tem um efeito significativo na velocidade do delivery.

Alguns provedores de acesso à Internet consideram automaticamente emails como spam se a taxa de endereços inválidos for muito alta. A quarentena, portanto, evita que você seja adicionado à lista de bloqueios por esses provedores.

Além disso, a quarentena ajuda a reduzir os custos de envio de SMS, excluindo números de telefone incorretos dos deliveries.

Para obter mais informações sobre as práticas recomendadas para proteger e otimizar seus deliveries, consulte [esta página](../../sending/using/delivery-best-practices.md).

### Quarentena versus Lista de bloqueios {#quarantine-vs-denylist}

A **quarentena** se aplica somente a um endereço, não ao próprio perfil. Isso significa que, se dois perfis tiverem o mesmo endereço de email, eles serão afetados se o endereço estiver em quarentena.

Da mesma forma, um perfil cujo endereço de email está em quarentena poderia atualizar seu perfil e inserir um novo endereço e pode ser alvo de ações de delivery novamente.

Por outro lado, com a **Lista de bloqueios**, o perfil não será mais alvo de qualquer delivery, por exemplo, depois da unsubscription (recusa). Para obter mais informações sobre o processo de  de lista de bloqueios, consulte [Sobre participação e não participação no Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!NOTE]
>
>Quando um usuário responde a uma mensagem SMS com uma palavra-chave, como &quot;PARAR&quot;, para recusar os deliveries de SMS, seu perfil não está em lista de bloqueios, como no processo de recusa de email. O número de telefone do perfil é enviado para a quarentena com o status **[!UICONTROL On denylist]**. Esse status se refere apenas ao número de telefone. O perfil não está lista de bloqueios para que o usuário continue recebendo mensagens de email. Para obter mais informações, consulte [esta seção](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

## Identificação de endereços em quarentena {#identifying-quarantined-addresses}

Os endereços em quarentena podem ser listados para um delivery específico ou para a plataforma inteira.

>[!NOTE]
>
>Se precisar remover um endereço da quarentena, entre em contato com o administrador técnico.

### Identificação de endereços em quarentena para um delivery {#identifying-quarantined-addresses-for-a-delivery}

Os endereços em quarentena para um delivery específico são listados durante a fase de preparação do delivery, na guia **[!UICONTROL Exclusion logs]** do painel de delivery (consulte [esta seção](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). Para saber mais sobre a preparação de deliveries, consulte [esta seção](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Identificação de endereços em quarentena para toda a plataforma {#identifying-quarantined-addresses-for-the-entire-platform}

Os administradores podem listar os endereços em quarentena para toda a plataforma do menu **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.

>[!NOTE]
>
>Esse menu lista os elementos em quarentena para os canais de **email**, **SMS** e **notificação por push**.

![](assets/quarantines1.png)

>[!NOTE]
>
>O aumento no número de quarentenas é um efeito normal relacionado ao “desgaste” do banco de dados. Por exemplo, se o tempo de vida de um endereço de email for de três anos e a tabela de recipients aumentar em 50% todo ano, o aumento nas quarentenas poderá ser calculado da seguinte maneira: Fim do ano 1: (1*0,33)/(1+0,5)=22%. Fim do ano 2: ((1,22*0,33)+0,33)/(1,5+0,75)=32,5%.

## Condições para enviar um endereço para quarentena {#conditions-for-sending-an-address-to-quarantine}

O Adobe Campaign gerencia a quarentena de acordo com o tipo de falha do delivery e o motivo atribuído durante a qualificação das mensagens de erro (consulte [Tipos e motivos de falha do delivery](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) e [Qualificação do email de rejeição](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)).

* **Erro ignorado**: os erros ignorados não enviam um endereço para quarentena.
* **Erro grave**: o endereço de email correspondente é enviado imediatamente para quarentena.
* **Erro suave**: erros suaves não enviam um endereço imediatamente para quarentena, mas incrementam um contador de erros. Quando o contador de erros atinge o limite da cota, o endereço vai para a quarentena. Na configuração padrão, a cota é definida em cinco erros, onde dois erros são significativos se ocorrerem pelo menos em 24 horas de distância. O endereço é colocado em quarentena no quinto erro. O limite do contador de erros pode ser modificado. Para obter mais informações, consulte esta [página](../../administration/using/configuring-email-channel.md#email-channel-parameters).

   Quando um delivery é bem-sucedido após uma tentativa, o contador de erros do endereço anterior à quarentena é reinicializado. O status do endereço é alterado para **[!UICONTROL Valid]** e excluído da lista de quarentenas após dois dias pelo fluxo de trabalho **[!UICONTROL Database cleanup]**.

Se um usuário qualificar um email como spam (**Loop de feedback**), a mensagem será automaticamente redirecionada para uma caixa de entrada técnica gerenciada pelo Campaign. Em seguida, o endereço de email do usuário será enviado automaticamente para quarentena com o status **[!UICONTROL On denylist]**. Esse status se refere somente ao endereço, o perfil não está na lista de bloqueios, portanto, o usuário continua recebendo mensagens SMS e notificações por push.

>[!NOTE]
A quarentena no Adobe Campaign diferencia maiúsculas de minúsculas. Certifique-se de importar endereços de email em letras minúsculas, para que não sejam redirecionados posteriormente.

Na lista de endereços em quarentena (consulte [Identificação de endereços em quarentena para toda a plataforma](#identifying-quarantined-addresses-for-the-entire-platform)), o campo **[!UICONTROL Error reason]** indica por que o endereço selecionado foi colocado em quarentena.

![](assets/quarantines2.png)

