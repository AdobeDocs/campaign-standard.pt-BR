---
title: Reconciliação de dados usando relações
description: O exemplo a seguir demonstra um fluxo de trabalho que atualiza o banco de dados usando os dados de compra em um arquivo.
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---


# Reconciliação de dados usando relações {#reconciliation-relations}

O exemplo a seguir demonstra um fluxo de trabalho que atualiza o banco de dados usando os dados de compra em um arquivo. Os dados de compra contêm dados que fazem referência a elementos de outras dimensões, como emails do cliente e códigos de produto.

>[!NOTE]
>
>Os recursos **Transações** e **Produtos** usados neste exemplo não existem no banco de dados do Adobe Campaign por padrão. Por conseguinte, foram previamente criados com a função de recursos [](../../developing/using/data-model-concepts.md) personalizados. Os perfis que correspondem aos endereços de email no arquivo importado, bem como os produtos, foram carregados no banco de dados antecipadamente.

O fluxo de trabalho é composto das seguintes atividades:

![](assets/reconciliation_example1.png)

* Uma atividade de arquivo [](../../automating/using/load-file.md) Load, que carrega e detecta os dados do arquivo a ser importado. O arquivo importado contém os seguintes dados:

   * Data da transação
   * Endereço de email do cliente
   * Código do produto comprado

   ```
   date;client;product
   2015-05-19 09:00:00;mail1@email.com;ZZ1
   2015-05-19 09:01:00;mail2@email.com;ZZ2
   2015-05-19 09:01:01;mail3@email.com;ZZ2
   2015-05-19 09:01:02;mail4@email.com;ZZ2
   2015-05-19 09:02:00;mail5@email.com;ZZ3
   2015-05-19 09:03:00;mail6@email.com;ZZ4
   2015-05-19 09:04:00;mail7@email.com;ZZ5
   2015-05-19 09:05:00;mail8@email.com;ZZ7
   2015-05-19 09:06:00;mail9@email.com;ZZ6
   ```

* Uma atividade de [reconciliação](../../automating/using/reconciliation.md) para vincular dados de compra a perfis de banco de dados e produtos. Por conseguinte, é necessário definir uma relação entre os dados do ficheiro e a tabela do perfil, bem como a tabela de produtos. Essa configuração é realizada na guia atividade **[!UICONTROL Relations]** :

   * Relação com os **Perfis**: a coluna do **cliente** do arquivo está vinculada ao campo de **email** da dimensão de **Perfis** .
   * Relação com os **produtos**: a coluna de **produto** do arquivo está vinculada ao campo **productCode** da dimensão **Perfis** .
   As colunas são adicionadas aos dados de entrada para fazer referência às chaves estrangeiras das dimensões vinculadas.

   ![](assets/reconciliation_example3.png)

* Uma atividade [Atualizar dados](../../automating/using/update-data.md) permite que você defina os campos do banco de dados a serem atualizados usando os dados importados. Como os dados já foram identificados como pertencendo à dimensão **Transações** na atividade anterior, aqui você pode usar a opção de **[!UICONTROL Directly using the targeting dimension]** identificação.

   Usando a opção que detecta automaticamente os campos a serem atualizados, os links configurados na atividade anterior (para perfis e produtos) são adicionados à lista de **[!UICONTROL Fields to update]**. Você também deve verificar se o campo que corresponde à data da transação foi adicionado corretamente a essa lista.

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)
