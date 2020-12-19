---
solution: Campaign Standard
product: campaign
title: Configuração do acesso à API
description: Saiba como configurar o acesso às APIs do Campaign Standard.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 3%

---


# Configuração do acesso à API {#setting-up-api-access}

O acesso à API do Adobe Campaign Standard é configurado através das etapas abaixo. Cada uma dessas etapas está detalhada na documentação [Adobe IO](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Para gerenciar certificados no Adobe IO, verifique se você tem <b>direitos de administrador do sistema</b> na organização ou uma [conta de desenvolvedor](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a> no Admin Console.

1. **Verifique se você tem um certificado** digital ou crie um, se necessário. As chaves públicas e privadas fornecidas com o certificado são necessárias nas etapas a seguir.
1. **Crie uma nova integração para o Adobe Campaign** Service Adobe e/S e configure-a. Suas credenciais serão geradas (chave da API, segredo do cliente...).
1. **Crie um JSON Web Token (JWT)** a partir das credenciais geradas anteriormente e assine-o com sua chave privada. O JWT codifica todas as informações de identidade e segurança necessárias ao Adobe para verificar sua identidade e conceder acesso à API.
1. **Troque seu JWT por um** Tokenface de acesso por meio de uma solicitação de POST. Esse Token de acesso deverá ser usado em cada cabeçalho das solicitações de API.

Para estabelecer uma sessão segura de API de serviço a serviço da Adobe I/O, cada solicitação a um serviço de Adobe deve incluir no cabeçalho de Autorização as informações abaixo.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**: Esta é a ID pessoal da ORGANIZAÇÃO, uma ID da ORGANIZAÇÃO é fornecida pelo Adobe para cada uma das instâncias:

   * &lt;organization> : sua instância de produção,
   * &lt;organization-mkt-stage>: sua instância do palco.

   Para obter o valor da ID da ORGANIZAÇÃO, consulte o administrador ou o contato técnico do Adobe. Você também pode recuperá-la no Adobe I/O ao criar uma nova integração, na lista de licenças (consulte a <a href="https://www.adobe.io/authentication.html">documentação de E/S do Adobe</a>).

* **&lt;access_token>**: Seu token de acesso pessoal, que foi recuperado ao trocar seu JSON Web Token por meio de uma solicitação de POST.

* **&lt;api_key>**: sua chave de API pessoal. Ele é fornecido na Adobe I/O após a criação de uma nova integração com o Adobe Campaign Service.

   ![texto alternativo](assets/tenant.png)

## Solução de problemas

Durante a integração do Adobe IO, se o seguinte erro for exibido:

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


Consulte o administrador ou o contato técnico do Adobe para verificar se o parâmetro CNAME foi criado corretamente.