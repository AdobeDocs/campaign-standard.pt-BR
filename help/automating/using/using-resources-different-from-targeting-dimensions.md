---
title: Uso de recursos diferentes de targeting dimensions
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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 81%

---


# Uso de recursos diferentes de targeting dimensions {#using-resources-different-from-targeting-dimensions}

Esses casos de uso apresentam como usar um recurso diferente do targeting dimension, por exemplo, para procurar um registro específico em uma tabela distante.

Para obter mais informações sobre targeting dimension e recursos, consulte [esta seção](../../automating/using/query.md#targeting-dimensions-and-resources)

**Exemplo 1: identificação de perfis direcionados pelo delivery com o rótulo “Bem-vindo de volta!”**.

* Nesse caso, queremos direcionar os perfis. Definiremos o targeting dimension como **[!UICONTROL Profiles (profile)]**.
* Queremos filtrar os perfis selecionados de acordo com o rótulo do delivery. Por isso, definiremos o recurso como **[!UICONTROL Delivery logs]**. Assim, estamos filtrando diretamente na tabela de logs do delivery, o que oferece melhores desempenhos.

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**Exemplo 2: identificação de perfis que não foram direcionados pelo delivery com o rótulo “Bem-vindo de volta!”**

No exemplo anterior, usamos um recurso diferente do targeting dimension. Essa operação só será possível se você quiser encontrar um registro que **esteja presente** na tabela distante (os logs do delivery no nosso exemplo).

Para encontrar um registro que **não esteja presente** na tabela distante (por exemplo, perfis que não foram direcionados por um delivery específico), use o mesmo recurso e targeting dimension já que o registro não estará presente na tabela distante (logs do delivery).

* Nesse caso, queremos direcionar os perfis. Definiremos o targeting dimension como **[!UICONTROL Profiles (profile)]**.
* Queremos filtrar os perfis selecionados de acordo com o rótulo do delivery. Não é possível filtrar diretamente nos logs do delivery, pois estamos procurando um registro que não está presente na tabela de logs do delivery. Portanto, definiremos os recursos como **[!UICONTROL Profile (profile)]** e criaremos nosso query na tabela de perfis.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
