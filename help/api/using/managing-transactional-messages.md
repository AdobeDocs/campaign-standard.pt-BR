---
solution: Campaign Standard
product: campaign
title: Gerenciamento de mensagens transacionais
description: Saiba como gerenciar mensagens transacionais com APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 3%

---


# Gerenciamento de mensagens transacionais {#managing-transactional-messages}

## Sobre mensagens transacionais

Depois de criar e publicar um evento transacional, é necessário integrar o acionamento desse evento no site.

>[!NOTE]
>
>A configuração de um evento é apresentada em [nesta seção](../../channels/using/configuring-transactional-event.md).

Por exemplo, você deseja que um evento de &quot;Abandono do carrinho&quot; seja acionado sempre que um dos clientes sair do site antes de comprar os produtos no carrinho. Para fazer isso, o desenvolvedor da Web deve usar a API REST Transactional Messages .

1. O desenvolvedor envia uma solicitação de acordo com o método POST, que aciona o [envio do evento transacional](#sending-a-transactional-event).
1. A resposta à solicitação POST contém uma Chave primária, que permite ao desenvolvedor enviar uma ou várias solicitações por meio de uma solicitação GET. Dessa forma, ele poderá obter o [status do evento](#transactional-event-status).

## Envio de um evento transacional {#sending-a-transactional-event}

O evento transacional é enviado por meio de uma solicitação POST com a seguinte estrutura de URL:

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;organization>**: sua ID pessoal da ORGANIZAÇÃO. Consulte [esta seção](../../api/using/must-read.md).

* **&lt;transactionalapi>**: os pontos finais da API de mensagens transacionais.

   O nome do endpoint da API de mensagens transacionais depende da configuração da instância. Corresponde ao valor &quot;mc&quot; seguido pela ID da organização pessoal. Considere o exemplo da empresa do Geometrixx, com &quot;geometrixx&quot; como a ID da organização. Nesse caso, a solicitação POST seria a seguinte:

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   (Observe que o endpoint da API de mensagens transacionais também está visível durante a visualização da API)

* **&lt;eventid>**: o tipo de evento que você deseja enviar. Essa ID é gerada ao criar a configuração do evento (consulte [esta seção](../../channels/using/configuring-transactional-event.md#creating-an-event)).

### Cabeçalho de solicitação de POST

A solicitação deve conter um &quot;Content-Type: application/json&quot;.

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

Os dados do evento estão contidos no corpo do POST JSON. A estrutura do evento depende de sua definição. O botão de visualização da API na tela de definição de recurso fornece uma amostra de solicitação. Consulte [esta seção](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

Os seguintes parâmetros opcionais podem ser adicionados ao conteúdo do evento para gerenciar o envio de mensagens transacionais vinculadas ao evento:

* **expiração**  (opcional): após essa data, o envio do evento transacional será cancelado.
* **agendado**  (opcional): a partir dessa data, o evento transacional será processado e a mensagem transacional será enviada.

>[!NOTE]
>
>Os valores dos parâmetros &quot;expiration&quot; e &quot;scheduled&quot; seguem o formato ISO 8601. A norma ISO 8601 especifica a utilização da letra maiúscula &quot;T&quot; para separar a data e a hora. No entanto, ele pode ser removido da entrada ou saída para melhorar a legibilidade.

### Resposta à solicitação POST

A resposta POST retorna o status do evento transacional no momento em que foi criado. Para recuperar o status atual (dados do evento, status do evento...), use a Chave primária retornada pela resposta do POST em uma solicitação GET:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***Solicitação de exemplo***

Solicitação de POST para enviar o evento.

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

Resposta à solicitação do POST.

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
* **processamento**: o evento está com o delivery pendente - ele está sendo transformado em uma mensagem e a mensagem está sendo enviada.
* **pausado**: o processo de evento está sendo pausado. Ele não é mais processado, mas mantido em fila no banco de dados do Adobe Campaign. Para obter mais informações, consulte [esta seção](../../channels/using/publishing-transactional-message.md#suspending-a-transactional-message-publication).
* **processado**: o evento foi processado e a mensagem foi enviada com êxito.
* **ignorado**: o evento foi ignorado pelo delivery, normalmente quando um endereço está em quarentena.
* **deliveryFailed**: ocorreu um erro de delivery enquanto o evento estava sendo processado.
* **routingFailed**: a fase de roteamento falhou - isso pode ocorrer, por exemplo, quando o tipo de evento especificado não pode ser encontrado.
* **demasiado** antigo: o evento expirou antes de poder ser processado - isso pode ocorrer por vários motivos, por exemplo, quando um envio falha várias vezes (o que resulta no evento não estar mais atualizado) ou quando o servidor não pode mais processar eventos após ficar sobrecarregado.
* **targetingFailed**: Falha do Campaign Standard ao enriquecer um link que está sendo usado para o direcionamento de mensagens.
