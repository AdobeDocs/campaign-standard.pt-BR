---
title: '"Etapa 3: verificar a extensão"'
description: Saiba mais sobre como acessar o campo estendido com a Rest API.
page-status-flag: nunca ativado
uuid: 35ba89a5-a354-466f-91a0-50de111a2e00
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: desenvolvimento
content-type: referência
topic-tags: caso de uso — extensão da api
discoiquuid: 21bad242-5921-445c-8df9-3d57dbe35197
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Etapa 3: verificar a extensão{#step-verify-the-extension}

1. Faça uma operação GET nos metadados da API de extensão de perfis e serviços para verificar se o campo adicionado ao recurso personalizado Perfis está disponível.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Ele retorna:

   ![](assets/extendpandsapiview.png)

   O campo está agora disponível para novos desenvolvimentos e integrações.

