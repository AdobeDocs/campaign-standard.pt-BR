---
title: Exportação de logs
description: Os dados de log, sejam eles relacionados a deliveries ou assinaturas, podem ser exportados por meio de um fluxo de trabalho simples.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: d74e2a2c-3ce1-44d6-a058-67b0600360ca
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 14%

---

# Exportação de logs{#exporting-logs}

Os dados de log, sejam eles relacionados a deliveries ou assinaturas, podem ser exportados por meio de um fluxo de trabalho simples. Ele permite analisar os resultados de suas campanhas em seus próprios relatórios ou ferramentas de BI.

>[!CAUTION]
>
>Apenas funcional [administradores](../../administration/using/users-management.md#functional-administrators), com **[!UICONTROL Administration]** funções e acesso a **Todos** as unidades podem acessar logs de envio, logs de mensagem, logs de rastreamento, exclusão ou logs de assinatura. Um usuário não administrador pode direcionar esses logs, mas começar em uma tabela vinculada (perfis, delivery).

Ao usar um **[!UICONTROL Incremental query]** que recupera somente novos logs sempre que o workflow é executado e um **[!UICONTROL Extract file]** para definir as colunas de saída, é possível obter um arquivo com o formato e todos os dados necessários. Em seguida, use um **[!UICONTROL Transfer file]** para recuperar o arquivo final. Cada execução de workflow é planejada por uma **[!UICONTROL Scheduler]**.

A operação de logs de exportação pode ser executada por usuários padrão. Recursos privados como: broadlogs, logs de rastreamento, logs de exclusão, logs de assinatura e logs do histórico de assinaturas em **Perfis** só pode ser gerenciado pelo administrador funcional.

1. Crie um novo workflow conforme detalhado em [esta seção](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Adicione um **[!UICONTROL Scheduler]** e defina-a de acordo com suas necessidades. Abaixo está um exemplo de execução mensal.

   ![](assets/export_logs_scheduler.png)

1. Adicione um **[!UICONTROL Incremental query]** e configure-a para selecionar os logs necessários. Por exemplo, para selecionar todos os broadlogs novos ou atualizados (logs do delivery do perfil):

   * No **[!UICONTROL Properties]** altere o recurso de destino para **Logs do delivery** (broadLogRcp).

      ![](assets/export_logs_query_properties.png)

   * No **[!UICONTROL Target]** , defina uma condição para recuperar todos os logs do delivery que correspondam aos deliveries enviados em 2016 ou depois. Para obter mais informações, consulte [Edição de consultas](../../automating/using/editing-queries.md#creating-queries) seção.

      ![](assets/export_logs_query_target.png)

   * No **[!UICONTROL Processed data]** guia , selecione **[!UICONTROL Use a date field]** e escolha a **lastModified** campo. Nas próximas execuções do workflow, somente os logs que tiverem sido modificados ou criados após a última execução serão recuperados.

      ![](assets/export_logs_query_processeddata.png)

      Após a primeira execução do workflow, você poderá ver nesta guia a última data de execução que será usada para a próxima execução. Ela é atualizada automaticamente todas as vezes que o workflow é executado. Você ainda tem a possibilidade de substituir esse valor, inserindo manualmente um novo para que ele se ajuste às suas necessidades.

1. Adicione um **[!UICONTROL Extract file]** atividade que exportará os dados consultados em um arquivo:

   * No **[!UICONTROL Extraction]** , especifique o nome do arquivo.

      Se você selecionar a variável **[!UICONTROL Add date and time to the file name]** , esse nome será automaticamente preenchido com a data da exportação para garantir que todos os arquivos extraídos sejam exclusivos. Selecione as colunas que deseja exportar no arquivo. Você pode selecionar aqui os dados provenientes de recursos relacionados, como informações de delivery ou perfil.

      >[!NOTE]
      >
      >Para exportar um identificador exclusivo para cada log, selecione o **[!UICONTROL Delivery log ID]** elemento.

      Para organizar o arquivo final, você pode aplicar uma classificação. Por exemplo, na data de log, como mostrado no exemplo abaixo.

      ![](assets/export_logs_extractfile_extraction.png)

   * No **[!UICONTROL File structure]** , defina o formato do arquivo de saída para atender às suas necessidades.

      Marque a opção **[!UICONTROL Export labels instead of internal values of enumerations]** caso exporte valores de uma lista discriminada. Essa opção permite recuperar rótulos mais curtos, que são fáceis de entender, em vez de IDs.

1. Adicione um **[!UICONTROL Transfer file]** e configure-a para transferir o arquivo recém-criado do servidor Adobe Campaign para outro local onde você pode acessá-lo, como um servidor SFTP.

   * No **[!UICONTROL General]** guia , selecione **[!UICONTROL File upload]** como o objetivo é enviar o arquivo do Adobe Campaign para outro servidor.
   * No **[!UICONTROL Protocol]** , especifique os parâmetros de transferência e selecione o [conta externa](../../administration/using/external-accounts.md#creating-an-external-account) para usar.

1. Adicione um **[!UICONTROL End]** para garantir que termine e salve o fluxo de trabalho corretamente.

   ![](assets/export_logs_example_workflow.png)

Agora é possível executar o workflow e recuperar o arquivo de saída no servidor externo.

**Tópicos relacionados:**

[Fluxos de trabalho](../../automating/using/get-started-workflows.md)
