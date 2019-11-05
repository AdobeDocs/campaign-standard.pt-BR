---
title: Modelos de página de aterrissagem
description: Saiba mais sobre os modelos de página inicial.
page-status-flag: nunca ativado
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: limatório
products: SG_CAMPAIGN/STANDARD
audience: canais
content-type: referência
topic-tags: páginas de aterrissagem
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,assistente;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Sobre modelos de página de aterrissagem {#landing-page-templates}

A campanha vem com um conjunto de modelos incorporados de página de aterrissagem:

* **[!UICONTROL Acquisition]**: este é o modelo padrão para páginas iniciais, que permite capturar e atualizar dados no banco de dados do Campaign.
* **[!UICONTROL Subscription]**: este modelo deve ser usado para oferecer assinaturas para um serviço.
* **[!UICONTROL Unsubscription]**: este modelo pode ser vinculado a partir de um email enviado aos assinantes para um serviço, para permitir que eles cancelem a assinatura deste serviço.
* **[!UICONTROL Blacklist]**: este modelo deve ser usado quando um perfil não quiser mais ser contatado pelo Campaign. Para obter mais informações sobre a lista negra, consulte [Sobre aceitação e não participação no Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Esses modelos são propostos por padrão ao criar uma nova página inicial.

![](assets/lp_creation_1.png)

Para acessar modelos de página inicial, clique no logotipo do Adobe Campaign no canto superior esquerdo e selecione **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Landing page templates]**.

>[!NOTE]
>
>A Adobe recomenda criar seus próprios modelos duplicando um modelo incorporado. Alguns parâmetros só podem ser definidos em modelos de página inicial e não podem ser modificados diretamente em páginas iniciais.

When building a template, we recommend adding a **'type'** attribute to tags. Essas informações serão processadas pelo editor e ajudarão o usuário a vincular um campo de banco de dados ao campo de formulário ao configurar o aplicativo da Web.

Exemplo de código HTML no template:

```
<input id="email" type="email" name="email"/>
```

A lista oficial de atributos 'type' está disponível no seguinte endereço: [http://www.w3schools.com/tags/att_input_type.asp](http://www.w3schools.com/tags/att_input_type.asp)