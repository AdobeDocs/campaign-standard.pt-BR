---
solution: Campaign Standard
product: campaign
title: Sinal externo e importação de dados
description: O exemplo a seguir ilustra a atividade de sinal Externo usada com a importação de dados.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: signal,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 79%

---


# Sinal externo e importação de dados {#external-signal-data-import}

O exemplo a seguir ilustra a atividade **[!UICONTROL External signal]** em um caso de uso comum. Uma importação de dados é realizada em um workflow de origem. Quando a importação for concluída e o banco de dados for atualizado, um segundo workflow será acionado. Esse segundo workflow é usado para atualizar uma agregação nos dados importados.

O workflow de origem é apresentado da seguinte maneira:

* Uma atividade [Load file](../../automating/using/load-file.md) carrega um arquivo contendo novos dados de compra. Observe que o [banco de dados foi estendido](../../developing/using/data-model-concepts.md) de acordo, pois dados de compra não estão presentes por padrão no datamart.

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
* Uma atividade [Atualizar dados](../../automating/using/update-data.md) insere e atualiza o recurso Transações do banco de dados com os dados recebidos.
* Uma atividade [End](../../automating/using/start-and-end.md) aciona o fluxo de trabalho de destino, que é usado para atualizar o agregação.

![](assets/signal_example_source1.png)

O workflow de destino é apresentado da seguinte forma:

* Uma atividade [sinal externo](../../automating/using/external-signal.md) aguarda a conclusão com êxito do fluxo de trabalho de origem.
* Uma atividade de [Query](../../automating/using/query.md#enriching-data) é direcionada a perfis e os enriquece com uma coleção definida para recuperar a data da última compra.
* Uma atividade [Atualizar dados](../../automating/using/update-data.md) armazena os dados adicionais em um campo personalizado dedicado. Observe que o recurso de perfil foi estendido para adicionar o campo **Last purchase date**.

![](assets/signal_example_source2.png)
