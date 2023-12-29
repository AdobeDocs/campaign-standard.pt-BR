---
title: Interface de relatórios
description: Saiba mais sobre a base da interface de relatório dinâmico e como navegar pelas diferentes guias e menus.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: 37e9acff-9576-472f-9fdf-2c0f6da773d1
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 3%

---

# Interface de relatórios{#reporting-interface}

A barra de ferramentas superior permite, por exemplo, modificar, salvar ou imprimir o relatório.

![](assets/dynamic_report_toolbar.png)

Use o **Projeto** Guia para:

* **Abrir...**: abre um relatório ou um modelo criado anteriormente.
* **Salvar como...**: modelos duplicados para poder modificá-los.
* **Atualizar projeto**: atualiza seu relatório com base em novos dados e alterações em filtros.
* **Baixar CSV**: exporta seus relatórios para um arquivo CSV.

A variável **Editar** permite:

* **Desfazer**: cancela a última ação no painel.
* **Limpar tudo**: exclui cada painel no painel.

A variável **Inserir** A tabela permite personalizar seus relatórios adicionando gráficos e tabelas ao painel:

* **Novo painel em branco**: adiciona um novo painel em branco ao painel.
* **Nova forma livre**: adiciona uma nova tabela de forma livre ao painel.
* **Nova linha**: adiciona um novo gráfico de linhas ao painel.
* **Nova barra**: adiciona um novo gráfico de barras ao painel.

**Tópicos relacionados:**

* [Adicionar painéis](../../reporting/using/adding-panels.md)
* [Adicionar visualizações](../../reporting/using/adding-visualizations.md)
* [Adição de componentes](../../reporting/using/adding-components.md)
* [Compartilhamento automático de relatórios com as partes interessadas por email](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)

## Guias {#tabs}

As guias à esquerda permitem criar o relatório e filtrar os dados conforme necessário.

![](assets/dynamic_report_interface.png)

Essas guias fornecem acesso aos seguintes itens:

* **[!UICONTROL Panels]**: adicione um painel ou formato livre em branco ao relatório para começar a filtrar seus dados. Para obter mais informações, consulte a seção Adição de painéis
* **[!UICONTROL Visualizations]**: arraste e solte uma seleção de itens de visualização para dar uma dimensão gráfica ao seu relatório. Para obter mais informações, consulte a seção Adição de visualizações.
* **[!UICONTROL Components]**: personalize seus relatórios com diferentes dimensões, métricas, segmentos e períodos.

## Barra de ferramentas {#toolbar}

A barra de ferramentas pode ser encontrada acima do seu espaço de trabalho. Composto por diferentes guias, permite, por exemplo, modificar, salvar, compartilhar ou imprimir seu relatório.

![](assets/dynamic_report_toolbar.png)

**Tópicos relacionados:**

* [Adicionar painéis](../../reporting/using/adding-panels.md)
* [Adicionar visualizações](../../reporting/using/adding-visualizations.md)
* [Adição de componentes](../../reporting/using/adding-components.md)

### Guia Projeto {#project-tab}

![](assets/tab_project.png)

Use o **Projeto** Guia para:

* **Abrir...**: abre um relatório ou um modelo criado anteriormente.
* **Salvar como...**: modelos duplicados para poder modificá-los.
* **Atualizar projeto**: atualiza seu relatório com base em novos dados e alterações em filtros.
* **Baixar CSV**: exporta seus relatórios para um arquivo CSV.
* **[!UICONTROL Print]**: imprima seu relatório.

### Guia Editar {#edit-tab}

![](assets/tab_edit.png)

A variável **Editar** permite:

* **Desfazer**: cancela a última ação no painel.
* **Limpar tudo**: exclui cada painel no painel.

### Guia Inserir {#insert-tab}

![](assets/tab_insert.png)

A variável **Inserir** permite personalizar seus relatórios adicionando gráficos e tabelas ao painel:

* **Novo painel em branco**: adiciona um novo painel em branco ao painel.
* **Nova forma livre**: adiciona uma nova tabela de forma livre ao painel.
* **Nova linha**: adiciona um novo gráfico de linhas ao painel.
* **Nova barra**: adiciona um novo gráfico de barras ao painel.

### Guia Compartilhar {#share-tab}

![](assets/tab_share_1.png)

A variável **[!UICONTROL Share]** permite enviar seus relatórios com os usuários do Adobe Campaign por emails únicos ou recorrentes. Os usuários direcionados receberão um email com o relatório anexado.

* **[!UICONTROL Send report now]**: envie seu relatório para uma lista de recipients escolhidos por meio de um email único.

   1. No **[!UICONTROL Send report]** adicione uma descrição, se necessário.

      ![](assets/tab_share_4.png)

   1. Selecione os recipients no menu suspenso. Observe que não é possível selecionar usuários fora da organização.
   1. Marcar **[!UICONTROL Show scheduling options]** se quiser enviar emails recorrentes. Isso também pode ser feito selecionando **[!UICONTROL Send Report on schedule]** no **[!UICONTROL Share]** guia.
   1. Clique em **[!UICONTROL Send now]**. Os recipients receberão um email com o relatório em anexo.

* **[!UICONTROL Send report on schedule]**: agende o relatório e envie emails recorrentes para os recipients.

   1. No **[!UICONTROL Send report]** adicione uma descrição, se necessário.
   1. Selecione os recipients no menu suspenso. Observe que não é possível selecionar usuários fora da organização.

      ![](assets/tab_share_5.png)

   1. Selecione a data de início e término para configurar a validade do email no **[!UICONTROL Starting on]** e **[!UICONTROL Ending on]** campos.
   1. Escolha a frequência com que seu email será enviado.

      ![](assets/tab_share_2.png)

   1. Clique em **[!UICONTROL Send on schedule]**, seus recipients receberão seu email recorrente dependendo da frequência escolhida.

* **[!UICONTROL Scheduled reports]**: encontre e configure todos os relatórios agendados.

   1. No **[!UICONTROL Scheduled reports]** localize todos os relatórios enviados recorrentes.

      ![](assets/tab_share_3.png)

   1. Se precisar excluir um dos relatórios agendados, selecione o relatório agendado que deseja excluir e clique em **[!UICONTROL Delete the section]**.
   1. Para configurar ou verificar seus relatórios agendados, clique diretamente no relatório que precisa ser alterado.
   1. A variável **[!UICONTROL Edit scheduled report]** for exibida, agora é possível alterar os recipients ou a frequência do email, se necessário.

Os usuários direcionados receberão um email com seu relatório anexado diretamente nas caixas de entrada. Os usuários sempre podem decidir parar de receber emails recorrentes usando um link de unsubscription disponível em cada email recorrente.

**Tópicos relacionados:**

* [Compartilhamento automático de relatórios com as partes interessadas por email](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
