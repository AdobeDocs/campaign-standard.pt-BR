---
title: Arquivamento de mensagens no Adobe Campaign Standard
description: Saiba como arquivar emails com o Adobe Campaign Standard usando um endereço de email CCO.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 7bf380d7-195e-413d-b14e-85e78b07ba8b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 16%

---

# Arquivamento com email Cco{#archiving-emails}

Você pode configurar o Adobe Campaign para manter uma cópia dos emails enviados de sua plataforma por meio do Email Cco.

Especificamente, se sua organização precisar arquivar todas as mensagens de e-mail enviadas para fins de conformidade, você poderá ativar esse recurso. Ele permite enviar uma cópia oculta exata das mensagens enviadas correspondentes para um endereço de email CCO (invisível para os recipients do delivery) que você deve especificar.

Depois de habilitado, você precisa ativar Email Cco na opção **[!UICONTROL Archive emails]** no modelo de entrega de email.

>[!NOTE]
>
>O próprio Adobe Campaign não gerencia arquivos arquivados. Ela permite enviar as mensagens de sua escolha para um endereço dedicado, de onde elas podem ser processadas e arquivadas usando um sistema externo.

## Recommendations e limitações {#recommendations-and-limitations}

* Este recurso é opcional. Verifique seu contrato de licença e entre em contato com o executivo da sua conta para ativá-lo.
* O endereço CCO de sua escolha deve ser fornecido à equipe do Adobe que irá configurá-lo para você.
* Você só pode usar um endereço de email CCO.
* Somente emails enviados com êxito são considerados. As rejeições não são.
* Por motivos de privacidade, os emails com CCO devem ser processados por um sistema de arquivamento capaz de armazenar informações de identificação pessoal (PII) seguras.
* Ao criar um novo template do delivery, o Email Cco não é habilitado por padrão, mesmo que a opção tenha sido adquirida. Você deve ativá-lo manualmente em cada template do delivery onde deseja usá-lo.

>[!NOTE]
>
>Atualmente, os emails arquivados ainda são enviados pelo módulo de arquivamento herdado que usa uma retransmissão SMTP simples.

## Ativação do arquivamento de emails {#activating-email-archiving}

Depois de habilitado, o Email Cco é ativado no [modelo de email](../../start/using/marketing-activity-templates.md), por meio de uma opção dedicada:

1. Acesse **Resources** > **Templates** > **Delivery templates**.
1. Duplique o modelo **[!UICONTROL Send via email]** pronto para uso.
1. Selecione o template duplicado.
1. Clique no botão **[!UICONTROL Edit properties]** para editar as propriedades do modelo.
1. Expanda a seção **[!UICONTROL Send]**.
1. Marque a caixa **[!UICONTROL Archive emails]** para manter uma cópia de todas as mensagens enviadas para cada entrega com base neste modelo.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>Se os emails enviados para o endereço CCo forem abertos e clicados, isso será considerado no **[!UICONTROL Total opens]** e **[!UICONTROL Clicks]** da análise de envio, o que poderá causar alguns erros de cálculo.
