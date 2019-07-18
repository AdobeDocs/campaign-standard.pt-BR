---
title: Definição de modelos de importação
seo-title: Definição de modelos de importação
description: Definição de modelos de importação
seo-description: Importe modelos para reduzir as configurações necessárias e importar dados mais rapidamente.
page-status-flag: nunca ativado
uuid: 651 eb 57 c-adac -4 e 3 e-b 454-b 39 aea 1 f 0484
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: importar e exportar dados
discoiquuid: 85 d 13147-fb 31-446 a -8476-f 112 c 841 fb 82
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Defining import templates{#defining-import-templates}

Importar modelos permite que o administrador pré-defina um determinado número de configurações de importação técnicas. Esses modelos podem ser disponibilizados para que usuários padrão executem e carreguem arquivos.

An import template is defined by the functional administrator and can be managed under the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Import templates]** menu.

![](assets/import_template_list.png)

Três modelos padrão somente leitura estão disponíveis:

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**: este modelo pode servir como base para novas importações para atualizar quarentena e logs de entrega para a correspondência direta. O fluxo de trabalho do modelo contém as seguintes atividades:
* **[!UICONTROL Import data]**: este modelo pode servir como base para novas importações para inserir dados de um arquivo no banco de dados. O fluxo de trabalho desse modelo contém as seguintes atividades:

   * **[!UICONTROL Load file]**: essa atividade permite carregar um arquivo no servidor do Adobe Campaign.
   * **[!UICONTROL Update data]**: essa atividade permite inserir dados do arquivo no banco de dados.

* **[!UICONTROL Import list]**: este modelo pode servir como base para novas importações para criar um público-alvo **de** tipo de lista a partir de dados em um arquivo. O fluxo de trabalho desse modelo contém as seguintes atividades:

   * **[!UICONTROL Load file]**: essa atividade permite carregar um arquivo no servidor do Adobe Campaign.
   * **[!UICONTROL Reconciliation]**: essa atividade permite vincular uma dimensão de direcionamento a dados importados. This then allows you to create a **List** type audience. If the targeting dimension of the imported data is not known, the audience is **File** type. See [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
   * **[!UICONTROL Save audience]**: essa atividade permite salvar dados importados na forma de um público-alvo de tipo **de lista** . O nome do público-alvo salvo corresponde ao nome do arquivo importado pelo usuário, e um sufixo que especifica a data e a hora da importação será adicionado. Por exemplo: ' profiles_ 20150406_ 151448 '.

Esses modelos padrão são somente leitura e não estão visíveis para usuários padrão. Para criar um modelo que estará disponível para os usuários, siga estas etapas:

1. Duplicar um modelo padrão. O modelo duplicado contém três guias:

   * **[!UICONTROL Properties]**: os parâmetros gerais do modelo de importação. Essa guia permite ativar o modelo e fazer upload de um arquivo de amostra.
   * **[!UICONTROL Workflow]**: fluxo de trabalho de importação. Esta guia permite definir as atividades do fluxo de trabalho. Essas atividades não são visíveis durante as importações simplificadas realizadas pelos usuários.
   * **[!UICONTROL Executed imports]**: lista de importações realizadas usando este modelo. Você pode exibir o status, os detalhes e os resultados de cada importação realizada usando este modelo. Você pode acessar diretamente o fluxo de trabalho (realizada de maneira transparente para o usuário) nesta lista.

1. From the **[!UICONTROL Properties]** tab, rename the template and add a description. Os usuários poderão visualizar a descrição quando o modelo estiver disponível.

   ![](assets/simplified_import_model1.png)

1. Go to the **[!UICONTROL Workflow]** tab. Aqui, você pode aprimorar o fluxo de trabalho oferecido por padrão, adicionando novas atividades de acordo com suas necessidades.

   For more on how to configure the workflow activities, refer to the use case describe in this section: [Example: Import workflow template](../../automating/using/importing-data.md#example--import-workflow-template). Esse caso de uso ajudará a configurar um fluxo de trabalho que pode ser reutilizado para importar perfis provenientes de um CRM no banco de dados do Adobe Campaign.

1. Salve o modelo para que a configuração do fluxo de trabalho seja levada em consideração corretamente.
1. Upload a sample file from the **[!UICONTROL Properties]** tab. O arquivo carregado pode ter apenas colunas necessárias para importações futuras ou dados de amostra. Os dados no arquivo de amostra permitem testar a importação simplificada após a definição do fluxo de trabalho.

   ![](assets/import_template_sample.png)

   Esse arquivo de amostra estará disponível para os usuários que usam o modelo para realizar uma importação. Eles poderão fazer o download em seu computador, por exemplo, para preenchê-lo com dados a serem importados. Certifique-se de considerar isso ao adicionar um arquivo de amostra.

1. Salve o modelo. O arquivo de amostra agora é levado em consideração. At any moment you can download it to your computer to check the content, or modify it by checking the **[!UICONTROL Drop a new sample file]** option.

   ![](assets/simplified_import_model2.png)

1. Go back to the **[!UICONTROL Workflow]** tab and open the **[!UICONTROL Load file]** activity to check and adjust the column configuration of the sample file that was uploaded at the previous step.
1. Teste a importação iniciando o fluxo de trabalho. The sample file uploaded at step **5** has to contain data.

   Os dados do arquivo de amostra são importados corretamente. Certifique-se de que os dados usados sejam pequenos e fictícios para garantir que o banco de dados não esteja comprometido.

1. Acesse o log de execução do fluxo de trabalho, disponível na barra de ações. Se você encontrar um erro, verifique se as atividades estão configuradas corretamente.

   ![](assets/simplified_import_model3.png)

1. In the **[!UICONTROL Properties]** tab, set the **[!UICONTROL Import template status]** to **[!UICONTROL Available]**, then save the template. To stop using this template, you can set the **[!UICONTROL Import template status]** to **[!UICONTROL Archived]**.

The template workflow can be modified by re-uploading the sample file and checking the **[!UICONTROL Load file]** configuration.

O modelo de importação agora está disponível para os usuários e pode ser usado para carregar arquivos.

**Tópicos relacionados:**

* [Fluxos de trabalho](../../automating/using/discovering-workflows.md)
* [Importação de dados](../../automating/using/importing-data.md)
* [Exemplo: Importar modelo de fluxo de trabalho](../../automating/using/importing-data.md#example--import-workflow-template)

