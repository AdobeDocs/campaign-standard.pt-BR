---
title: Enriquecendo os dados do perfil com os dados contidos em um arquivo
description: Este exemplo mostra como enriquecer os dados do perfil com os dados de compra contidos em um arquivo.
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---


# Enriquecendo os dados do perfil com os dados contidos em um arquivo {#enriching-profile-data-with-data-contained-in-a-file}

Este exemplo mostra como enriquecer os dados do perfil com os dados de compra contidos em um arquivo.Consideramos aqui que os dados de compra são armazenados em um sistema de terceiros. Cada perfil pode ter várias compras armazenadas no arquivo. O objetivo final do fluxo de trabalho é enviar um e-mail aos perfis públicos alvos que compraram pelo menos dois itens para agradecer sua lealdade.

O fluxo de trabalho é configurado da seguinte maneira:

![](assets/enrichment_example_workflow.png)

* Uma atividade de [Query](../../automating/using/query.md) que público alvo os perfis que receberão a mensagem.
* Uma atividade de arquivo [](../../automating/using/load-file.md) Load que carrega os dados de compra. Por exemplo:

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   Com esse arquivo de exemplo, usaremos o endereço de email para reconciliar os dados com os perfis do banco de dados. Você também pode ativar IDs exclusivas conforme descrito em [esse documento](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

* Uma atividade de [Enriquecimento](../../automating/using/enrichment.md) que cria um link entre os dados de transação carregados do arquivo e os perfis selecionados no **[!UICONTROL Query]**. O link é definido na **[!UICONTROL Advanced relations]** guia da atividade. O link é baseado na transição que vem da **[!UICONTROL Load file]** atividade. Ele usa o campo &quot;email&quot; do recurso de perfil e a coluna &quot;cliente&quot; do arquivo importado como critérios de reconciliação.

   ![](assets/enrichment_example_workflow2.png)

   Depois que o link é criado, dois conjuntos de **[!UICONTROL Additional data]** são adicionados:

   * Uma coleção de duas linhas correspondentes às duas últimas transações de cada perfil. Para essa coleção, o nome do produto, a data da transação e o preço do produto são adicionados como dados adicionais. Uma classificação decrescente é aplicada aos dados. Para criar a coleção, na **[!UICONTROL Additional data]** guia:

      Selecione o link definido anteriormente na **[!UICONTROL Advanced relations]** guia da atividade.

      ![](assets/enrichment_example_workflow3.png)

      Verifique **[!UICONTROL Collection]** e especifique o número de linhas a serem recuperadas (2 neste exemplo). Nessa tela, você pode personalizar o **[!UICONTROL Alias]** e o da coleção **[!UICONTROL Label]** . Esses valores estarão visíveis nas seguintes atividades do fluxo de trabalho ao se referirem a essa coleção.

      ![](assets/enrichment_example_workflow4.png)

      Quanto **[!UICONTROL Data]** manter para a coleção, selecione as colunas que serão usadas no delivery final.

      ![](assets/enrichment_example_workflow6.png)

      Aplique uma classificação decrescente na data da transação para garantir a recuperação das transações mais recentes.

      ![](assets/enrichment_example_workflow7.png)

   * Uma agregação que conta o número total de transações para cada perfil. Essa agregação será usada posteriormente para filtrar perfis que tenham pelo menos duas transações registradas. Para criar a agregação, na **[!UICONTROL Additional data]** guia:

      Selecione o link definido anteriormente na **[!UICONTROL Advanced relations]** guia da atividade.

      ![](assets/enrichment_example_workflow3.png)

      Selecione **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      Como **[!UICONTROL Data]** manter, defina uma agregação **Contar tudo** . Se necessário, especifique um alias personalizado para encontrá-lo mais rapidamente nas atividades a seguir.

      ![](assets/enrichment_example_workflow9.png)

* Uma atividade [de segmentação](../../automating/using/segmentation.md) com apenas um segmento, que recupera perfis do público alvo inicial que têm pelo menos duas transações registradas. Perfis com apenas uma transação são excluídos. Para isso, o query da segmentação é feito na agregação definida anteriormente.

   ![](assets/enrichment_example_workflow5.png)

* Uma atividade de delivery [de e-](../../automating/using/email-delivery.md) mail que usa os dados adicionais definidos no **[!UICONTROL Enrichment]** para recuperar dinamicamente as duas últimas compras feitas pelo perfil. Os dados adicionais podem ser encontrados no nó Dados **adicionais (TargetData)** ao adicionar um campo de personalização.

   ![](assets/enrichment_example_workflow10.png)

**Tópicos relacionados:**

* [Enriquecendo perfis de clientes com dados externos](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)
