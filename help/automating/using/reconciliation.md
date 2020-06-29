---
title: Reconciliação
description: A atividade Reconciliação permite vincular dados não identificados aos recursos existentes.
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
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 1%

---


# Reconciliação{#reconciliation}

## Descrição {#description}

![](assets/reconciliation.png)

A **[!UICONTROL Reconciliation]** atividade permite que você vincule dados não identificados aos recursos existentes.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Reconciliation]** atividade é essencialmente utilizada para fins de Gestão de dados e implica dois casos de utilização diferentes:

* Adicionar relações: uma **[!UICONTROL Links]** guia permite que você adicione links entre os dados de entrada e várias outras dimensões do banco de dados de Adobe Campaign.

   Por exemplo, um arquivo que contém dados de compra também pode conter informações para identificar os produtos comprados, bem como o comprador. Por conseguinte, os dados do ficheiro dizem respeito a duas dimensões adicionais (para além das **Compras**): as dimensões **Produtos** e **Perfis** . As relações precisam ser criadas entre essas e a dimensão **Compras** (consulte o exemplo a seguir).

   Ao definir uma relação, uma coluna é adicionada aos dados de entrada para fazer referência à chave estrangeira da dimensão vinculada.

   >[!NOTE]
   >
   >Esta operação implica que os dados das dimensões vinculadas já estejam no banco de dados. Por exemplo, se você importar um arquivo de compras mostrando qual produto foi comprado, em que momento, por qual cliente, etc., o produto e o cliente já devem existir no banco de dados.

* Identificação de dados: uma **[!UICONTROL Identification]** guia permite que você simplesmente vincule dados de entrada a colunas de uma dimensão existente no banco de dados do Adobe Campaign. Após a atividade, os dados são identificados como pertencendo à dimensão definida.

   Por exemplo, você pode executar uma audiência de salvamento, uma atualização do banco de dados etc.

Por exemplo, a **[!UICONTROL Reconciliation]** atividade pode ser colocada após uma atividade de dados de carga com o objetivo de importar dados não padrão para o banco de dados.

**Tópicos relacionados:**

* [Caso de uso: Reconciliação de dados usando relações](../../automating/using/reconciliation-using-relations.md)
* [Caso de uso: Atualização de dados usando reconciliação](../../automating/using/data-update-reconciliation.md)
* [Caso de uso: Reconciliar uma audiência de arquivo com o banco de dados](../../automating/using/reconcile-file-audience-with-database.md)

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Reconciliation]** atividade no seu fluxo de trabalho, seguindo uma transição que contém uma população cujo targeting dimension não provém diretamente do Adobe Campaign. Para obter mais informações, consulte [Targeting dimension e recursos](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Se você deseja definir links entre os dados de entrada e outras dimensões do banco de dados, vá para a **[!UICONTROL Links]** guia.

   Adicione quantas relações forem necessárias. Para cada relação, primeiro selecione a dimensão vinculada e, em seguida, nos detalhes do link, especifique os campos correspondentes.

1. Se você deseja identificar simplesmente os dados de entrada, vá para a **[!UICONTROL Identification]** guia e marque a **[!UICONTROL Identify the document from the working data]** caixa.

   Selecione o targeting dimension para o qual deseja reconciliar os dados de entrada.

   Adicione critérios de reconciliação para vincular um registro de transição de entrada a um registro de targeting dimension selecionado. Se vários critérios forem especificados, todos eles devem ser verificados para que o link entre todos os dados funcione.

   Escolha o **[!UICONTROL Processing unidentified source lines]** modo:

   * **[!UICONTROL Ignore them]**: somente os dados identificáveis são mantidos na transição de saída da atividade.
   * **[!UICONTROL Keep in the outbound population]**: todos os dados da transição de entrada são mantidos na transição de saída da atividade.

1. Confirme a configuração da atividade e salve o fluxo de trabalho.
