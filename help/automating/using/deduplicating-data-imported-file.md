---
title: Desduplicando os dados de um arquivo importado
description: Este exemplo mostra como desduplicar dados de um arquivo importado antes de carregar os dados no banco de dados.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---


# Desduplicando os dados de um arquivo importado {#deduplicating-the-data-from-an-imported-file}

Este exemplo mostra como desduplicar dados de um arquivo importado antes de carregar os dados no banco de dados. Esse procedimento melhora a qualidade dos dados carregados no banco de dados.

O fluxo de trabalho é composto de:

![](assets/deduplication_example2_workflow.png)

* Um arquivo que contém uma lista de perfis é importado usando uma atividade de arquivo [](../../automating/using/load-file.md) Load. Neste exemplo, o arquivo importado está no formato .csv e contém 10 perfis:

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

   Esse arquivo também pode ser usado como um arquivo de amostra para detectar e definir o formato das colunas. Na **[!UICONTROL Column definition]** guia, verifique se cada coluna do arquivo importado está configurada corretamente.

   ![](assets/deduplication_example2_fileloading.png)

* Uma atividade [Desduplicação-duplicada](../../automating/using/deduplication.md) . O Desduplicação-duplicado é realizado diretamente após a importação do arquivo e antes da inserção dos dados no banco de dados. Deve, por conseguinte, basear-se no **[!UICONTROL Temporary resource]** resultado da **[!UICONTROL Load file]** atividade.

   Neste exemplo, queremos manter uma única entrada por endereço de email exclusivo contido no arquivo. A identificação do Duplicado é, portanto, realizada na coluna de **email** do recurso temporário. No entanto, dois endereços de email são exibidos duas vezes no arquivo. Por conseguinte, serão consideradas duplicados duas linhas.

   ![](assets/deduplication_example2_dedup.png)

* Uma atividade de dados [](../../automating/using/update-data.md) Update permite inserir os dados mantidos do processo desduplicação-duplicado no banco de dados. Somente quando os dados são atualizados é que os dados importados são identificados como pertencendo à dimensão do perfil.

   Aqui, gostaríamos de ver **[!UICONTROL Insert only]** os perfis que ainda não existem no banco de dados. Vamos fazer isso usando a coluna de e-mail do arquivo e o campo de e-mail da dimensão do **Perfil** como a chave de reconciliação.

   ![](assets/deduplication_example2_writer1.png)

   Especifique os mapeamentos entre as colunas do arquivo a partir das quais deseja inserir os dados e os campos do banco de dados na **[!UICONTROL Fields to update]** guia.

   ![](assets/deduplication_example2_writer2.png)

Em seguida, start o fluxo de trabalho. Os registros salvos do processo desduplicação-duplicado são adicionados aos perfis no banco de dados.
