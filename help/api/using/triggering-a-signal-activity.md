---
solution: Campaign Standard
product: campaign
title: Acionamento de uma atividade de sinal
description: Saiba como acionar uma atividade de sinal com APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 2%

---


# Acionamento de uma atividade de sinal {#triggering-a-signal-activity}

Em um workflow do Adobe Campaign Standard, pode haver uma ou mais atividades **External signal**. Essas atividades são &quot;ouvintes&quot; que aguardam para serem acionadas.

As APIs do Campaign Standard permitem acionar uma atividade **External signal** para chamar um workflow. A chamada da API pode incluir parâmetros que serão assimilados nas variáveis de eventos do fluxo de trabalho (um nome de público-alvo a ser direcionado, um nome de arquivo a ser importado, uma parte do conteúdo da mensagem etc.). Dessa forma, você pode integrar facilmente suas automações do Campaign com seu sistema externo.

>[!NOTE]
>
>As atividades de sinal externo não podem ser acionadas com mais frequência do que a cada 10 minutos e o workflow de destino já deve estar em execução.

Para acionar um workflow, siga as etapas abaixo:

1. Execute uma solicitação **GET** no workflow para recuperar o URL do acionador da atividade External signal .

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. Execute uma solicitação **POST** no URL retornado para acionar a atividade do sinal, com o parâmetro **&quot;source&quot;** no payload. Esse atributo é obrigatório e permite indicar a fonte de solicitação de acionamento.

Se quiser chamar o workflow com parâmetros, adicione-os ao payload com o atributo **&quot;parameters&quot;**. A sintaxe consiste no nome do parâmetro seguido pelo seu valor (os seguintes tipos são compatíveis: **sequência**, **número**, **booleano** e **data/hora**).

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
>Ao adicionar um parâmetro à carga útil, verifique se os valores **name** e **type** estão consistentes com as informações declaradas na atividade External signal . Além disso, o tamanho da carga não deve exceder 64 Ko.

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

Retorna a atividade de sinal de workflow e o url de acionador associado.

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

Para acionar uma atividade de sinal, execute uma solicitação de POST no url do acionador com a &quot;fonte&quot;. Adicione os atributos &quot;parameters&quot; se quiser chamar o workflow com parâmetros.

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

Se um dos parâmetros não for declarado na atividade External signal , a solicitação POST retornará o erro abaixo, indicando qual parâmetro está ausente.

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
