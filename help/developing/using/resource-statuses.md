---
title: Status do recurso
seo-title: Status do recurso
description: Status do recurso
seo-description: Descubra os diferentes status de recursos de acordo com seu estado de publicação.
page-status-flag: nunca ativado
uuid: 215 c 0 a 2 e -27 ec -43 f 3-baac -1 eaac 7640784
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 85516477-1 b 95-4273-a 0 a 7-d 2 cbb 9950 afd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Resource statuses{#resource-statuses}

Os recursos podem ter status diferentes de acordo com seu status de publicação ou ativação.

There are two columns dedicated to displaying these statuses in the **[!UICONTROL Custom resources]** screen.

![](assets/schema_colonne_1.png)

**Status de publicação**

* **Rascunho: o recurso acabou de ser criado ou recompilado.** Para criar as tabelas de banco de dados, bem como as apis correspondentes, o recurso deve ser republicado. Se um recurso estiver sendo recompilado, ele será renderizado automaticamente após a etapa da publicação.
* **Rerascunho pendente**: o recurso foi recompilado. O processo de rerascunho ocorrerá durante a próxima publicação. A reedição é irreversível. Várias mensagens de aviso avisam o usuário desse fato ao refazer a nova edição, em seguida, ao se preparar para publicar.

   For more on re-drafting, see [Deleting a resource](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >The **[!UICONTROL Cancel re-draft]** option is available when the resource that you want to re-draft still contains links through other resources with the "Published" status. Esta opção permite reverter o processo de "rerascunho". Os recursos personalizados retornarão para seus status originais.

* **Publicado**: o recurso foi publicado. Se o recurso for modificado após a última data de modificação, será exibida uma mensagem solicitando que o usuário publique novamente para considerar as modificações mais recentes.

The **[!UICONTROL Do not publish latest modifications]** field prevents modifications from being taken into account during future publications.

Esse campo pode ser configurado na definição de recurso personalizada.
