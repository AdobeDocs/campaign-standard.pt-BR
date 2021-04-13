---
solution: Campaign Standard
product: campaign
title: Leitura obrigatória
description: Leitura obrigatória antes de usar APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9e2d1b59-55a5-4715-adfb-35191a9df536
translation-type: tm+mt
source-git-commit: 01e4eb027b55815c3680b26691e61cbe5b63ee8c
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 0%

---

# Leitura obrigatória {#must-read}

## Requisitos técnicos

* As APIs do Adobe Campaign devem ser usadas somente do Servidor para o Servidor.
* Verifique sempre com seu contato técnico do Adobe se o caso de uso que você deseja implementar está alinhado com a escala permitida pelas APIs do Adobe Campaign.
* A configuração de um acesso AdobeIO requer permissões específicas. Entre em contato com o Suporte do Adobe para verificar se há problemas.

## Direitos e acesso

* Por padrão, as APIs do Adobe Campaign usam o contexto de administrador e, portanto, as unidades e funções da organização não se aplicam.
* As APIs do Adobe Campaign são excluídas do contexto de função.
* Se quiser configurar as APIs com uma unidade ou funções de organização, verifique primeiro com seu contato técnico do Adobe.

## Representação de recursos

Todos os recursos da API estão disponíveis em **JSON** com uma extensão de URL ou dentro de um Cabeçalho de Aceitação HTTP:

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>Sem a extensão no URL, o formato **json é o padrão** para o tipo de conteúdo.

<br/>

***exemplo de solicitação***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile.json \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

## Chave primária e URLs

* Não tente criar um URL sozinho. Todos os URLs são retornados pela API. No entanto, é possível criar um URL com base no nome do recurso de nível superior.

* Os valores da chave primária automática (PKey) que ilustram os exemplos não devem funcionar em outra implantação específica. Eles são produzidos pela API do Adobe Campaign.

* Os valores de Chave primária automática gerados pelo Adobe Campaign nunca devem ser armazenados em um banco de dados ou site externo. Você deve gerar campos-chave específicos na definição do banco de dados e usá-los durante os desenvolvimentos.

## Chaves personalizadas {#custom-keys}

Se o recurso de perfil tiver sido estendido com um campo de chave personalizada, você poderá usar esse campo como uma chave em vez da Chave primária automática gerada pelo Adobe Campaign:

`GET /.../profileAndServicesExt/profile/<customKey>`

As chaves personalizadas não podem ser modificadas usando uma operação PATCH se o valor da chave for diferente da chave de origem ou se estiver usando sua própria chave comercial como URI em vez da fornecida pelo Adobe.

Use uma chave personalizada somente para **recursos de perfil de nível superior**. Os URLs são retornados pela API e nunca devem ser criados por você mesmo.

<br/>

***Solicitação de exemplo***

Para recuperar as assinaturas de um perfil usando uma chave personalizada, execute uma operação de GET na chave personalizada.

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

Retorna a lista de assinaturas do perfil.

```
"service": {
"PKey": "<PKEY>",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
"label": "Sport Newsletter",
"name": "SVC1",
"title": "Sport Newsletter (SVC1)"
}
```
