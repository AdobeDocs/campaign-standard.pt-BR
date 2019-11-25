---
title: Gerenciamento de mensagens transacionais
description: Saiba como gerenciar mensagens transacionais com APIs.
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


# Gerenciamento de mensagens transacionais {#managing-transactional-messages}

## Sobre mensagens transacionais

Depois de criar um evento, é necessário integrar o acionamento desse evento ao seu site.

>[!NOTE]
>
>A criação e publicação de um evento são apresentadas na documentação <a href="https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html">da Campanha</a>.

Por exemplo, você deseja que um evento de "abandono do carrinho" seja acionado sempre que um de seus clientes sair do site antes de comprar os produtos no carrinho. Para isso, o desenvolvedor da Web deve usar a REST Transactional Messages API (API de mensagens transacionais REST).

1. O desenvolvedor envia uma solicitação de acordo com o método POST, que aciona o [envio do evento](#sending-a-transactional-event)transacional.
1. A resposta à solicitação POST contém uma chave primária, que permite ao desenvolvedor enviar uma ou várias solicitações por meio de uma solicitação GET. Assim, ele pode obter o status [do](#transactional-event-status)evento.

## Envio de um evento transacional {#sending-a-transactional-event}

O evento transacional é enviado por meio de uma solicitação POST com a seguinte estrutura de URL:

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;ORGANIZAÇÃO&gt;**: sua ID pessoal da ORGANIZAÇÃO. Consulte [esta seção](../../api/using/must-read.md).

* **&lt;transactionalAPI&gt;**: os pontos finais da API de mensagens transacionais.

   O nome do endpoint da API de mensagens transacionais depende da configuração da sua instância. Corresponde ao valor "mc" seguido pela ID pessoal da organização. Vejamos o exemplo da empresa Geometrixx, com "geometrixx" como ID da empresa. Nesse caso, a solicitação POST seria a seguinte:

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   (Observe que o endpoint da API de mensagens transacionais também está visível durante a visualização da API)

* **&lt;eventID&gt;**: o tipo de evento que você deseja enviar. Essa ID é gerada ao criar a definição do evento. Consulte a documentação da [Campanha](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html).

### Cabeçalho de solicitação POST

A solicitação deve conter um "Tipo de conteúdo: application/json".

Você deve adicionar um charset, por exemplo **utf-8**. Observe que esse valor depende do aplicativo REST que você está usando.

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### corpo da solicitação POST

Os dados do evento estão contidos no corpo do POST JSON. A estrutura do evento depende de sua definição. O botão de visualização da API na tela de definição de recurso fornece uma amostra de solicitação. Consulte a documentação da [Campanha](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html).

Os seguintes parâmetros opcionais podem ser adicionados ao conteúdo do evento para gerenciar o envio de mensagens transacionais vinculadas ao evento:

* **expiração** (opcional): após essa data, o envio do evento transacional será cancelado.
* **programado** (opcional): a partir dessa data, o evento transacional será processado e a mensagem transacional será enviada.

>[!NOTE]
>
>Os valores dos parâmetros "expiração" e "agendada" seguem o formato ISO 8601. A norma ISO 8601 especifica a utilização da letra maiúscula "T" para separar a data e a hora. No entanto, ele pode ser removido da entrada ou saída para melhorar a leitura.

### Resposta à solicitação POST

A resposta POST retorna o status do evento transacional no momento em que foi criado. Para recuperar seu status atual (dados do evento, status do evento...), use a Chave primária retornada pela resposta POST em uma solicitação GET:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***Solicitação de amostra***

Solicitação POST para enviar o evento.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/mcAdobe/EVTcartAbandonment \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79'

{
  "email":"test@example.com",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "ctx":
  {
    "cartAmount": "$ 125",
    "lastProduct": "Leather motorbike jacket",
    "firstName": "Jack"
  }
}
```

Resposta à solicitação POST.

```
{
  "PKey":"<PKEY>",
  "ctx":
  {
    "cartAmount": "",
    "lastProduct": "",
    "firstName": ""
  }
  "email":"",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "href": "mcAdobe/EVTcartAbandonment/<PKEY>",
  "serverUrl":" https://myserver.com ",
  "status":"pending",
  "type":""
}
```

### Status do evento transacional {#transactional-event-status}

Na resposta, o campo "status" permite que você saiba se o evento foi processado ou não:

* **pendente**: o evento está pendente - o evento assume esse status quando acaba de ser acionado.
* **processamento**: o evento está com entrega pendente - está sendo transformado em uma mensagem e a mensagem está sendo enviada.
* **pausado**: o processo de evento está sendo pausado. Não é mais processado, mas mantido em fila no banco de dados do Adobe Campaign. For more on this, refer to the [Campaign documentation](https://helpx.adobe.com/campaign/standard/channels/using/event-transactional-messages.html#unpublishing-a-transactional-message).
* **processados**: o evento foi processado e a mensagem foi enviada com êxito.
* **ignorado**: o evento foi ignorado pela entrega, normalmente quando um endereço está em quarentena.
* **deliveryFailed**: ocorreu um erro de entrega enquanto o evento estava sendo processado.
* **routeFailed**: falha na fase de roteamento - isso pode ocorrer, por exemplo, quando o tipo de evento especificado não pode ser encontrado.
* **demasiado** antigo: o evento expirou antes de poder ser processado - isso pode ocorrer por vários motivos, por exemplo, quando um envio falha várias vezes (isso resulta no evento não atualizado) ou quando o servidor não pode mais processar eventos após ficar sobrecarregado.
* **targetingFailed**: O Campaign Standard não pôde enriquecer um link que está sendo usado para direcionamento de mensagem.
