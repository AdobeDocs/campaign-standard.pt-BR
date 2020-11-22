---
solution: Campaign Standard
product: campaign
title: Desduplicação de dados a partir de um arquivo importado
description: Este exemplo mostra como desduplicar dados de um arquivo importado antes de carregá-los no banco de dados.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 89%

---


# Desduplicação de dados a partir de um arquivo importado {#deduplicating-the-data-from-an-imported-file}

Este exemplo mostra como desduplicar dados de um arquivo importado antes de carregá-los no banco de dados. Esse procedimento melhora a qualidade dos dados carregados no banco de dados.

Este fluxo de trabalho é composto por:

![](assets/deduplication_example2_workflow.png)

* A file that contains a list of profiles is imported using a [Load file](../../automating/using/load-file.md) activity. Neste exemplo, o arquivo importado está no formato .csv e contém 10 perfis:

   ```
   lastname;firstname;dateofbirth;email
   Smith;Hayden;23/05/1989;hayden.smith@example.com
   Mars;Daniel;17/11/1987;dannymars@example.com
   Smith;Clara;08/02/1989;hayden.smith@example.com
   Durance;Allison;15/12/1978;allison.durance@example.com
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com
   Binder;Tom;19/01/1982;tombinder@example.com
   Binder;Tommy;19/01/1915;tombinder@example.com
   Connor;Jade;10/10/1979;connor.jade@example.com
   Mack;Clarke;02/03/1985;clarke.mack@example.com
   Ross;Timothy;04/07/1986;timross@example.com
   ```

   Esse arquivo também pode ser usado como um arquivo de amostra para detectar e definir o formato das colunas. Na guia **[!UICONTROL Column definition]**, verifique se cada coluna do arquivo importado está configurada corretamente.

   ![](assets/deduplication_example2_fileloading.png)

* Uma atividade [Desduplicação-duplicada](../../automating/using/deduplication.md) . A desduplicação é feita diretamente após a importação do arquivo e antes da inserção dos dados no banco de dados. Por conseguinte, ela deve se basear no **[!UICONTROL Temporary resource]** da atividade de **[!UICONTROL Load file]**.

   Neste exemplo, queremos manter uma única entrada por endereço de email exclusivo contido no arquivo. A identificação de duplicatas é, portanto, feita na coluna de **email** do recurso temporário. Com isso, dois endereços de email são exibidos duas vezes no arquivo. Assim sendo, duas linhas são consideradas duplicatas.

   ![](assets/deduplication_example2_dedup.png)

* An [Update data](../../automating/using/update-data.md) activity allows you to insert the data kept from the deduplication process into the database. Somente quando os dados são atualizados é que os dados importados são identificados como pertencendo à dimensão do perfil.

   Aqui, gostaríamos de **[!UICONTROL Insert only]** os perfis que ainda não existem no banco de dados. Vamos fazer isso usando a coluna de email do arquivo e o campo de email da dimensão do **Perfil** como a chave de reconciliação.

   ![](assets/deduplication_example2_writer1.png)

   Especifique os mapeamentos entre as colunas do arquivo a partir das quais deseja inserir os dados e os campos do banco de dados da guia **[!UICONTROL Fields to update]**.

   ![](assets/deduplication_example2_writer2.png)

Em seguida, inicie o fluxo de trabalho. Os registros salvos do processo de desduplicação são adicionados aos perfis no banco de dados.
