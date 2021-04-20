---
solution: Campaign Standard
product: campaign
title: '"Etapa 3: verificar a extensão"'
description: Saiba como acessar o campo estendido com a API Rest.
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: Data Model
role: Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 12%

---


# Etapa 3: verificar a extensão{#step-verify-the-extension}

1. Faça uma operação GET nos metadados da API da extensão de perfis e serviços para verificar se o campo adicionado ao recurso personalizado Perfis agora está disponível.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Ele retorna:

   ![](assets/extendpandsapiview.png)

   O campo agora está disponível para novos desenvolvimentos e integrações.

