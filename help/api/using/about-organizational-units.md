---
title: Sobre unidades organizacionais
description: Saiba mais sobre unidades organizacionais e APIs.
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
source-wordcount: '116'
ht-degree: 0%
---

# Sobre unidades organizacionais {#about-organizational-units}

O ponto de extremidade **orgUnitBase** permite interagir com unidades organizacionais, permitindo, por exemplo, atualizar seus atributos ou atualizar a unidade organizacional de um perfil. Para obter mais informações sobre as unidades organizacionais no Campaign, consulte a [documentação do Campaign](https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=pt-BR#administrating).

O campo **Unidade organizacional** é adicionado a um perfil ao estender o recurso de perfil. Como resultado, sempre use o ponto de extremidade **profileAndServicesExt** para interagir com as unidades geográficas. Para obter mais informações sobre a extensão de recursos do perfil, consulte a [documentação do Campaign](https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=pt-BR#partitioning-profiles).
