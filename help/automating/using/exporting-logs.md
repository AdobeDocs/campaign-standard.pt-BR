---
title: Exportação de logs
seo-title: Exportação de logs
description: Exportação de logs
seo-description: Os dados de log, relacionados a entregas ou assinaturas, podem ser exportados por meio de um fluxo de trabalho simples.
page-status-flag: nunca ativado
uuid: 954 e 919 c -0 a 33-47 c 3-9 a 3 c -63 c 7 a 2 a 4 edc 4
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: importar e exportar dados
discoiquuid: ca 8 a 95 d 8-523 f -4085-a 2 fc-e 1 d 8262 cfbae
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Exporting logs{#exporting-logs}

Os dados de log, relacionados a entregas ou assinaturas, podem ser exportados por meio de um fluxo de trabalho simples. Isso permite analisar os resultados de suas campanhas em seu próprio relatório ou ferramenta BI.

By using an **[!UICONTROL Incremental query]** that only retrieves new logs every time the workflow is executed and a simple **[!UICONTROL Extract file]** activity to define the output columns, you can get a file with the format and all the data you need. Then use a **[!UICONTROL Transfer file]** activity to retrieve the final file. Each workflow execution is planned by a **[!UICONTROL Scheduler]**.

A operação de logs de exportação pode ser executada por usuários padrão. Private resources such as: broadlogs, tracking logs, exclusion logs subscription logs and subscription history logs on **Profiles** can only be managed by functional administrator.

1. Create a new workflow as detailed in [this section](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Add a **[!UICONTROL Scheduler]** activity and set it according to your needs. Abaixo está um exemplo de execução mensal.

   ![](assets/export_logs_scheduler.png)

1. Add an **[!UICONTROL Incremental query]** activity and configure it so that it selects the logs you need. Por exemplo, para selecionar todos os logs broadnovos ou atualizados (logs de entrega de perfil):

   * In the **[!UICONTROL Properties]** tab, change the target resource to **Delivery logs** (broadLogRcp).

      ![](assets/export_logs_query_properties.png)

   * In the **[!UICONTROL Target]** tab, set a condition to retrieve all delivery logs that correspond to deliveries sent in 2016 or after. For more information, refer to the [Editing queries](../../automating/using/editing-queries.md#creating-queries) section.

      ![](assets/export_logs_query_target.png)

   * In the **[!UICONTROL Processed data]** tab, select **[!UICONTROL Use a date field]** and choose the **lastModified** field. Nas próximas execuções do fluxo de trabalho, apenas os logs que terão sido modificados ou criados após a última execução serão recuperados.

      ![](assets/export_logs_query_processeddata.png)

      Após a primeira execução do fluxo de trabalho, você pode ver nesta guia a última data de execução que será usada para a próxima execução. É automaticamente atualizado toda vez que o fluxo de trabalho é executado. Você ainda tem a possibilidade de substituir esse valor inserindo manualmente um novo para que ele se ajuste às suas necessidades.

1. Add an **[!UICONTROL Extract file]** activity that will export the queried data in a file:

   * In the **[!UICONTROL Extraction]** tab, specify the name of the file. Esse nome será automaticamente concluído com a data da exportação para garantir que todos os arquivos extraídos sejam exclusivos.

      Selecione as colunas que deseja exportar no arquivo. Você pode selecionar aqui dados provenientes de recursos relacionados, como informações de entrega ou perfil. Para organizar o arquivo final, é possível aplicar uma classificação. Por exemplo, na data de registro, como mostrado no exemplo abaixo.

      ![](assets/export_logs_extractfile_extraction.png)

      >[!NOTE]
      >
      >Não é possível exportar identificadores exclusivos (chaves primárias) dos recursos de log.

   * In the **[!UICONTROL File structure]** tab, define the format of the output file to match your needs.

      Check the **[!UICONTROL Export labels instead of internal values of enumerations]** option in case you export enumeration values. Essa opção permite recuperar rótulos mais curtos que são fáceis de entender em vez de IDs.

1. Add a **[!UICONTROL Transfer file]** activity and configure it to transfer the newly created file from the Adobe Campaign server to another location where you can access it, such as a SFTP server.

   * In the **[!UICONTROL General]** tab, select **[!UICONTROL File upload]** as the purpose is to send the file from Adobe Campaign to another server.
   * In the **[!UICONTROL Protocol]** tab, specify the transfer parameters and select the [external account](../../administration/using/external-accounts.md#creating-an-external-account) to use.

1. Add an **[!UICONTROL End]** activity to make sure it properly ends and save your workflow.

   ![](assets/export_logs_example_workflow.png)

Agora é possível executar o fluxo de trabalho e recuperar o arquivo de saída no servidor externo.

**Tópico relacionado:**

[Fluxos de trabalho](../../automating/using/discovering-workflows.md)
