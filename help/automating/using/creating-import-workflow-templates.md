---
solution: Campaign Standard
product: campaign
title: Criação de modelos de workflow para importar dados
description: Saiba como criar modelos de fluxo de trabalho para importar dados.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 58%

---


# Criação de modelos de workflow para importar dados {#import-workflow-template}

Usar um template de importação é uma prática recomendada se você precisar importar arquivos regularmente com a mesma estrutura.

Esse exemplo mostra como predefinir um workflow que pode ser reutilizado para importar perfis provenientes de um CRM no banco de dados do Adobe Campaign.

1. Crie um novo modelo de workflow a partir de **[!UICONTROL Resources > Templates > Workflow templates]**.
1. Adicione as seguintes atividades:

   * **[!UICONTROL Load file]**: defina a estrutura esperada do arquivo que contém os dados que serão importados.

      >[!NOTE]
      >
      >Você só pode importar dados de um único arquivo. Se o fluxo de trabalho tiver várias **[!UICONTROL Load file]** atividades, o mesmo arquivo será usado sempre.

   * **[!UICONTROL Reconciliation]**: reconcilie os dados importados com os dados do banco de dados.
   * **[!UICONTROL Segmentation]**: crie filtros para processar registros de forma diferente, sejam eles reconciliados ou não.
   * **[!UICONTROL Deduplication]**: elimine a duplicação dos dados do arquivo de entrada antes de ele ser inserido no banco de dados.
   * **[!UICONTROL Update data]**: atualize o banco de dados com os perfis importados.

   ![](assets/import_template_example0.png)

1. Configure a atividade **[!UICONTROL Load file]**:

   * Defina a estrutura esperada carregando um arquivo de amostra. O arquivo de amostra deve conter apenas algumas linhas, mas todas as colunas necessárias para a importação. Verifique e edite o formato de arquivo para verificar se o tipo de cada coluna está definido corretamente: texto, data, inteiro, etc. Por exemplo:

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * Na seção **[!UICONTROL File to load]**, selecione **[!UICONTROL Upload a new file from the local machine]** e deixe o campo em branco. Toda vez que um novo workflow for criado a partir desse modelo, você pode especificar aqui o arquivo desejado, desde que ele corresponda à estrutura definida.

      Você pode usar qualquer uma das opções, mas precisa modificar o template adequadamente. Por exemplo, se você selecionar **[!UICONTROL Use the file specified in the inbound transition]**, será possível adicionar uma atividade **[!UICONTROL Transfer file]** antes de recuperar o arquivo para importar de um servidor FTP/SFTP.

      Se quiser que os usuários possam baixar um arquivo que contém erros que ocorreram durante uma importação, verifique a opção **[!UICONTROL Keep the rejects in a file]** e especifique **[!UICONTROL File name]**.

      ![](assets/import_template_example1.png)

