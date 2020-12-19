---
solution: Campaign Standard
product: campaign
title: Controle de um workflow
description: Saiba como controlar um fluxo de trabalho com APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 9%

---


# Controle de um workflow {#controlling-a-workflow}

É possível controlar um fluxo de trabalho diretamente da REST API, por meio de uma solicitação de POST que contenha a ID do fluxo de trabalho e o comando de execução necessário:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>Se a ID do fluxo de trabalho for alterada no Adobe Campaign, a solicitação da API não funcionará mais.

Quatro comandos de execução estão disponíveis para controlar um fluxo de trabalho:

* Start
* Pause
* Retomar
* Stop

Para obter mais informações sobre os comandos de execução, consulte a [documentação de Campanha](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/executing-a-workflow/about-workflow-execution.html).

<br/>

***Pedidos de amostra***

* Start de um fluxo de trabalho.

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -i
   -d '{"method":"start"}'
   ```

   <!-- + réponse -->

* Pare um fluxo de trabalho.

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -i
   -d '{"method":"stop"}'
   ```

   <!-- + réponse -->
