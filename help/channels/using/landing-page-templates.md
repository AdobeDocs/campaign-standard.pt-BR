---
title: Modelos de Landing page
description: Saiba mais sobre os modelos de landing page.
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
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 12%

---


# Sobre modelos de página de aterrissagem {#landing-page-templates}

A Campanha vem com um conjunto de modelos de landing page incorporados:

* **[!UICONTROL Acquisition]**: este é o modelo padrão do landing page, que permite capturar e atualizar dados no banco de dados do Campaign.
* **[!UICONTROL Subscription]**: este modelo deve ser usado para oferta de subscrições a um serviço.
* **[!UICONTROL Unsubscription]**: este modelo pode ser vinculado a partir de um email enviado aos assinantes para um serviço, para permitir que eles cancelem a assinatura deste serviço.
* **[!UICONTROL Block list]**: esse modelo deve ser usado quando um perfil não quiser mais ser contatado pela Campanha. Para obter mais informações sobre o gerenciamento de listas de blocos, consulte [Sobre aceitação e não participação na Campanha](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Esses modelos são propostos por padrão ao criar uma nova landing page.

![](assets/lp_creation_1.png)

Para acessar modelos de landing page, clique no logotipo Adobe Campaign no canto superior esquerdo e selecione **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Landing page templates]**.

>[!NOTE]
>
>A Adobe recomenda criar seus próprios modelos duplicando um modelo incorporado. Alguns parâmetros só podem ser definidos em modelos de landing page e não podem ser modificados diretamente no landing page.

Ao criar um template, recomendamos adicionar um atributo **‘type’** às  tags. Essas informações serão processadas pelo editor e ajudarão o usuário a vincular um campo de banco de dados ao campo de formulário ao configurar o aplicativo da Web.

Exemplo de código HTML no template:

```
<input id="email" type="email" name="email"/>
```

A lista oficial dos atributos &#39;type&#39; está disponível no seguinte endereço: [https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp)