---
solution: Campaign Standard
product: campaign
title: Calcular a data de envio
description: Descubra como enviar uma mensagem em uma data e hora específicas.
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Monitoramento de desempenho
role: Profissional
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 7%

---


# Calcular a data de envio{#computing-the-sending-date}

Você pode definir uma fórmula para enviar a mensagem a cada recipient em uma data e hora específicas.

## Personalizando fórmula de data {#customizing-date-formula}

Por exemplo, você pode usar a otimização de tempo de envio durante o processo de inicialização.

Quando os emails são enviados usando uma nova plataforma, os provedores de serviços de Internet (ISPs) suspeitam de endereços IP que não são reconhecidos. Se grandes volumes de emails forem enviados repentinamente, os ISPs freqüentemente os marcam como spam.

Para evitar ser marcado como spam, você pode aumentar progressivamente o volume enviado distribuindo grandes volumes de emails em momentos diferentes. Isso deve garantir o desenvolvimento suave da fase de inicialização e permitir que você reduza a taxa geral de endereços inválidos.

Por exemplo, você pode segmentar seu público-alvo aleatoriamente para enviar seu delivery em cinco lotes. Você enviará um primeiro lote representando 10% do público-alvo em 1º de junho às 10h00, um segundo lote 24 horas depois com 15% do público-alvo e assim por diante.

Você pode agendar isso usando um workflow.

![](assets/send-time_opt_workflow1.png)

1. Acesse a lista de atividades de marketing e crie um novo workflow. Consulte [Criação de um workflow](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Arraste e solte uma atividade **Query** no seu fluxo de trabalho e abra-a. Consulte a seção [Query](../../automating/using/query.md).
1. Selecione um público-alvo, por exemplo, todos os clientes Gold e clique em **[!UICONTROL Confirm]** para salvar o query.
1. Arraste e solte uma atividade **Segmentation** no seu fluxo de trabalho e abra-a. Consulte a seção [Segmentação](../../automating/using/segmentation.md) .
1. Defina cinco segmentos. Para cada segmento:

   * Preencha o campo **[!UICONTROL Segment code]** : insira manualmente a data e a hora desejadas para enviar a mensagem.

      Por exemplo, você deseja enviar o primeiro lote em 1º de junho às 10h GMT+1. Use o seguinte formato: **AAAA-MM-DD hh:mm:ss+tz**.

      ![](assets/send-time_opt_segment_configuration.png)

      Para enviar o próximo lote no dia seguinte, digite **2017-06-02 10:00:00+01** para o segundo segmento.

      Para os segmentos restantes, defina os próximos lotes da seguinte maneira:

      * **2017-06-03 10:00:00+01**
      * **2017-06-04 10:00:00+01**
      * **2017-06-05 10:00:00+01**
   * Selecione a opção **[!UICONTROL Limit the population of this segment]**.

      Na guia **[!UICONTROL Limitation]** , selecione **[!UICONTROL Random sampling]** e insira a porcentagem desejada para cada segmento: 10 para o primeiro lote, 15 para o segundo e assim por diante.

      ![](assets/send-time_opt_segment_limitation.png)


1. Depois que todos os segmentos forem definidos, selecione **[!UICONTROL Generate all segments in the same transition]** e clique em **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment_dates.png)

1. Arraste e solte uma atividade **Email delivery** no seu fluxo de trabalho e abra-a. Consulte a seção [Delivery de email](../../automating/using/email-delivery.md) .
1. Clique na seção **[!UICONTROL Schedule]** no painel de email e selecione **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. No campo **[!UICONTROL Start sending from]**, defina uma data de contato.
1. No menu suspenso de otimização do tempo de envio , escolha **[!UICONTROL Send at a custom date defined by a formula]**.
1. Clique no botão **[!UICONTROL Edit an expression]** do campo **[!UICONTROL Custom date formula]**.

   ![](assets/send-time_opt_formula_define.png)

1. Crie a seguinte expressão usando a função **[!UICONTROL ToDateTime]** e o campo **[!UICONTROL Segment code]**. Você também pode digitar diretamente na expressão, mas certifique-se de usar a sintaxe e a ortografia corretas.

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   A função **[!UICONTROL ToDateTime]** transforma o código do segmento de uma string de texto em um valor de data e hora.

   Confirme a expressão para retornar à tela anterior.

   ![](assets/send-time_opt_formula_define_segment.png)

   Na janela **[!UICONTROL Schedule]**, a fórmula de data personalizada é exibida da seguinte maneira:

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   ![](assets/send-time_opt_custom_formula.png)

1. Confirme o agendamento, salve o delivery e execute o workflow.

O delivery será enviado progressivamente para todos os recipients alvos por cinco dias.

