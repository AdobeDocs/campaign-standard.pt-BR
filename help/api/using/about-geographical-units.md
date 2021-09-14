---
title: Sobre unidades geográficas
description: Saiba mais sobre unidades geográficas e APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 5%

---


# Sobre unidades geográficas {#about-geographical-units}

>[!CAUTION]
>
>O recurso de unidade geográfica foi descontinuado com o Campaign Standard 18.7.
>
>Como resultado, novas instâncias do Campaign Standard, bem como instâncias existentes sem unidades geográficas criadas, não podem ter esse recurso implementado a partir da versão 18.7.
>
>Para obter mais informações, consulte a página <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=pt-BR#release-notes">Deprecated features</a>.

O endpoint **geoUnitBase** permite interagir com unidades geográficas, permitindo, por exemplo, atualizar seus atributos ou atualizar a unidade de um perfil.

O campo **Geografia unit** é adicionado a um perfil ao estender o recurso de perfil. Como resultado, lembre-se sempre de usar o endpoint **profileAndServicesExt** para interagir com as unidades geográficas. Para obter mais informações sobre a extensão de recurso do perfil, consulte a [documentação do Campaign](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).
