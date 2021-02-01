---
solution: Campaign Standard
product: campaign
title: Arquivamento de mensagens no Adobe Campaign Standard
description: Saiba como arquivar emails com a Adobe Campaign Standard usando um endereço de email Cco.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
translation-type: tm+mt
source-git-commit: 0f057375e5cd63605af460f08cd39bed00435184
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 16%

---


# Arquivamento com email Cco{#archiving-emails}

Você pode configurar a Adobe Campaign para manter uma cópia dos emails enviados de sua plataforma por meio do Email BCC.

Em particular, se sua organização precisar arquivar todas as mensagens de email de saída para fins de conformidade, você poderá habilitar esse recurso. Ele permite enviar uma cópia oculta exata das mensagens enviadas correspondentes para um endereço de email Cco (invisível aos recipient do delivery) que você deve especificar.

Depois de habilitado, é necessário ativar o Email BCC na opção **[!UICONTROL Archive emails]** no template do delivery de email.

>[!NOTE]
>
>A própria Adobe Campaign não gerencia arquivos arquivados. Ela permite que você envie as mensagens de sua escolha para um endereço dedicado, de onde elas podem ser processadas e arquivadas usando um sistema externo.

## Recommendations e limitações {#recommendations-and-limitations}

* Este recurso é opcional. Verifique seu contrato de licença e entre em contato com o executivo da sua conta para ativá-lo.
* O endereço CCO de sua escolha deve ser fornecido à equipe do Adobe que o configurará para você.
* Você só pode usar um endereço de email Cco.
* Somente emails enviados com êxito são levados em conta. Rejeições não são.
* Por motivos de privacidade, os emails CCO devem ser processados por um sistema de arquivamento capaz de armazenar informações de identificação pessoal (PII) seguras.
* Ao criar um novo template do delivery, a Cco de email não é ativada por padrão, mesmo que a opção tenha sido adquirida. Você deve ativá-lo manualmente em cada template do delivery em que deseja usá-lo.

>[!NOTE]
>
>Atualmente, os e-mails arquivados não podem ser enviados com o Adobe Campaign Enhanced MTA.

## Ativando o arquivamento de e-mails {#activating-email-archiving}

Depois de ativada, a CCO de email é ativada no [modelo de email](../../start/using/marketing-activity-templates.md), por meio de uma opção dedicada:

1. Acesse **Resources** > **Templates** > **Delivery templates**.
1. Duplicado o modelo predefinido **[!UICONTROL Send via email]**.
1. Selecione o modelo duplicado.
1. Clique no botão **[!UICONTROL Edit properties]** para editar as propriedades do modelo.
1. Expanda a seção **[!UICONTROL Send]**.
1. Marque a caixa **[!UICONTROL Archive emails]** para manter uma cópia de todas as mensagens enviadas para cada delivery com base neste modelo.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>Se os emails enviados para o endereço CCo forem abertos e clicados, isso será considerado no **[!UICONTROL Total opens]** e **[!UICONTROL Clicks]** da análise de envio, o que poderá causar alguns erros de cálculo.