---
title: Carregar arquivo
description: A atividade Carregar arquivo permite importar dados em um formulário estruturado para usar esses dados no Adobe Campaign.
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '1771'
ht-degree: 5%

---


# Carregar arquivo {#load-file}

## Descrição {#description}

![](assets/data_loading.png)

A **[!UICONTROL Load file]** atividade permite importar dados em um formulário estruturado para usá-los no Adobe Campaign. Os dados são temporariamente importados e outra atividade é necessária para integrá-los definitivamente ao banco de dados do Adobe Campaign.

## Contexto de utilização {#context-of-use}

A forma como os dados serão extraídos é definida quando a atividade for configurada. O arquivo a ser carregado pode ser uma lista de contatos, por exemplo.

>[!CAUTION]
>
>Somente arquivos de estrutura &quot;simples&quot; são considerados, como arquivos .txt, .csv etc., por exemplo.

É possível:

* Use a estrutura do arquivo para aplicá-lo aos dados de outro arquivo (recuperados usando a **[!UICONTROL Transfer file]** atividade) ou
* Use a estrutura e os dados do arquivo para importá-lo para o Adobe Campaign.

## Configuração {#configuration}

A configuração da atividade envolve duas etapas. Primeiro, é necessário definir a estrutura de arquivos esperada carregando um arquivo de amostra. Quando isso for feito, você poderá especificar a origem do arquivo cujos dados serão importados.

>[!NOTE]
>
>Os dados do arquivo de amostra são usados para configurar a atividade, mas não são importados. Recomendamos usar um arquivo de amostra contendo poucos dados.

1. Arraste e solte uma **[!UICONTROL Load file]** atividade no seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Carregue o arquivo de amostra que permitirá que você defina a estrutura esperada ao importar o arquivo final.

   ![](assets/wkf_file_loading.png)

   Depois que o arquivo de dados é carregado, duas novas guias são exibidas na atividade: **[!UICONTROL File structure]** e **[!UICONTROL Column definition]**.

1. Vá até a **[!UICONTROL File structure]** guia para visualização da estrutura que é detectada automaticamente do arquivo de amostra.

   Se a estrutura do arquivo foi detectada incorretamente, você tem várias opções para corrigir possíveis erros:

   * Você pode optar por usar a estrutura de outro arquivo selecionando a **[!UICONTROL Detect structure from a new file]** opção.
   * Você pode modificar os parâmetros de detecção padrão para adaptá-los ao seu arquivo. O **[!UICONTROL File type]** campo permite especificar se o arquivo que você deseja importar é composto de colunas com comprimento fixo. Nesse caso, você também deve especificar o número máximo de caracteres para cada coluna na **[!UICONTROL Column definition]** guia.

      Todas as opções de detecção necessárias para recuperar corretamente os dados do arquivo são agrupadas em **[!UICONTROL File format]**. Você pode modificá-las e detectar novamente a estrutura do último arquivo carregado na atividade levando em conta essas novas configurações. Para fazer isso, use o **[!UICONTROL Apply configuration]** botão. Por exemplo, você pode especificar um separador de coluna diferente.

      >[!NOTE]
      >
      >Esta operação leva em conta o último arquivo que foi carregado na atividade. Se o arquivo detectado for grande, a pré-visualização de dados mostrará apenas as primeiras 30 linhas.

      ![](assets/wkf_file_loading3.png)

      Na **[!UICONTROL File format]** seção, a **[!UICONTROL Check columns from file against column definitions]** opção permite verificar se as colunas do arquivo que você está carregando correspondem à definição da coluna.

      Se o número e/ou o nome das colunas não corresponderem à definição da coluna, uma mensagem de erro será exibida ao executar o fluxo de trabalho. Se a opção não estiver ativada, os avisos serão exibidos no arquivo de log.

      ![](assets/wkf_file_loading_check.png)

