---
title: Uso de recursos diferentes de targeting dimension
description: Saiba como usar um recurso diferente do targeting dimension.
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f3a668860659e40645ce3e4aab879cae5ad90083
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---


# Uso de recursos diferentes de targeting dimension {#using-resources-different-from-targeting-dimensions}

Esses casos de uso apresentam como usar um recurso diferente do targeting dimension, por exemplo, para procurar um registro específico em uma tabela distante.

Para obter mais informações sobre targeting dimension e recursos, consulte [esta seção](../../automating/using/query.md#targeting-dimensions-and-resources)

**Exemplo 1: identificação de perfis direcionados pelo delivery com a etiqueta &quot;Bem-vindo de volta !&quot;**.

* Neste caso, queremos público alvo de perfis. Nós vamos definir o targeting dimension como **[!UICONTROL Profiles (profile)]**.
* Queremos filtrar os perfis selecionados de acordo com o rótulo do delivery. Por isso, vamos definir o recurso para **[!UICONTROL Delivery logs]**. Dessa forma, estamos filtrando diretamente na tabela de log de delivery, o que oferta melhores desempenhos.

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**Exemplo 2: identificação de perfis que não foram direcionados pelo delivery com o rótulo &quot;Bem-vindo de volta!&quot;**

No exemplo anterior, usamos um recurso diferente do targeting dimension. Essa operação só é possível se você quiser encontrar um registro que **esteja presente** na tabela distante (logs do delivery em nosso exemplo).

Se desejarmos encontrar um registro que não **esteja presente** na tabela distante (por exemplo, perfis que não foram direcionados por um delivery específico), será necessário usar o mesmo recurso e targeting dimension, já que o registro não estará presente na tabela distante (logs do delivery).

* Neste caso, queremos público alvo de perfis. Nós vamos definir o targeting dimension como **[!UICONTROL Profiles (profile)]**.
* Queremos filtrar os perfis selecionados de acordo com o rótulo do delivery. Não é possível filtrar diretamente nos logs do delivery, pois estamos procurando um registro não presente na tabela logs do delivery. Por conseguinte, vamos definir os recursos para **[!UICONTROL Profile (profile)]** e construir o nosso query na mesa dos perfis.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
