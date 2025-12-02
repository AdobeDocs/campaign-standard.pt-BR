---
title: Acionamento de uma atividade de sinal
description: Saiba como acionar uma atividade de sinal com APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 9f94e98f-fe04-4369-8946-1380e02cdece
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 2%

---

# Acionamento de uma atividade de sinal {#triggering-a-signal-activity}

Em um fluxo de trabalho do Adobe Campaign Standard, pode haver uma ou mais **atividades de sinal externo**. Essas atividades são &quot;ouvintes&quot; que aguardam para serem acionados.

As APIs do Campaign Standard permitem acionar uma atividade **Sinal externo** para chamar um fluxo de trabalho. A chamada de API pode incluir parâmetros que serão assimilados nas variáveis de eventos do fluxo de trabalho (um nome de público-alvo para direcionamento, um nome de arquivo para importar, uma parte do conteúdo da mensagem etc.). Dessa forma, você pode integrar facilmente as automações do Campaign ao sistema externo.

>[!NOTE]
>
>As atividades de sinal externo não podem ser acionadas com mais frequência do que a cada 10 minutos e o workflow de destino já deve estar em execução.

Para acionar um workflow, siga as etapas abaixo:

1. Execute uma solicitação **GET** no fluxo de trabalho para recuperar a URL do acionador da atividade de sinal externo.

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. Execute uma solicitação **POST** na URL retornada para acionar a atividade de sinal, com o parâmetro **&quot;source&quot;** na carga. Esse atributo é obrigatório e permite indicar a origem da solicitação de acionamento.

Se quiser chamar o fluxo de trabalho com parâmetros, adicione-os à carga com o atributo **&quot;parameters&quot;**. A sintaxe consiste no nome do parâmetro seguido por seu valor (há suporte para os seguintes tipos: **string**, **number**, **booleano** e **date/time**).

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
>Ao adicionar um parâmetro à carga, verifique se os valores **name** e **type** estão consistentes com as informações declaradas na atividade de sinal externo. Além disso, o tamanho do conteúdo não deve exceder 64Ko.

<br/>

***Solicitação de exemplo***

Execute uma solicitação GET no fluxo de trabalho.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna a atividade do sinal de workflow e o url de acionador associado.

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

Para acionar uma atividade de sinal, execute uma solicitação POST no url do acionador com a &quot;origem&quot;. Adicione os atributos &quot;parameters&quot; se quiser chamar o workflow com parâmetros.

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

Se um dos parâmetros não for declarado na atividade External signal, a solicitação POST retornará o erro abaixo, indicando qual parâmetro está ausente.

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
