---
solution: Campaign Standard
product: campaign
title: Status dos recursos
description: Descubra os diferentes status de recursos de acordo com o estado da publicação.
audience: developing
content-type: reference
topic-tags: about-custom-resources
translation-type: tm+mt
source-git-commit: 2729852365a2e74d2a603d95f75285fe54313e71
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 1%

---


# Status dos recursos{#resource-statuses}

Dependendo do status de publicação ou ativação, os recursos podem ter status diferentes.

Há duas colunas dedicadas à exibição desses status na tela **[!UICONTROL Custom resources]**.

![](assets/schema_colonne_1.png)

**Status de publicação**

* **Rascunho**: o recurso acabou de ser criado ou reformulado. Para criar as tabelas do banco de dados e as APIs correspondentes, o recurso deve ser republicado. Se um recurso estiver sendo redesenhado, ele se torna automaticamente inativo após a etapa de publicação.
* **Redesenho** pendente: o recurso foi reelaborado. O processo de rerascunho ocorrerá durante a próxima publicação. A reformulação é irreversível. Várias mensagens de aviso são exibidas para informar o usuário, tanto ao redesenhar quanto ao preparar para publicar.

   Para obter mais informações sobre a reformulação, consulte [Excluindo um recurso](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >A opção **[!UICONTROL Cancel re-draft]** está disponível quando o recurso que você deseja redesenhar ainda contém links por meio de outros recursos com o status &quot;Publicado&quot;. Essa opção permite reverter o processo de &quot;rerascunho&quot;. Os recursos personalizados retornarão aos status originais.

* **Publicado**: o recurso foi publicado. Se o recurso for modificado após a última data modificada, uma mensagem será exibida para convidá-lo a publicar novamente o recurso a fim de levar em conta as modificações mais recentes.

O campo **[!UICONTROL Do not publish latest modifications]** impede que modificações sejam consideradas durante publicações futuras.

Este campo pode ser configurado na definição de recurso personalizado.
