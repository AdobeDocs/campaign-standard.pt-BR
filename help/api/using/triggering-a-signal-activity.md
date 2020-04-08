---
title: Acionamento de uma atividade de sinal
description: Saiba como disparar uma atividade de sinal com APIs.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f5c91f886335e43940caac4d3b18924c020a2d2b

---


# Acionamento de uma atividade de sinal {#triggering-a-signal-activity}

Em um fluxo de trabalho Adobe Campaign Standard, pode haver uma ou mais atividades de sinal **** externo. Essas atividades são &quot;ouvintes&quot; que esperam para serem acionadas.

As APIs de Campaign Standard permitem disparar uma atividade de sinal **** externo para chamar um fluxo de trabalho. A chamada da API pode incluir parâmetros que serão assimilados nas variáveis de eventos do fluxo de trabalho (um nome de audiência para público alvo, um nome de arquivo a ser importado, uma parte do conteúdo da mensagem etc.). Dessa forma, você pode integrar facilmente suas automações de Campanha ao seu sistema externo.

>[!NOTE]
>
>atividades de sinal externo não podem ser acionadas com mais frequência do que a cada 10 minutos e o fluxo de trabalho de destino já deve estar em execução.

Para acionar um fluxo de trabalho, siga as etapas abaixo:

1. Execute uma solicitação **GET** no fluxo de trabalho para recuperar o URL de disparo da atividade de sinal externo.

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. Execute uma solicitação **POST** no URL retornado para disparar a atividade do sinal, com o parâmetro **&quot;source&quot;** na carga. Esse atributo é obrigatório, permite que você indique a fonte de solicitação de acionamento.

Se você quiser chamar o fluxo de trabalho com parâmetros, adicione-os à carga com o atributo **&quot;parameters&quot;** . A sintaxe consiste no nome do parâmetro seguido pelo seu valor (os seguintes tipos são suportados: **string**, **número**, **booleano** e **data/hora**).

```
  -X POST <TRIGGER_URL>
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8' \
  -H 'Content-Length:79' \
  -i
  -d {
  -d    "source":"<SOURCE>",
  -d    "parameters":{
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",  
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>"
  -d    }
  -d }
```

>[!NOTE]
>
>Ao adicionar um parâmetro à carga, verifique se seus valores de **nome** e **tipo** são consistentes com as informações declaradas na atividade de sinal externo. Além disso, a carga útil não deve exceder 64 Ko.

<br/>

***Solicitação de amostra***

Execute uma solicitação GET no fluxo de trabalho.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna a atividade do sinal de fluxo de trabalho e o url de disparo associado.

```
{
"PKey": "<PKEY>",
"activities": {
  "activity": {
    "signal1": {
      ...
      "trigger": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger/"
        },
        ...
      }
    }
  }
}
```

Para disparar uma atividade de sinal, execute uma solicitação POST no url de disparo com a &quot;fonte&quot;. Adicione os atributos &quot;parâmetros&quot; se desejar chamar o fluxo de trabalho com parâmetros.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{
-d "source":"API",
-d "parameters":{
-d    "audience":"audience",
-d    "email":"anna.varney@mail.com",
-d    "template":"05",
-d    "contentURL":"http://www.adobe.com",
-d    "test":"true",
-d    "segmentCode":"my segment",
-d    "attribute":"2019-04-03 08:17:19.100Z"}
-d  }'
```

<!-- + réponse -->

Se um dos parâmetros não for declarado na atividade de sinal externo, a solicitação POST retornará o erro abaixo, indicando qual parâmetro está ausente.

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
