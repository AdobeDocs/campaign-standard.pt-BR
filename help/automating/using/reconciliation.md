---
solution: Campaign Standard
product: campaign
title: Reconciliação
description: A atividade Reconciliation permite vincular dados não identificados aos recursos existentes.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Fluxos de trabalho
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 95%

---


# Reconciliação{#reconciliation}

## Descrição {#description}

![](assets/reconciliation.png)

A atividade **[!UICONTROL Reconciliation]** permite vincular dados não identificados aos recursos existentes.

## Contexto de uso {#context-of-use}

A atividade **[!UICONTROL Reconciliation]** é basicamente utilizada para fins de gestão de dados e inclui dois casos de uso diferentes:

* Adição de relações: uma guia **[!UICONTROL Links]** permite adicionar links entre os dados de entrada e várias outras dimensões do banco de dados do Adobe Campaign.

   Por exemplo, um arquivo contendo dados de compra também pode ter informações para identificar os produtos comprados, bem como o comprador. Portanto, duas dimensões adicionais (para além da dimensão **Compras**) estão relacionadas aos dados do arquivo: **Produtos** e **Perfis**. É necessário criar relações entre elas e a dimensão **Purchases** (consulte o exemplo a seguir).

   Para definir uma relação, uma coluna é adicionada aos dados de entrada para fazer referência à chave estrangeira da dimensão vinculada.

   >[!NOTE]
   >
   >Essa operação considera que os dados das dimensões vinculadas já estão no banco de dados. Por exemplo, se você importar um arquivo de compras que mostre qual produto foi comprado, em que momento, por qual cliente, etc., o produto e o cliente já deverão existir no banco de dados.

* Identificação de dados: uma guia **[!UICONTROL Identification]** permite que você simplesmente vincule os dados de entrada às colunas de uma dimensão existente no banco de dados do Adobe Campaign. Após a atividade, os dados são identificados como pertencentes à dimensão definida.

   Por exemplo, você poderá salvar um público-alvo, atualizar o banco de dados etc.

Por exemplo, a atividade **[!UICONTROL Reconciliation]** pode ser colocada após uma atividade de carregamento de dados com o objetivo de importar dados não padrão para o banco de dados.

**Tópicos relacionados:**

* [Caso de uso: Reconciliação de dados usando relações](../../automating/using/reconciliation-using-relations.md)
* [Caso de uso: Atualização de dados usando reconciliação](../../automating/using/data-update-reconciliation.md)
* [Caso de uso: Reconciliar um público do tipo Arquivo com o banco de dados](../../automating/using/reconcile-file-audience-with-database.md)

## Configuração {#configuration}

1. Arraste e solte uma atividade **[!UICONTROL Reconciliation]** no fluxo de trabalho, seguindo uma transição que contém uma população cujo targeting dimension não é diretamente proveniente do Adobe Campaign. Para saber mais, consulte [Targeting dimensions e recursos](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Se quiser definir links entre os dados de entrada e outras dimensões do banco de dados, acesse a guia **[!UICONTROL Links]**.

   Adicione quantas relações forem necessárias. Para cada relação, primeiro selecione a dimensão vinculada e, nos detalhes do link, especifique os campos correspondentes.

1. Se quiser simplesmente identificar os dados de entrada, acesse a guia **[!UICONTROL Identification]** e marque a caixa **[!UICONTROL Identify the document from the working data]**.

   Selecione o targeting dimension para o qual deseja reconciliar os dados de entrada.

   Adicione critérios de reconciliação para vincular um registro de transição de entrada a um registro de targeting dimension selecionado. Se vários critérios forem especificados, todos eles deverão ser verificados para que o link funcione entre todos os dados.

   Escolha o modo **[!UICONTROL Processing unidentified source lines]**:

   * **[!UICONTROL Ignore them]**: somente os dados identificáveis são mantidos na transição de saída da atividade.
   * **[!UICONTROL Keep in the outbound population]**: todos os dados da transição de entrada são mantidos na transição de saída da atividade.

1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.
