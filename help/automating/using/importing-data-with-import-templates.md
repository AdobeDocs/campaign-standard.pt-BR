---
title: Importação de dados com modelos de importação
description: Saiba como coletar dados para alimentar seu banco de dados do Campaign.
page-status-flag: nunca ativado
uuid: bfc03235-2032-448a-a9ed-21ff2a83fa09
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: importar e exportar dados
discoiquuid: fb511bb8-6be7-43f6-86ab-94d5cfa3efc9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Importação de dados com modelos de importação{#importing-data-with-import-templates}

A importação de dados permite coletar dados para alimentar o banco de dados do Campaign.

Como alternativa para [Fluxos de trabalho](../../automating/using/discovering-workflows.md), o Adobe Campaign oferece uma função de importação simplificada que permite ao usuário gerenciar certos tipos de importação definidos por um administrador.

O princípio de funcionamento é o seguinte: um **administrador** define e gerencia modelos de importação (consulte [Definição de modelos](../../automating/using/defining-import-templates.md)de importação). Esses modelos de importação ficam disponíveis para usuários com exibições simplificadas no menu **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Imports]** .

Portanto, esses usuários precisam apenas selecionar o tipo de importação que desejam realizar e fazer upload do arquivo com os dados a serem importados. O fluxo de trabalho definido pelo administrador é executado de forma transparente para o usuário, que pode acessar os detalhes do resultado da importação após sua conclusão.

>[!NOTE]
>
>Import data function can be managed by users with **[!UICONTROL GENERIC IMPORT (import)]** and **[!UICONTROL WORKFLOW (workflow)]** roles. Para saber mais sobre as funções, consulte [esta seção](../../administration/using/list-of-roles.md).

As importações podem ser filtradas de acordo com o modelo a partir do qual foram executadas, sua data de execução e seu status de execução.

1. Na visão geral das importações, clique no **[!UICONTROL Create]** botão. O assistente é aberto.
1. Selecione o tipo de importação que deseja realizar. Os tipos de importação correspondem aos modelos de importação disponíveis.
1. Se necessário, baixe o arquivo de amostra vinculado ao modelo no computador para exibir os tipos de dados esperados no arquivo a ser importado.
1. Baixe o arquivo que contém os dados a serem importados no assistente.
1. Inicie a importação. O assistente o fecha e o leva de volta à lista de importações realizadas com o modelo usado.
1. Atualize sua página e selecione a importação que você acabou de realizar para exibir os detalhes da execução.

   ![](assets/simplified_import1.png)

Os detalhes da execução da importação estão disponíveis. Tanto o arquivo importado quanto o que contém os dados rejeitados (dados que não foram importados) podem ser baixados para o computador.
