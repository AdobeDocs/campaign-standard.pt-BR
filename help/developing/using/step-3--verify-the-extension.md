---
title: "Etapa 3: verificar a extensão"
description: Saiba como acessar o campo estendido com a API Rest.
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: 34cb416c-ee3d-4b7c-a75b-640432db320d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '61'
ht-degree: 8%

---

# Etapa 3: verificar a extensão{#step-verify-the-extension}

1. Faça uma operação GET nos metadados da API de extensão de Perfis e serviços para verificar se o campo adicionado no recurso personalizado Perfis agora está disponível.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Ele retorna:

   ![](assets/extendpandsapiview.png)

   O campo agora está disponível para novos desenvolvimentos e integrações.
