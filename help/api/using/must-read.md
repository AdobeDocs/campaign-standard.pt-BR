---
title: Leitura obrigatória
description: Deve ler antes de usar as APIs.
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
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# Leitura obrigatória {#must-read}

## Requisitos técnicos

* As APIs do Adobe Campaign devem ser usadas somente como Servidor para Servidor.
* Verifique sempre com seu contato técnico da Adobe se o caso de uso que você deseja implementar está alinhado com a escala permitida pelas APIs do Adobe Campaign.
* A configuração de um acesso AdobeIO requer permissões específicas, entre em contato com o suporte da Adobe para obter qualquer problema.

## Representação de recursos

Todos os recursos da API estão disponíveis no **JSON** com uma extensão de URL ou dentro de um cabeçalho HTTP Accept:

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>Sem extensão no URL, o formato **json é o padrão** para o tipo de conteúdo.

<br/>

***amostra de solicitação***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile.json \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

## Chave primária e URLs

* Não tente criar um URL sozinho. Todos os URLs são retornados pela API. No entanto, é possível criar um URL com base no nome do recurso de nível superior.

* Os valores de chave primária automática (PKey) que ilustram os exemplos não devem funcionar em outra implantação específica. Eles são produzidos pela Adobe Campaign API.

* Os valores de Chave primária automática gerados pelo Adobe Campaign nunca devem ser armazenados em um banco de dados ou site externo. Você deve gerar campos-chave específicos na definição do banco de dados e usá-los durante seus desenvolvimentos.

## Teclas personalizadas {#custom-keys}

Se o recurso de perfil tiver sido estendido com um campo de chave personalizado, você poderá usar esse campo como uma chave em vez da Chave primária automática gerada pelo Adobe Campaign:

`GET /.../profileAndServicesExt/profile/<customKey>`

As chaves personalizadas não podem ser modificadas usando uma operação PATCH se o valor da chave for diferente da chave de origem ou se você estiver usando sua própria chave comercial como URI em vez da fornecida pela Adobe.

Use uma chave personalizada somente para recursos **de perfil de nível** superior. Os URLs são retornados pela API e nunca devem ser criados por você mesmo.

<br/>

***Solicitação de amostra***

Para recuperar as assinaturas de um perfil usando uma chave personalizada, execute uma operação GET na chave personalizada.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<customKey> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Execute uma solicitação GET no URL de assinaturas retornado.

```
-X GET <SUBSCRIPTION_URL> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna a lista de assinaturas do perfil.

```
"service": {
"PKey": "<PKEY>",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
"label": "Sport Newsletter",
"name": "SVC1",
"title": "Sport Newsletter (SVC1)"
}
```
