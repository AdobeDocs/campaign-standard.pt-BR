---
title: Importação de dados
description: Saiba como importar dados com um fluxo de trabalho.
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9048e11fe063707e1c6b5a86de095f72d22800c1

---


# Importação de dados{#importing-data}

## Coleta de dados {#collecting-data}

Você pode coletar dados de um arquivo para processá-lo e/ou importá-lo no banco de dados do Adobe Campaign.

* A **[!UICONTROL Load file]** atividade permite importar dados em um formulário estruturado para usá-los no Adobe Campaign. Os dados são importados temporariamente e outra atividade é necessária para integrá-los definitivamente ao banco de dados do Adobe Campaign.

   For more on how to use this activity, refer to [this section](../../automating/using/load-file.md).

* A **[!UICONTROL Transfer file]** atividade permite que você receba ou envie arquivos, teste se há arquivos presentes ou liste arquivos no Adobe Campaign.
Você pode usar essa atividade antes de uma **[!UICONTROL Load file]** caso precise recuperar o arquivo de uma fonte externa.

   For more on how to use this activity, refer to [this section](../../automating/using/transfer-file.md).

## Práticas recomendadas de importação {#import-best-practices}

Ser cuidadoso e seguir apenas algumas regras simples detalhadas abaixo ajudará a garantir a consistência dos dados dentro do banco de dados e evitar erros comuns durante a atualização ou exportação de dados.

### Uso de templates de importação {#using-import-templates}

A maioria dos workflows de importação deve conter as seguintes atividades: **[!UICONTROL Load file]**, **[!UICONTROL Reconciliation]**, **[!UICONTROL Segmentation]**, **[!UICONTROL Deduplication]**, **[!UICONTROL Update data]**.

É muito conveniente usar templates de importação para preparar importações semelhantes e garantir a consistência dos dados no banco de dados.

In many projects, imports are built without **[!UICONTROL Deduplication]** activity because the files used in the project do not have duplicates. As duplicatas às vezes surgem da importação de arquivos diferentes. A eliminação de duplicatas é difícil. Portanto, a etapa de eliminação de duplicatas é uma boa precaução em todos os workflows de importação.

Não confie na suposição de que os dados de entrada são consistentes e corretos, ou que o departamento de TI ou o supervisor do Adobe Campaign irá resolver isso. Durante o projeto, mantenha a limpeza dos dados em mente. Elimine duplicatas, reconcilie e mantenha de consistência ao importar dados.

