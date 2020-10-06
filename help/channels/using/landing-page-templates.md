---
title: Templates de landing page
description: Saiba mais sobre templates de landing page.
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9c812b0b622b82ba7aa382f04edb7a2a3f717cd4
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 94%

---


# Sobre templates de landing page {#landing-page-templates}

O Campaign vem com um conjunto de templates de landing page incorporados:

* **[!UICONTROL Acquisition]**: este é o template padrão para landing pages, que permite capturar e atualizar dados no banco de dados do Campaign.
* **[!UICONTROL Subscription]**: esse template deve ser usado para oferecer assinaturas de um serviço.
* **[!UICONTROL Unsubscription]**: esse template pode ser vinculado a partir de um email enviado aos assinantes de um serviço, para permitir que eles cancelem a assinatura desse serviço.
* **[!UICONTROL Denylist]**: esse template deve ser usado quando um perfil não deseja mais ser contatado pelo Campaign. For more about denylist management, refer to [About opt-in and opt-out in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Esses templates são propostos por padrão ao criar uma nova landing page.

![](assets/lp_creation_1.png)

Para acessar templates de landing page, clique no logotipo do Adobe Campaign no canto superior esquerdo e selecione **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Landing page templates]**.

>[!NOTE]
>
>A Adobe recomenda criar seus próprios templates duplicando um template incorporado. Alguns parâmetros só podem ser definidos em templates de landing pages e não podem ser modificados diretamente na landing page.

Ao criar um template, recomendamos adicionar um atributo **‘type’** às tags. Essas informações serão processadas pelo editor e ajudarão o usuário a vincular um campo do banco de dados ao campo de formulário ao configurar o aplicativo web.

Exemplo de código HTML no template:

```
<input id="email" type="email" name="email"/>
```

A lista oficial de atributos &#39;type&#39; está disponível no seguinte endereço: [https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp)

