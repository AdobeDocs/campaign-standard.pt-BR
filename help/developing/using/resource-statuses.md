---
title: Status dos recursos
description: Descubra os diferentes status de recursos de acordo com o estado da publicação.
page-status-flag: nunca ativado
uuid: 215c0a2e-27ec-43f3-baac-1eaac7640784
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: desenvolvimento
content-type: referência
topic-tags: about-custom-resources
discoiquuid: 85516477-1b95-4273-a0a7-d2cbb9950afd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Status dos recursos{#resource-statuses}

Os recursos podem ter status diferentes de acordo com o status de publicação ou ativação.

Há duas colunas dedicadas à exibição desses status na **[!UICONTROL Custom resources]** tela.

![](assets/schema_colonne_1.png)

**Status de publicação**

* **Rascunho**: o recurso acabou de ser criado ou reformulado. Para criar as tabelas do banco de dados e as APIs correspondentes, o recurso deve ser republicado. Se um recurso estiver sendo redesenhado, ele será automaticamente renderizado inativo após a etapa de publicação.
* **Redesenho** pendente: o recurso foi reelaborado. O processo de rerascunho ocorrerá durante a próxima publicação. A reformulação é irreversível. Várias mensagens de aviso alertam o usuário sobre esse fato ao reformular e, em seguida, ao se preparar para publicar.

   Para obter mais informações sobre a reformulação, consulte [Excluir um recurso](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >A **[!UICONTROL Cancel re-draft]** opção está disponível quando o recurso que você deseja redesenhar ainda contém links por meio de outros recursos com o status "Publicado". Essa opção permite reverter o processo de "rerascunho". Os recursos personalizados retornarão aos status originais.

* **Publicado**: o recurso foi publicado. Se o recurso for modificado após a última data modificada, será exibida uma mensagem solicitando que o usuário publique novamente para levar em conta as modificações mais recentes.

O **[!UICONTROL Do not publish latest modifications]** campo impede que modificações sejam levadas em conta em futuras publicações.

Este campo pode ser configurado na definição de recurso personalizado.
