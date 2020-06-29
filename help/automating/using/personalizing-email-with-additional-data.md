---
title: Personalização de um email com dados adicionais
description: Este caso de uso apresenta como adicionar diferentes tipos de dados adicionais a um query e usá-los como um campo de personalização em um email.
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---


# Personalização de um email com dados adicionais {#example--personalizing-an-email-with-additional-data}

O exemplo a seguir ilustra a adição de diferentes tipos de dados adicionais a um query e seu uso como campo de personalização em um email. Para obter mais informações sobre como aprimorar os dados direcionados por uma **[!UICONTROL Query]** atividade, consulte [esta seção](../../automating/using/query.md#enriching-data).

Neste exemplo, recursos [](../../developing/using/data-model-concepts.md) personalizados são usados:

* O recurso de **perfil** foi estendido para adicionar um campo que permite que cada ponto de fidelidade do perfil seja salvo.
* Um recurso de **transações** foi criado e identifica todas as compras realizadas pelos perfis no banco de dados. A data, o preço e o produto comprados são salvos para cada transação.
* Um recurso de **produtos** foi criado e faz referência aos produtos disponíveis para compra.

O objetivo é enviar um email aos perfis para os quais pelo menos uma transação foi salva. Através deste e-mail, os clientes receberão um lembrete da última transação realizada, bem como uma visão geral de todas as suas transações: o número de produtos comprados, o total gasto, um lembrete do número total de pontos de fidelidade acumulados.

O fluxo de trabalho é apresentado da seguinte forma:

![](assets/enrichment_example1.png)

1. Adicione uma atividade de [Query](../../automating/using/query.md) , que permite público alvo dos perfis que realizaram pelo menos uma transação.

   ![](assets/enrichment_example2.png)

   Na guia query, defina os diferentes dados a serem exibidos no email final: **[!UICONTROL Additional data]**

   * O campo simples da dimensão do **perfil** correspondente aos pontos de fidelidade. Consulte a seção [Adicionar um campo](../../automating/using/query.md#adding-a-simple-field) simples.
   * Duas agregações com base na coleção de transações: O número de produtos comprados e o montante total gasto. Você pode adicioná-los na **[!UICONTROL Data]** guia da janela de configuração da agregação, usando as agregações **Contagem** e **Soma** . Consulte a seção [Adicionar uma agregação](../../automating/using/query.md#adding-an-aggregate) .
   * Uma coleção que retorna a quantia gasta, a data e o produto da última transação realizada.

      Para fazer isso, é necessário adicionar os diferentes campos que deseja exibir na **[!UICONTROL Data]** guia da janela de configuração da coleção.

      Para retornar apenas a transação mais recente, é necessário digitar &quot;1&quot; para o **[!UICONTROL Number of lines to return]** e aplicar uma classificação decrescente no campo **Data** da coleção na **[!UICONTROL Sort]** guia.

      Consulte [Adicionar uma coleção](../../automating/using/query.md#adding-a-collection) e [Classificar seções de dados](../../automating/using/query.md#sorting-additional-data) adicionais.
   ![](assets/enrichment_example4.png)

   Se você quiser verificar se os dados foram transferidos corretamente pela transição de saída da atividade, start o fluxo de trabalho pela primeira vez (sem a **[!UICONTROL Email delivery]** atividade) e abra a transição de saída do query.

   ![](assets/enrichment_example5.png)

1. Adicione uma atividade de delivery [](../../automating/using/email-delivery.md) de email. No conteúdo do email, insira os campos de personalização correspondentes aos dados calculados no query. Você pode encontrá-lo através do **[!UICONTROL Additional data (targetData)]** link do explorador de campos de personalização.

   ![](assets/enrichment_example3.png)

Seu fluxo de trabalho está pronto para ser executado. Os perfis direcionados no query receberão um email personalizado contendo os dados calculados de suas transações.
