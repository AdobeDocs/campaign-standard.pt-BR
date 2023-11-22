---
title: Configuração do acesso à API
description: Saiba como configurar o acesso a APIs Campaign Standard.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: efbbd0cd-9c56-4ad0-8bcb-efba4b63c28b
source-git-commit: 7ca7e9bd9541a4db708565e65e2ff87e44393238
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 3%

---

# Configuração do acesso à API {#setting-up-api-access}

O acesso à API do Adobe Campaign Standard é configurado de acordo com as etapas abaixo. Cada uma dessas etapas é detalhada na seção [Documentação do Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Para gerenciar certificados no [Adobe Developer](https://developer.adobe.com/), verifique se você tem **Administrador do sistema** direitos sobre a organização ou uma [conta do desenvolvedor](https://helpx.adobe.com/br/enterprise/using/manage-developers.html) no Admin Console.

1. **Verifique se você tem um certificado digital**, ou crie um, se necessário. As chaves públicas e privadas fornecidas com o certificado são necessárias nas etapas a seguir.
1. **Criar uma nova integração com o Adobe Campaign Service** in [Adobe Developer](https://developer.adobe.com/) e configure-a. Suas credenciais serão geradas (Chave da API, Segredo do cliente...).
1. **Criar um JSON Web Token (JWT)** das credenciais geradas anteriormente e assine-a com a chave privada. O JWT codifica todas as informações de identidade e segurança necessárias para que o Adobe verifique sua identidade e conceda acesso à API.

   >[!AVAILABILITY]
   >
   >O JWT (JSON Web Tokens) está atualmente no processo de depreciação e está sendo substituído pelo OAuth. A transição está sendo realizada progressivamente nas próximas versões do Campaign e a documentação será atualizada para refletir essas atualizações.

1. **Trocar seu JWT por um token de acesso** por meio de uma solicitação POST. Esse token de acesso precisará ser usado em cada cabeçalho das solicitações de API.

Para estabelecer uma sessão segura de API de Adobe I/O de serviço para serviço, cada solicitação para um serviço da Adobe deve incluir as informações abaixo no cabeçalho de Autorização.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**: esta é a sua ID de ORGANIZAÇÃO pessoal, uma ID de ORGANIZAÇÃO é fornecida pelo Adobe para cada uma de suas instâncias:

   * &lt;organization> : sua instância de produção,
   * &lt;organization-mkt-stage>: a instância do estágio.

  Para obter o valor ID da ORGANIZAÇÃO, consulte o administrador ou o contato técnico da Adobe. Você também pode recuperá-la no Adobe I/O ao criar uma nova integração, na lista de licenças (consulte a <a href="https://developer.adobe.com/developer-console/docs/guides/authentication/">Documentação do Adobe Developer</a>).

* **&lt;access_token>**: seu token de acesso pessoal, que foi recuperado ao trocar seu JSON Web Token por meio de uma solicitação POST.

* **&lt;api_key>**: sua chave de API pessoal. Ele é fornecido no Adobe I/O após a criação de uma nova integração ao Adobe Campaign Service.

  ![texto alternativo](assets/tenant.png)

## Solução de problemas

Durante a integração do AdobeIO, se o seguinte erro for exibido:

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


Consulte o administrador ou o contato técnico do Adobe para verificar se o parâmetro CNAME foi criado corretamente.
