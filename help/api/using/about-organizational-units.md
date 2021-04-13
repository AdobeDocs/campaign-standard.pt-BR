---
solution: Campaign Standard
product: campaign
title: Sobre unidades organizacionais
description: Saiba mais sobre unidades organizacionais e APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 01e4eb027b55815c3680b26691e61cbe5b63ee8c
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 0%

---


# Sobre unidades organizacionais {#about-organizational-units}

O endpoint **orgUnitBase** permite interagir com unidades organizacionais, permitindo, por exemplo, atualizar seus atributos ou atualizar a unidade organizacional de um perfil. Para obter mais informações sobre Unidades organizacionais no Campaign, consulte a [documentação do Campaign](https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=en#administrating).

O campo **Organizational Unit** é adicionado a um perfil ao estender o recurso de perfil. Como resultado, lembre-se sempre de usar o endpoint **profileAndServicesExt** para interagir com as unidades geográficas. Para obter mais informações sobre a extensão de recurso do perfil, consulte a [documentação do Campaign](https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=en#partitioning-profiles).
