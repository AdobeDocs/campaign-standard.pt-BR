---
title: Arquivamento de mensagens no Adobe Campaign Standard
description: Saiba como arquivar emails com o Adobe Campaign Standard usando um endereço de email Cco.
page-status-flag: never-activated
uuid: c3721647-0663-4614-a9c9-3b3a40af328a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
discoiquuid: 6fa50f0d-3dcf-4a9e-bccc-1ecda2bfb449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2bf1f8acb581645a6f89f50443a8d9a49d8acaf1

---


# Arquivamento com Cco de email{#archiving-emails}

Você pode configurar o Adobe Campaign para manter uma cópia dos emails enviados da sua plataforma por meio do Email BCC.

Em particular, se sua organização precisar arquivar todas as mensagens de email de saída para fins de conformidade, você poderá habilitar esse recurso. Permite enviar uma cópia oculta exata das mensagens enviadas correspondentes para um endereço de email Cco (invisível para os destinatários da entrega) que você deve especificar.

Depois de habilitado, é necessário ativar a Cco de email a partir da **[!UICONTROL Archive emails]** opção no modelo de entrega de email.

>[!NOTE]
>
>O próprio Adobe Campaign não gerencia arquivos arquivados. Ela permite que você envie as mensagens de sua escolha para um endereço dedicado, de onde elas podem ser processadas e arquivadas usando um sistema externo.

## Recomendações e limitações {#recommendations-and-limitations}

* Este recurso é opcional. Verifique seu contrato de licença e entre em contato com o executivo da sua conta para ativá-lo.
* O endereço Cco de sua escolha deve ser fornecido à equipe da Adobe que o irá configurar para você.
* Você só pode usar um endereço de email Cco.
* Somente emails enviados com êxito são levados em conta. Rejeições não são.
* Por motivos de privacidade, os emails CCO devem ser processados por um sistema de arquivamento capaz de armazenar informações de identificação pessoal (PII) seguras.
* Ao criar um novo modelo de entrega, o Email BCC não é ativado por padrão, mesmo se a opção foi adquirida. Você deve ativá-lo manualmente em cada modelo de entrega em que deseja usá-lo.

>[!NOTE]
>
>Atualmente, os e-mails arquivados não podem ser enviados com o MTA [aprimorado do](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)Adobe Campaign, mesmo se você já tiver atualizado para o MTA aprimorado.

## Ativando o arquivamento de e-mails {#activating-email-archiving}

Depois de ativada, a Cco de email é ativada no modelo [de](../../start/using/marketing-activity-templates.md)email por meio de uma opção dedicada:

1. Go to **Resources** > **Templates** > **Delivery templates**.
1. Duplique o modelo predefinido **[!UICONTROL Send via email]** .
1. Selecione o modelo duplicado.
1. Clique no **[!UICONTROL Edit properties]** botão para editar as propriedades do modelo.
1. Expanda a **[!UICONTROL Send]** seção.
1. Marque a **[!UICONTROL Archive emails]** caixa para manter uma cópia de todas as mensagens enviadas para cada entrega com base neste modelo.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>If the emails sent to the BCC address are opened and clicked through, this will be taken into account in the **[!UICONTROL Total opens]** and **[!UICONTROL Clicks]** from the send analysis, which could cause some miscalculations.