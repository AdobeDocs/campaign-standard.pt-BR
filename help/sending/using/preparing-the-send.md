---
solution: Campaign Standard
product: campaign
title: Preparação do envio
description: Saiba como definir a preparação antes do envio.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Enviar Otimização de Tempo
role: User
level: Intermediate
exl-id: 0140c41a-7255-4b77-a1b7-c6f7b1135e51
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 5%

---

# Preparação do envio{#preparing-the-send}

A preparação corresponde à etapa de calcular a população do target e gerar o conteúdo da mensagem para cada perfil incluído no target. Quando a preparação for concluída, as mensagens estarão prontas para serem enviadas, imediatamente ou em [a data e hora programadas](../../sending/using/about-scheduling-messages.md).

1. Para começar a preparar o envio, clique no botão **Prepare** localizado na barra de ações.

   ![](assets/preparing_delivery_2.png)

1. O bloco **[!UICONTROL Deployment]** mostra o progresso da preparação e, em seguida, as estatísticas de preparação: número de mensagens direcionadas, número de mensagens a serem enviadas, etc.

   Dependendo do tamanho do público alvo, essa operação pode levar algum tempo.

   ![](assets/preparing_delivery.png)

1. Pare a preparação a qualquer momento usando o botão **Stop**, localizado na barra de ação.

   Durante a fase de preparação, nenhuma mensagem é enviada. Portanto, você pode iniciar ou parar isso sem correr o risco de afetar nada.

   ![](assets/preparing_delivery_6.png)

1. Sua mensagem é salva automaticamente durante o estágio de preparação para delivery. Se precisar fazer alterações no agendamento da mensagem após a etapa de preparação, será necessário clicar novamente no botão **[!UICONTROL Prepare]** para que essas alterações sejam levadas em conta. Para obter mais informações sobre como agendar uma mensagem, consulte esta [página](../../sending/using/about-scheduling-messages.md).

   ![](assets/preparing_delivery_5.png)

1. Para exibir os logs de preparação, clique no botão localizado na parte inferior direita do bloco .

   ![](assets/preparing_delivery_4.png)

1. A janela **[!UICONTROL Deployment]** é aberta, corrija quaisquer erros e reinicie a preparação.

   A última mensagem de log exibe mensagens de erro e o número de erros. Um ícone específico mostra o tipo de erro encontrado: o ícone amarelo indica um erro de processamento não crítico, o ícone vermelho indica um erro crítico que impede o início do delivery.

   ![](assets/preparing_delivery_3.png)

1. Verifique as estatísticas de preparação antes de confirmar o envio das mensagens. Se o número de mensagens para enviar não corresponder à sua configuração, edite o público alvo (consulte [Selecionar um público em uma mensagem](../../audiences/using/selecting-an-audience-in-a-message.md)) e reinicie a preparação.

Uma vez concluída a preparação, sua mensagem estará pronta para ser enviada. Para obter mais informações, consulte [Confirmando o envio](../../sending/using/confirming-the-send.md).

**Regras de tipologia**

O Adobe Campaign vem com um conjunto de regras de tipologia incorporadas que são aplicadas durante a preparação da mensagem. Eles são usados para verificar se uma mensagem é válida e atende aos seus critérios de qualidade. Consulte [Tipologias](../../sending/using/about-typology-rules.md). Você pode definir suas próprias regras de tipologia, por exemplo, pode definir regras de fadiga globais entre canais que excluirão automaticamente perfis supersolúveis de campanhas. Consulte [Regras de fadiga](../../sending/using/fatigue-rules.md).

**Verificação de mensagem SMS**

Se você tiver inserido campos de personalização ou texto condicional no conteúdo da mensagem SMS, esses fatores poderão introduzir caracteres que não são considerados pela codificação GSM. Quando a preparação é executada, o comprimento da mensagem é monitorado e uma mensagem de aviso será exibida se ele passar no limite.

Para obter mais informações, consulte as seções [Codificação, comprimento e transliteração do SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) e [Personalização de mensagens SMS](../../channels/using/personalizing-sms-messages.md) .
