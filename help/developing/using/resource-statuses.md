---
title: Status dos recursos
description: Descubra os diferentes status de recursos de acordo com seu estado de publicação.
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: 7290ebc5-8a58-4b7f-99bf-d942e37c944e
TQID: https://experienceleague.adobe.com/f0ihge9X4opmgRRdswkBt7yMWSmJc36viZKWXPoQCe4
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 233
ht-degree: 1%

---

# Status dos recursos{#resource-statuses}

Dependendo do status de publicação ou ativação, os recursos podem ter status diferentes.

Há duas colunas dedicadas à exibição desses status na tela **[!UICONTROL Custom resources]**.

![](assets/schema_colonne_1.png)

**Status da publicação**

* **Rascunho**: o recurso acabou de ser criado ou recriado. Para criar as tabelas do banco de dados, bem como as APIs correspondentes, o recurso deve ser republicado. Se um recurso estiver sendo recriado, ele se tornará inativo automaticamente após a etapa de publicação.
* **Rascunho pendente**: o recurso foi recriado. O processo de recriação de rascunho ocorrerá durante a próxima publicação. A reformulação é irreversível. Várias mensagens de aviso são exibidas para informar o usuário, tanto ao recriar quanto ao se preparar para publicar.

  Para obter mais informações sobre como recriar, consulte [Excluindo um recurso](../../developing/using/deleting-a-resource.md).

  >[!NOTE]
  >
  >A opção **[!UICONTROL Cancel re-draft]** está disponível quando o recurso que você deseja refazer ainda contém links através de outros recursos com o status &quot;Publicado&quot;. Essa opção permite reverter o processo de &quot;recriação de rascunho&quot;. Os recursos personalizados retornarão aos status originais.

* **Publicado**: o recurso foi publicado. Se o recurso for modificado após a última data de modificação, uma mensagem será exibida convidando você a republicar o recurso para considerar as modificações mais recentes.

O campo **[!UICONTROL Do not publish latest modifications]** impede que as modificações sejam consideradas durante publicações futuras.

Esse campo pode ser configurado na definição de recurso personalizado.
