---
solution: Campaign Standard
product: campaign
title: Classificação
description: Saiba mais sobre como executar operações de classificação
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 11%

---


# Classificação

A classificação está disponível em ordem crescente ou decrescente. Para fazer isso, use o parâmetro **%20desc** ou **%20asc** para sua solicitação.

Para saber se um campo pode ser classificado, verifique o parâmetro &quot;classificável&quot; nos metadados do recurso. Para obter mais informações, consulte [esta seção](../../api/using/metadata-mechanism.md).

<br/>

***Pedidos de amostra***

* Solicitação de amostra de GET para recuperar e-mails no banco de dados ordenados alfabeticamente.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email/email?_order=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Resposta à solicitação.

   ```
   {
   "content": [
       "adam@email.com",
       "allison.durance@example.com",
       "amy.dakota@mail.com",
       "andrea.johnson@mail.com",
       ...
   ]
   ...
   }
   ```

* Amostra de solicitação de GET para recuperar o email no banco de dados em uma ordem alfabética decrescente.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email%20desc \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Resposta à solicitação.

   ```
   {
   "content": [
       "tombinder@example.com",
       "tombinder@example.com",
       "timross@example.com",
       "john.smith@example.com",
       ...
   ]
   }
   ```
