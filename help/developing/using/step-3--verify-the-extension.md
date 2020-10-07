---
title: '"Etapa 3: verificar a extensão"'
description: Saiba mais sobre como acessar o campo estendido com a Rest API.
page-status-flag: never-activated
uuid: 35ba89a5-a354-466f-91a0-50de111a2e00
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
discoiquuid: 21bad242-5921-445c-8df9-3d57dbe35197
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 13%

---


# Etapa 3: verificar a extensão{#step-verify-the-extension}

1. Faça uma operação de GET nos metadados da API de extensão de Perfis e serviços para verificar se o campo adicionado no recurso personalizado de Perfis está disponível.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Ele retorna:

   ![](assets/extendpandsapiview.png)

   O campo está agora disponível para novos desenvolvimentos e integrações.

