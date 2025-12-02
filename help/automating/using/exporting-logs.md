---
title: Exportação de logs
description: Os dados de log, estejam eles relacionados a deliveries ou subscrições, podem ser exportados por meio de um simples workflow.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: d74e2a2c-3ce1-44d6-a058-67b0600360ca
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 14%

---

# Exportação de logs{#exporting-logs}

Os dados de log, estejam eles relacionados a deliveries ou subscrições, podem ser exportados por meio de um simples workflow. Ela permite analisar os resultados de suas campanhas em seus próprios relatórios ou na ferramenta de BI.

>[!CAUTION]
>
>Somente [administradores](../../administration/using/users-management.md#functional-administrators) funcionais, com função **[!UICONTROL Administration]** e acesso a **Todas** unidades, podem acessar logs de envio, logs de mensagens, logs de rastreamento, de exclusão ou de assinatura. Um usuário não administrador pode direcionar esses logs, mas começando por uma tabela vinculada (perfis, delivery).

Ao usar uma **[!UICONTROL Incremental query]** que recupera apenas novos logs toda vez que o fluxo de trabalho é executado e uma atividade **[!UICONTROL Extract file]** simples para definir as colunas de saída, você pode obter um arquivo com o formato e todos os dados necessários. Em seguida, use uma atividade **[!UICONTROL Transfer file]** para recuperar o arquivo final. Cada execução de fluxo de trabalho é planejada por um **[!UICONTROL Scheduler]**.

A operação de exportar logs pode ser executada por usuários padrão. Recursos privados como: broadlogs, logs de rastreamento, logs de exclusão, logs de assinatura e logs de histórico de assinatura em **Perfis** só podem ser gerenciados pelo administrador funcional.

1. Crie um novo fluxo de trabalho conforme detalhado em [esta seção](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Adicione uma atividade **[!UICONTROL Scheduler]** e defina-a de acordo com suas necessidades. Veja abaixo um exemplo de execução mensal.

   ![](assets/export_logs_scheduler.png)

1. Adicione uma atividade **[!UICONTROL Incremental query]** e a configure para selecionar os logs necessários. Por exemplo, para selecionar todos os broadlogs novos ou atualizados (logs do delivery do perfil):

   * Na guia **[!UICONTROL Properties]**, altere o recurso de destino para **Logs de entrega** (broadLogRcp).

     ![](assets/export_logs_query_properties.png)

   * Na guia **[!UICONTROL Target]**, defina uma condição para recuperar todos os logs de entrega que correspondam a entregas enviadas em 2016 ou depois. Para obter mais informações, consulte a seção [Edição de consultas](../../automating/using/editing-queries.md#creating-queries).

     ![](assets/export_logs_query_target.png)

   * Na guia **[!UICONTROL Processed data]**, selecione **[!UICONTROL Use a date field]** e escolha o campo **lastModified**. Nas próximas execuções do workflow, somente os logs que terão sido modificados ou criados após a última execução serão recuperados.

     ![](assets/export_logs_query_processeddata.png)

     Após a primeira execução do fluxo de trabalho, você poderá ver nesta guia a última data de execução que será usada para a próxima execução. Ela é atualizada automaticamente todas as vezes que o fluxo de trabalho é executado. Você ainda tem a possibilidade de substituir esse valor, inserindo manualmente um novo para que ele se ajuste às suas necessidades.

1. Adicionar uma atividade **[!UICONTROL Extract file]** que exportará os dados consultados em um arquivo:

   * Na guia **[!UICONTROL Extraction]**, especifique o nome do arquivo.

     Se você selecionar a opção **[!UICONTROL Add date and time to the file name]**, esse nome será automaticamente preenchido com a data de exportação para garantir que todos os arquivos extraídos sejam exclusivos. Selecione as colunas que deseja exportar no arquivo. Você pode selecionar aqui os dados provenientes de recursos relacionados, como entrega ou informações de perfil.

     >[!NOTE]
     >
     >Para exportar um identificador exclusivo para cada log, selecione o elemento **[!UICONTROL Delivery log ID]**.

     Para organizar o arquivo final, é possível aplicar uma classificação. Por exemplo, na data de log, como mostrado no exemplo abaixo.

     ![](assets/export_logs_extractfile_extraction.png)

   * Na guia **[!UICONTROL File structure]**, defina o formato do arquivo de saída para atender às suas necessidades.

     Marque a opção **[!UICONTROL Export labels instead of internal values of enumerations]** caso exporte valores de uma enumeração. Essa opção permite recuperar rótulos mais curtos, que são fáceis de entender, em vez de IDs.

1. Adicione uma atividade **[!UICONTROL Transfer file]** e a configure para transferir o arquivo recém-criado do servidor do Adobe Campaign para outro local onde você possa acessá-lo, como um servidor SFTP.

   * Na guia **[!UICONTROL General]**, selecione **[!UICONTROL File upload]**, pois a finalidade é enviar o arquivo do Adobe Campaign para outro servidor.
   * Na guia **[!UICONTROL Protocol]**, especifique os parâmetros de transferência e selecione a [conta externa](../../administration/using/external-accounts.md#creating-an-external-account) a ser usada.

1. Adicione uma atividade **[!UICONTROL End]** para verificar se ela termina corretamente e salve seu fluxo de trabalho.

   ![](assets/export_logs_example_workflow.png)

Agora é possível executar o workflow e recuperar o arquivo de saída no servidor externo.

**Tópicos relacionados:**

[Fluxos de trabalho](../../automating/using/get-started-workflows.md)