Um exemplo de um modelo de fluxo de trabalho genérico projetado para importar dados está disponível no [Exemplo: Importar seção de modelo](#example--import-workflow-template) de fluxo de trabalho.

>[!NOTE]
>
>Também é possível usar modelos [de](../../automating/using/importing-data-with-import-templates.md)importação. São modelos de fluxo de trabalho definidos por um administrador que, uma vez ativado, oferece apenas a possibilidade de especificar o arquivo que contém os dados a serem importados.

**Tópicos relacionados:**

* [Carregar atividade de arquivo](../../automating/using/load-file.md)
* [Atividade de reconciliação](../../automating/using/reconciliation.md)
* [Atividade de segmentação](../../automating/using/segmentation.md)
* [Atividade de desduplicação](../../automating/using/deduplication.md)
* [Atualizar atividade de dados](../../automating/using/update-data.md)

### Uso dos formatos de arquivo simples {#using-flat-file-formats}

O formato mais eficiente para importações é o arquivo simples. Arquivos simples podem ser importados no modo em massa no nível do banco de dados.

Por exemplo:

* Separador: tabulação ou ponto e vírgula
* Primeira linha com cabeçalhos
* Nenhum delimitador de cadeia de caracteres
* Formato de data: AAAA/MM/DD HH:mm:SS

Exemplo de arquivo a ser importado:

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

### Uso da compactação {#using-compression}

Use arquivos compactados para importações e exportações sempre que possível. O GZIP é suportado por padrão. Você pode adicionar pré-processamento ao importar arquivos ou pós-processamento ao extrair dados, respectivamente, nas atividades do fluxo de trabalho **[!UICONTROL Load file]** e do fluxo de **[!UICONTROL Extract file]** trabalho.

**Tópicos relacionados:**

* [Carregar atividade de arquivo](../../automating/using/load-file.md)
* [Extrair atividade de arquivo](../../automating/using/extract-file.md)

### Importação no modo Delta {#importing-in-delta-mode}

As importações regulares devem ser efetuadas no modo delta. Isso significa que somente os dados modificados ou novos são enviados ao Adobe Campaign, em vez da tabela toda sempre.

As importações completas devem ser usadas somente para carregamento inicial.

### Manutenção da consistência {#maintaining-consistency}

Para manter a consistência dos dados no banco de dados do Adobe Campaign, siga os princípios abaixo:

* Se os dados importados corresponderem a uma tabela de referência no Adobe Campaign, então ele deverá ser reconciliado com essa tabela no workflow. Os registros que não correspondem devem ser rejeitados.
* Certifique-se de que os dados importados sejam sempre **&quot;normalizados&quot;** (email, número de telefone, endereço de mala direta) e que essa normalização seja confiável e não será alterada ao longo dos anos. Se não for o caso, provavelmente aparecerão algumas duplicatas no banco de dados e, como o Adobe Campaign não fornece ferramentas para fazer a correspondência &quot;difusa&quot;, será muito difícil removê-las e gerencia-las.
* Os dados transacionais devem ter uma chave de reconciliação e serem reconciliados com os dados existentes para evitar a criação de duplicatas.
* **Importação de arquivos relacionados em ordem**. Se a importação for composta de vários arquivos que dependem uns dos outros, o workflow deve garantir que os arquivos sejam importados na ordem correta. Quando um arquivo falhar, os outros arquivos não serão importados.
* **Elimine duplicatas**, reconcilie e mantenha de consistência ao importar dados.

## Gerenciamento de dados criptografados {#managing-encrypted-data}

Em alguns casos, os dados que você deseja importar para os Servidores de campanha podem precisar ser criptografados, por exemplo, se contiverem dados de PII.

Para importar ou exportar arquivos criptografados, primeiro é necessário entrar em contato com o Atendimento ao cliente da Adobe para que ele forneça à sua instância os comandos de criptografia/descriptografia necessários.

Para fazer isso, envie uma solicitação indicando:

* O **rótulo** que será exibido na interface do Campaign para usar o comando. Por exemplo, &quot;Criptografar arquivo&quot;.
* O **comando** a ser instalado em sua instância.
Por exemplo, para descriptografar um arquivo usando PGP, o comando será:

   ```
   <path-to_pgp_if-not_global_or_server/>pgp.exe --decrypt --input nl6/var/vp/import/filename.pgp --passphrase "your password" --recipient recipient @email.com --verbose --output nl6/var/vp/import/filename
   ```

Depois que a solicitação for processada, os comandos de criptografia/descriptografia estarão disponíveis no **!UICONTROL Pre-processing stage]** campo nas atividades **[!UICONTROL Load file]** e **[!UICONTROL Extract file]** . Você pode usá-los para descriptografar ou criptografar os arquivos que deseja importar ou exportar.

![](assets/preprocessing-encryption.png)

**Tópicos relacionados:**

* [Carregar arquivo](../../automating/using/load-file.md)
* [Extrair arquivo](../../automating/using/extract-file.md)

## Criação de modelos de fluxo de trabalho para importar dados {#example--import-workflow-template}

Usar um template de importação é uma prática recomendada se você precisar importar arquivos regularmente com a mesma estrutura.

Esse exemplo mostra como predefinir um workflow que pode ser reutilizado para importar perfis provenientes de um CRM no banco de dados do Adobe Campaign.

1. Crie um novo modelo de fluxo de trabalho a partir de **[!UICONTROL Resources > Templates > Workflow templates]**.
1. Adicione as seguintes atividades:

   * **[!UICONTROL Load file]**: Defina a estrutura esperada do arquivo que contém os dados a serem importados.

      >[!NOTE]
      >
      >Você só pode importar dados de um único arquivo. Se o fluxo de trabalho tiver várias **[!UICONTROL Load file]** atividades, o mesmo arquivo será usado sempre.

   * **[!UICONTROL Reconciliation]**: Reconcilie os dados importados com os dados do banco de dados.
   * **[!UICONTROL Segmentation]**: Crie filtros para processar registros de forma diferente conforme sejam eles reconciliados ou não.
   * **[!UICONTROL Deduplication]**: Elimine a duplicação dos dados do arquivo de entrada antes de ele ser inserido no banco de dados.
   * **[!UICONTROL Update data]**: Atualize o banco de dados com os perfis importados.
   ![](assets/import_template_example0.png)

