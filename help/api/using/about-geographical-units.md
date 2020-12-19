---
solution: Campaign Standard
product: campaign
title: Sobre unidades geográficas
description: Saiba mais sobre as unidades geográficas e as APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: ad7322905c69f9575e11efc9d8f68cf909dc425f
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 5%

---


# Sobre as unidades geográficas {#about-geographical-units}

>[!CAUTION]
>
>O recurso de unidade geográfica foi substituído pela versão de Campaign Standard 18.7.
>
>Como resultado, novas instâncias de Campaign Standard, bem como instâncias existentes sem unidades geográficas criadas, não podem ter esse recurso implementado a partir da versão 18.7.
>
>Para obter mais informações, consulte a página <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=pt-BR#release-notes">Recursos obsoletos</a>.

O endpoint **geoUnitBase** permite interagir com unidades Geográficas, permitindo, por exemplo, atualizar seus atributos ou atualizar uma unidade de perfil.

O campo **Unidade geográfica** é adicionado a um perfil ao estender o recurso do perfil. Como resultado, lembre-se sempre de usar o ponto de extremidade **profileAndServicesExt** para interagir com as unidades geográficas. Para obter mais informações sobre a extensão de recursos do perfil, consulte a [documentação da Campanha](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).
