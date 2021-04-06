---
solution: Campaign Standard
product: campaign
title: Arquivamento de mensagens no Adobe Campaign Standard
description: Saiba como arquivar emails com o Adobe Campaign Standard usando um endereço de email CCO.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: Monitoramento de desempenho
role: Profissional de negócios
level: Intermediário
exl-id: 7bf380d7-195e-413d-b14e-85e78b07ba8b
translation-type: tm+mt
source-git-commit: f7d77f524a6c141066056e53fc8616f35189fc39
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 16%

---

# Arquivamento com email Cco{#archiving-emails}

Você pode configurar o Adobe Campaign para manter uma cópia dos emails enviados de sua plataforma por meio do Email Cco.

Especificamente, se sua organização precisar arquivar todas as mensagens de email de saída para fins de conformidade, você poderá habilitar esse recurso. Ele permite enviar uma cópia oculta exata das mensagens enviadas correspondentes para um endereço de email CCO (invisível aos recipients do delivery) que você deve especificar.

Depois de habilitado, é necessário ativar o Email Cco na opção **[!UICONTROL Archive emails]** no template do delivery de email.

>[!NOTE]
>
>A Adobe Campaign em si não gerencia arquivos arquivados. Ele permite enviar as mensagens de sua escolha para um endereço dedicado, de onde elas podem ser processadas e arquivadas usando um sistema externo.

## Recommendations e limitações {#recommendations-and-limitations}

* Este recurso é opcional. Verifique seu contrato de licença e entre em contato com o executivo da sua conta para ativá-lo.
* O endereço CCO de sua escolha deve ser fornecido à equipe do Adobe que o configurará para você.
* Você só pode usar um endereço de email CCO.
* Somente emails enviados com êxito são considerados. Rejeições não são.
* Por motivos de privacidade, os emails CCO devem ser processados por um sistema de arquivamento capaz de armazenar informações de identificação pessoal (PII) seguras.
* Ao criar um novo modelo de delivery, o CCo não é ativado por padrão, mesmo que a opção tenha sido adquirida. Você deve habilitá-lo manualmente em cada template de delivery onde deseja usá-lo.

>[!NOTE]
>
>Atualmente, os emails arquivados ainda são enviados pelo módulo de arquivamento herdado que usa uma retransmissão SMTP simples.

## Ativação do arquivamento de email {#activating-email-archiving}

Depois de habilitado, o Cco de email é ativado no [modelo de email](../../start/using/marketing-activity-templates.md), por meio de uma opção dedicada:

1. Acesse **Resources** > **Templates** > **Delivery templates**.
1. Duplique o template pronto para uso **[!UICONTROL Send via email]**.
1. Selecione o template duplicado.
1. Clique no botão **[!UICONTROL Edit properties]** para editar as propriedades do modelo.
1. Expanda a seção **[!UICONTROL Send]**.
1. Marque a caixa **[!UICONTROL Archive emails]** para manter uma cópia de todas as mensagens enviadas para cada delivery com base nesse template.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>Se os emails enviados para o endereço CCo forem abertos e clicados, isso será considerado no **[!UICONTROL Total opens]** e **[!UICONTROL Clicks]** da análise de envio, o que poderá causar alguns erros de cálculo.
