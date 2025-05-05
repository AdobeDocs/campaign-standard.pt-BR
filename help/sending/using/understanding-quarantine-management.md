---
title: Noções básicas sobre gestão de quarentena
description: Saiba como otimizar sua capacidade de entrega com o gerenciamento de quarentenas.
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Deliverability
role: User
level: Intermediate
exl-id: ed269751-78ab-4189-89d9-116bf42c0c90
source-git-commit: 449187bba167f9ce00e644d44a124b36030ba001
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 64%

---

# Compreensão do gerenciamento de quarentena{#understanding-quarantine-management}

## Sobre quarentenas {#about-quarantines}

Um endereço de email pode ser colocado em quarentena, por exemplo, quando a caixa de entrada estiver cheia ou se o endereço não existir.

Em qualquer caso, o procedimento de quarentena está em conformidade com as regras específicas descritas nesta [seção](#conditions-for-sending-an-address-to-quarantine).

### Otimização de sua entrega por meio de quarentenas {#optimizing-your-delivery-through-quarantines}

Os perfis cujos endereços de email ou número de telefone estão em quarentena são excluídos automaticamente durante a preparação da mensagem (consulte [Identificação de endereços em quarentena para uma entrega](#identifying-quarantined-addresses-for-a-delivery)). Isso irá acelerar as entregas, pois a taxa de erro tem um efeito significativo na velocidade da entrega.

Alguns provedores de acesso à Internet consideram automaticamente emails como spam se a taxa de endereços inválidos é muito alta. A quarentena, portanto, evita que você seja adicionado à lista de bloqueios por esses provedores.

Além disso, a quarentena ajuda a reduzir os custos de envio de SMS, excluindo números de telefone incorretos das entregas.

Para obter mais informações sobre as práticas recomendadas para proteger e otimizar suas entregas, consulte [esta página](../../sending/using/delivery-best-practices.md).

### Quarentena versus Inclui na lista de bloqueios {#quarantine-vs-denylist}

A quarentena e a lista de bloqueios não se aplicam ao mesmo objeto:

* A **quarentena** se aplica somente a um **endereço** (ou número de telefone etc.), não ao próprio perfil. Por exemplo, um perfil cujo endereço de email esteja em quarentena poderia atualizar seu perfil e inserir um novo endereço, podendo então ser alvo de ações de delivery novamente. Da mesma forma, se dois perfis tiverem o mesmo número de telefone, ambos serão afetados se o número estiver em quarentena.

  Os endereços em quarentena ou os números de telefone são exibidos nos [logs de exclusão](#identifying-quarantined-addresses-for-a-delivery) (para uma entrega) ou na [lista de quarentena](#identifying-quarantined-addresses-for-the-entire-platform) (para toda a plataforma).

* Por outro lado, com a inclusão na **lista de bloqueios**, o **perfil** não será mais direcionado pela entrega, por exemplo, depois de um cancelamento de inscrição (recusa de participação) de um determinado canal. Incluir na lista de bloqueios Por exemplo, se um perfil no canal tiver dois endereços de email, ambos os endereços serão excluídos do delivery. Para obter mais informações sobre o processo de inclui na lista de bloqueios, consulte [Sobre participação e não participação no Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

  Você pode verificar se um perfil está na lista de bloqueios de um ou mais canais na seção **[!UICONTROL No longer contact (on denylist)]** da guia **[!UICONTROL General]** do perfil. Consulte [esta seção](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

>[!NOTE]
>
>A quarentena inclui um status **Em inclui na lista de bloqueios**, que se aplica quando os recipients marcam sua mensagem como spam ou respondem a uma mensagem SMS com uma palavra-chave como &quot;PARAR&quot;. Nesse caso, o endereço do perfil envolvido ou o número de telefone é enviado para quarentena com o status **[!UICONTROL On denylist]**. Para obter mais informações sobre como gerenciar mensagens SMS PARAR, consulte [esta seção](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

&lt;!—Quando um usuário responde a uma mensagem SMS com uma palavra-chave, como PARAR, para recusar os deliveries de SMS, seu perfil não é adicionado à inclui na lista de bloqueios, como no processo de recusa de email. Em vez disso, o número de telefone do perfil é enviado para quarentena com o status **[!UICONTROL On denylist]**. Este status se refere apenas ao número de telefone, o que significa que o perfil continuará recebendo mensagens de email.<!-- Also, if the profile has another phone number, he can still receive SMS messages on the other number. For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).-->

## Identificação de endereços em quarentena {#identifying-quarantined-addresses}

Os endereços em quarentena podem ser exibidos para um delivery específico ou para a plataforma inteira.

<!--
If you need to remove an address from quarantine, contact your technical administrator.
-->

### Identificação de endereços em quarentena para uma entrega {#identifying-quarantined-addresses-for-a-delivery}

Os endereços em quarentena para uma entrega específica são listados durante a fase de preparação da entrega, na guia **[!UICONTROL Exclusion logs]** do painel de entrega (consulte [esta seção](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). Para saber mais sobre a preparação de entregas, consulte [esta seção](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Identificação de endereços em quarentena para toda a plataforma {#identifying-quarantined-addresses-for-the-entire-platform}

Os administradores podem acessar a lista detalhada dos endereços de email em quarentena para toda a plataforma do menu **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.

<!--
This menu lists quarantined elements for **Email**, **SMS** and **Push notification** channels.
-->

![](assets/quarantines1.png)

>[!NOTE]
>
>O aumento no número de quarentenas é um efeito normal relacionado ao &quot;desgaste&quot; do banco de dados. Por exemplo, se o tempo de vida de um endereço de email for de três anos e a tabela de recipients aumentar em 50% todo ano, o aumento nas quarentenas poderá ser calculado da seguinte maneira: Fim do ano 1: (1&#42;0.33)/(1+0.5)=22%. Fim do ano 2: ((1,22&#42;0,33)+0,33)/(1,5+0,75)=32,5%.

Os filtros estão disponíveis para ajudá-lo a navegar pela lista. Você pode filtrar pelo endereço, status e/ou canal.

![](assets/quarantines-filters.png)

Você pode editar ou [excluir](#removing-a-quarantined-address) cada entrada, bem como criar novas entradas.

Para editar uma entrada, clique na linha correspondente e modifique os campos conforme necessário.

![](assets/quarantines-edit.png)

Para adicionar uma nova entrada manualmente, use o botão **[!UICONTROL Create]**.

![](assets/quarantines-create-button.png)

Defina o endereço (ou número de telefone etc.) e tipo de canal. Você pode definir um status para estar na lista da quarentena e um motivo de erro. Você também pode indicar a data em que o erro ocorreu, o número de erros e inserir o texto do erro. Se necessário, selecione o último delivery que foi enviado para o endereço na lista suspensa.

![](assets/quarantines-create-last-delivery.png)

## Remoção de um endereço da quarentena {#removing-a-quarantined-address}

### Atualizações automáticas {#unquarantine-auto}

Os endereços que correspondem a condições específicas são excluídos automaticamente da lista de quarentena pelo workflow de limpeza do banco de dados. Saiba mais sobre fluxos de trabalho técnicos, consulte [esta seção](../../administration/using/technical-workflows.md#list-of-technical-workflows).

Os endereços são removidos automaticamente da lista de quarentena nos seguintes casos:

* Os endereços em um status **[!UICONTROL Erroneous]** serão removidos da lista de quarentena após uma entrega bem-sucedida.
* Os endereços em um status **[!UICONTROL Erroneous]** serão removidos da lista de quarentena se o último retorno de erro tiver ocorrido há mais de 10 dias. Para obter mais informações sobre o gerenciamento de erros de software, consulte [esta seção](#soft-error-management).
* Os endereços em um status **[!UICONTROL Erroneous]** que tiverem retornado com o erro **[!UICONTROL Mailbox full]** serão removidos da lista de quarentena após 30 dias.

O status muda então para **[!UICONTROL Valid]**.

O número máximo de tentativas a serem executadas em caso de status **[!UICONTROL Erroneous]** e o atraso mínimo entre tentativas agora se baseiam no desempenho histórico e atual de um IP em um determinado domínio.


>[!IMPORTANT]
>
>Os destinatários com um endereço em um status **[!UICONTROL Quarantine]** ou **[!UICONTROL Denylisted]** nunca serão removidos, mesmo se receberem um email.


### Atualizações manuais {#unquarantine-manual}

Também é possível cancelar a quarentena de um endereço manualmente.  Para remover manualmente um endereço da lista da quarentena, você pode removê-lo da lista ou alterar seu status para **[!UICONTROL Valid]**.

* Selecione o endereço na lista **[!UICONTROL Administration > Channels > Quarantines > Addresses]** e selecione **[!UICONTROL Delete element]**.

  ![](assets/quarantine-delete-address.png)

* Selecione um endereço e altere seu **[!UICONTROL Status]** para **[!UICONTROL Valid]**.

  ![](assets/quarantine-valid-status.png)


### Atualizações em massa {#unquarantine-bulk}

Talvez seja necessário executar atualizações em massa na lista de quarentena. Por exemplo, no caso de uma interrupção de ISP. Nesse caso, os emails são marcados incorretamente como rejeições porque não podem ser entregues com êxito ao destinatário. Esses endereços devem ser removidos da lista de quarentena.

Para fazer isso, crie um fluxo de trabalho e adicione uma atividade **[!UICONTROL Query]** na tabela de quarentena para filtrar todos os destinatários afetados. Uma vez identificados, eles podem ser removidos da lista de quarentena e incluídos em entregas de email futuros do Campaign.

Com base no período do incidente, abaixo estão as diretrizes recomendadas para esse query.

* **O texto de erro (texto de quarentena)** contém “550-5.1.1” E **o texto de erro (texto de quarentena)** contém “support.ISP.com”,

  onde “support.ISP.com” pode ser “support.apple.com” ou “support.google.com”, por exemplo

* **Atualizar status (@lastModified)** em ou depois de `MM/DD/YYYY HH:MM:SS AM`
* **Atualizar status (@lastModified)** em ou antes de `MM/DD/YYYY HH:MM:SS PM`

Depois de ter a lista de destinatários afetados, adicione uma atividade **[!UICONTROL Update data]** para definir seu status de endereço de email como **[!UICONTROL Valid]** para que eles sejam removidos da lista de quarentena pelo fluxo de trabalho **[!UICONTROL Database cleanup]**. Também é possível excluí-los da tabela de quarentena.

## Condições para enviar um endereço para quarentena {#conditions-for-sending-an-address-to-quarantine}

O Adobe Campaign gerencia a quarentena de acordo com o tipo de falha da entrega e o motivo atribuído durante a qualificação das mensagens de erro (consulte [Tipos e motivos de falha da entrega](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) e [Qualificação do email de rejeição](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)).

* **Erro ignorado**: os erros ignorados não enviam um endereço para quarentena.
* **Erro grave**: o endereço de email correspondente é enviado imediatamente para quarentena.
* **Erro suave**: erros suaves não enviam um endereço imediatamente para quarentena, mas incrementam um contador de erros. Para obter mais informações, consulte [Gerenciamento de erros leves](#soft-error-management).

  <!--
  When the error counter reaches the limit threshold, the address goes into quarantine. In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error. The error counter threshold can be modified. For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).
  When a delivery is successful after a retry, the error counter of the address which was prior to that quarantined is reinitialized. The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.
  -->

Se um usuário qualificar um email como spam ([loop de feedback](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=pt-BR#feedback-loops)), a mensagem será automaticamente redirecionada para uma caixa de entrada técnica gerenciada pela Adobe. Em seguida, o endereço de email do usuário será enviado automaticamente para quarentena com o status **[!UICONTROL On denylist]**. Esse status se refere apenas ao endereço. O perfil não é incluído na lista de bloqueio para que o usuário continue recebendo mensagens SMS e notificações por push.

>[!NOTE]
>
>A quarentena no Adobe Campaign diferencia maiúsculas de minúsculas. Certifique-se de importar endereços de email em letras minúsculas, para que não sejam redirecionados posteriormente.

Na lista de endereços em quarentena (consulte [Identificação de endereços em quarentena para toda a plataforma](#identifying-quarantined-addresses-for-the-entire-platform)), o campo **[!UICONTROL Error reason]** indica por que o endereço selecionado foi colocado em quarentena.

![](assets/quarantines2.png)

### Gerenciamento de erros leves {#soft-error-management}

Ao contrário de erros graves, os erros recuperáveis não enviam um endereço imediatamente para quarentena, mas incrementam um contador de erros.

As tentativas serão executadas no decorrer da [duração da entrega](../../administration/using/configuring-email-channel.md#validity-period-parameters). Quando o contador de erros atinge o limite da cota, o endereço vai para a quarentena. Para obter mais informações, consulte [Tentativas após uma falha temporária de entrega](understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error.
The error counter threshold can be modified.-->

O contador de erros será reinicializado se o último erro significativo ocorrer há mais de 10 dias. O status do endereço é alterado para **Válido** e excluído da lista de quarentenas pelo fluxo de trabalho **Limpeza do banco de dados**. (Para obter mais informações sobre fluxos de trabalho técnicos, consulte [esta seção](../../administration/using/technical-workflows.md#list-of-technical-workflows).)
