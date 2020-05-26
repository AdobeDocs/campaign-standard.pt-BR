---
title: Definição de modelos de importação
description: Templates de importação permitem reduzir as configurações necessárias e importar dados mais rapidamente.
page-status-flag: never-activated
uuid: 651eb57c-adac-4e3e-b454-b39aea1f0484
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: 85d13147-fb31-446a-8476-f112c841fb82
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 1%

---


# Definição de modelos de importação{#defining-import-templates}

Os Templates de importação permitem que o administrador pré-defina um certo número de configurações técnicas de importação. Esses modelos podem ser disponibilizados para usuários padrão para realizar e fazer upload de arquivos.

Um template de importação é definido pelo administrador funcional e pode ser gerenciado no menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Import templates]** .

![](assets/import_template_list.png)

Três modelos padrão somente leitura estão disponíveis:

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**: este modelo pode servir de base para novas importações para atualizar quarentenas e logs do delivery de mala direta. O fluxo de trabalho do modelo contém as seguintes atividades:
* **[!UICONTROL Import data]**: esse modelo pode servir de base para novas importações inserirem dados de um arquivo no banco de dados. O fluxo de trabalho deste modelo contém as seguintes atividades:

   * **[!UICONTROL Load file]**: esta atividade permite carregar um arquivo no servidor Adobe Campaign.
   * **[!UICONTROL Update data]**: essa atividade permite inserir dados do arquivo no banco de dados.

* **[!UICONTROL Import list]**: este modelo pode servir de base para novas importações para criar uma audiência de tipo de **Lista** a partir de dados em um arquivo. O fluxo de trabalho deste modelo contém as seguintes atividades:

   * **[!UICONTROL Load file]**: esta atividade permite carregar um arquivo no servidor Adobe Campaign.
   * **[!UICONTROL Reconciliation]**: essa atividade permite vincular um targeting dimension aos dados importados. Isso permite criar uma audiência do tipo **Lista** . Se o targeting dimension dos dados importados não for conhecido, a audiência será do tipo **Arquivo** . Consulte [Targeting dimension e recursos](../../automating/using/query.md#targeting-dimensions-and-resources).
   * **[!UICONTROL Save audience]**: essa atividade permite salvar dados importados na forma de uma audiência do tipo **Lista** . O nome da audiência salva corresponde ao nome do arquivo importado pelo usuário e um sufixo que especifica a data e a hora da importação será adicionado. Por exemplo: &#39;perfis_20150406_151448&#39;.

Esses modelos padrão são somente leitura e não estão visíveis para usuários padrão. Para criar um modelo que estará disponível para os usuários, siga estas etapas:

1. Duplicado um modelo padrão. O modelo duplicado contém três guias:

   * **[!UICONTROL Properties]**: os parâmetros gerais do template de importação. Esta guia permite ativar o modelo e fazer upload de um arquivo de amostra.
   * **[!UICONTROL Workflow]**: importar fluxo de trabalho. Essa guia permite que você defina as atividades do fluxo de trabalho. Estas atividades não são visíveis durante as importações simplificadas efetuadas pelos utilizadores.
   * **[!UICONTROL Executed imports]**: lista das importações efetuadas utilizando este modelo. Você pode visualização o status, os detalhes e os resultados de cada importação realizada usando este modelo. Você pode acessar diretamente o fluxo de trabalho (realizado de forma transparente para o usuário) desta lista.

1. Na **[!UICONTROL Properties]** guia, renomeie o modelo e adicione uma descrição. Os usuários poderão visualização na descrição quando o modelo estiver disponível.

   ![](assets/simplified_import_model1.png)

1. Go to the **[!UICONTROL Workflow]** tab. Aqui você pode enriquecer o fluxo de trabalho oferecido por padrão adicionando novas atividades de acordo com suas necessidades.

   Para obter mais informações sobre como configurar as atividades de fluxo de trabalho, consulte o caso de uso descrito nesta seção: [Exemplo: Importar modelo](../../automating/using/creating-import-workflow-templates.md)de fluxo de trabalho. Esse caso de uso ajudará você a configurar um fluxo de trabalho que pode ser reutilizado para importar perfis provenientes de um CRM no banco de dados do Adobe Campaign.

1. Salve o modelo para que a configuração do fluxo de trabalho seja considerada corretamente.
1. Carregue um arquivo de amostra na **[!UICONTROL Properties]** guia. O arquivo carregado só pode ter colunas necessárias para importações futuras ou dados de amostra. Os dados no arquivo de amostra permitem testar a importação simplificada assim que o fluxo de trabalho for definido.

   ![](assets/import_template_sample.png)

   Esse arquivo de amostra estará disponível para usuários que usam o modelo para realizar uma importação. Eles poderão baixá-lo em seus computadores, por exemplo, para preenchê-lo com dados a serem importados. Considere isso ao adicionar um arquivo de amostra.

1. Salve o modelo. O arquivo de amostra agora é considerado. A qualquer momento, você pode baixá-lo em seu computador para verificar o conteúdo ou modificá-lo marcando a **[!UICONTROL Drop a new sample file]** opção.

   ![](assets/simplified_import_model2.png)

1. Retorne à guia **[!UICONTROL Workflow]** e abra a **[!UICONTROL Load file]** atividade para verificar e ajustar a configuração da coluna do arquivo de amostra que foi carregado na etapa anterior.
1. Teste a importação iniciando o fluxo de trabalho. O arquivo de amostra carregado na etapa **5** deve conter dados.

   Os dados do arquivo de amostra são, então, genuinamente importados. Certifique-se de que os dados usados sejam pequenos e fictícios para garantir que seu banco de dados não fique comprometido.

1. Vá para o log de execução do fluxo de trabalho, disponível na barra de ações. Se encontrar um erro, verifique se o atividade está configurado corretamente.

   ![](assets/simplified_import_model3.png)

1. Na **[!UICONTROL Properties]** guia, defina como **[!UICONTROL Import template status]** e, em seguida, salve o modelo **[!UICONTROL Available]**. Para parar de usar este modelo, você pode definir **[!UICONTROL Import template status]** como **[!UICONTROL Archived]**.

O fluxo de trabalho do modelo pode ser modificado fazendo o upload do arquivo de amostra e verificando a **[!UICONTROL Load file]** configuração.

O template de importação agora está disponível para os usuários e pode ser usado para carregar arquivos.

**Tópicos relacionados:**

* [Workflows](../../automating/using/get-started-workflows.md)
* [Importação e exportação de dados](../../automating/using/about-data-import-and-export.md)
* [Exemplo: Importar modelo de fluxo de trabalho](../../automating/using/creating-import-workflow-templates.md)

