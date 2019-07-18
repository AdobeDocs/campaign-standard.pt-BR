---
title: Importação de dados com modelos de importação
seo-title: Importação de dados com modelos de importação
description: Importação de dados com modelos de importação
seo-description: Saiba como coletar dados para feed do banco de dados da Campanha.
page-status-flag: nunca ativado
uuid: bfc 03235-2032-448 a-a 9 ed -21 ff 2 a 83 fa 09
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: importar e exportar dados
discoiquuid: fb 511 bb 8-6 be 7-43 f 6-86 ab -94 d 5 cfa 3 efc 9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Importing data with import templates{#importing-data-with-import-templates}

A importação de dados permite coletar dados para alimentar o banco de dados de sua campanha.

Alternatively to [Workflows](../../automating/using/discovering-workflows.md), Adobe Campaign offers a simplified import function that allows the user to manage certain types of import that were defined by an administrator.

The operating principle is as follows: an **administrator** defines and manages import templates (see [Defining import templates](../../automating/using/defining-import-templates.md)). These import templates are then made available to users with simplified views under the **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Imports]** menu.

Portanto, esses usuários só precisam selecionar o tipo de importação que desejam executar e fazer upload do arquivo com os dados a serem importados. O fluxo de trabalho definido pelo administrador é executado de forma transparente para o usuário, que pode acessar os detalhes do resultado da importação depois que terminar.

>[!NOTE]
>
>Import data function can be managed by users with **[!UICONTROL GENERIC IMPORT (import)]** and **[!UICONTROL WORKFLOW (workflow)]** roles. Para saber mais sobre as funções, consulte [esta seção](../../administration/using/list-of-roles.md).

As importações podem ser filtradas de acordo com o modelo a partir do qual foram executadas, sua data de execução e o status de execução.

1. From the imports overview, click the **[!UICONTROL Create]** button. O assistente é aberto.
1. Selecione o tipo de importação que deseja executar. Os tipos de importação correspondem aos modelos de importação disponíveis.
1. Se necessário, faça download do arquivo de amostra vinculado ao modelo ao computador para exibir os tipos de dados esperados no arquivo a serem importados.
1. Baixe o arquivo que contém os dados a serem importados no assistente.
1. Inicie a importação. O assistente é fechado e leva você de volta à lista de importações realizadas com o modelo usado.
1. Atualize sua página e selecione a importação que acabou de realizar para exibir os detalhes da execução.

   ![](assets/simplified_import1.png)

Os detalhes da execução de importação estão disponíveis agora. O arquivo que foi importado, assim como o arquivo que contém os dados rejeitados (dados que não foram importados), pode ser baixado para o computador.
