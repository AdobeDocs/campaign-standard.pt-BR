---
title: 'Etapa 3: verificar a extensão'
description: Saiba como acessar o campo estendido com a API Rest.
audience: developing
content-type: reference
topic-tags: use-case-extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: 34cb416c-ee3d-4b7c-a75b-640432db320d
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: tm+mt
source-wordcount: '61'
ht-degree: 16%

---

# Etapa 3: verificar a extensão{#step-verify-the-extension}

1. Faça uma operação GET nos metadados da API de extensão de Perfis e serviços para verificar se o campo adicionado no recurso personalizado Perfis agora está disponível.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Ele retorna:

   ![](assets/extendpandsapiview.png)

   O campo agora está disponível para novos desenvolvimentos e integrações.
