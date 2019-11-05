---
title: Definição de modelos de importação
description: Os modelos de importação permitem reduzir as configurações necessárias e importar dados mais rapidamente.
page-status-flag: nunca ativado
uuid: 651eb57c-adac-4e3e-b454-b39aea1f0484
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: importar e exportar dados
discoiquuid: 85d13147-fb31-446a-8476-f112c841fb82
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Definição de modelos de importação{#defining-import-templates}

Os modelos de importação permitem que o administrador pré-defina um certo número de configurações técnicas de importação. Esses modelos podem ser disponibilizados para usuários padrão para realizar e fazer upload de arquivos.

Um modelo de importação é definido pelo administrador funcional e pode ser gerenciado no menu **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Import templates]** .

![](assets/import_template_list.png)

Três modelos padrão somente leitura estão disponíveis:

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**: este modelo pode servir de base para novas importações atualizarem quarentena e registros de entrega para a Mala direta. O fluxo de trabalho do modelo contém as seguintes atividades:
* **[!UICONTROL Import data]**: esse modelo pode servir de base para novas importações inserirem dados de um arquivo no banco de dados. O fluxo de trabalho deste modelo contém as seguintes atividades:

   * **[!UICONTROL Load file]**: essa atividade permite carregar um arquivo no servidor do Adobe Campaign.
   * **[!UICONTROL Update data]**: essa atividade permite inserir dados do arquivo no banco de dados.

* **[!UICONTROL Import list]**: este modelo pode servir de base para novas importações para criar um público-alvo do tipo **Lista** a partir de dados em um arquivo. O fluxo de trabalho deste modelo contém as seguintes atividades:

   * **[!UICONTROL Load file]**: essa atividade permite carregar um arquivo no servidor do Adobe Campaign.
   * **[!UICONTROL Reconciliation]**: essa atividade permite que você vincule uma dimensão de definição de metas aos dados importados. Isso permite criar um público-alvo do tipo **Lista** . Se a dimensão de definição de metas dos dados importados não for conhecida, o público-alvo será o tipo **Arquivo** . Consulte Dimensões e recursos [de](../../automating/using/query.md#targeting-dimensions-and-resources)definição de metas.
   * **[!UICONTROL Save audience]**: essa atividade permite salvar dados importados no formulário de um público-alvo do tipo **Lista** . O nome do público-alvo salvo corresponde ao nome do arquivo importado pelo usuário e um sufixo que especifica a data e a hora da importação será adicionado.  Por exemplo: 'profile_20150406_151448'.

Esses modelos padrão são somente leitura e não estão visíveis para usuários padrão. Para criar um modelo que estará disponível para os usuários, siga estas etapas:

1. Duplicar um modelo padrão. O modelo duplicado contém três guias:

   * **[!UICONTROL Properties]**: os parâmetros gerais do modelo de importação. Esta guia permite ativar o modelo e fazer upload de um arquivo de amostra.
   * **[!UICONTROL Workflow]**: importar fluxo de trabalho. Essa guia permite que você defina as atividades do fluxo de trabalho. Estas atividades não são visíveis durante as importações simplificadas efetuadas pelos utilizadores.
   * **[!UICONTROL Executed imports]**: lista das importações efetuadas utilizando este modelo. Você pode exibir o status, os detalhes e os resultados de cada importação realizada usando este modelo. Você pode acessar diretamente o fluxo de trabalho (realizado de forma transparente para o usuário) nesta lista.

1. Na **[!UICONTROL Properties]** guia, renomeie o modelo e adicione uma descrição. Os usuários poderão exibir a descrição quando o modelo estiver disponível.

   ![](assets/simplified_import_model1.png)

1. Vá para a **[!UICONTROL Workflow]** guia. Aqui você pode enriquecer o fluxo de trabalho oferecido por padrão adicionando novas atividades de acordo com suas necessidades.

   Para obter mais informações sobre como configurar as atividades do fluxo de trabalho, consulte o caso de uso descrito nesta seção: [Exemplo: Importar modelo](../../automating/using/importing-data.md#example--import-workflow-template)de fluxo de trabalho. Esse caso de uso ajudará você a configurar um fluxo de trabalho que pode ser reutilizado para importar perfis provenientes de um CRM no banco de dados do Adobe Campaign.

1. Salve o modelo para que a configuração do fluxo de trabalho seja considerada corretamente.
1. Carregue um arquivo de amostra na **[!UICONTROL Properties]** guia. O arquivo carregado só pode ter colunas necessárias para importações futuras ou dados de amostra. Os dados no arquivo de amostra permitem testar a importação simplificada assim que o fluxo de trabalho for definido.

   ![](assets/import_template_sample.png)

   Esse arquivo de amostra estará disponível para usuários que usam o modelo para realizar uma importação. Eles poderão baixá-lo em seus computadores, por exemplo, para preenchê-lo com dados a serem importados. Considere isso ao adicionar um arquivo de amostra.

1. Salve o modelo. O arquivo de amostra agora é considerado. A qualquer momento, você pode baixá-lo em seu computador para verificar o conteúdo ou modificá-lo marcando a **[!UICONTROL Drop a new sample file]** opção.

   ![](assets/simplified_import_model2.png)

1. Retorne à guia **[!UICONTROL Workflow]** e abra a **[!UICONTROL Load file]** atividade para verificar e ajustar a configuração da coluna do arquivo de amostra que foi carregado na etapa anterior.
1. Teste a importação iniciando o fluxo de trabalho. O arquivo de amostra carregado na etapa **5** deve conter dados.

   Os dados do arquivo de amostra são importados genuinamente. Verifique se os dados usados são pequenos e fictícios para garantir que seu banco de dados não fique comprometido.

1. Vá para o log de execução do fluxo de trabalho, disponível na barra de ações. Se encontrar um erro, verifique se as atividades estão configuradas corretamente.

   ![](assets/simplified_import_model3.png)

1. Na **[!UICONTROL Properties]** guia, defina como **[!UICONTROL Import template status]** e, em seguida, salve o modelo **[!UICONTROL Available]**. Para parar de usar este modelo, você pode definir **[!UICONTROL Import template status]** como **[!UICONTROL Archived]**.

O fluxo de trabalho do modelo pode ser modificado fazendo o upload do arquivo de amostra e verificando a **[!UICONTROL Load file]** configuração.

O modelo de importação agora está disponível para os usuários e pode ser usado para carregar arquivos.

**Tópicos relacionados:**

* [Fluxos de trabalho](../../automating/using/discovering-workflows.md)
* [Importação de dados](../../automating/using/importing-data.md)
* [Exemplo: Importar modelo de fluxo de trabalho](../../automating/using/importing-data.md#example--import-workflow-template)

