---
title: Solução de problemas
description: Saiba mais sobre problemas comuns relacionados às APIs do Campaign Standard.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Solução de problemas {#troubleshooting}

* **Ao acessar o Adobe.io Console, você recebe o seguinte erro: "O console de E/S da Adobe só está disponível para selecionar membros de contas corporativas. Se você achar que deve ter acesso, entre em contato com o administrador do sistema."**

Você só pode criar Chaves de API para as organizações IMS das quais você é administrador. Se esta mensagem for exibida e você quiser criar chaves de API e perguntar a um administrador da organização IMS.

* **Ao fazer uma solicitação para o Adobe.io, você obtém {"error_code":"403023","message":"Profile is not valid"}**

Isso significa que há um problema com o provisionamento IMS do seu produto específico do Campaign: a equipe IMS precisa consertá-lo.

Para obter mais detalhes, você pode chamar a API IMS com seu token para ver a aparência do perfil IMS: É necessário ter um prodCtx em que a Organization_id seja a mesma que você inseriu no URL para que o Adobe.io possa rotear sua solicitação.
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

Verifique seu perfil IMS com esta solicitação.

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

* **Ao fazer uma solicitação para o Adobe.io você obtém {"code":500, "message":"Oops. Algo deu errado. Verifique seu URI e tente novamente."}**

O Adobe.io declara seu URI inválido: provavelmente o URI que você está solicitando não é válido. No Adobe.io, ao selecionar o serviço de Campanha, você obtém um seletor com uma lista de IDs_organizacionais possíveis. É necessário verificar se a opção escolhida é aquela que você coloca no URL.

* **Ao fazer uma solicitação para o Adobe.io, você obtém {"error_code":"401013","message":"Oauth token is not valid"}**

Seu token é inválido (chamada IMS incorreta usada para gerar um token) ou seu token expirou.

* **Não vejo meu perfil depois da criação**

Dependendo da configuração da instância, o perfil criado precisa ser associado a uma **orgUnit**. Para saber como adicionar este campo à sua criação, consulte [esta seção](../../api/using/creating-profiles.md).

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
