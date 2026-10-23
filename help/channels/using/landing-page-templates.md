---
title: Modelos de página de destino
description: Saiba mais sobre modelos de página de destino.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
feature: Landing Pages
role: User
level: Intermediate
exl-id: 29d1badf-9ce3-470c-9bdc-169586d2e943
TQID: 'https://experienceleague.adobe.com/vJyIRO33IjK6o3--ekx-Iw9K-GcIZMViLz9wEr-kxY0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 93%
---
# Sobre modelos de páginas de destino {#landing-page-templates}

O Campaign vem com um conjunto de modelos de página de destino integrados:

* **[!UICONTROL Acquisition]**: este é o modelo padrão para páginas de destino, que permite capturar e atualizar dados no banco de dados do Campaign.
* **[!UICONTROL Subscription]**: esse modelo deve ser usado para oferecer assinaturas de um serviço.
* **[!UICONTROL Unsubscription]**: esse modelo pode ser vinculado a partir de um email enviado aos assinantes de um serviço, para permitir que eles cancelem a assinatura desse serviço.
* **[!UICONTROL Denylist]**: esse modelo deve ser usado quando um perfil não deseja mais ser contatado pelo Campaign. Para obter mais informações sobre o gerenciamento de inclui na lista de bloqueios, consulte [Sobre participação e não participação no Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Esses modelos são propostos por padrão ao criar uma nova página de destino.

![](assets/lp_creation_1.png)

Para acessar modelos de página de destino, clique no logotipo do Adobe Campaign no canto superior esquerdo e selecione **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Landing page templates]**.

>[!NOTE]
>
>A Adobe recomenda criar seus próprios modelos duplicando um modelo integrado. Alguns parâmetros só podem ser definidos em modelos de páginas de destino e não podem ser modificados diretamente na página de destino.

Ao criar um modelo, recomendamos adicionar um atributo **‘type’** às tags. Essas informações serão processadas pelo editor e ajudarão o usuário a vincular um campo do banco de dados ao campo de formulário ao configurar o aplicativo web.

Exemplo de código HTML no modelo:

```
<input id="email" type="email" name="email"/>
```

A lista oficial de atributos &#39;type&#39; está disponível no seguinte endereço: [https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp)
