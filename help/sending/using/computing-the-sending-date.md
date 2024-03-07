---
title: Cálculo da data de envio
description: Descubra como enviar uma mensagem em uma data e hora específicas.
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 7a0cd10a-24e6-44d1-842c-2067bfbac838
source-git-commit: 21bcc9818b881212985988ef3377687069a1dbea
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 7%

---

# Cálculo da data de envio{#computing-the-sending-date}

Você pode definir uma fórmula para enviar a mensagem para cada recipient em uma data e hora específicas.

## Personalização da fórmula de data {#customizing-date-formula}

Por exemplo, você pode usar a otimização de tempo de envio durante o processo de aumento.

Quando os emails são enviados usando uma nova plataforma, os provedores de serviços de Internet (ISPs) suspeitam de endereços IP que não são reconhecidos. Se grandes volumes de emails forem enviados repentinamente, os ISPs freqüentemente os marcam como spam.

Para evitar ser marcado como spam, você pode aumentar progressivamente o volume enviado distribuindo grandes volumes de emails em diferentes horários. Isso deve garantir o desenvolvimento suave da fase de inicialização e permitir que você reduza a taxa geral de endereços inválidos.

Por exemplo, você pode segmentar seu público-alvo aleatoriamente para enviar sua entrega em cinco lotes. Você enviará um primeiro lote representando 10% do público-alvo em 1º de junho às 10h, um segundo lote 24 horas depois com 15% do público-alvo e assim por diante.

Você pode programar isso usando um workflow.

![](assets/send-time_opt_workflow1.png)

1. Acesse a lista de atividades de marketing e crie um novo workflow. Consulte [Criação de um workflow](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Arraste e solte uma **Query** atividade no seu fluxo de trabalho e abra-o. Consulte a [Query](../../automating/using/query.md) seção.
1. Selecione um público, por exemplo, todos os seus clientes Gold e clique em **[!UICONTROL Confirm]** para salvar a consulta.
1. Arraste e solte uma **Segmentação** atividade no seu fluxo de trabalho e abra-o. Consulte a [Segmentação](../../automating/using/segmentation.md) seção.
1. Defina cinco segmentos. Para cada segmento:

   * Preencha o **[!UICONTROL Segment code]** field: insira manualmente a data e a hora desejadas para enviar a mensagem.

     Por exemplo, você deseja enviar o primeiro lote em 1º de junho às 10h GMT+1. Usar o seguinte formato: **`YYYY-MM-DD hh:mm:ss+tz`**.

     ![](assets/send-time_opt_segment_configuration.png)

     Para enviar o próximo lote no dia seguinte, informe **02-06-2017 10:00:00+01** para o segundo segmento.

     Para os segmentos restantes, defina os próximos lotes da seguinte maneira:

      * **03-06-2017 10:00:00+01**
      * **04-06-2017 10:00:00+01**
      * **05/06/2017 10:00:00+01**

   * Selecione o **[!UICONTROL Limit the population of this segment]** opção.

     No **[!UICONTROL Limitation]** selecione **[!UICONTROL Random sampling]** e insira a porcentagem desejada para cada segmento: 10 para o primeiro lote, 15 para o segundo e assim por diante.

     ![](assets/send-time_opt_segment_limitation.png)

1. Após definir todos os segmentos, selecione **[!UICONTROL Generate all segments in the same transition]** e clique em **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment_dates.png)

1. Arraste e solte um **Entrega de email** atividade no seu fluxo de trabalho e abra-o. Consulte a [Entrega de email](../../automating/using/email-delivery.md) seção.
1. Clique em **[!UICONTROL Schedule]** no painel de email e selecione **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. No **[!UICONTROL Start sending from]** defina uma data de contato.
1. No menu suspenso de otimização de tempo de envio, escolha **[!UICONTROL Send at a custom date defined by a formula]**.
1. Clique em **[!UICONTROL Edit an expression]** botão do **[!UICONTROL Custom date formula]** campo.

   ![](assets/send-time_opt_formula_define.png)

1. Crie a seguinte expressão usando o **[!UICONTROL ToDateTime]** e a função **[!UICONTROL Segment code]** campo. Você também pode digitar diretamente a expressão, mas certifique-se de usar a sintaxe e a ortografia corretas.

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   A variável **[!UICONTROL ToDateTime]** Esta função transforma o código de segmento de uma sequência de caracteres de texto em um valor de data e hora.

   Confirme a expressão para retornar à tela anterior.

   ![](assets/send-time_opt_formula_define_segment.png)

   No **[!UICONTROL Schedule]** , a fórmula de data personalizada é exibida da seguinte maneira:

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   ![](assets/send-time_opt_custom_formula.png)

1. Confirme a programação, salve o delivery e execute o workflow.

O delivery será progressivamente enviado para todos os recipients alvos ao longo de cinco dias.

