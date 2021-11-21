---
title: Personalização de um email com dados adicionais
description: Este caso de uso apresenta como adicionar diferentes tipos de dados adicionais a um query e usá-lo como um campo de personalização em um email.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: b207dc73-03dc-4f25-95e5-573e4b4bce54
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 86%

---

# Personalização de um email com dados adicionais {#example--personalizing-an-email-with-additional-data}

O exemplo a seguir ilustra a adição de diferentes tipos de dados adicionais a um query e o uso de cada um deles como campo de personalização em um email. Para obter mais informações sobre como enriquecer os dados direcionados por um **[!UICONTROL Query]** atividade , consulte [esta seção](../../automating/using/query.md#enriching-data).

Neste exemplo, são usados [recursos personalizados](../../developing/using/data-model-concepts.md):

* O recurso **perfil** foi estendido para a adição de um campo que permite salvar os pontos de fidelidade de cada perfil.
* Um recurso **transações** foi criado e identifica todas as compras realizadas pelos perfis no banco de dados. A data, o preço e o produto comprado são salvos para cada transação.
* Um recurso **produtos** foi criado e faz referência aos produtos disponíveis para compra.

O objetivo é enviar um email aos perfis para os quais pelo menos uma transação foi salva. Nesse email, os clientes receberão um lembrete da última transação realizada, bem como uma visão geral de todas as transações: a quantidade de produtos comprados, o total gasto e um lembrete do total de pontos de fidelidade acumulados.

O fluxo de trabalho é apresentado da seguinte forma:

![](assets/enrichment_example1.png)

1. Adicione um [Query](../../automating/using/query.md) atividade , que permite direcionar os perfis que executaram pelo menos uma transação.

   ![](assets/enrichment_example2.png)

1. Na guia **[!UICONTROL Additional data]** do query, defina os diferentes dados a serem exibidos no email final:

   * O campo simples da dimensão do **perfil** correspondente aos pontos de fidelidade. Consulte a seção [Adição de um campo simples](../../automating/using/query.md#adding-a-simple-field).
   * Duas agregações com base na coleção de transações: o número de produtos comprados e o total gasto. Você pode adicioná-los da guia **[!UICONTROL Data]** da janela de configuração da agregação, usando as agregações **Count** e **Sum**. Consulte a seção [Adição de uma agregação](../../automating/using/query.md#adding-an-aggregate).
   * Uma coleção que retorna o valor gasto, a data e o produto da última transação realizada.

      Para isso, adicione os diferentes campos que deseja exibir da guia **[!UICONTROL Data]** da janela de configuração da coleção.

      Para retornar apenas a transação mais recente, digite “1” para o **[!UICONTROL Number of lines to return]** e aplique uma classificação decrescente ao campo **Date** da coleção da guia **[!UICONTROL Sort]**.

      Consulte as seções [Adição de uma coleção](../../automating/using/query.md#adding-a-collection) e [Classificação de dados adicionais](../../automating/using/query.md#sorting-additional-data).
   ![](assets/enrichment_example4.png)

1. Se você quiser verificar se os dados foram transferidos corretamente pela transição de saída da atividade, inicie o fluxo de trabalho pela primeira vez (sem a atividade **[!UICONTROL Email delivery]**) e abra a transição de saída do query.

   ![](assets/enrichment_example5.png)

1. Adicione um [Delivery por email](../../automating/using/email-delivery.md) atividade . No conteúdo do email, insira os campos de personalização correspondentes aos dados calculados no query. Você pode encontrá-los no link **[!UICONTROL Additional data (targetData)]** do explorador de campos de personalização.

   ![](assets/enrichment_example3.png)

Seu fluxo de trabalho agora está pronto para ser executado. Os perfis direcionados no query receberão um email personalizado com os dados calculados das transações.
