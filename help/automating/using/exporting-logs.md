---
solution: Campaign Standard
product: campaign
title: Exportar logs
description: Os dados de registro, sejam eles relacionados a delivery ou subscrições, podem ser exportados por meio de um fluxo de trabalho simples.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 14%

---


# Exportar logs{#exporting-logs}

Os dados de registro, sejam eles relacionados a delivery ou subscrições, podem ser exportados por meio de um fluxo de trabalho simples. Ele permite que você analise os resultados de suas campanhas em sua própria ferramenta relatórios ou BI.

>[!CAUTION]
>
>Somente os [administradores](../../administration/using/users-management.md#functional-administrators) funcionais, com a função **[!UICONTROL Administration]** e o acesso a **Todas** unidades podem acessar registros de envio, registros de mensagens, logs de rastreamento, exclusão ou registros de subscrições. Um usuário não administrativo pode público alvo desses registros, mas iniciando em uma tabela vinculada (perfis, delivery).

Ao usar um **[!UICONTROL Incremental query]** que recupera somente novos logs toda vez que o fluxo de trabalho é executado e uma simples atividade **[!UICONTROL Extract file]** para definir as colunas de saída, você pode obter um arquivo com o formato e todos os dados necessários. Em seguida, use uma atividade **[!UICONTROL Transfer file]** para recuperar o arquivo final. Cada execução de fluxo de trabalho é planejada por um **[!UICONTROL Scheduler]**.

A operação de logs de exportação pode ser realizada por usuários padrão. Recursos privados como: os registros de subscrições, logs de rastreamento, registros de exclusão e registros de histórico de subscrições em **Perfis** só podem ser gerenciados pelo administrador funcional.

1. Crie um novo fluxo de trabalho conforme detalhado em [esta seção](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Adicione uma atividade **[!UICONTROL Scheduler]** e defina-a de acordo com suas necessidades. Abaixo está um exemplo de uma execução mensal.

   ![](assets/export_logs_scheduler.png)

1. Adicione uma atividade **[!UICONTROL Incremental query]** e configure-a para que selecione os registros necessários. Por exemplo, para selecionar todos os blogs novos ou atualizados (logs do delivery de perfis):

   * Na guia **[!UICONTROL Properties]**, altere o recurso de público alvo para **Logs do delivery** (wideLogRcp).

      ![](assets/export_logs_query_properties.png)

   * Na guia **[!UICONTROL Target]**, defina uma condição para recuperar todos os logs do delivery que correspondem aos delivery enviados em 2016 ou depois. Para obter mais informações, consulte a seção [Edição de query](../../automating/using/editing-queries.md#creating-queries).

      ![](assets/export_logs_query_target.png)

   * Na guia **[!UICONTROL Processed data]**, selecione **[!UICONTROL Use a date field]** e escolha o campo **lastModified**. Nas próximas execuções do fluxo de trabalho, somente os logs que serão modificados ou criados após a última execução serão recuperados.

      ![](assets/export_logs_query_processeddata.png)

      Após a primeira execução do workflow, você poderá ver nesta guia a última data de execução que será usada para a próxima execução. Ela é atualizada automaticamente todas as vezes que o workflow é executado. Você ainda tem a possibilidade de substituir esse valor, inserindo manualmente um novo para que ele se ajuste às suas necessidades.

1. Adicione uma atividade **[!UICONTROL Extract file]** que exportará os dados consultados em um arquivo:

   * Na guia **[!UICONTROL Extraction]**, especifique o nome do arquivo.

      Se você selecionar a opção **[!UICONTROL Add date and time to the file name]**, esse nome será automaticamente preenchido com a data da exportação para garantir que todos os arquivos extraídos sejam exclusivos. Selecione as colunas que deseja exportar no arquivo. É possível selecionar aqui os dados provenientes de recursos relacionados, como informações sobre delivery ou perfis.

      >[!NOTE]
      >
      >Para exportar um identificador exclusivo para cada log, selecione o elemento **[!UICONTROL Delivery log ID]**.

      Para organizar o arquivo final, é possível aplicar uma classificação. Por exemplo, na data de registro, como mostrado no exemplo abaixo.

      ![](assets/export_logs_extractfile_extraction.png)

   * Na guia **[!UICONTROL File structure]**, defina o formato do arquivo de saída de acordo com suas necessidades.

      Marque a opção **[!UICONTROL Export labels instead of internal values of enumerations]** caso exporte valores de uma lista discriminada. Essa opção permite recuperar rótulos mais curtos, que são fáceis de entender, em vez de IDs.

1. Adicione uma atividade **[!UICONTROL Transfer file]** e configure-a para transferir o arquivo recém-criado do servidor Adobe Campaign para outro local onde você possa acessá-la, como um servidor SFTP.

   * Na guia **[!UICONTROL General]**, selecione **[!UICONTROL File upload]**, pois o objetivo é enviar o arquivo da Adobe Campaign para outro servidor.
   * Na guia **[!UICONTROL Protocol]**, especifique os parâmetros de transferência e selecione a [conta externa](../../administration/using/external-accounts.md#creating-an-external-account) a ser usada.

1. Adicione uma atividade **[!UICONTROL End]** para garantir que ela termine e salve seu fluxo de trabalho corretamente.

   ![](assets/export_logs_example_workflow.png)

Agora você pode executar o fluxo de trabalho e recuperar o arquivo de saída no servidor externo.

**Tópicos relacionados:**

[Fluxos de trabalho](../../automating/using/get-started-workflows.md)
