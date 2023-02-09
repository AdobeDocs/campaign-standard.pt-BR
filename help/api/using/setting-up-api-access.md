---
title: Configuração do acesso à API
description: Saiba como configurar o acesso às APIs do Campaign Standard.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: efbbd0cd-9c56-4ad0-8bcb-efba4b63c28b
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 2%

---

# Configuração do acesso à API {#setting-up-api-access}

O acesso à API do Adobe Campaign Standard é configurado pelas etapas abaixo. Cada uma dessas etapas é detalhada no [Documentação do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Para gerenciar certificados no [Adobe Developer](https://developer.adobe.com/), certifique-se de que **Administrador do sistema** direitos sobre a organização ou [conta do desenvolvedor](https://helpx.adobe.com/br/enterprise/using/manage-developers.html) na Admin Console.

1. **Verifique se você tem um certificado digital**, ou crie um, se necessário. As chaves públicas e privadas fornecidas com o certificado são necessárias nas etapas a seguir.
1. **Criar uma nova integração com o Adobe Campaign Service** em [Adobe Developer](https://developer.adobe.com/) e configure-a. Suas credenciais serão geradas (Chave da API, Segredo do cliente...).
1. **Criar um JSON Web Token (JWT)** das credenciais geradas anteriormente e assine-as com sua chave privada. O JWT codifica todas as informações de identidade e segurança necessárias para o Adobe verificar sua identidade e conceder acesso à API.
1. **Troque seu JWT por um token de acesso** por meio de uma solicitação de POST. Esse Token de acesso precisará ser usado em cada cabeçalho das solicitações de API.

Para estabelecer uma sessão de Adobe I/O de serviço para serviço seguro, cada solicitação para um serviço da Adobe deve incluir no cabeçalho de Autorização as informações abaixo.

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

   Para obter o valor da ID da ORGANIZAÇÃO, consulte o administrador ou o contato técnico do Adobe. Você também pode recuperá-la no Adobe I/O ao criar uma nova integração, na lista de licenças (consulte <a href="https://developer.adobe.com/developer-console/docs/guides/authentication/">Documentação do Adobe Developer</a>).

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
