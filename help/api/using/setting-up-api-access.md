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
source-git-commit: fa80fefc1c897afb8448fc0121705102091ecf5c

---


# Configuração do acesso à API {#setting-up-api-access}

O acesso à API do Adobe Campaign Standard é configurado através das etapas abaixo. Cada uma dessas etapas está detalhada na documentação [de E/S da](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)Adobe.

>[!IMPORTANT]
>
>Para gerenciar certificados no Adobe IO, verifique se você tem direitos de administrador <b>do</b> sistema na organização ou em uma conta [de](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a> desenvolvedor no Admin Console.

1. **Verifique se você tem um certificado** digital ou crie um, se necessário. As chaves públicas e privadas fornecidas com o certificado são necessárias nas etapas a seguir.
1. **Crie uma nova integração ao Adobe Campaign Service** no Adobe IO e configure-o. Suas credenciais serão geradas (chave da API, segredo do cliente...).
1. **Crie um JSON Web Token (JWT)** a partir das credenciais geradas anteriormente e assine-o com sua chave privada. O JWT codifica todas as informações de identidade e segurança necessárias para a Adobe verificar sua identidade e conceder acesso à API.
1. **Troque seu JWT por um Token de acesso** por meio de uma solicitação POST. Esse Token de acesso deverá ser usado em cada cabeçalho das solicitações de API.

Para estabelecer uma sessão segura de API de E/S da Adobe de serviço para serviço, cada solicitação a um serviço da Adobe deve incluir no cabeçalho de Autorização as informações abaixo.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;ORGANIZAÇÃO>**: Esta é sua ID pessoal DA ORGANIZAÇÃO, uma ID DA ORGANIZAÇÃO é fornecida pela Adobe para cada uma de suas instâncias:

   * &lt;ORGANIZAÇÃO> : sua instância de produção,
   * &lt;ORGANIZATION-mkt-stage>: sua instância do palco.
   Para obter o valor da ID da ORGANIZAÇÃO, consulte o administrador ou o contato técnico da Adobe. Você também pode recuperá-la em E/S da Adobe ao criar uma nova integração, na lista de licenças (consulte a documentação <a href="https://www.adobe.io/authentication.html">de E/S da</a>Adobe).

* **&lt;ACCESS_TOKEN>**: Seu token de acesso pessoal, que foi recuperado ao trocar seu JSON Web Token por meio de uma solicitação POST.

* **&lt;API_KEY>**: sua chave de API pessoal. Ele é fornecido em E/S da Adobe após a criação de uma nova integração com o Serviço de Adobe Campaign.

   ![texto alternativo](assets/tenant.png)
