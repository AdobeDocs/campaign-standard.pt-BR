---
solution: Campaign Standard
product: campaign
title: Status dos recursos
description: Descubra os diferentes status de recursos de acordo com seu estado de publicação.
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 1%

---


# Status dos recursos{#resource-statuses}

Dependendo do status de publicação ou ativação, os recursos podem ter status diferentes.

Há duas colunas dedicadas à exibição desses status na tela **[!UICONTROL Custom resources]**.

![](assets/schema_colonne_1.png)

**Status da publicação**

* **Rascunho**: o recurso acabou de ser criado ou reelaborado. Para criar as tabelas do banco de dados, bem como as APIs correspondentes, o recurso deve ser republicado. Se um recurso estiver sendo reelaborado, ele ficará inativo automaticamente após a etapa de publicação.
* **Redesenho** pendente: o recurso foi reelaborado. O processo de recriação de rascunho ocorrerá durante a próxima publicação. A reformulação é irreversível. Várias mensagens de aviso são exibidas para informar o usuário, tanto ao reformular quanto ao se preparar para publicar.

   Para obter mais informações sobre a reformulação, consulte [Excluindo um recurso](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >A opção **[!UICONTROL Cancel re-draft]** estará disponível quando o recurso que você deseja redesenhar ainda contiver links por meio de outros recursos com o status &quot;Publicado&quot;. Essa opção permite reverter o processo de &quot;recriação de rascunho&quot;. Os recursos personalizados retornarão aos status originais.

* **Publicado**: o recurso foi publicado. Se o recurso for modificado após a última data de modificação, uma mensagem será exibida para convidá-lo a republicar o recurso para considerar as modificações mais recentes.

O campo **[!UICONTROL Do not publish latest modifications]** impede que as modificações sejam levadas em conta durante publicações futuras.

Esse campo pode ser configurado na definição de recurso personalizado.
