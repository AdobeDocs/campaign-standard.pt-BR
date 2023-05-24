---
title: Exportação de logs
description: Os dados de log, estejam eles relacionados a deliveries ou subscrições, podem ser exportados por meio de um simples workflow.
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

Os dados de log, estejam eles relacionados a deliveries ou subscrições, podem ser exportados por meio de um simples workflow. Ela permite analisar os resultados de suas campanhas em seus próprios relatórios ou na ferramenta de BI.

>[!CAUTION]
>
>Somente funcional [administradores](../../administration/using/users-management.md#functional-administrators), com **[!UICONTROL Administration]** função e acesso a **Todos** as unidades podem acessar logs de envio, logs de mensagem, logs de rastreamento, logs de exclusão ou de subscrição. Um usuário não administrador pode direcionar esses logs, mas começando por uma tabela vinculada (perfis, delivery).

Ao usar uma **[!UICONTROL Incremental query]** que recupera apenas novos logs toda vez que o workflow é executado e uma **[!UICONTROL Extract file]** atividade para definir as colunas de output, você pode obter um arquivo com o formato e todos os dados necessários. Em seguida, use um **[!UICONTROL Transfer file]** atividade para recuperar o arquivo final. Cada execução de workflow é planejada por um **[!UICONTROL Scheduler]**.

A operação de exportar logs pode ser executada por usuários padrão. Recursos privados, como broadlogs, logs de rastreamento, logs de exclusão, logs de assinatura, logs de assinatura e logs de histórico de assinatura no **Perfis** só pode ser gerenciado pelo administrador funcional.

1. Crie um novo workflow conforme detalhado em [nesta seção](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Adicionar um **[!UICONTROL Scheduler]** atividade e defina-a de acordo com suas necessidades. Veja abaixo um exemplo de execução mensal.

   ![](assets/export_logs_scheduler.png)

1. Adicionar um **[!UICONTROL Incremental query]** atividade e a configure para selecionar os logs necessários. Por exemplo, para selecionar todos os broadlogs novos ou atualizados (logs do delivery do perfil):

   * No **[!UICONTROL Properties]** , altere o recurso de destino para **Logs de entrega** (broadLogRcp).

      ![](assets/export_logs_query_properties.png)

   * No **[!UICONTROL Target]** defina uma condição para recuperar todos os logs do delivery que correspondam aos deliveries enviados em 2016 ou depois. Para obter mais informações, consulte [Edição de consultas](../../automating/using/editing-queries.md#creating-queries) seção.

      ![](assets/export_logs_query_target.png)

   * No **[!UICONTROL Processed data]** selecione **[!UICONTROL Use a date field]** e escolha o **lastModified** campo. Nas próximas execuções do workflow, somente os logs que terão sido modificados ou criados após a última execução serão recuperados.

      ![](assets/export_logs_query_processeddata.png)

      Após a primeira execução do workflow, você poderá ver nesta guia a última data de execução que será usada para a próxima execução. Ela é atualizada automaticamente todas as vezes que o workflow é executado. Você ainda tem a possibilidade de substituir esse valor, inserindo manualmente um novo para que ele se ajuste às suas necessidades.

1. Adicionar um **[!UICONTROL Extract file]** atividade que exportará os dados consultados em um arquivo:

   * No **[!UICONTROL Extraction]** especifique o nome do arquivo.

      Se você selecionar a variável **[!UICONTROL Add date and time to the file name]** , esse nome será automaticamente preenchido com a data da exportação para garantir que todos os arquivos extraídos sejam exclusivos. Selecione as colunas que deseja exportar no arquivo. Você pode selecionar aqui os dados provenientes de recursos relacionados, como entrega ou informações de perfil.

      >[!NOTE]
      >
      >Para exportar um identificador exclusivo para cada log, selecione o **[!UICONTROL Delivery log ID]** elemento.

      Para organizar o arquivo final, é possível aplicar uma classificação. Por exemplo, na data de log, como mostrado no exemplo abaixo.

      ![](assets/export_logs_extractfile_extraction.png)

   * No **[!UICONTROL File structure]** defina o formato do arquivo de saída para atender às suas necessidades.

      Marque a opção **[!UICONTROL Export labels instead of internal values of enumerations]** caso exporte valores de uma lista discriminada. Essa opção permite recuperar rótulos mais curtos, que são fáceis de entender, em vez de IDs.

1. Adicionar um **[!UICONTROL Transfer file]** atividade e configurá-la para transferir o arquivo recém-criado do servidor do Adobe Campaign para outro local onde você pode acessá-lo, como um servidor SFTP.

   * No **[!UICONTROL General]** selecione **[!UICONTROL File upload]** já que o objetivo é enviar o arquivo do Adobe Campaign para outro servidor.
   * No **[!UICONTROL Protocol]** especifique os parâmetros de transferência e selecione o [conta externa](../../administration/using/external-accounts.md#creating-an-external-account) para usar.

1. Adicionar um **[!UICONTROL End]** atividade para garantir que ela termine e salve seu fluxo de trabalho corretamente.

   ![](assets/export_logs_example_workflow.png)

Agora é possível executar o workflow e recuperar o arquivo de saída no servidor externo.

**Tópicos relacionados:**

[Fluxos de trabalho](../../automating/using/get-started-workflows.md)
