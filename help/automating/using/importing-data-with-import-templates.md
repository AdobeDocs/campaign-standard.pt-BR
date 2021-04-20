---
solution: Campaign Standard
product: campaign
title: Importação de dados com modelos de importação
description: Saiba como coletar dados para alimentar seu banco de dados do Campaign.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1094'
ht-degree: 99%

---


# Importação de dados com modelos de importação{#importing-data-with-import-templates}

A importação de dados permite coletar dados para alimentar o banco de dados do Campaign.

Como alternativa para os [Fluxos de trabalho](../../automating/using/get-started-workflows.md), o Adobe Campaign oferece uma função de importação simplificada com a qual o usuário gerencia certos tipos de importação que foram definidos por um administrador.

O princípio de execução é o seguinte: um **administrador** define e gerencia modelos de importação (consulte [Definição de modelos de importação](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)). Esses modelos de importação são então disponibilizados a usuários com visualizações simplificadas no menu **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Imports]**.

Portanto, esses usuários só precisam selecionar o tipo de importação que desejam realizar e fazer upload do arquivo com os dados que serão importados. O fluxo de trabalho definido pelo administrador é executado de forma transparente para o usuário, que pode acessar os detalhes do resultado da importação após a conclusão.

>[!NOTE]
>
>A função Importar dados pode ser gerenciada por usuários com as funções **[!UICONTROL GENERIC IMPORT (import)]** e **[!UICONTROL WORKFLOW (workflow)]**. Para saber mais sobre funções, consulte [esta seção](../../administration/using/list-of-roles.md).

As importações podem ser filtradas de acordo com o modelo a partir do qual foram executadas, sua data de execução e seu status de execução.

1. Na visão geral das importações, clique no botão **[!UICONTROL Create]**. O assistente é aberto.
1. Selecione o tipo de importação que deseja realizar. Os tipos de importação correspondem aos modelos de importação disponíveis.
1. Se necessário, baixe o arquivo de amostra vinculado ao modelo no seu computador para exibir os tipos de dados esperados no arquivo que será importado.
1. Baixe o arquivo que contém os dados que serão importados no assistente.
1. Inicie a importação. O assistente fecha e você é direcionado de volta à lista de importações feitas com o modelo usado.
1. Atualize a página e selecione a importação que acabou de fazer para exibir os detalhes da execução.

   ![](assets/simplified_import1.png)

Os detalhes da execução da importação agora estão disponíveis. Tanto o arquivo importado quanto o que contém os dados rejeitados (dados que não foram importados) podem ser baixados no computador.

## Configuração de modelos de importação {#setting-up-import-templates}

Os templates de importação permitem que o administrador predefina um certo número de configurações técnicas de importação. Esses templates depois podem ser disponibilizados para os usuários padrão executarem e fazerem upload de arquivos.

Um template de importação é definido pelo administrador funcional e pode ser gerenciado no menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Import templates]**.

![](assets/import_template_list.png)

Três templates padrão somente leitura estão disponíveis:

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**: este template pode servir como base das novas importações para atualizar quarentenas e logs de delivery de correspondência direta. O fluxo de trabalho do template contém as seguintes atividades:
* **[!UICONTROL Import data]**: este template pode servir como base das novas importações para inserir dados de um arquivo no banco de dados. O fluxo de trabalho desse template contém as seguintes atividades:

   * **[!UICONTROL Load file]**: esta atividade permite fazer upload de um arquivo no servidor do Adobe Campaign.
   * **[!UICONTROL Update data]**: esta atividade permite inserir dados do arquivo no banco de dados.

