---
title: Sinal externo e importação de dados
description: O exemplo a seguir ilustra a atividade de sinal externo usada com a importação de dados.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: signal,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: e2997cf5-861b-4202-aeb7-3a47c4d55bef
TQID: 'https://experienceleague.adobe.com/fQTQgLluJa5WPu4ju1gGs84gWfqQ-sWIWuJSTXgQYHA'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 79%
---
# Sinal externo e importação de dados {#external-signal-data-import}

O exemplo a seguir ilustra a atividade **[!UICONTROL External signal]** em um caso de uso comum. Uma importação de dados é realizada em um fluxo de trabalho de origem. Quando a importação for concluída e o banco de dados for atualizado, um segundo fluxo de trabalho será acionado. Esse segundo fluxo de trabalho é usado para atualizar uma agregação nos dados importados.

O fluxo de trabalho de origem é apresentado da seguinte maneira:

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
* Uma atividade [End](../../automating/using/start-and-end.md) aciona o fluxo de trabalho de destino, que é usado para atualizar agregações.

![](assets/signal_example_source1.png)

O fluxo de trabalho de destino é apresentado da seguinte forma:

* Uma atividade [External signal](../../automating/using/external-signal.md) aguarda a conclusão com êxito do fluxo de trabalho de origem.
* Uma atividade de [Consulta](../../automating/using/query.md#enriching-data) é direcionada a perfis e os enriquece com uma coleção definida para recuperar a data da última compra.
* Uma atividade [Atualizar dados](../../automating/using/update-data.md) armazena os dados adicionais em um campo personalizado dedicado. Observe que o recurso de perfil foi estendido para adicionar o campo **Data da última compra**.

![](assets/signal_example_source2.png)