>[!NOTE]
>
>Verifique se todas as datas estão no futuro ao confirmar o envio. Caso contrário, a mensagem será enviada assim que o envio for confirmado.

## Usar uma expressão {#using-an-expression}

A otimização de tempo de envio também é útil para campanhas que envolvem uma central de atendimento. Você pode garantir que nenhuma mensagem seja recebida ao mesmo tempo. Isso permite que sua organização processe o número de chamadas de acordo com sua capacidade.

Por exemplo, você deseja enviar um email convidando seus clientes a entrar em contato com uma central de atendimento para obter uma oferta promocional. Para não sobrecarregar a central de atendimento, você decide segmentar o público-alvo aleatoriamente para enviar seu email em quatro lotes.

Você pode programar isso usando um workflow.

![](assets/send-time_opt_workflow2.png)

1. Acesse a lista de atividades de marketing e crie um novo workflow. Consulte [Criação de um workflow](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Arraste e solte uma **Query** atividade no seu fluxo de trabalho e abra-o. Consulte a [Query](../../automating/using/query.md) seção.
1. Selecione um público, por exemplo, com mais de 35 perfis e clique em **[!UICONTROL Confirm]** para salvar a consulta.
1. Arraste e solte uma **Segmentação** atividade no seu fluxo de trabalho e abra-o. Consulte a [Segmentação](../../automating/using/segmentation.md) seção.
1. Defina quatro segmentos. Para cada segmento:

   * Defina os códigos de segmento da seguinte maneira:

      * 8H ÀS 10H: **0**. A mensagem será enviada para o primeiro trimestre do público-alvo às 8h (data de contato).
      * 10H ÀS 12H: **2**. A mensagem será enviada para o segundo trimestre do público-alvo às 10h (data de contato + 2 horas).
      * 14H - 16H: **6**. Sendo a central de atendimento fechada entre 12h e 14h, a mensagem será enviada para o terceiro trimestre da população do target às 14h (data de contato + 6 horas).
      * 16H - 18H: **8**. A mensagem será enviada para o último trimestre da população do target às 16h (data de contato + 8 horas).

     >[!NOTE]
     >
     >A data de contato será definida na atividade Email delivery posteriormente no workflow.

   * Selecione o **[!UICONTROL Limit the population of this segment]** opção.
   * No **[!UICONTROL Limitation]** selecione **[!UICONTROL Random sampling]** e insira a porcentagem desejada para cada segmento: **25**.

1. Após definir todos os segmentos, selecione **[!UICONTROL Generate all segments in the same transition]** e clique em **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment.png)

1. Arraste e solte um **Entrega de email** atividade no seu fluxo de trabalho e abra-o. Consulte a [Entrega de email](../../automating/using/email-delivery.md) seção.
1. Clique em **[!UICONTROL Schedule]** no painel de email.
1. Selecione **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. No **[!UICONTROL Start sending from]** defina uma data de contato.

   Neste exemplo, selecione 25 de maio às 8h.

1. No menu suspenso de otimização de tempo de envio, escolha **[!UICONTROL Send at a custom date defined by a formula]** e clique no link **[!UICONTROL Edit an expression]** botão.

   ![](assets/send-time_opt_formula_expression.png)

1. No **[!UICONTROL Expression editor]**, defina a data e os códigos de segmento para calcular os dados de cada cliente.

   Na lista de funções, selecione **[!UICONTROL AddHours]**.

   ![](assets/send-time_opt_formula_expression_addhours.png)

   Nos campos disponíveis, selecione **[!UICONTROL Current delivery]** > **[!UICONTROL Delivery scheduling]** > **[!UICONTROL Contact date]**.

   ![](assets/send-time_opt_formula_expression_contact_date.png)

   Isso permite recuperar a data e a hora especificadas no **[!UICONTROL Start sending from]** campo.

   Na lista de funções, selecione **[!UICONTROL ToInteger]**. Nos campos disponíveis, selecione **[!UICONTROL Additional data]** > **[!UICONTROL Segment code]**.

   ![](assets/send-time_opt_formula_expression_segment_code.png)

   Isso permite recuperar os números especificados nos códigos de segmento.

   Você deve obter a seguinte fórmula:

   ```
   AddHours([currentDelivery/scheduling/@contactDate], ToInteger([targetData/@segmentCode]))
   ```

1. Confirme para salvar a expressão. Confirme a programação, salve o delivery e execute o workflow.

* O primeiro segmento receberá a mensagem na data de contato (25 de maio às 8h).
* O segundo segmento receberá a mensagem duas horas depois (25 de maio às 10h).
* O terceiro segmento receberá a mensagem seis horas depois (25 de maio às 14h).
* O quarto segmento receberá a mensagem oito horas depois (25 de maio às 16h).
