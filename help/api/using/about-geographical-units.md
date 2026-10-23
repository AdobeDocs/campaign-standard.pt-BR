---
title: Sobre unidades geográficas
description: Saiba mais sobre unidades geográficas e APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 6%
---

# Sobre unidades geográficas {#about-geographical-units}

>[!CAUTION]
>
>O recurso de unidade geográfica foi descontinuado na versão 18.7 do Campaign Standard.
>
>Como resultado, novas instâncias do Campaign Standard, bem como instâncias existentes sem unidades geográficas criadas, não podem ter esse recurso implementado a partir da versão 18.7.
>
>Para obter mais informações, consulte a página <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=pt-BR#release-notes">Recursos obsoletos</a>.

O ponto de extremidade **geoUnitBase** permite interagir com unidades geográficas, permitindo, por exemplo, atualizar seus atributos ou atualizar a unidade de um perfil.

O campo **Unidade geográfica** é adicionado a um perfil ao estender o recurso de perfil. Como resultado, sempre use o ponto de extremidade **profileAndServicesExt** para interagir com as unidades geográficas. Para obter mais informações sobre a extensão de recursos do perfil, consulte a [documentação do Campaign](https://helpx.adobe.com/br/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).
