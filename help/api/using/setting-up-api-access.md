---
title: Configuração do acesso à API
description: Saiba como configurar o acesso às APIs do Campaign Standard.
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


# Configuração do acesso à API {#setting-up-api-access}

O acesso à API do Adobe Campaign Standard é configurado pelas etapas abaixo. Cada uma dessas etapas está detalhada na documentação [de E/S da](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)Adobe.

>[!CAUTION]
>
>Para gerenciar certificados no Adobe IO, verifique se você tem direitos de administrador <b>do</b> sistema na organização ou em uma conta <a href="https://helpx.adobe.com/enterprise/using/manage-developers.html">de</a> desenvolvedor no Admin Console.

1. **Verifique se você tem um certificado** digital ou crie um, se necessário. As chaves públicas e privadas fornecidas com o certificado são necessárias nas etapas a seguir.
1. **Crie uma nova integração com o Adobe Campaign Service** no Adobe IO e configure-a. Suas credenciais serão geradas (chave da API, segredo do cliente...).
1. **Crie um JSON Web Token (JWT)** a partir das credenciais geradas anteriormente e assine-o com sua chave privada. O JWT codifica todas as informações de identidade e segurança necessárias para a Adobe verificar sua identidade e conceder acesso à API.
1. **Troque seu JWT por um token** de acesso por meio de uma solicitação POST. Este token de acesso terá de ser utilizado em cada cabeçalho das suas solicitações de API.

Para estabelecer uma sessão segura de API de E/S da Adobe de serviço para serviço, cada solicitação a um serviço da Adobe deve incluir no cabeçalho de Autorização as informações abaixo.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;ORGANIZAÇÃO&gt;**: Esta é sua ID pessoal DA ORGANIZAÇÃO, uma ID DA ORGANIZAÇÃO é fornecida pela Adobe para cada uma de suas instâncias:

   * &lt;ORGANIZAÇÃO&gt; : sua instância de produção,
   * &lt;ORGANIZATION-mkt-stage&gt;: sua instância do palco.
   Para obter o valor da ID da ORGANIZAÇÃO, consulte o administrador ou o contato técnico da Adobe. Você também pode recuperá-la em E/S da Adobe ao criar uma nova integração, na lista de licenças (consulte a documentação <a href="https://www.adobe.io/authentication.html">de E/S da</a>Adobe).

* **&lt;ACCESS_TOKEN&gt;**: Seu token de acesso pessoal, que foi recuperado ao trocar seu token JSON Web por meio de uma solicitação POST.

* **&lt;API_KEY&gt;**: sua chave de API pessoal. Ele é fornecido em E/S da Adobe após criar uma nova integração com o Adobe Campaign Service.

   ![texto alternativo](assets/tenant.png)
