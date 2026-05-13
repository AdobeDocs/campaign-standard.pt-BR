---
title: Uso de recursos diferentes de dimensões de direcionamento
description: Saiba como usar um recurso diferente do targeting dimension.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 5805bdfa-fb33-4a46-ba1e-7a10b067349b
TQID: https://experienceleague.adobe.com/tGVP20eQpo7EuB1xluX2AQHHMZ-IM-q6JmgFGp6Iwk4
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 295
ht-degree: 76%

---

# Uso de recursos diferentes de dimensões de direcionamento {#using-resources-different-from-targeting-dimensions}

Esses casos de uso apresentam como usar um recurso diferente do targeting dimension, por exemplo, para procurar um registro específico em uma tabela distante.

Para obter mais informações sobre targeting dimensions e recursos, consulte [esta seção](../../automating/using/query.md#targeting-dimensions-and-resources)

**Exemplo 1: identificação de perfis direcionados pela entrega com o rótulo “Bem-vindo de volta!”**.

* Nesse caso, queremos direcionar os perfis. Definiremos a dimensão de direcionamento como **[!UICONTROL Profiles (profile)]**.
* Queremos filtrar os perfis selecionados de acordo com o rótulo da entrega. Por isso, definiremos o recurso como **[!UICONTROL Delivery logs]**. Dessa forma, estamos filtrando diretamente na tabela de logs do delivery, o que oferecerá melhor desempenho.

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**Exemplo 2: identificação de perfis que não foram direcionados pela entrega com o rótulo “Bem-vindo de volta!”**

No exemplo anterior, usamos um recurso diferente da dimensão de direcionamento. Essa operação só será possível se você quiser encontrar um registro que **esteja presente** na tabela distante (os logs da entrega no nosso exemplo).

Para encontrar um registro que **não esteja presente** na tabela distante (por exemplo, perfis que não foram direcionados por uma entrega específica), use o mesmo recurso e dimensão de direcionamento já que o registro não estará presente na tabela distante (logs da entrega).

* Nesse caso, queremos direcionar os perfis. Definiremos a dimensão de direcionamento como **[!UICONTROL Profiles (profile)]**.
* Queremos filtrar os perfis selecionados de acordo com o rótulo da entrega. Não é possível filtrar diretamente nos logs da entrega, pois estamos procurando um registro que não está presente na tabela de logs da entrega. Portanto, definiremos os recursos como **[!UICONTROL Profile (profile)]** e criaremos nossa consulta na tabela de perfis.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
