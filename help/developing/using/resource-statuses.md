---
title: Status dos recursos
description: Descubra os diferentes status de recursos de acordo com o estado da publicação.
page-status-flag: never-activated
uuid: 215c0a2e-27ec-43f3-baac-1eaac7640784
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 85516477-1b95-4273-a0a7-d2cbb9950afd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# Status dos recursos{#resource-statuses}

Dependendo do status de publicação ou ativação, os recursos podem ter status diferentes.

Há duas colunas dedicadas à exibição desses status na **[!UICONTROL Custom resources]** tela.

![](assets/schema_colonne_1.png)

**Status de publicação**

* **Rascunho**: o recurso acabou de ser criado ou reformulado. Para criar as tabelas do banco de dados e as APIs correspondentes, o recurso deve ser republicado. Se um recurso estiver sendo redesenhado, ele se torna automaticamente inativo após a etapa de publicação.
* **Redesenho** pendente: o recurso foi reelaborado. O processo de rerascunho ocorrerá durante a próxima publicação. A reformulação é irreversível. Várias mensagens de aviso são exibidas para informar o usuário, tanto ao redesenhar quanto ao preparar para publicar.

   Para obter mais informações sobre a reformulação, consulte [Excluir um recurso](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >A **[!UICONTROL Cancel re-draft]** opção está disponível quando o recurso que você deseja redesenhar ainda contém links por meio de outros recursos com o status &quot;Publicado&quot;. Essa opção permite reverter o processo de &quot;rerascunho&quot;. Os recursos personalizados retornarão aos status originais.

* **Publicado**: o recurso foi publicado. Se o recurso for modificado após a última data de modificação, uma mensagem será exibida para convidá-lo a republicar o recurso a fim de levar em conta as modificações mais recentes.

O **[!UICONTROL Do not publish latest modifications]** campo impede que modificações sejam levadas em conta em futuras publicações.

Este campo pode ser configurado na definição de recurso personalizado.
