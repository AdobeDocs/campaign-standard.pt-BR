---
title: Gerenciamento de mensagens transacionais
description: Saiba como gerenciar mensagens transacionais com APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 00d39438-a232-49f1-ae5e-1e98c73397e3
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 3%

---

# Gerenciamento de mensagens transacionais {#managing-transactional-messages}

Depois de criar e publicar um evento transacional, é necessário integrar o acionamento desse evento ao site.

>[!NOTE]
>
>A configuração do evento é detalhada em [nesta seção](../../channels/using/configuring-transactional-event.md).

Por exemplo, você deseja que um evento de &quot;Abandono de carrinho&quot; seja acionado sempre que um de seus clientes sair do site antes de comprar os produtos no carrinho. Para fazer isso, como desenvolvedor da Web, você deve usar a API de mensagens transacionais REST.

1. Envie uma solicitação de acordo com o método POST, que aciona o [envio do evento transacional](#sending-a-transactional-event).
1. A resposta à solicitação POST contém uma chave primária, que permite enviar uma ou várias solicitações por meio de uma solicitação GET. É possível obter a variável [status do evento](#transactional-event-status).

## Envio de um evento transacional {#sending-a-transactional-event}

O evento transacional é enviado por meio de uma solicitação POST com a seguinte estrutura de URL:

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;organization>**: a ID pessoal da organização. Consulte [esta seção](../../api/using/must-read.md).

* **&lt;transactionalapi>**: os endpoints da API de mensagens transacionais.

  O nome do endpoint da API de Mensagens transacionais depende da configuração da sua instância. Ele corresponde ao valor &quot;mc&quot; seguido pela ID de organização pessoal. Vejamos o exemplo da empresa Geometrixx, com &quot;geometrixx&quot; como a ID da organização. Nesse caso, o pedido POST seria o seguinte:

  `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

  Observe que o endpoint da API de mensagens transacionais também está visível durante a pré-visualização da API.

* **&lt;eventid>**: o tipo de evento que você deseja enviar. Essa ID é gerada ao criar a configuração do evento (consulte [nesta seção](../../channels/using/configuring-transactional-event.md#creating-an-event)).

### cabeçalho da solicitação POST

A solicitação deve conter um cabeçalho &quot;Content-Type: application/json&quot;.

Você deve adicionar um conjunto de caracteres, por exemplo **utf-8**. Observe que esse valor depende do aplicativo REST que você está usando.

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### corpo da solicitação POST

Os dados do evento estão contidos no corpo do POST JSON. A estrutura do evento depende de sua definição. O botão de visualização da API na tela de definição de recursos fornece um exemplo de solicitação. Consulte [esta seção](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

Os seguintes parâmetros opcionais podem ser adicionados ao conteúdo do evento para gerenciar o envio de mensagens transacionais vinculadas ao evento:

* **expiração** (opcional): após essa data, o envio do evento transacional será cancelado.
* **programado** (opcional): a partir dessa data, o evento transacional será processado e a mensagem transacional será enviada.

>[!NOTE]
>
>Os valores dos parâmetros &quot;expiration&quot; e &quot;scheduled&quot; seguem o formato ISO 8601. A norma ISO 8601 especifica a utilização da letra maiúscula &quot;T&quot; para separar a data e a hora. No entanto, ele pode ser removido da entrada ou saída para melhorar a legibilidade.

### Resposta à solicitação POST

A resposta POST retorna o status do evento transacional no momento em que foi criada. Para recuperar o status atual (dados do evento, status do evento...), use a Chave primária retornada pela resposta POST em uma solicitação GET:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***Exemplo de solicitação***

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

Na resposta, o campo &quot;status&quot; permite saber se o evento foi processado ou não:

* **pendente**: o evento está pendente - o evento assume esse status quando acabou de ser acionado.
* **processando**: a entrega do evento está pendente - ele está sendo transformado em uma mensagem e a mensagem está sendo enviada.
* **pausado**: o processo do evento está sendo pausado. Ele não é mais processado, mas mantido em fila no banco de dados do Adobe Campaign. Para obter mais informações, consulte [esta seção](../../channels/using/publishing-transactional-message.md#suspending-a-transactional-message-publication).
* **processado**: o evento foi processado e a mensagem foi enviada com êxito.
* **ignorado**: o evento foi ignorado pelo delivery, normalmente quando um endereço está em quarentena.
* **deliveryFailed**: ocorreu um erro de delivery enquanto o evento estava sendo processado.
* **routingFailed**: a fase de roteamento falhou - isso pode ocorrer, por exemplo, quando o tipo de evento especificado não pode ser encontrado.
* **tooOld**: o evento expirou antes de poder ser processado - isso pode acontecer por vários motivos, por exemplo, quando um envio falha várias vezes (isso resulta no evento não estar mais atualizado) ou quando o servidor não pode mais processar eventos após ficar sobrecarregado.
* **targetingFailed**: o Campaign Standard falhou ao enriquecer um link que está sendo usado para o direcionamento de mensagens.
