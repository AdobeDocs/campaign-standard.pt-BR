---
title: Exportar logs
description: Os dados de registro, sejam eles relacionados a delivery ou subscrições, podem ser exportados por meio de um fluxo de trabalho simples.
page-status-flag: never-activated
uuid: 954e919c-0a33-47c3-9a3c-63c7a2a4edc4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: ca8a95d8-523f-4085-a2fc-e1d8262cfbae
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Exportar logs{#exporting-logs}

Os dados de registro, sejam eles relacionados a delivery ou subscrições, podem ser exportados por meio de um fluxo de trabalho simples. Ele permite que você analise os resultados de suas campanhas em sua própria ferramenta relatórios ou BI.

Ao usar uma atividade que recupera somente novos logs toda vez que o fluxo de trabalho é executado e uma simples **[!UICONTROL Incremental query]** **[!UICONTROL Extract file]** para definir as colunas de saída, você pode obter um arquivo com o formato e todos os dados necessários. Em seguida, use uma **[!UICONTROL Transfer file]** atividade para recuperar o arquivo final. Cada execução de fluxo de trabalho é planejada por um **[!UICONTROL Scheduler]**.

A operação de logs de exportação pode ser realizada por usuários padrão. Recursos privados como: os registros de subscrições, logs de rastreamento, registros de exclusão e registros de histórico de subscrições em **Perfis** só podem ser gerenciados pelo administrador funcional.

1. Crie um novo fluxo de trabalho conforme detalhado [nesta seção](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Add a **[!UICONTROL Scheduler]** activity and set it according to your needs. Abaixo está um exemplo de uma execução mensal.

   ![](assets/export_logs_scheduler.png)

1. Adicione uma **[!UICONTROL Incremental query]** atividade e configure-a para que selecione os registros necessários. Por exemplo, para selecionar todos os blogs novos ou atualizados (logs do delivery de perfis):

   * Na **[!UICONTROL Properties]** guia, altere o recurso público alvo para **Logs do delivery** (wideLogRcp).

      ![](assets/export_logs_query_properties.png)

   * Na **[!UICONTROL Target]** guia, defina uma condição para recuperar todos os logs do delivery que correspondem aos delivery enviados em 2016 ou depois. For more information, refer to the [Editing queries](../../automating/using/editing-queries.md#creating-queries) section.

      ![](assets/export_logs_query_target.png)

   * Na **[!UICONTROL Processed data]** guia, selecione **[!UICONTROL Use a date field]** e escolha o campo **lastModifid** . Nas próximas execuções do fluxo de trabalho, somente os logs que serão modificados ou criados após a última execução serão recuperados.

      ![](assets/export_logs_query_processeddata.png)

      Após a primeira execução do fluxo de trabalho, você pode ver nesta guia a última data de execução que será usada para a próxima execução. Ele é atualizado automaticamente toda vez que o fluxo de trabalho é executado. Você ainda tem a possibilidade de substituir esse valor inserindo manualmente um novo para que ele se ajuste às suas necessidades.

1. Adicione uma **[!UICONTROL Extract file]** atividade que exportará os dados consultados em um arquivo:

   * Na **[!UICONTROL Extraction]** guia, especifique o nome do arquivo.

      Se você selecionar a **[!UICONTROL Add date and time to the file name]** opção, esse nome será automaticamente preenchido com a data da exportação para garantir que todos os arquivos extraídos sejam exclusivos. Selecione as colunas que deseja exportar no arquivo. É possível selecionar aqui os dados provenientes de recursos relacionados, como informações sobre delivery ou perfis.

      >[!NOTE]
      >
      >Para exportar um identificador exclusivo para cada log, selecione o **[!UICONTROL Delivery log ID]** elemento.

      Para organizar o arquivo final, é possível aplicar uma classificação. Por exemplo, na data de registro, como mostrado no exemplo abaixo.

      ![](assets/export_logs_extractfile_extraction.png)

   * Na **[!UICONTROL File structure]** guia, defina o formato do arquivo de saída para corresponder às suas necessidades.

      Marque a **[!UICONTROL Export labels instead of internal values of enumerations]** opção caso você exporte valores de lista discriminada. Essa opção permite recuperar rótulos mais curtos, fáceis de entender em vez de IDs.

1. Adicione uma **[!UICONTROL Transfer file]** atividade e configure-a para transferir o arquivo recém-criado do servidor Adobe Campaign para outro local onde você possa acessá-la, como um servidor SFTP.

   * Na **[!UICONTROL General]** guia, selecione **[!UICONTROL File upload]** a finalidade de enviar o arquivo do Adobe Campaign para outro servidor.
   * Na **[!UICONTROL Protocol]** guia, especifique os parâmetros de transferência e selecione a [conta externa](../../administration/using/external-accounts.md#creating-an-external-account) a ser usada.

1. Adicione uma **[!UICONTROL End]** atividade para garantir que ela termine e salve seu fluxo de trabalho corretamente.

   ![](assets/export_logs_example_workflow.png)

Agora você pode executar o fluxo de trabalho e recuperar o arquivo de saída no servidor externo.

**Tópicos relacionados:**

[Workflows](../../automating/using/get-started-workflows.md)
