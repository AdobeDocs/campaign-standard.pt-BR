---
solution: Campaign Standard
product: campaign
title: Gerenciamento de mensagens transacionais
description: Saiba como gerenciar mensagens transacionais com APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 1%

---


# Gerenciamento de mensagens transacionais {#managing-transactional-messages}

## Sobre mensagens transacionais

Depois de criar um evento, é necessário integrar o acionamento desse evento ao seu site.

>[!NOTE]
>
>Criar e publicar um evento são apresentados na documentação [](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html)da Campanha.

Por exemplo, você deseja que um evento de &quot;abandono do carrinho&quot; seja acionado sempre que um de seus clientes sair do site antes de comprar os produtos no carrinho. Para isso, seu desenvolvedor da Web deve usar a REST Mensagen transacional API.

1. O desenvolvedor envia uma solicitação de acordo com o método POST, que aciona o [envio do evento](#sending-a-transactional-event)transacional.
1. A resposta à solicitação de POST contém uma Chave primária, que permite ao desenvolvedor enviar uma ou várias solicitações por meio de uma solicitação de GET. Desta forma, ele consegue obter o status [de](#transactional-event-status)evento.

## Envio de um evento transacional {#sending-a-transactional-event}

O evento transacional é enviado por meio de uma solicitação de POST com a seguinte estrutura de URL:

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;ORGANIZAÇÃO>**: sua ID pessoal da ORGANIZAÇÃO. Consulte [esta seção](../../api/using/must-read.md).

* **&lt;transactionalAPI>**: os pontos finais da API de Mensagens transacionais.

   O nome do terminal da API de Mensagens transacionais depende da configuração da sua instância. Corresponde ao valor &quot;mc&quot; seguido pela ID pessoal da organização. Vejamos o exemplo da empresa de Geometrixx, com &quot;geometrixx&quot; como sua ID de empresa. Nesse caso, o pedido de POST seria o seguinte:

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   (Observe que o ponto de extremidade da API de mensagens transacionais também está visível durante a pré-visualização da API)

* **&lt;eventID>**: o tipo de evento que você deseja enviar. Essa ID é gerada ao criar a definição do evento. Refer to the [Campaign documentation](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html).

### cabeçalho de solicitação de POST

A solicitação deve conter um &quot;Tipo de conteúdo: application/json&quot;.

Você deve adicionar um charset, por exemplo **utf-8**. Observe que esse valor depende do aplicativo REST que você está usando.

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### corpo de solicitação de POST

Os dados do evento estão contidos no corpo do POST JSON. A estrutura do evento depende de sua definição. O botão pré-visualização da API na tela de definição de recurso fornece uma amostra de solicitação. Refer to the [Campaign documentation](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html).

Os seguintes parâmetros opcionais podem ser adicionados ao conteúdo do evento para gerenciar o envio de mensagens transacionais vinculados ao evento:

* **expiração** (opcional): após essa data, o envio do evento transacional será cancelado.
* **programado** (opcional): a partir dessa data, o evento transacional será processado e o mensagen transacional será enviado.

>[!NOTE]
>
>Os valores dos parâmetros &quot;expiração&quot; e &quot;agendada&quot; seguem o formato ISO 8601. A norma ISO 8601 especifica a utilização da letra maiúscula &quot;T&quot; para separar a data e a hora. No entanto, ele pode ser removido da entrada ou saída para melhorar a leitura.

### Resposta à solicitação de POST

A resposta POST retorna o status do evento transacional no momento em que foi criado. Para recuperar seu status atual (dados do evento, status do evento...), use a Chave Primária retornada pela resposta do POST em uma solicitação de GET:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***Solicitação de amostra***

POST para enviar o evento.

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

Resposta à solicitação de POST.

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

Na resposta, o campo &quot;status&quot; permite que você saiba se o evento foi processado ou não:

* **pendente**: o evento está pendente - o evento assume esse status quando acaba de ser acionado.
* **processamento**: o evento está com delivery pendente - ele está sendo transformado em uma mensagem e a mensagem está sendo enviada.
* **pausado**: o processo de evento está sendo pausado. Não é mais processado, mas mantido em fila no banco de dados Adobe Campaign. For more on this, refer to the [Campaign documentation](https://helpx.adobe.com/campaign/standard/channels/using/event-transactional-messages.html#unpublishing-a-transactional-message).
* **processados**: o evento foi processado e a mensagem foi enviada com êxito.
* **ignorado**: o evento foi ignorado pelo delivery, geralmente quando um endereço está na quarentena.
* **deliveryFailed**: ocorreu um erro de delivery enquanto o evento estava sendo processado.
* **routeFailed**: falha na fase do roteamento - isso pode ocorrer, por exemplo, quando o tipo de evento especificado não pode ser encontrado.
* **demasiado** antigo: o evento expirou antes de ser processado - isso pode ocorrer por vários motivos, por exemplo, quando um envio falha várias vezes (isso resulta no evento não atualizado) ou quando o servidor não pode mais processar eventos depois de sobrecarregado.
* **targetingFailed**: O Campaign Standard não conseguiu enriquecer um link que está sendo usado para o direcionamento de mensagens.
