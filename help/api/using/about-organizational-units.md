---
title: Sobre unidades organizacionais
description: Saiba mais sobre unidades organizacionais e APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 0%

---


# Sobre unidades organizacionais {#about-organizational-units}

O ponto de extremidade **orgUnitBase** permite interagir com unidades organizacionais, permitindo, por exemplo, atualizar seus atributos ou atualizar a unidade organizacional de um perfil. Para obter mais informações sobre as unidades organizacionais no Campaign, consulte a [documentação do Campaign](https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=pt-BR#administrating).

O campo **Unidade organizacional** é adicionado a um perfil ao estender o recurso de perfil. Como resultado, sempre use o ponto de extremidade **profileAndServicesExt** para interagir com as unidades geográficas. Para obter mais informações sobre a extensão de recursos do perfil, consulte a [documentação do Campaign](https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=pt-BR#partitioning-profiles).