1. Vá até a **[!UICONTROL Column definition]** guia para verificar o formato de dados para cada coluna e ajuste os parâmetros, se necessário.

   A **[!UICONTROL Column definition]** guia permite especificar com precisão a estrutura de dados de cada coluna para importar dados que não contenham erros (por exemplo, usando o gerenciamento nulo) e fazer com que eles correspondam aos tipos que já estão presentes no banco de dados do Adobe Campaign para operações futuras.

   Por exemplo, você pode alterar o rótulo de uma coluna, selecionar seu tipo (string, número inteiro, data etc.) ou até mesmo especifique o processamento de erros.

   For more information, refer to the [Column format](#column-format) section.

   ![](assets/wkf_file_loading4.png)

1. Na **[!UICONTROL Execution]** guia, especifique se o arquivo deve ser processado para carregar dados:

   * Vem de uma transição de entrada no fluxo de trabalho.
   * É aquele que você carregou durante a etapa anterior.
   * É um novo arquivo para carregar a partir do computador local. A **[!UICONTROL Upload a new file from local machine]** opção será exibida se o upload de um primeiro arquivo já tiver sido definido no fluxo de trabalho. Isso permite que você carregue outro arquivo a ser processado se o arquivo atual não atender às suas necessidades.

      ![](assets/wkf_file_loading1.png)

1. Se o arquivo do qual você deseja carregar os dados for compactado em um arquivo GZIP (.gz), selecione a **[!UICONTROL Decompression]** opção no **[!UICONTROL Add a pre-processing step]** campo. Isso permite descompactar o arquivo antes de carregar os dados. Essa opção só estará disponível se o arquivo for proveniente da transição de entrada do atividade.
1. A **[!UICONTROL Keep the rejects in a file]** opção permite baixar um arquivo que contém erros que ocorreram durante a importação e aplicar a ele uma etapa de pós-processamento. Quando a opção é ativada, a transição de saída é renomeada como &quot;Rejeita&quot;.

   >[!NOTE]
   >
   >A **[!UICONTROL Add date and time to the file name]** opção permite que você adicione um carimbo de data e hora ao nome do arquivo que contém os rejeitos.

   ![](assets/wkf_file_loading_keeprejects.png)

1. Confirme a configuração da atividade e salve o fluxo de trabalho.

Se ocorrer algum erro com a atividade após a execução do fluxo de trabalho, consulte os registros para obter mais detalhes sobre os valores que estão incorretos no arquivo. For more on workflows logs, refer to [this section](../../automating/using/monitoring-workflow-execution.md).

## Formato de coluna {#column-format}

Quando você carrega um arquivo de amostra, o formato da coluna é detectado automaticamente com os parâmetros padrão para cada tipo de dados. Você pode modificar esses parâmetros padrão para especificar os processos específicos a serem aplicados aos seus dados, principalmente quando há um erro ou um valor vazio.

Para fazer isso, selecione uma **[!UICONTROL Edit properties]** das ações rápidas da coluna cujo formato você deseja definir. A janela de detalhes do formato da coluna será aberta.

![](assets/wkf_file_loading4.png)

Em seguida, é possível modificar a formatação de cada coluna.

A formatação de coluna permite definir o processamento de valor de cada coluna:

* **[!UICONTROL Ignore column]**: não processa esta coluna durante o carregamento de dados.
* **[!UICONTROL Data type]**: especifica o tipo de dados esperado para cada coluna.
* **[!UICONTROL Format and separators]**, **Propriedades**: especifique as propriedades de um texto, a hora, a data e o formato de valor numérico, bem como o separador especificado pelo contexto da coluna.

   * **[!UICONTROL Maximum number of characters]**: especifica o número máximo de caracteres para colunas de tipo de string.

      Esse campo deve ser preenchido ao carregar arquivos compostos de colunas com comprimento fixo.

   * **[!UICONTROL Letter case management]**: define se um processo de caso de caractere precisa ser aplicado aos dados de **Texto** .
   * **[!UICONTROL White space management]**: especifica se determinados espaços precisam ser ignorados em uma string para dados de **Texto** .
   * **[!UICONTROL Time format]**, **[!UICONTROL Date format]**: especifique o formato dos dados de **Data**, **Hora** e **Data e Hora** .
   * **[!UICONTROL Format]**: permite que você defina o formato dos valores numéricos para **Inteiro** e dados de número **** flutuante.
   * **[!UICONTROL Separator]**: define o separador especificado pelo contexto da coluna (separador de milhares ou separador decimal para valores numéricos, separador para datas e hora) para dados de **Data**, **Hora**, **Data e hora**, **Número inteiro** e Número **** flutuante.

* **[!UICONTROL Remapping of values]**: esse campo só está disponível na configuração detalhada da coluna. Isso permite transformar certos valores quando eles são importados. Por exemplo, você pode transformar &quot;três&quot; em &quot;3&quot;.
* **[!UICONTROL Error processing]**: define o comportamento se um erro for encontrado.

   * **[!UICONTROL Ignore the value]**: o valor é ignorado. Um aviso é gerado no log de execução do workflow.
   * **[!UICONTROL Reject the line]**: a linha inteira não é processada.
   * **[!UICONTROL Use a default value]**: substitui o valor que causa o erro por um valor padrão, definido no **[!UICONTROL Default value]** campo.
   * **[!UICONTROL Use a default value in case the value is not remapped]**: substitui o valor que causa o erro por um valor padrão, definido no **[!UICONTROL Default value]** campo, a menos que um mapeamento tenha sido definido para o valor errado (consulte a **[!UICONTROL Remapping of values]** opção acima).
   * **[!UICONTROL Reject the line when there is no remapping value]**: a linha inteira não é processada a menos que um mapeamento tenha sido definido para o valor errado (consulte a **[!UICONTROL Remapping of values]** opção acima).
   >[!NOTE]
   >
   >**[!UICONTROL Error processing]** refere-se a erros referentes a valores no arquivo importado. Por exemplo, um tipo de dados com falha foi encontrado (&quot;quatro&quot; em letras para uma coluna &quot;Número inteiro&quot;), uma string contendo mais caracteres do que o número máximo autorizado, uma data com separadores com falha etc. No entanto, essa opção não diz respeito a erros gerados pelo gerenciamento de valores vazio.

* **[!UICONTROL Default value]**: especifica o valor padrão de acordo com o processamento de erros escolhido.
* **[!UICONTROL Empty value management]**: especifica como gerenciar valores vazios durante o carregamento de dados.

   * **[!UICONTROL Generate an error for numerical fields]**: gera um erro apenas para os campos numéricos, caso contrário, insere um valor NULL.
   * **[!UICONTROL Insert NULL in the corresponding field]**: autoriza valores vazios. O valor NULL é então inserido.
   * **[!UICONTROL Generate an error]**: gera um erro se um valor estiver vazio.

## Exemplo 1: Atualização do banco de dados {#example-1-update-the-database}

A atividade load file estrutura principalmente os dados de uma atividade de arquivo de transferência para integrá-los aos dados existentes.

O exemplo a seguir mostra o resultado de uma atividade de arquivo de carregamento automaticamente baixada por meio de uma atividade de arquivo de transferência, seguido por uma atividade de dados de atualização. Esse fluxo de trabalho tem como objetivo aprimorar o banco de dados do Adobe Campaign com novos perfis ou atualizar perfis existentes usando os dados recuperados do arquivo importado.

![](assets/load_file_workflow_ex1.png)

1. Arraste e solte uma **[!UICONTROL Transfer file]** atividade em seu fluxo de trabalho e configure-a de uma maneira que recupere o arquivo que você deseja.
1. Arraste e solte uma **[!UICONTROL Load file]** atividade no seu fluxo de trabalho e coloque-a depois da **[!UICONTROL Transfer file]** atividade.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Na **[!UICONTROL File to load]** seção da **[!UICONTROL Execution]** guia, marque a **[!UICONTROL Use the file specified in the inbound transition]** opção.

   ![](assets/wkf_file_loading8.png)

1. Configure sua atividade conforme especificado anteriormente.
1. Arraste e solte uma **[!UICONTROL Update data]** atividade em seu fluxo de trabalho e coloque-a depois da **[!UICONTROL Load file]** atividade e configure-a. Refer to [Update data](../../automating/using/update-data.md).

Depois que o fluxo de trabalho é iniciado, os dados do arquivo carregado são extraídos e depois usados para enriquecer o banco de dados do Adobe Campaign.

## Exemplo 2: Envio de um email com campos aprimorados {#example-2-email-with-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

A atividade de carregamento de arquivo também permite enviar um email enriquecido com dados adicionais de um arquivo externo no mesmo fluxo de trabalho.

O exemplo abaixo mostra como enviar um email usando dados adicionais recuperados de um arquivo externo por meio da atividade de arquivo de carregamento. Neste exemplo, o arquivo externo contém uma lista de perfis com seu número de conta associado. Você deseja importar esses dados para enviar um email para cada perfil com o número da conta.

![](assets/load_file_workflow_ex2.png)

1. Arraste e solte uma **[!UICONTROL Query]** atividade no seu fluxo de trabalho e abra-a para definir o público alvo principal.

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. Arraste e solte uma **[!UICONTROL Load file]** atividade para atribuir alguns dados a um perfil. Neste exemplo, carregue um arquivo contendo números de conta correspondentes a alguns perfis do banco de dados.

   ![](assets/load_file_activity.png)

1. Arraste e solte uma **[!UICONTROL Enrichment]** atividade em seu fluxo de trabalho e vincule o arquivo de carregamento e as atividades do query a ele.

1. Na **[!UICONTROL Advanced relations]** guia da atividade do enriquecimento, selecione **[!UICONTROL 0 or 1 cardinality simple link]** e defina os campos a serem usados para reconciliação. Aqui usamos o sobrenome para reconciliar os dados com os perfis do banco de dados.

   ![](assets/load_file_enrichment_relation.png)

1. Na **[!UICONTROL Additional data]** guia, selecione os elementos que deseja usar no seu email. Aqui, selecione Número da conta (coluna do arquivo que você recuperou por meio da atividade do arquivo de carregamento).

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   Para obter mais informações, consulte a seção [Enriquecimentos](../../automating/using/enrichment.md) .

1. Arraste e solte uma **[!UICONTROL Segmentation]** atividade no seu fluxo de trabalho e abra-a para refinar o público alvo principal.

   ![](assets/load_file_segmentation.png)

   Para obter mais informações, consulte a seção [Segmentação](../../automating/using/segmentation.md) .

1. Arraste e solte uma **[!UICONTROL Email delivery]** atividade no seu fluxo de trabalho e abra-a.

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. Adicione um campo de personalização e selecione os dados adicionais definidos na atividade do enriquecimento (aqui Número da conta) do **[!UICONTROL Additional data (targetData)]** nó. Isso permite recuperar dinamicamente o número de conta de cada perfil no conteúdo do email.

   ![](assets/load_file_perso_field.png)

1. Salve o e-mail e o start do fluxo de trabalho.

O email é enviado ao público alvo. Cada perfil recebe o e-mail com seu número de conta correspondente.

![](assets/load_file_email.png)
