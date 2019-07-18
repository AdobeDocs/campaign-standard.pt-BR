---
title: Carregar arquivo
seo-title: Carregar arquivo
description: Carregar arquivo
seo-description: A atividade de arquivo Carregar permite importar dados em um formulário estruturado para usar esses dados no Adobe Campaign.
page-status-flag: nunca ativado
uuid: 69 af 12 cc -6 f 82-4977-9 f 53-aa 7 bc 26 f 5 d 7 e
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: gerenciamento de dados-atividades
discoiquuid: 584 ff 893-9 b 1 b -46 c 9-9628-714 ab 349 ab 88
context-tags: Fileimport, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Load file{#load-file}

## Description {#description}

![](assets/data_loading.png)

The **[!UICONTROL Load file]** activity allows you to import data in one structured form to use this data in Adobe Campaign. Os dados são importados temporariamente e outra atividade é necessária para integrá-la definitivamente no banco de dados do Adobe Campaign.

## Context of use {#context-of-use}

A maneira como os dados serão extraídos é definida quando a atividade é configurada. O arquivo a ser carregado pode ser uma lista de contatos, por exemplo.

>[!CAUTION]
>
>Somente os arquivos de estrutura "simples" são considerados como, por exemplo, os arquivos.txt. csv etc., por exemplo.

Você pode:

* Use the file structure to apply it to another file's data (recovered using the **[!UICONTROL Transfer file]** activity) or,
* Use a estrutura e os dados do arquivo para importá-lo para o Adobe Campaign.

## Configuration {#configuration}

A configuração da atividade envolve duas etapas. Primeiro, é necessário definir a estrutura do arquivo esperado fazendo upload de um arquivo de amostra. Uma vez feita, é possível especificar a origem do arquivo cujos dados serão importados.

>[!NOTE]
>
>Os dados do arquivo de amostra são usados para configurar a atividade, mas não são importados. Recomendamos usar um arquivo de amostra contendo poucos dados.

1. Drag and drop a **[!UICONTROL Load file]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Carregue o arquivo de amostra que permitirá definir a estrutura esperada ao importar o arquivo final.

   ![](assets/wkf_file_loading.png)

   Once the data file is uploaded, two new tabs appear in the activity: **[!UICONTROL File structure]** and **[!UICONTROL Column definition]**.

1. Go to the **[!UICONTROL File structure]** tab to view the structure that is automatically detected from the sample file.

   Se a estrutura do arquivo foi detectada incorretamente, você tem várias opções para corrigir possíveis erros:

   * You can choose to use the structure of another file by selecting the **[!UICONTROL Detect structure from a new file]** option.
   * É possível modificar os parâmetros de detecção padrão para adaptá-los ao seu arquivo. The **[!UICONTROL File type]** field lets you specify if the file you want to import is made up of columns with fixed length. In that case, you must also specify the maximum number of characters for each column in the **[!UICONTROL Column definition]** tab.

      All of the detection options necessary to correctly recover the data from the file are regrouped in **[!UICONTROL File format]**. É possível modificá-los e redetectar a estrutura do último arquivo carregado na atividade levando em conta essas novas configurações. To do this, use the **[!UICONTROL Apply configuration]** button. Por exemplo, você pode especificar um separador de coluna diferente.

      >[!NOTE]
      >
      >Esta operação considera o último arquivo carregado na atividade. Se o arquivo detectado for grande, a visualização de dados mostrará apenas as primeiras 30 linhas.

      ![](assets/wkf_file_loading3.png)

      In the **[!UICONTROL File format]** section, the **[!UICONTROL Check columns from file against column definitions]** option lets you verify that the columns of the file you are uploading correspond to the column definition.

      Se o número e/ou o nome das colunas não corresponderem à definição da coluna, uma mensagem de erro será exibida durante a execução do fluxo de trabalho. Se a opção não estiver ativada, os avisos serão exibidos no arquivo de log.

      ![](assets/wkf_file_loading_check.png)

1. Go to the **[!UICONTROL Column definition]** tab to check the data format for each column and adjust the parameters if necessary.

   The **[!UICONTROL Column definition]** tab allows you to precisely specify the data structure of each column in order to import data that does not contain any errors (for example, using null management) and make it match the types that are already present in the Adobe Campaign database for future operations.

   Por exemplo, é possível alterar o rótulo de uma coluna, selecionar o tipo (sequência, número inteiro, data etc.) ou até mesmo especificar o processamento de erros.

   For more information, refer to the [Column format](../../automating/using/load-file.md#column-format) section.

   ![](assets/wkf_file_loading4.png)

1. In the **[!UICONTROL Execution]** tab, specify whether the file is to be processed for loading data:

   * Vem de uma transição de entrada no fluxo de trabalho.
   * É aquele que você carregou durante a etapa anterior.
   * É um novo arquivo para carregar a partir da máquina local. The **[!UICONTROL Upload a new file from local machine]** option appears if uploading a first file was already defined in the workflow. Isso permite que você carregue outro arquivo para ser processado se o arquivo atual não atender às suas necessidades.

      ![](assets/wkf_file_loading1.png)

1. If the file that you want to load the data from is compressed into a GZIP file (.gz), select the **[!UICONTROL Decompression]** option in the **[!UICONTROL Add a pre-processing step]** field. Isso permite descompactar o arquivo antes de carregar os dados. Essa opção só estará disponível se o arquivo vir da transição de entrada da atividade.
1. The **[!UICONTROL Keep the rejects in a file]** option enables you to download a file containing errors that occurred during the import, and to apply to it a post-processing stage.

   >[!NOTE]
   >
   >The **[!UICONTROL Add date and time to the file name]** option lets you add a timestamp the name of the file containing the rejects.

   ![](assets/wkf_file_loading_keeprejects.png)

1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

## Column format {#column-format}

Quando um arquivo de amostra é carregado, o formato da coluna é detectado automaticamente com os parâmetros padrão para cada tipo de dados. Você pode modificar esses parâmetros padrão para especificar os processos específicos a serem aplicados aos seus dados, especialmente quando há um erro ou um valor vazio.

To do this, select **[!UICONTROL Edit properties]** from the quick actions of the column whose format you would like to define. A janela de detalhes do formato de coluna será aberta.

![](assets/wkf_file_loading4.png)

Você pode modificar a formatação de cada coluna.

A formatação da coluna permite definir o processamento de valor de cada coluna:

* **[!UICONTROL Ignore column]**: não processa essa coluna durante o carregamento dos dados.
* **[!UICONTROL Data type]**: especifica o tipo de dados esperados para cada coluna.
* **[!UICONTROL Format and separators]**, **Propriedades**: especifique as propriedades de um texto, a hora, a data e o formato de valor numérico, bem como o separador especificado pelo contexto da coluna.

   * **[!UICONTROL Maximum number of characters]**: especifica o número máximo de caracteres para colunas de tipo de sequência de caracteres.

      Esse campo deve ser preenchido ao carregar arquivos constituídos de colunas com comprimento fixo.

   * **[!UICONTROL Letter case management]**: define se um processo de caso de caractere precisa ser aplicado aos dados **de Texto** .
   * **[!UICONTROL White space management]**: especifica se determinados espaços devem ser ignorados em uma string para dados **de Texto** .
   * **[!UICONTROL Time format]****[!UICONTROL Date format]**: especifique o formato para **Data**, **Hora** e **Dados de data** e hora.
   * **[!UICONTROL Format]**: permite definir o formato de valores numéricos para dados **inteiros** e **de número** flutuante.
   * **[!UICONTROL Separator]**: define o separador especificado pelo contexto da coluna (separador de milhares ou separador decimal para valores numéricos, separador para datas e hora) para **Data**, **Hora**, **Data e Hora**, **Número inteiro** e Dados **de número** flutuante.

* **[!UICONTROL Remapping of values]**: este campo está disponível apenas na configuração de detalhes da coluna. Permite transformar determinados valores quando eles são importados. Por exemplo, você pode transformar "três" em "3".
* **[!UICONTROL Error processing]**: define o comportamento se um erro for encontrado.

   * **[!UICONTROL Ignore the value]**: o valor é ignorado. Um aviso é gerado no log de execução do fluxo de trabalho.
   * **[!UICONTROL Reject the line]**: toda a linha não é processada.
   * **[!UICONTROL Use a default value]**: substitui o valor que causa o erro com um valor padrão, definido no **[!UICONTROL Default value]** campo.
   * **[!UICONTROL Use a default value in case the value is not remapped]**: substitui o valor que causa o erro com um valor padrão, definido no **[!UICONTROL Default value]** campo, a menos que um mapeamento tenha sido definido para o valor errado (consulte a **[!UICONTROL Remapping of values]** opção acima).
   * **[!UICONTROL Reject the line when there is no remapping value]**: a linha inteira não é processada a não ser que um mapeamento tenha sido definido para o valor errado (consulte a **[!UICONTROL Remapping of values]** opção acima).
   >[!NOTE]
   >
   >**[!UICONTROL Error processing]** refere-se a erros relacionados aos valores no arquivo importado. Por exemplo, um tipo de dados defeituoso encontrado ("quatro" todos em letras para uma coluna "Número inteiro"), uma string contendo mais caracteres do que o número máximo autorizado, uma data com separadores padrão etc. No entanto, essa opção não diz respeito a erros gerados pelo gerenciamento de valor vazio.

* **[!UICONTROL Default value]**: especifica o valor padrão de acordo com o processamento de erro escolhido.
* **[!UICONTROL Empty value management]**: especifica como gerenciar valores vazios durante o carregamento dos dados.

   * **[!UICONTROL Generate an error for numerical fields]**: gera um erro apenas para os campos numéricos; caso contrário, insere um valor NULL.
   * **[!UICONTROL Insert NULL in the corresponding field]**: autoriza valores vazios. Portanto, o valor NULL é inserido.
   * **[!UICONTROL Generate an error]**: gera um erro se um valor estiver vazio.

## Example {#example}

A atividade do arquivo de carregamento estrutura principalmente os dados de uma atividade de arquivo de transferência para integrá-la aos dados existentes.

O exemplo a seguir mostra o resultado de uma atividade de arquivo carregada automaticamente por meio de uma atividade de arquivo de transferência, seguida por uma atividade de dados de atualização. Esse fluxo de trabalho visa aprimorar o banco de dados do Adobe Campaign com novos perfis ou atualizar perfis existentes usando os dados recuperados do arquivo importado.

1. Drag and drop a **[!UICONTROL Transfer file]** activity into your workflow and configure it in a way so that it recovers the file you would like.
1. Drag and drop a **[!UICONTROL Load file]** activity into your workflow and place it after the **[!UICONTROL Transfer file]** activity.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. In the **[!UICONTROL File to load]** section of the **[!UICONTROL Execution]** tab, check the **[!UICONTROL Use the file specified in the inbound transition]** option.

   ![](assets/wkf_file_loading8.png)

1. Configure sua atividade como especificado anteriormente.
1. Drag and drop an **[!UICONTROL Update data]** activity into your workflow and place it after the **[!UICONTROL Load file]** activity, then configure it. Refer to [Update data](../../automating/using/update-data.md).

Depois que o fluxo de trabalho é iniciado, os dados do arquivo carregado são extraídos e, em seguida, são usados para aprimorar o banco de dados do Adobe Campaign.