>[!NOTE]
>
>Certifique-se de que todas as datas estejam no futuro ao confirmar o envio. Caso contrário, a mensagem será enviada assim que o envio for confirmado.

## Uso de uma expressão {#using-an-expression}

A otimização de tempo de envio também é útil para campanhas que envolvam uma central de atendimento. Você pode garantir que todas as mensagens não sejam recebidas ao mesmo tempo. Isso permite que sua organização processe o número de chamadas de acordo com sua capacidade.

Por exemplo, você deseja enviar um email convidando seus clientes para entrar em contato com uma central de atendimento para obter uma oferta promocional. Para evitar sobrecarregar a central de atendimento, você decide segmentar seu público-alvo aleatoriamente para enviar seu email em quatro lotes.

Você pode agendar isso usando um workflow.

![](assets/send-time_opt_workflow2.png)

1. Acesse a lista de atividades de marketing e crie um novo workflow. Consulte [Criação de um workflow](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Arraste e solte uma atividade **Query** no seu fluxo de trabalho e abra-a. Consulte a seção [Query](../../automating/using/query.md).
1. Selecione um público-alvo, por exemplo, mais de 35 perfis e clique em **[!UICONTROL Confirm]** para salvar o query.
1. Arraste e solte uma atividade **Segmentation** no seu fluxo de trabalho e abra-a. Consulte a seção [Segmentação](../../automating/using/segmentation.md) .
1. Defina quatro segmentos. Para cada segmento:

   * Defina os códigos do segmento da seguinte maneira:

      * 08:00 - 10:00: **0**. A mensagem será enviada para o primeiro trimestre da população do target às 8h (data de contato).
      * 22:00 - 12:00: **2**. A mensagem será enviada para o segundo trimestre da população do target às 10h (data de contato + 2 horas).
      * 14:00 - 16:00: **6**. Sendo a central de atendimento fechada entre as 12h00 e as 14h00, a mensagem será enviada para o terceiro trimestre da população do target às 14h00 (data de contato + 6 horas).
      * 16:00 - 18:00: **8**. A mensagem será enviada ao último trimestre da população do target às 16:00 PM (data de contato + 8 horas).

      >[!NOTE]
      >
      >A data de contato será definida na atividade Email delivery posteriormente no workflow.

   * Selecione a opção **[!UICONTROL Limit the population of this segment]**.
   * Na guia **[!UICONTROL Limitation]** , selecione **[!UICONTROL Random sampling]** e insira a porcentagem desejada para cada segmento: **25**.


1. Depois que todos os segmentos forem definidos, selecione **[!UICONTROL Generate all segments in the same transition]** e clique em **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment.png)

1. Arraste e solte uma atividade **Email delivery** no seu fluxo de trabalho e abra-a. Consulte a seção [Delivery de email](../../automating/using/email-delivery.md) .
1. Clique na seção **[!UICONTROL Schedule]** no painel de email.
1. Selecione **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. No campo **[!UICONTROL Start sending from]**, defina uma data de contato.

   Neste exemplo, selecione 25 de maio às 8h.

1. No menu suspenso de otimização de tempo de envio , escolha **[!UICONTROL Send at a custom date defined by a formula]** e clique no botão **[!UICONTROL Edit an expression]**.

   ![](assets/send-time_opt_formula_expression.png)

1. No **[!UICONTROL Expression editor]**, defina a data e os códigos do segmento para calcular os dados de cada cliente.

   Na lista de funções, selecione **[!UICONTROL AddHours]**.

   ![](assets/send-time_opt_formula_expression_addhours.png)

   Nos campos disponíveis, selecione **[!UICONTROL Current delivery]** > **[!UICONTROL Delivery scheduling]** > **[!UICONTROL Contact date]**.

   ![](assets/send-time_opt_formula_expression_contact_date.png)

   Isso permite recuperar a data e a hora especificadas no campo **[!UICONTROL Start sending from]**.

   Na lista de funções, selecione **[!UICONTROL ToInteger]**. Nos campos disponíveis, selecione **[!UICONTROL Additional data]** > **[!UICONTROL Segment code]**.

   ![](assets/send-time_opt_formula_expression_segment_code.png)

   Isso permite recuperar os números especificados nos códigos do segmento.

   Você deve obter a seguinte fórmula:

   ```
   AddHours([currentDelivery/scheduling/@contactDate], ToInteger([targetData/@segmentCode]))
   ```

1. Confirme para salvar a expressão. Confirme o agendamento, salve o delivery e execute o workflow.

* O primeiro segmento receberá a mensagem na data de contato (25 de maio às 8h).
* O segundo segmento receberá a mensagem duas horas depois (25 de maio às 10h).
* O terceiro segmento receberá a mensagem seis horas depois (25 de maio às 14:00).
* O quarto segmento receberá a mensagem oito horas depois (25 de maio às 16h).

