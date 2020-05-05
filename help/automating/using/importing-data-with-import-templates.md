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
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Importação de dados com modelos de importação{#importing-data-with-import-templates}

A importação de dados permite coletar dados para alimentar o banco de dados do Campaign.

Como alternativa para [Workflows](../../automating/using/get-started-workflows.md), o Adobe Campaign oferta uma função de importação simplificada que permite ao usuário gerenciar certos tipos de importação que foram definidos por um administrador.

O princípio de funcionamento é o seguinte: um **administrador** define e gerencia templates de importação (consulte [Definição de templates de importação](../../automating/using/defining-import-templates.md)). Esses templates de importação são então disponibilizados para usuários com visualizações simplificadas no menu **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Imports]** .

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
