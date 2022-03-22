---
title: Solução de problemas de API
description: Saiba mais sobre problemas comuns relacionados a APIs do Campaign Standard
feature: API
role: Data Engineer
level: Experienced
exl-id: 404356cd-021f-4739-a88f-b8b1b79e19bc
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 1%

---

# Solução de problemas de API {#troubleshooting}

* **Ao acessar o console do Adobe.io, você recebe o seguinte erro: &quot;O console Adobe I/O só está disponível para selecionar membros de contas corporativas. Se você acha que deve ter acesso, entre em contato com o administrador do sistema.&quot;**

Você só pode criar Chaves de API para as organizações IMS das quais é administrador. Se essa mensagem for exibida e você quiser criar Chaves de API e solicitar um administrador da organização IMS.

* **Ao fazer uma solicitação ao Adobe.io, você obtém o {&quot;error_code&quot;:&quot;403023&quot;, &quot;message&quot;:&quot;Profile is not valid&quot;}**

Isso significa que há um problema com o provisionamento IMS do seu produto específico do Campaign: a equipe IMS precisa corrigi-la.

Para obter mais detalhes, chame a API IMS com o token para ver a aparência do perfil IMS: Você precisa ter um prodCtx em que a organization_id é igual àquela que você colocou no URL do Adobe.io para poder rotear sua solicitação.
Se estiver faltando, o provisionamento IMS precisa ser corrigido.

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

Verifique o perfil IMS com essa solicitação.

```
-X GET https://ims-na1.adobelogin.com/ims/profile/v1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Na resposta, o valor ORGANIZATION_ID deve ser o mesmo na primeira solicitação do GET.

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

Adobe.io declara seu URI inválido: provavelmente o URI que você está solicitando não é válido. No Adobe.io, ao selecionar o serviço Campaign, você obtém um seletor com uma lista de IDs_da_organização possíveis. Você precisa verificar se aquele que escolher é aquele que você colocou no URL.

* **Ao fazer uma solicitação ao Adobe.io, você obtém o {&quot;error_code&quot;:&quot;401013&quot;, &quot;message&quot;:&quot;Oauth token is not valid&quot;}**

Seu token é inválido (chamada IMS incorreta usada para gerar um token) ou seu token expirou.

* **Não vejo meu perfil após a criação**

Dependendo da configuração da instância, o perfil criado precisa ser associado a um **orgUnit**. Para entender como adicionar esse campo à criação, consulte [esta seção](../../api/using/creating-profiles-api.md).

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
