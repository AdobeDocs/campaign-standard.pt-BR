---
solution: Campaign Standard
product: campaign
title: '"Etapa 3: verificar a extensão"'
description: Saiba mais sobre como acessar o campo estendido com a Rest API.
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
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

