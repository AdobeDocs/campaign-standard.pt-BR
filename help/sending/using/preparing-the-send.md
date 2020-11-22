---
solution: Campaign Standard
product: campaign
title: Preparação do envio
description: Saiba como definir a preparação antes do envio.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 5%

---


# Preparação do envio{#preparing-the-send}

A preparação corresponde à etapa de cálculo da população do público alvo e de geração do conteúdo da mensagem para cada perfil incluído no público alvo. Quando a preparação estiver concluída, as mensagens estarão prontas para serem enviadas, imediatamente ou [na data e hora](../../sending/using/about-scheduling-messages.md)programadas.

1. Para preparar o envio para o start, clique no botão **Preparar** localizado na barra de ações.

   ![](assets/preparing_delivery_2.png)

1. O **[!UICONTROL Deployment]** bloco mostra o progresso da preparação e, em seguida, as estatísticas da preparação: número de mensagens direcionadas, número de mensagens a serem enviadas, etc.

   Dependendo do tamanho da população-alvo, essa operação pode levar algum tempo.

   ![](assets/preparing_delivery.png)

1. Pare a preparação a qualquer momento usando o botão **Parar** , localizado na barra de ação.

   Durante a fase de preparação, não são enviadas mensagens. Portanto, você pode start ou parar isso sem o risco de afetar nada.

   ![](assets/preparing_delivery_6.png)

1. Sua mensagem é salva automaticamente durante a preparação para a fase de delivery. Se precisar fazer alterações no agendamento da sua mensagem após a etapa de preparação, será necessário clicar no **[!UICONTROL Prepare]** botão novamente para que essas alterações sejam levadas em consideração. For more information on how to schedule a message, refer to this [page](../../sending/using/about-scheduling-messages.md).

   ![](assets/preparing_delivery_5.png)

1. Para visualização dos registros de preparação, clique no botão localizado na parte inferior direita do bloco.

   ![](assets/preparing_delivery_4.png)

1. A **[!UICONTROL Deployment]** janela é aberta, corrija os erros e reinicie a preparação.

   A última mensagem de log exibe mensagens de erro e o número de erros. Um ícone específico mostra o tipo de erro encontrado: o ícone amarelo indica um erro de processamento não crítico, o ícone vermelho indica um erro crítico que impede que o delivery seja iniciado.

   ![](assets/preparing_delivery_3.png)

1. Verifique as estatísticas de preparação antes de confirmar o envio das mensagens. Se o número de mensagens a serem enviadas não corresponder à sua configuração, edite o público-alvo (consulte [Selecionar uma audiência em uma mensagem](../../audiences/using/selecting-an-audience-in-a-message.md)) e reinicie a preparação.

Quando a preparação estiver concluída, sua mensagem estará pronta para ser enviada. Para obter mais informações, consulte [Confirmação de envio](../../sending/using/confirming-the-send.md).

**Regras de tipologia**

O Adobe Campaign vem com um conjunto de regras de tipologia incorporadas que são aplicadas durante a preparação da mensagem. Eles são usados para verificar se uma mensagem é válida e atende aos seus critérios de qualidade. Consulte [Tipologias](../../sending/using/about-typology-rules.md). Você pode definir suas próprias regras de tipologia, por exemplo, pode definir regras globais de fadiga entre canais que excluirão automaticamente perfis supersolacionados do campanha. Consulte [Regras de fadiga](../../sending/using/fatigue-rules.md).

**Verificação de mensagem SMS**

Se você tiver inserido campos de personalização ou texto condicional no conteúdo da sua mensagem SMS, esses fatores poderão introduzir caracteres que não são considerados pela codificação GSM. Quando a preparação é executada, a duração da mensagem é monitorada e uma mensagem de aviso será exibida se ela ultrapassar o limite.

Para obter mais informações, consulte as seções de codificação, comprimento e transliteração [do](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) SMS e [Personalização de mensagens](../../channels/using/personalizing-sms-messages.md) SMS.
