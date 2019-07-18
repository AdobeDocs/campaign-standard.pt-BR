---
title: Preparação do envio
seo-title: Preparação do envio
description: Preparação do envio
seo-description: Saiba como definir a preparação antes do envio.
page-status-flag: nunca ativado
uuid: 1038 dae 2-164 c -4579-9294-bdf 2 a 4 eb 12 d 6
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviando
content-type: reference
topic-tags: preparando e testando-messages
discoiquuid: 003 abc 83-7 f 07-471 f-ab 2 f -1 d 352 d 22 c 26 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Preparing the send{#preparing-the-send}

A preparação corresponde à etapa de calcular o público-alvo e gerar o conteúdo da mensagem para cada perfil incluído na meta. Once preparation is finished, the messages are ready to be sent, either immediately or at [the scheduled date and time](../../sending/using/about-scheduling-messages.md).

1. To start preparing the send, click the **Prepare** button located in the action bar.

   ![](assets/preparing_delivery_2.png)

1. The **[!UICONTROL Deployment]** block shows the preparation progress, then the preparation statistics: number of targeted messages, number of messages to send, etc.

   Dependendo do tamanho da população direcionada, esta operação pode levar algum tempo.

   ![](assets/preparing_delivery.png)

1. Stop the preparation at any time using the **Stop** button, located in the action bar.

   Durante a fase de preparação, nenhuma mensagem é enviada. Portanto, é possível iniciar ou parar isso sem risco de afetar qualquer item.

   ![](assets/preparing_delivery_6.png)

1. A mensagem é salva automaticamente durante a preparação para o estágio de entrega. If you need to make any changes to your message's schedule after the preparation step, you will need to make sure that you click the **[!UICONTROL Prepare]** button again for those changes to be taken into account. For more information on how to schedule a message, refer to this [page](../../sending/using/about-scheduling-messages.md).

   ![](assets/preparing_delivery_5.png)

1. Para exibir os logs de preparação, clique no botão localizado na parte inferior direita do bloco.

   ![](assets/preparing_delivery_4.png)

1. The **[!UICONTROL Deployment]** window opens, correct any errors then restart the preparation.

   A última mensagem de registro exibe quaisquer mensagens de erro e o número de erros. Um ícone específico mostra o tipo de erro encontrado: o ícone amarelo indica um erro de processamento não-crítico, o ícone vermelho indica um erro crítico que impede a execução da entrega.

   ![](assets/preparing_delivery_3.png)

1. Verifique as estatísticas de preparação antes de confirmar o envio das mensagens. If the number of messages to send does not correspond to your configuration, edit the targeted population (see [Selecting an audience in a message](../../audiences/using/selecting-an-audience-in-a-message.md)) and restart the preparation.

Depois que a preparação for concluída, sua mensagem estará pronta para ser enviada. For more on this, see [Confirming send](../../sending/using/confirming-the-send.md).

**Regras de tipologia**

O Adobe Campaign vem com um conjunto de regras de tipologia de criação que são aplicadas durante a preparação da mensagem. Eles são usados para verificar se uma mensagem é válida e atender aos critérios de qualidade. See [Typologies](../../administration/using/about-typology-rules.md). Você pode definir suas próprias regras de tipologia, por exemplo, pode definir regras globais de esgotamento entre canais que excluirão automaticamente os perfis substituídos das campanhas. See [Fatigue rules](../../administration/using/fatigue-rules.md).

**Verificação de mensagem SMS**

Se você inseriu campos de personalização ou texto condicional no conteúdo de sua mensagem SMS, esses fatores poderão inserir caracteres que não são considerados pela codificação GSM. Quando a preparação for executada, o comprimento da mensagem será monitorado e uma mensagem de aviso será exibida se passar o limite.

For more on this, refer to the [SMS encoding, length and transliteration](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) and [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md) sections.
