---
solution: Campaign Standard
product: campaign
title: Adicionar conteúdo dinâmico do Target
description: Saiba como adicionar conteúdo dinâmico do Adobe Target em uma de suas entregas do Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Acionadores
role: Data Architect
level: Intermediate
exl-id: 7dfbd89f-877e-4598-bfe3-d743bb31ae9e
source-git-commit: 92365fe416fced72e7ad5818da0dbed5d8f52f15
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 33%

---

# Adicionar conteúdo dinâmico do Target{#adding-target-dynamic-content}

Com a integração do Adobe Target, imagens dinâmicas podem ser adicionadas em um delivery para personalizar seu conteúdo dependendo das experiências.

Ao editar um email, você pode inserir uma imagem dinâmica do Adobe Target que será alterada dependendo dos recipients.

Antes de acessar a imagem no Adobe Campaign, as seguintes tarefas devem ser executadas primeiro no Adobe Target:

* Crie uma ou várias [ofertas de redirecionamento](https://experienceleague.adobe.com/docs/target/using/experiences/offers/offer-redirect.html), em que você deve especificar o URL da imagem que usará.
* Crie um ou vários [públicos](https://experienceleague.adobe.com/docs/target/using/audiences/create-audiences/audiences.html)para definir o target da atividade.
* Crie uma atividade [Experience Composer baseado em formulário](https://experienceleague.adobe.com/docs/target/using/experiences/form-experience-composer.html) , na qual você deve selecionar um rawbox e especificar várias experiências, dependendo do número de ofertas de redirecionamento criadas. Para cada experiência, você deve selecionar uma das ofertas de redirecionamento criadas.
* Crie segmentos usando informações do Adobe Campaign para especificar experiências. Para usar dados do Adobe Campaign nas regras de seleção da oferta, especifique os dados no rawbox no Adobe Target.

1. Crie um delivery de email
1. Ao editar o conteúdo de um email ou de uma landing page, vá para um bloco de imagem e selecione **[!UICONTROL Dynamic image from Adobe Target]** pelo menu contextual.

   ![](assets/tar_insert_dynamic_image.png)

1. Selecione a imagem que será exibida por padrão no email. Você pode especificar diretamente a URL da imagem ou selecionar uma imagem compartilhada por [Assets](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   A integração só oferece suporte a imagens estáticas. O restante do conteúdo não é personalizável.

1. Insira o nome do rawbox especificado no Adobe Target.
1. Se você usar permissões do Enterprise em suas configurações no Adobe Target, adicione a propriedade correspondente nesse campo. Saiba mais sobre as permissões do Target Enterprise [nesta página](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html?lang=pt-BR). Este campo é opcional e não é necessário se você não usar permissões do Enterprise no Target.
1. Em **[!UICONTROL Additional decision parameters]**, especifique o mapeamento entre os campos definidos nos segmentos do Adobe Target e os campos do Adobe Campaign.

   Os campos do Adobe Campaign usados devem ter sido especificados no rawbox. Aqui, definiremos experiências diferentes dependendo do sexo do recipient.

   ![](assets/tar_additional_decisionning_parameters.png)

1. Visualize seu email para ver se, ao selecionar perfis diferentes, a imagem inseriu alterações, dependendo dos parâmetros especificados na atividade do Adobe Target e do Adobe Campaign.

O delivery contendo a imagem dinâmica agora pode ser enviado. Seus resultados podem ser encontrados no Adobe Target.

**Tópicos relacionados:**

* [Adobe Target Portal](https://experienceleague.adobe.com/docs/target/using/integrate/campaign-and-target.html)
* [Sobre design de conteúdo de email](../../designing/using/designing-content-in-adobe-campaign.md)
* [Personalizar imagens de email em ](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) tempo real