* **[!UICONTROL Import list]**: este template pode servir como base das novas importações para criar um público-alvo do tipo **Lista** dos dados de um arquivo. O fluxo de trabalho desse template contém as seguintes atividades:

   * **[!UICONTROL Load file]**: esta atividade permite fazer upload de um arquivo no servidor do Adobe Campaign.
   * **[!UICONTROL Reconciliation]**: esta atividade permite vincular um targeting dimension aos dados importados. Depois, é possível criar um público-alvo do tipo **Lista**. Se o targeting dimension dos dados importados não for conhecido, o público-alvo será do tipo **File**. Consulte [Targeting dimensions e recursos](../../automating/using/query.md#targeting-dimensions-and-resources).
   * **[!UICONTROL Save audience]**: esta atividade permite salvar os dados importados na forma de um público-alvo do tipo **Lista**. O nome do público-alvo salvo corresponde ao nome do arquivo importado pelo usuário, e um sufixo que especifica a data e hora da importação será adicionado. Por exemplo: &#39;profiles_20150406_151448&#39;.

Esses templates padrão são somente leitura e não estão visíveis para usuários padrão. Para criar um template que estará disponível aos usuários, siga estas etapas:

1. Duplique um template padrão. O template duplicado contém três guias:

   * **[!UICONTROL Properties]**: os parâmetros gerais do template de importação. Essa guia permite ativar o template e fazer upload de um arquivo de amostra.
   * **[!UICONTROL Workflow]**: fluxo de trabalho de importação. Essa guia permite definir as atividades do fluxo de trabalho. Essas atividades não estão visíveis durante as importações simplificadas feitas pelos usuários.
   * **[!UICONTROL Executed imports]**: lista das importações feitas com este template. Você pode exibir o status, os detalhes e os resultados de cada importação feita usando este template. Você pode acessar o fluxo de trabalho diretamente (feito de maneira transparente para o usuário) desta lista.

1. Na guia **[!UICONTROL Properties]**, renomeie o template e adicione uma descrição. Os usuários poderão exibir a descrição quando o template estiver disponível.

   ![](assets/simplified_import_model1.png)

1. Acesse a guia **[!UICONTROL Workflow]**. Aqui você pode enriquecer o fluxo de trabalho oferecido por padrão adicionando novas atividades de acordo com suas necessidades.

   Para saber mais sobre como configurar as atividades de fluxo de trabalho, consulte o caso de uso descrito nesta seção: [Exemplo: importar template de fluxo de trabalho](../../automating/using/creating-import-workflow-templates.md). Esse caso de uso ajudará você a configurar um fluxo de trabalho que poderá ser reutilizado para importar os perfis de um CRM no banco de dados do Adobe Campaign.

1. Salve o template para que a configuração do fluxo de trabalho seja considerada corretamente.
1. Carregue um arquivo de amostra da guia **[!UICONTROL Properties]**. O arquivo carregado só poderá ter colunas necessárias para importações futuras ou dados de amostra. Os dados no arquivo de amostra permitem testar a importação simplificada assim que o fluxo de trabalho for definido.

   ![](assets/import_template_sample.png)

   Esse arquivo de amostra estará disponível para quem usa o template para fazer uma importação. Os usuários poderão baixá-lo nos computadores, por exemplo, para preenchê-lo com os dados a serem importados. Considere isso ao adicionar um arquivo de amostra.

1. Salve o template. O arquivo de amostra agora é considerado. Você poderá baixá-lo a qualquer momento no computador para verificar o conteúdo ou modificá-lo marcando a opção **[!UICONTROL Drop a new sample file]**.

   ![](assets/simplified_import_model2.png)

1. Retorne à guia **[!UICONTROL Workflow]** e abra a atividade **[!UICONTROL Load file]** para verificar e ajustar a configuração da coluna do arquivo de amostra que foi carregado na etapa anterior.
1. Teste a importação iniciando o fluxo de trabalho. O arquivo de amostra carregado na etapa **5** deve conter dados.

   Em seguida, os dados do arquivo de amostra são importados. Verifique se os dados usados são pequenos e fictícios para não comprometer seu banco de dados.

1. Vá para o log de execução do fluxo de trabalho, disponível na barra de ação. Se encontrar um erro, verifique se as atividades estão configuradas corretamente.

   ![](assets/simplified_import_model3.png)

1. Na guia **[!UICONTROL Properties]**, defina o **[!UICONTROL Import template status]** como **[!UICONTROL Available]** e salve o template. Para interromper o uso desse template, você pode definir o **[!UICONTROL Import template status]** como **[!UICONTROL Archived]**.

O fluxo de trabalho do template pode ser modificado fazendo novamente o upload do arquivo de amostra e verificando a configuração **[!UICONTROL Load file]**.

O template de importação agora está disponível para os usuários e pode ser usado para fazer upload de arquivos.

**Tópicos relacionados:**

* [Fluxos de trabalho](../../automating/using/get-started-workflows.md)
* [Exemplo: importar template de fluxo de trabalho](../../automating/using/creating-import-workflow-templates.md)
