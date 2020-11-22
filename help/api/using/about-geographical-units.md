---
solution: Campaign Standard
product: campaign
title: Sobre unidades geográficas
description: Saiba mais sobre as unidades geográficas e as APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 3%

---


# Sobre unidades geográficas {#about-geographical-units}

>[!CAUTION]
>
>O recurso de unidade geográfica foi substituído pela versão de Campaign Standard 18.7.
>
>Como resultado, novas instâncias de Campaign Standard, bem como instâncias existentes sem unidades geográficas criadas, não podem ter esse recurso implementado a partir da versão 18.7.
>
>For more on this, refer to the <a href="https://helpx.adobe.com/br/campaign/kb/acs-deprecated-and-removed-features.html">Deprecated features</a> page.

O endpoint **geoUnitBase** permite interagir com unidades Geográficas, permitindo, por exemplo, atualizar seus atributos ou atualizar uma unidade de perfil.

O campo Unidade **** geográfica é adicionado a um perfil ao estender o recurso do perfil. Como resultado, lembre-se sempre de usar o endpoint **profileAndServicesExt** para interagir com as unidades Geográficas. Para obter mais informações sobre a extensão de recursos do perfil, consulte a documentação [da](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles)Campanha.
