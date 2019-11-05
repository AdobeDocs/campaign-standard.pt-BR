---
title: Reconciliação
description: A atividade Reconciliação permite vincular dados não identificados aos recursos existentes.
page-status-flag: nunca ativado
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: atividades de gestão de dados
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliação,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Reconciliação{#reconciliation}

## Descrição {#description}

![](assets/reconciliation.png)

A **[!UICONTROL Reconciliation]** atividade permite vincular dados não identificados aos recursos existentes.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Reconciliation]** atividade é essencialmente utilizada para fins de Gerenciamento de dados e implica dois casos de uso diferentes:

* Adicionar relações: uma **[!UICONTROL Links]** guia permite adicionar links entre os dados de entrada e várias outras dimensões do banco de dados do Adobe Campaign.

   Por exemplo, um arquivo que contém dados de compra também pode conter informações para identificar os produtos comprados e o comprador. Por conseguinte, os dados do ficheiro dizem respeito a duas dimensões adicionais (para além das **Compras**): as dimensões **Produtos** e **Perfis** . As relações precisam ser criadas entre essas e a dimensão **Compras** (consulte o exemplo a seguir).

   Ao definir uma relação, uma coluna é adicionada aos dados de entrada para fazer referência à chave estrangeira da dimensão vinculada.

   >[!NOTE]
   >
   >Esta operação implica que os dados das dimensões vinculadas já estejam no banco de dados. Por exemplo, se você importar um arquivo de compras mostrando qual produto foi comprado, em que momento, por qual cliente, etc., o produto e o cliente já devem existir no banco de dados.

* Identificação de dados: uma **[!UICONTROL Identification]** guia permite que você simplesmente vincule dados de entrada a colunas de uma dimensão existente no banco de dados do Adobe Campaign. Após a atividade, os dados são identificados como pertencendo à dimensão definida.

   Por exemplo, você pode executar um público salvo, uma atualização do banco de dados etc.

Por exemplo, a **[!UICONTROL Reconciliation]** atividade pode ser colocada após uma atividade de dados de carga com o objetivo de importar dados não padrão para o banco de dados.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Reconciliation]** atividade em seu fluxo de trabalho, após uma transição que contém uma população cuja dimensão de definição de metas não é diretamente proveniente do Adobe Campaign. Para obter mais informações, consulte Dimensões e recursos [de](../../automating/using/query.md#targeting-dimensions-and-resources)definição de metas.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Se você deseja definir links entre os dados de entrada e outras dimensões do banco de dados, vá para a **[!UICONTROL Links]** guia.

   Adicione quantas relações forem necessárias. Para cada relação, primeiro selecione a dimensão vinculada e, em seguida, nos detalhes do link, especifique os campos correspondentes.

1. Se você deseja identificar simplesmente os dados de entrada, vá para a **[!UICONTROL Identification]** guia e marque a **[!UICONTROL Identify the document from the working data]** caixa.

   Selecione a dimensão de definição de metas para a qual deseja reconciliar os dados de entrada.

   Adicione critérios de reconciliação para vincular um registro de transição de entrada a um registro de dimensão de definição de metas selecionado. Se vários critérios forem especificados, todos eles devem ser verificados para que o link entre todos os dados funcione.

   Escolha o **[!UICONTROL Processing unidentified source lines]** modo:

   * **[!UICONTROL Ignore them]**: somente os dados identificáveis são mantidos na transição de saída da atividade.
   * **[!UICONTROL Keep in the outbound population]**: todos os dados da transição de entrada são mantidos na transição de saída da atividade.

1. Confirme a configuração da atividade e salve o fluxo de trabalho.

## Exemplo 1: Definição da relação {#example-1--relation-definition}

O exemplo a seguir demonstra um fluxo de trabalho que atualiza o banco de dados usando os dados de compra em um arquivo. Os dados de compra contêm dados que fazem referência a elementos de outras dimensões, como emails do cliente e códigos de produto.

>[!NOTE]
>
>Os recursos **Transações** e **Produtos** usados neste exemplo não existem no banco de dados do Adobe Campaign por padrão. Por conseguinte, foram previamente criados com a função de recursos [](../../developing/using/data-model-concepts.md) personalizados. Os perfis que correspondem aos endereços de email no arquivo importado, bem como os produtos, foram carregados no banco de dados antecipadamente.

O fluxo de trabalho é composto das seguintes atividades:

![](assets/reconciliation_example1.png)

* Uma **[!UICONTROL Load file]** atividade que carrega e detecta os dados do arquivo a ser importado. O arquivo importado contém os seguintes dados:

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

* Uma **[!UICONTROL Reconciliation]** atividade para vincular dados de compra a perfis de banco de dados e produtos. Por conseguinte, é necessário definir uma relação entre os dados do ficheiro e a tabela de perfis, bem como a tabela de produtos. Essa configuração é realizada na **[!UICONTROL Relations]** guia da atividade:

   * Relação com os **Perfis**: a coluna do **cliente** do arquivo está vinculada ao campo de **email** da dimensão **Perfis** .
   * Relação com os **produtos**: a coluna de **produto** do arquivo está vinculada ao campo **productCode** da dimensão **Perfis** .
   As colunas são adicionadas aos dados de entrada para fazer referência às chaves estrangeiras das dimensões vinculadas.

   ![](assets/reconciliation_example3.png)

* Uma **[!UICONTROL Update data]** atividade permite que você defina os campos do banco de dados a serem atualizados usando os dados importados. Como os dados já foram identificados como pertencendo à dimensão **Transações** na atividade anterior, aqui você pode usar a opção de **[!UICONTROL Directly using the targeting dimension]** identificação.

   Usando a opção que detecta automaticamente os campos a serem atualizados, os links configurados na atividade anterior (para perfis e produtos) são adicionados à lista de **[!UICONTROL Fields to update]**. Você também deve verificar se o campo que corresponde à data da transação foi adicionado corretamente a essa lista.

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)

## Exemplo 2: Identificação {#example-2--identification}

O exemplo a seguir demonstra um fluxo de trabalho que cria um público-alvo de perfis diretamente de um arquivo importado que contém novos clientes. É constituído pelas seguintes atividades:

![](assets/identification_example2.png)

* Uma **[!UICONTROL Load file]** atividade que carrega e detecta os dados do arquivo a ser importado. O arquivo importado contém os seguintes dados:

   ```
   lastname;firstname;email;dateofbirth
   jackman;megan;megan.jackman@testmail.com;07/08/1975
   phillips;edward;phillips@testmail.com;09/03/1986
   weaver;justin;justin_w@testmail.com;11/15/1990
   martin;babeth;babeth_martin@testmail.net;11/25/1964
   reese;richard;rreese@testmail.com;02/08/1987
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
   grimes;daryl;daryl_890@testmail.com;12/06/1979
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
   ```

* Uma **[!UICONTROL Reconciliation]** atividade que vincula cada coluna do arquivo carregado a uma coluna de dimensão de perfil. Os registros de arquivos que não podem ser identificados (dados ausentes, tipo de dados incompatível etc.) são ignorados para preservar a integridade dos dados finais do público-alvo.

   ![](assets/identification_example1.png)

* Uma **[!UICONTROL Save audience]** atividade que salva o público-alvo dos perfis.

   ![](assets/identification_example3.png)