1. Configure a atividade **[!UICONTROL Reconciliation]**. A finalidade dessa atividade nesse contexto é identificar os dados de entrada.

   * Na guia **[!UICONTROL Relations]**, selecione **[!UICONTROL Create element]** e defina um link entre os dados importados e o targeting dimension de recipient (consulte [Targeting dimension e recursos](../../automating/using/query.md#targeting-dimensions-and-resources)). Neste exemplo, o campo personalizado **ID do CRM** é usado para criar a condição de associação. Use o campo ou uma combinação de campos que você precisa, desde que isso permita identificar registros únicos.
   * Na guia **[!UICONTROL Identification]**, deixe a opção **[!UICONTROL Identify the document from the working data]** desmarcada.

   ![](assets/import_template_example2.png)

1. Configure a atividade **[!UICONTROL Segmentation]** para recuperar os recipients reconciliados em uma transição e recipients que não puderam ser reconciliados, mas que tenham dados suficientes em uma segunda transição.

   A transição com recipients reconciliados pode ser usada para atualizar o banco de dados. A transição com recipients desconhecidos pode ser usada para criar novas entradas de recipients no banco de dados se um conjunto mínimo de informações estiver disponível no arquivo.

   Os recipients que não podem ser reconciliados e não têm dados suficientes estão selecionados em uma transição de saída de complemento e podem ser exportados em um arquivo separado ou simplesmente ignorado.

   * Na guia **[!UICONTROL General]** da atividade, defina **[!UICONTROL Resource type]** como **[!UICONTROL Temporary resource]** e selecione **[!UICONTROL Reconciliation]** como o conjunto de metas.
   * Na guia **[!UICONTROL Advanced options]**, marque a opção **[!UICONTROL Generate complement]** para ver se não é possível inserir nenhum registro no banco de dados. Se for necessário, você pode aplicar processamento adicional aos dados complementares: exportação de arquivos, atualização de lista etc.
   * No primeiro segmento da guia **[!UICONTROL Segments]**, adicione uma condição de filtragem ao preenchimento de entrada para selecionar somente os registros cujo ID do CRM do perfil não seja igual a 0. Dessa forma, os dados do arquivo que são reconciliados com perfis do banco de dados são selecionados nesse subconjunto.

      ![](assets/import_template_example3.png)

   * Adicione um segundo segmento que selecione registros não reconciliados que tenham dados suficientes para serem inseridos no banco de dados. Por exemplo: endereço de email, nome e sobrenome. Os registros não reconciliados têm o valor da ID CRM do perfil igual a 0.

      ![](assets/import_template_example3_2.png)

   * Todos os registros que não estão selecionados nos dois primeiros subconjuntos são selecionados no **[!UICONTROL Complement]**.

1. Configure a atividade **[!UICONTROL Update data]** localizada após a primeira transição de saída da atividade **[!UICONTROL Segmentation]** configurada anteriormente.

   * Selecione **[!UICONTROL Update]** como **[!UICONTROL Operation type]** desde que a transição de entrada contenha apenas os recipients já presentes no banco de dados.
   * Na guia **[!UICONTROL Identification]**, selecione **[!UICONTROL Using reconciliation criteria]** e defina uma chave entre os Perfis **[!UICONTROL Dimension to update]** - nesse caso - e o link criado na atividade **[!UICONTROL Reconciliation]**. Neste exemplo, o campo personalizado **ID do CRM** é usado.

      ![](assets/import_template_example6.png)

   * Na guia **[!UICONTROL Fields to update]**, indique os campos da dimensão Perfis a serem atualizados com o valor da coluna correspondente do arquivo. Se os nomes das colunas de arquivo forem idênticos ou quase idênticos aos dos campos de dimensão dos recipients, você poderá usar o botão de varinha mágica para combinar os diferentes campos automaticamente.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Se você planeja enviar emails diretos para esses perfis, certifique-se de incluir um endereço postal, pois essas informações são essenciais para o provedor de mala direta. Verifique também se a caixa **[!UICONTROL Address specified]** nas informações dos perfis está marcada. Para atualizar essa opção de um fluxo de trabalho, basta adicionar um elemento aos campos a serem atualizados e especificar **1** como **[!UICONTROL Source]** e selecionar o campo `postalAddress/@addrDefined` como **[!UICONTROL Destination]**. Para obter mais informações sobre mala direta e o uso da opção **[!UICONTROL Address specified]**, consulte [este documento](../../channels/using/about-direct-mail.md#recommendations).

1. Configure a atividade **[!UICONTROL Deduplication]** localizada após a transição que contém perfis não reconciliados:

   * Na guia **[!UICONTROL Properties]**, defina **[!UICONTROL Resource type]** para o recurso temporário gerado da atividade **[!UICONTROL Reconciliation]** do fluxo de trabalho.

      ![](assets/import_template_example4.png)

   * Nesse exemplo, o campo de email é usado para localizar perfis únicos. Você pode usar qualquer campo que você tem certeza que está preenchido e é parte de uma combinação única.
   * Escolha um **[!UICONTROL Deduplication method]**. Neste caso, o pedido decide automaticamente quais os registros que são mantidos em caso de duplicado.

   ![](assets/import_template_example7.png)

1. Configure a atividade **[!UICONTROL Update data]**, localizada após a atividade **[!UICONTROL Deduplication]**, configurada anteriormente.

   * Selecione **[!UICONTROL Insert only]** como **[!UICONTROL Operation type]**, uma vez que a transição de entrada contém apenas perfis não presentes no banco de dados.
   * Na guia **[!UICONTROL Identification]**, selecione **[!UICONTROL Using reconciliation criteria]** e defina uma chave entre os Perfis **[!UICONTROL Dimension to update]** - nesse caso - e o link criado na atividade **[!UICONTROL Reconciliation]**. Neste exemplo, o campo personalizado **ID do CRM** é usado.

      ![](assets/import_template_example6.png)

   * Na guia **[!UICONTROL Fields to update]**, indique os campos da dimensão Perfis a serem atualizados com o valor da coluna correspondente do arquivo. Se os nomes das colunas de arquivo forem idênticos ou quase idênticos aos dos campos de dimensão dos recipients, você poderá usar o botão de varinha mágica para combinar os diferentes campos automaticamente.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Se você planeja enviar emails diretos para esses perfis, certifique-se de incluir um endereço postal, pois essas informações são essenciais para o provedor de mala direta. Verifique também se a caixa **[!UICONTROL Address specified]** nas informações dos perfis está marcada. Para atualizar essa opção de um fluxo de trabalho, basta adicionar um elemento aos campos a serem atualizados e especificar **1** como **[!UICONTROL Source]** e selecionar o campo **[postalAddress/@addrDefined]** como **[!UICONTROL Destination]**. Para obter mais informações sobre mala direta e o uso da opção **[!UICONTROL Address specified]**, consulte [este documento](../../channels/using/about-direct-mail.md#recommendations).

1. Após a terceira transição da atividade **[!UICONTROL Segmentation]**, adicione uma atividade **[!UICONTROL Extract file]** e uma atividade **[!UICONTROL Transfer file]** se desejar acompanhar os dados não inseridos no banco de dados. Configure essas atividades para exportar a coluna necessária e transferir o arquivo em um servidor FTP ou SFTP, onde você pode recuperá-la.
1. Adicione uma atividade **[!UICONTROL End]** e salve o template do workflow.

Agora o template pode ser usado e está disponível para cada novo workflow. Basta especificar o arquivo que contém os dados que serão importados na atividade **[!UICONTROL Load file]**.

![](assets/import_template_example9.png)
