---
title: Importação de dados com modelos de importação
description: Saiba como coletar dados para alimentar seu banco de dados de Campanhas.
page-status-flag: never-activated
uuid: bfc03235-2032-448a-a9ed-21ff2a83fa09
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: fb511bb8-6be7-43f6-86ab-94d5cfa3efc9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 1%

---


# Importação de dados com modelos de importação{#importing-data-with-import-templates}

A importação de dados permite coletar dados para alimentar o banco de dados do Campaign.

Como alternativa para [Workflows](../../automating/using/get-started-workflows.md), o Adobe Campaign oferta uma função de importação simplificada que permite ao usuário gerenciar certos tipos de importação que foram definidos por um administrador.

O princípio de funcionamento é o seguinte: um **administrador** define e gerencia templates de importação (consulte [Definição de templates de importação](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)). Esses templates de importação são então disponibilizados para usuários com visualizações simplificadas no menu **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Imports]** .

Portanto, esses usuários precisam apenas selecionar o tipo de importação que desejam realizar e fazer upload do arquivo com os dados a serem importados. O fluxo de trabalho definido pelo administrador é executado de forma transparente para o usuário, que pode acessar os detalhes do resultado da importação após sua conclusão.

>[!NOTE]
>
>Import data function can be managed by users with **[!UICONTROL GENERIC IMPORT (import)]** and **[!UICONTROL WORKFLOW (workflow)]** roles. Para saber mais sobre as funções, consulte [esta seção](../../administration/using/list-of-roles.md).

As importações podem ser filtradas de acordo com o modelo a partir do qual foram executadas, sua data de execução e seu status de execução.

1. Na visão geral das importações, clique no **[!UICONTROL Create]** botão. O assistente é aberto.
1. Selecione o tipo de importação que deseja realizar. Os tipos de importação correspondem aos templates de importação disponíveis.
1. Se necessário, baixe o arquivo de amostra vinculado ao modelo no computador para visualização dos tipos de dados esperados no arquivo a ser importado.
1. Baixe o arquivo que contém os dados a serem importados no assistente.
1. Start a importação. O assistente o fecha e o leva de volta à lista de importações realizadas com o modelo usado.
1. Atualize sua página e selecione a importação que você acabou de realizar para visualização dos detalhes de execução.

   ![](assets/simplified_import1.png)

Os detalhes da execução da importação estão disponíveis. Tanto o arquivo importado quanto o que contém os dados rejeitados (dados que não foram importados) podem ser baixados para o computador.

## Configuração de templates de importação {#setting-up-import-templates}

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
* [Exemplo: Importar modelo de fluxo de trabalho](../../automating/using/creating-import-workflow-templates.md)
