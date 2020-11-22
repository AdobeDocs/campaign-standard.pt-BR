---
solution: Campaign Standard
product: campaign
title: Leitura obrigatória
description: Deve ler antes de usar as APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---


# Must-Read {#must-read}

## Requisitos técnicos

* As APIs da Adobe Campaign devem ser usadas apenas como Servidor para Servidor.
* Verifique sempre com seu contato técnico do Adobe se o caso de uso que você deseja implementar está alinhado com a escala permitida pelas APIs do Adobe Campaign.
* A configuração de um acesso AdobeIO requer permissões específicas, entre em contato com o Suporte ao Adobe para encontrar qualquer problema.

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

* Os valores de chave primária automática (PKey) que ilustram os exemplos não devem funcionar em outra implantação específica. Eles são produzidos pela API da Adobe Campaign.

* Os valores de Chave Primária Automática gerados pela Adobe Campaign nunca devem ser armazenados em um banco de dados ou site externo. Você deve gerar campos-chave específicos na definição do banco de dados e usá-los durante seus desenvolvimentos.

## Teclas personalizadas {#custom-keys}

Se o recurso de perfil tiver sido estendido com um campo de chave personalizado, você poderá usar esse campo como uma chave em vez da Chave primária automática gerada pela Adobe Campaign:

`GET /.../profileAndServicesExt/profile/<customKey>`

As chaves personalizadas não podem ser modificadas usando uma operação PATCH se o valor da chave for diferente da chave de origem ou se você estiver usando sua própria chave de negócio como URI em vez da fornecida pelo Adobe.

Use uma chave personalizada somente para recursos **de perfil de nível** superior. Os URLs são retornados pela API e nunca devem ser criados por você mesmo.

<br/>

***Solicitação de amostra***

Para recuperar as subscrições de um perfil usando uma chave personalizada, execute uma operação de GET na chave personalizada.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<customKey> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Execute uma solicitação de GET no URL do subscrição retornado.

```
-X GET <SUBSCRIPTION_URL> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna a lista das subscrições para o perfil.

```
"service": {
"PKey": "<PKEY>",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
"label": "Sport Newsletter",
"name": "SVC1",
"title": "Sport Newsletter (SVC1)"
}
```
