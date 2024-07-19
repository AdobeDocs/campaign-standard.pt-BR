---
title: Solução de problemas de API
description: Saiba mais sobre problemas comuns relacionados às APIs de Campaign Standard
feature: API
role: Data Engineer
level: Experienced
exl-id: 404356cd-021f-4739-a88f-b8b1b79e19bc
source-git-commit: b65bf28565c25072c6a95cebdb999ce38a2e2e1a
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---

# Solução de problemas de API {#troubleshooting}

* **Ao acessar o Console do Adobe.io, ocorre o seguinte erro: &quot;O console do Adobe I/O só está disponível para membros selecionados de contas corporativas. Se você acha que deve ter acesso, contate o Administrador do Sistema.&quot;**

Você só pode criar chaves de API para as organizações das quais é administrador. Se essa mensagem for exibida e você quiser criar chaves de API e solicitar que um dos administradores da organização faça isso.

* **Ao fazer uma solicitação para o Adobe.io, você obtém {&quot;error_code&quot;:&quot;403023&quot;,&quot;message&quot;:&quot;Profile is not valid&quot;}**

Isso significa que há um problema com o provisionamento IMS do seu produto específico do Campaign: a equipe IMS precisa corrigi-lo.

Para obter mais detalhes, você pode chamar a API do IMS com seu token para ver a aparência do seu perfil IMS: É necessário ter um prodCtx, em que a organization_id seja a mesma que você inseriu no URL do Adobe.io para poder rotear sua solicitação.
Se estiver faltando, o provisionamento de IMS precisará ser corrigido.

```
-X GET https://mc.adobe.io/{ORGANIZATION}/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna o seguinte erro.

```
{"error_code":"403023","message":"Profile is not valid"}
```

Verifique seu perfil IMS com essa solicitação.

```
-X GET https://ims-na1.adobelogin.com/ims/profile/v1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Na resposta, o valor ORGANIZATION_ID deve ser o mesmo na primeira solicitação GET.

```
{
  "countryCode": "FR",
  "mrktPermEmail": null,
  "projectedProductContext": [
    {
    "prodCtx": {
      "statusCode": "ACTIVE",
      "ident": "ZQ9FRQK7BF09YXAESFY9DDQP1G",
      "modDts": 1448307260000,
      "organization_id": "actest",
      "owningEntity": "6096892F54B5819E0A4C98A2@AdobeOrg",
      "serviceCode": "dma_tartan",
      "label": "Adobe Marketing Cloud",
      "serviceLevel": "standard",
      "createDts": 1421181343000,
      "deal_id": " "
      }
    }
  ]
}
```

* **Ao fazer uma solicitação para o Adobe.io, você obtém {&quot;code&quot;:500, &quot;message&quot;:&quot;Oops. Algo deu errado. Verifique seu URI e tente novamente.&quot;}**

O Adobe.io declara seu URI inválido: provavelmente o URI que você está solicitando não é válido. No Adobe.io, ao selecionar o serviço do Campaign, você obtém um seletor com uma lista de IDs_organizações possíveis. Você precisa verificar se aquele que você escolher é o que você colocou no seu URL.

* **Ao fazer uma solicitação para o Adobe.io, você obtém {&quot;error_code&quot;:&quot;401013&quot;,&quot;message&quot;:&quot;Oauth token is not valid&quot;}**

Seu token é inválido (chamada IMS inadequada usada para gerar um token) ou seu token expirou.

* **Não vejo meu perfil após a criação**

Dependendo da configuração da instância, o perfil criado precisa ser associado a uma **orgUnit**. Para entender como adicionar este campo à sua criação, consulte [esta seção](../../api/using/creating-profiles-api.md).

<!-- * (error duplicate key : quand tu crées un profile qui existe déjà , il faut faire un patch pour updater le profile plutôt qu’un POST)

With Curl
List all profiles

Create a profile

Update the mobilePhone attribute of a profile

API Calls on Service

GET the list of services

-->

<!--

How to find and use a filter?
Error codes:

* PAtch sur Age = message d'erreur :
500
Cannot update the 'age' property that is read-only
'age' property is not valid for the 'profile' resource.
-->

<!--
How to filter a list of subscribed profiles with available profile filters ? by date (by les filtres dispo sur la ressource) ?

Pattern classique :

recupérer la liste des subscriptions filtrées d'un profile
1) get sur profile
2) recup PKey
3) get sur PKey
4) get sur href des subscriptions

Comment savoir quel filtre appliquer ?

1) get sur metadata de profile
2) retourne description de la collection subscription
3) get sur la valeur du champ resTarget
4) get sur le href dans filters
5) retourne les filtres applicables sur l'url des data.

-->
