---
solution: Campaign Standard
product: campaign
title: Configuração do acesso à API
description: Saiba como configurar o acesso às APIs do Campaign Standard.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 4%

---


# Configuração do acesso à API {#setting-up-api-access}

O acesso à API do Adobe Campaign Standard é configurado pelas etapas abaixo. Cada uma dessas etapas é detalhada na [documentação de Adobe IO](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Para gerenciar certificados no Adobe IO, verifique se você tem os direitos de <b>Administrador do sistema</b> na organização ou uma [conta do desenvolvedor](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a> no Admin Console.

1. **Verifique se você tem um certificado** digital ou crie um, se necessário. As chaves públicas e privadas fornecidas com o certificado são necessárias nas etapas a seguir.
1. **Crie uma nova integração com o Adobe Campaign** Service no Adobe IO e configure-a. Suas credenciais serão geradas (Chave da API, Segredo do cliente...).
1. **Crie um JSON Web Token (JWT)** a partir das credenciais geradas anteriormente e assine-o com sua chave privada. O JWT codifica todas as informações de identidade e segurança necessárias para o Adobe verificar sua identidade e conceder acesso à API.
1. **Troque seu JWT por um** Tokenthrough em uma solicitação de POST. Esse Token de acesso precisará ser usado em cada cabeçalho das solicitações de API.

Para estabelecer uma sessão de Adobe I/O de serviço a serviço seguro, cada solicitação para um serviço do Adobe deve incluir no cabeçalho de Autorização as informações abaixo.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**: Esta é a ID da ORGANIZAÇÃO pessoal, uma ID da ORGANIZAÇÃO é fornecida pelo Adobe para cada uma das instâncias :

   * &lt;organization> : sua instância de produção,
   * &lt;organization-mkt-stage>: sua instância do estágio.

   Para obter o valor da ID da ORGANIZAÇÃO, consulte o administrador ou o contato técnico do Adobe. Você também pode recuperá-la no Adobe I/O ao criar uma nova integração, na lista de licenças (consulte a <a href="https://www.adobe.io/authentication.html">documentação do Adobe IO</a>).

* **&lt;access_token>**: Seu token de acesso pessoal, que foi recuperado ao trocar seu token Web JSON por meio de uma solicitação POST.

* **&lt;api_key>**: sua Chave de API pessoal. Ele é fornecido no Adobe I/O após criar uma nova integração com o Adobe Campaign Service.

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