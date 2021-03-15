---
solution: Campaign Standard
product: campaign
title: Exportar logs
description: Os dados de log, sejam eles relacionados a deliveries ou assinaturas, podem ser exportados por meio de um fluxo de trabalho simples.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Fluxos de trabalho
role: Arquiteto de dados
level: Experienciado
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 14%

---


# Exportar logs{#exporting-logs}

Os dados de log, sejam eles relacionados a deliveries ou assinaturas, podem ser exportados por meio de um fluxo de trabalho simples. Ele permite analisar os resultados de suas campanhas em seus próprios relatórios ou ferramentas de BI.

>[!CAUTION]
>
>Somente os [administradores](../../administration/using/users-management.md#functional-administrators) funcionais, com a função **[!UICONTROL Administration]** e o acesso a **Todas** unidades podem acessar logs de envio, logs de mensagem, logs de rastreamento, exclusões ou logs de assinatura. Um usuário não administrador pode direcionar esses logs, mas começar em uma tabela vinculada (perfis, delivery).

Ao usar um **[!UICONTROL Incremental query]** que recupera apenas novos logs toda vez que o workflow é executado e uma atividade **[!UICONTROL Extract file]** simples para definir as colunas de saída, você pode obter um arquivo com o formato e todos os dados necessários. Em seguida, use uma atividade **[!UICONTROL Transfer file]** para recuperar o arquivo final. Cada execução de workflow é planejada por um **[!UICONTROL Scheduler]**.

A operação de logs de exportação pode ser executada por usuários padrão. Recursos privados como: broadlogs, logs de rastreamento, logs de exclusão, logs de assinatura e logs do histórico de assinaturas em **Profiles** só podem ser gerenciados pelo administrador funcional.

1. Crie um novo workflow conforme detalhado em [this section](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Adicione uma atividade **[!UICONTROL Scheduler]** e a defina de acordo com suas necessidades. Abaixo está um exemplo de execução mensal.

   ![](assets/export_logs_scheduler.png)

1. Adicione uma atividade **[!UICONTROL Incremental query]** e a configure para que ela selecione os logs necessários. Por exemplo, para selecionar todos os broadlogs novos ou atualizados (logs do delivery do perfil):

   * Na guia **[!UICONTROL Properties]** , altere o recurso de destino para **Delivery logs** (broadLogRcp).

      ![](assets/export_logs_query_properties.png)

   * Na guia **[!UICONTROL Target]** , defina uma condição para recuperar todos os logs do delivery que correspondem aos deliveries enviados em 2016 ou depois. Para obter mais informações, consulte a seção [Edição de consultas](../../automating/using/editing-queries.md#creating-queries) .

      ![](assets/export_logs_query_target.png)

   * Na guia **[!UICONTROL Processed data]**, selecione **[!UICONTROL Use a date field]** e escolha o campo **lastModified**. Nas próximas execuções do workflow, somente os logs que tiverem sido modificados ou criados após a última execução serão recuperados.

      ![](assets/export_logs_query_processeddata.png)

      Após a primeira execução do workflow, você poderá ver nesta guia a última data de execução que será usada para a próxima execução. Ela é atualizada automaticamente todas as vezes que o workflow é executado. Você ainda tem a possibilidade de substituir esse valor, inserindo manualmente um novo para que ele se ajuste às suas necessidades.

1. Adicione uma atividade **[!UICONTROL Extract file]** que exportará os dados consultados em um arquivo:

   * Na guia **[!UICONTROL Extraction]** , especifique o nome do arquivo.

      Se você selecionar a opção **[!UICONTROL Add date and time to the file name]** , esse nome será automaticamente preenchido com a data da exportação para garantir que todos os arquivos extraídos sejam exclusivos. Selecione as colunas que deseja exportar no arquivo. Você pode selecionar aqui os dados provenientes de recursos relacionados, como informações de delivery ou perfil.

      >[!NOTE]
      >
      >Para exportar um identificador exclusivo para cada log, selecione o elemento **[!UICONTROL Delivery log ID]**.

      Para organizar o arquivo final, você pode aplicar uma classificação. Por exemplo, na data de log, como mostrado no exemplo abaixo.

      ![](assets/export_logs_extractfile_extraction.png)

   * Na guia **[!UICONTROL File structure]** , defina o formato do arquivo de saída para corresponder às suas necessidades.

      Marque a opção **[!UICONTROL Export labels instead of internal values of enumerations]** caso exporte valores de uma lista discriminada. Essa opção permite recuperar rótulos mais curtos, que são fáceis de entender, em vez de IDs.

1. Adicione uma atividade **[!UICONTROL Transfer file]** e a configure para transferir o arquivo recém-criado do servidor Adobe Campaign para outro local onde você pode acessá-lo, como um servidor SFTP.

   * Na guia **[!UICONTROL General]** , selecione **[!UICONTROL File upload]** como o objetivo é enviar o arquivo do Adobe Campaign para outro servidor.
   * Na guia **[!UICONTROL Protocol]** , especifique os parâmetros de transferência e selecione a [conta externa](../../administration/using/external-accounts.md#creating-an-external-account) a ser usada.

1. Adicione uma atividade **[!UICONTROL End]** para garantir que ela termine e salve o workflow corretamente.

   ![](assets/export_logs_example_workflow.png)

Agora é possível executar o workflow e recuperar o arquivo de saída no servidor externo.

**Tópicos relacionados:**

[Fluxos de trabalho](../../automating/using/get-started-workflows.md)
