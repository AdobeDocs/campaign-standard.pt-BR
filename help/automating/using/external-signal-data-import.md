---
title: Sinal externo e importação de dados
description: O exemplo a seguir ilustra a atividade de sinal Externo usada com a importação de dados.
page-status-flag: never-activated
uuid: 884b6daf-bfd9-440b-8336-004b80c76def
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 911c71b5-da8b-4916-b645-13bba6d21715
context-tags: signal,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---


# Sinal externo e importação de dados {#external-signal-data-import}

O exemplo a seguir ilustra a **[!UICONTROL External signal]** atividade em um caso de uso comum. Uma importação de dados é executada em um fluxo de trabalho de origem. Quando a importação for concluída e o banco de dados for atualizado, um segundo fluxo de trabalho será acionado. Esse segundo fluxo de trabalho é usado para atualizar uma agregação nos dados importados.

O fluxo de trabalho de origem é apresentado da seguinte maneira:

* Uma atividade [Carregar arquivo](../../automating/using/load-file.md) carrega um arquivo contendo novos dados de compra. Observe que o [banco de dados foi estendido](../../developing/using/data-model-concepts.md) de acordo com esse procedimento, pois os dados de compra não estão presentes por padrão no datamart.

   Por exemplo:

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2015;dannymars@example.com;A2;799
   aze124;28/05/2015;dannymars@example.com;A7;8
   aze125;31/07/2015;john.smith@example.com;A7;8
   aze126;14/12/2015;john.smith@example.com;A10;4
   aze127;02/01/2016;dannymars@example.com;A3;79
   aze128;04/03/2016;clara.smith@example.com;A8;149
   ```

* Uma atividade de [Reconciliação](../../automating/using/reconciliation.md) cria os links entre os dados importados e o banco de dados para que os dados de transações sejam conectados corretamente a perfis e produtos.
* Uma atividade de dados [](../../automating/using/update-data.md) Update insere e atualiza o recurso Transações do banco de dados com os dados recebidos.
* Uma atividade [End](../../automating/using/start-and-end.md) aciona o fluxo de trabalho de destino, que é usado para atualizar o agregação.

![](assets/signal_example_source1.png)

O fluxo de trabalho de destino é apresentado da seguinte forma:

* Uma atividade de sinal [](../../automating/using/external-signal.md) externo aguarda a conclusão com êxito do fluxo de trabalho de origem.
* Um perfil de públicos alvos de atividade [de](../../automating/using/query.md#enriching-data) Querye os enriquece com uma coleção definida para recuperar a data da última compra.
* Uma atividade de dados [](../../automating/using/update-data.md) Update armazena os dados adicionais em um campo personalizado dedicado. Observe que o recurso de perfil foi estendido para adicionar o campo Data **da** última compra.

![](assets/signal_example_source2.png)