1. Configure a **[!UICONTROL Load file]** atividade:

   * Defina a estrutura esperada carregando um arquivo de amostra. O arquivo de amostra deve conter apenas algumas linhas, mas todas as colunas necessárias para a importação. Verifique e edite o formato de arquivo para verificar se o tipo de cada coluna está definido corretamente: texto, data, inteiro, etc. Por exemplo:

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * Na **[!UICONTROL File to load]** seção, selecione **[!UICONTROL Upload a new file from the local machine]** e deixe o campo em branco. Toda vez que um novo workflow for criado a partir desse modelo, você pode especificar aqui o arquivo desejado, desde que ele corresponda à estrutura definida.

      Você pode usar qualquer uma das opções, mas precisa modificar o template adequadamente. For example, if you select **[!UICONTROL Use the file specified in the inbound transition]**, you can add a **[!UICONTROL Transfer file]** activity before to retrieve the file to import from a FTP/SFTP server.

      Se quiser que os usuários possam baixar um arquivo que contenha erros que ocorreram durante uma importação, marque a **[!UICONTROL Keep the rejects in a file]** opção e especifique o **[!UICONTROL File name]**.

      ![](assets/import_template_example1.png)

1. Configure a **[!UICONTROL Reconciliation]** atividade. A finalidade dessa atividade nesse contexto é identificar os dados de entrada.

   * Na **[!UICONTROL Relations]** guia, selecione **[!UICONTROL Create element]** e defina um link entre os dados importados e a dimensão de direcionamento dos destinatários (consulte Dimensões e recursos [de](../../automating/using/query.md#targeting-dimensions-and-resources)direcionamento). Neste exemplo, o campo personalizado **ID do CRM** é usado para criar a condição de associação. Use o campo ou uma combinação de campos que você precisa, desde que isso permita identificar registros únicos.
   * Na **[!UICONTROL Identification]** guia, deixe a opção **[!UICONTROL Identify the document from the working data]** desmarcada.
   ![](assets/import_template_example2.png)

1. Configure the **[!UICONTROL Segmentation]** activity to retrieve reconciled recipients in one transition and recipients that could not be reconciled but who have enough data in a second transition.

   A transição com recipients reconciliados pode ser usada para atualizar o banco de dados. A transição com recipients desconhecidos pode ser usada para criar novas entradas de recipients no banco de dados se um conjunto mínimo de informações estiver disponível no arquivo.

   Os recipients que não podem ser reconciliados e não têm dados suficientes estão selecionados em uma transição de saída de complemento e podem ser exportados em um arquivo separado ou simplesmente ignorado.

   * Na **[!UICONTROL General]** guia da atividade, defina o **[!UICONTROL Resource type]** como **[!UICONTROL Temporary resource]** e selecione **[!UICONTROL Reconciliation]** como o conjunto de metas.
   * In the **[!UICONTROL Advanced options]** tab, check the **[!UICONTROL Generate complement]** option to be able to see if any record cannot be inserted in the database. Se for necessário, processamento adicional pode ser aplicado aos dados complementares: exportação de arquivos, atualização de lista etc.
   * In the first segment of the **[!UICONTROL Segments]** tab, add a filtering condition on the inbound population to select only records for which the profile&#39;s CRM ID is not equal to 0. Dessa forma, os dados do arquivo que são reconciliados com perfis do banco de dados são selecionados nesse subconjunto.

      ![](assets/import_template_example3.png)

   * Adicione um segundo segmento que selecione registros não reconciliados que tenham dados suficientes para serem inseridos no banco de dados. Por exemplo: endereço de email, nome e sobrenome. Os registros não reconciliados têm o valor da ID do CRM do perfil igual a 0.

      ![](assets/import_template_example3_2.png)

   * Todos os registros que não estão selecionados nos dois primeiros subconjuntos são selecionados no **[!UICONTROL Complement]**.

1. Configure the **[!UICONTROL Update data]** activity located after the first outbound transition of the **[!UICONTROL Segmentation]** activity configured previously.

   * Select **[!UICONTROL Update]** as **[!UICONTROL Operation type]** since the inbound transition only contains recipients already present in the database.
   * Na **[!UICONTROL Identification]** guia, selecione **[!UICONTROL Using reconciliation criteria]** e defina uma chave entre **[!UICONTROL Dimension to update]** - nesse caso, Perfis - e o link criado na **[!UICONTROL Reconciliation]** atividade. Neste exemplo, o campo personalizado **ID do CRM** é usado.

      ![](assets/import_template_example6.png)

   * In the **[!UICONTROL Fields to update]** tab, indicate the fields from the Profiles dimension to update with the value of the corresponding column from the file. Se os nomes das colunas de arquivo forem idênticos ou quase idênticos aos dos campos de dimensão dos recipients, você poderá usar o botão da varinha mágica para combinar os diferentes campos automaticamente.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Se você planeja enviar emails diretos para esses perfis, certifique-se de incluir um endereço postal, pois essas informações são essenciais para o provedor de mala direta. Verifique também se a **[!UICONTROL Address specified]** caixa nas informações dos perfis está marcada. Para atualizar essa opção de um fluxo de trabalho, basta adicionar um elemento aos campos a serem atualizados e especificar **1** como **[!UICONTROL Source]** e selecionar o `postalAddress/@addrDefined` campo como **[!UICONTROL Destination]**. Para obter mais informações sobre mala direta e o uso da **[!UICONTROL Address specified]** opção, consulte [este documento](../../channels/using/about-direct-mail.md#recommendations).

1. Configure the **[!UICONTROL Deduplication]** activity located after the transition containing unreconciled profiles:

   * Na **[!UICONTROL Properties]** guia, defina o **[!UICONTROL Resource type]** para o recurso temporário gerado a partir da **[!UICONTROL Reconciliation]** atividade do fluxo de trabalho.

      ![](assets/import_template_example4.png)

   * Nesse exemplo, o campo de email é usado para localizar perfis únicos. Você pode usar qualquer campo que você tem certeza que está preenchido e é parte de uma combinação única.
   * Escolha um **[!UICONTROL Deduplication method]**. Neste caso, o pedido decide automaticamente quais os registros que são mantidos em caso de duplicações.
   ![](assets/import_template_example7.png)

1. Configure the **[!UICONTROL Update data]** activity located after the **[!UICONTROL Deduplication]** activity configured previously.

   * Select **[!UICONTROL Insert only]** as **[!UICONTROL Operation type]** since the inbound transition only contains profiles not present in the database.
   * Na **[!UICONTROL Identification]** guia, selecione **[!UICONTROL Using reconciliation criteria]** e defina uma chave entre **[!UICONTROL Dimension to update]** - nesse caso, Perfis - e o link criado na **[!UICONTROL Reconciliation]** atividade. Neste exemplo, o campo personalizado **ID do CRM** é usado.

      ![](assets/import_template_example6.png)

   * In the **[!UICONTROL Fields to update]** tab, indicate the fields from the Profiles dimension to update with the value of the corresponding column from the file. Se os nomes das colunas de arquivo forem idênticos ou quase idênticos aos dos campos de dimensão dos recipients, você poderá usar o botão da varinha mágica para combinar os diferentes campos automaticamente.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Se você planeja enviar emails diretos para esses perfis, certifique-se de incluir um endereço postal, pois essas informações são essenciais para o provedor de mala direta. Verifique também se a **[!UICONTROL Address specified]** caixa nas informações dos perfis está marcada. Para atualizar essa opção de um fluxo de trabalho, basta adicionar um elemento aos campos a serem atualizados e especificar **1** como **[!UICONTROL Source]** e selecionar o campo **[postalAddress/@addrDefined]** como **[!UICONTROL Destination]**. Para obter mais informações sobre mala direta e o uso da **[!UICONTROL Address specified]** opção, consulte [este documento](../../channels/using/about-direct-mail.md#recommendations).

1. After the third transition of the **[!UICONTROL Segmentation]** activity, add a **[!UICONTROL Extract file]** activity and a **[!UICONTROL Transfer file]** activity if you want to keep track of data not inserted in the database. Configure essas atividades para exportar a coluna necessária e transferir o arquivo em um servidor FTP ou SFTP, onde você pode recuperá-la.
1. Add an **[!UICONTROL End]** activity and save the workflow template.

Agora o template pode ser usado e está disponível para todo workflow novo. All is needed is then to specify the file containing the data to import in the **[!UICONTROL Load file]** activity.

![](assets/import_template_example9.png)
