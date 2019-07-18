---
title: '" Exemplo: Personalização de email "'
seo-title: '" Exemplo: Personalização de email "'
description: '" Exemplo: Personalização de email "'
seo-description: Veja um exemplo completo de como personalizar um e-mail com conteúdo dinâmico e texto de acordo com as idades dos perfis.
page-status-flag: nunca ativado
uuid: 3 d 30213 c -474 f -4 e 5 f -8688-9260 ea 2 e 2583
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: personalização-conteúdo
discoiquuid: d 1 b 618 ac-a 842-41 e 8-9 ba 6-7 a 50 f 7315 b 02
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Example: Email personalization{#example-email-personalization}

Neste exemplo, um membro da equipe de serviços de marketing criou um email para informar alguns dos clientes que há uma oferta especial apenas para eles. O membro da equipe decidiu personalizar o email de acordo com as respectivas idades. Os clientes com idades entre 18 e 27 anos receberão um e-mail contendo uma imagem e um slogan diferentes para aqueles que os clientes anteriores a 27 receberão.

O e-mail é criado da seguinte maneira:

* O conteúdo dinâmico é aplicado à imagem e esses conteúdos dinâmicos são configurados de acordo com a faixa etária.

   ![](assets/delivery_content_43.png)

   Adding and configuring dynamic content is detailed in the [Defining dynamic content in an email](../../designing/using/defining-dynamic-content-in-an-email.md) section.

* Os campos de personalização e o conteúdo dinâmico são aplicados ao texto. Dependendo da faixa etária do perfil, o e-mail começa com o primeiro nome do perfil ou o título e o sobrenome do perfil.

   ![](assets/delivery_content_44.png)

   Adding and configuring the personalization fields is detailed in the [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md) section.

## Configuring images {#configuring-images}

Neste exemplo, o conteúdo dinâmico aplicado às imagens é configurado da seguinte maneira:

**Como meta de 18a 27 anos:**

1. Select the dynamic content in the **[!UICONTROL Properties]** palette and click the **[!UICONTROL Edit]** button.

   ![](assets/delivery_content_48.png)

1. Edit the label then select the **[!UICONTROL Age]** field from the **[!UICONTROL Profile]** node.

   ![](assets/delivery_content_49.png)

1. Select the **Greater than or equal to** operator then enter **18** to create the **older than 18** expression.

   ![](assets/delivery_content_50.png)

1. Add a new **[!UICONTROL Age]** condition.

   Select the **Less than or equal to** operator followed by 27 in the value field to create the **younger than 27** expression.

   ![](assets/delivery_content_51.png)

1. Confirme suas alterações.

**Para direcionar perfis de aged 7 e above::**

1. Selecione o conteúdo dinâmico da paleta e edite-o.
1. Edit the label then select the **[!UICONTROL Age]** field from the **[!UICONTROL Profile]** node.
1. Add the **Greater than** operator followed by 27 in the value field to create the **older than 27** expression.

   ![](assets/delivery_content_52.png)

1. Confirme suas alterações.

Seu conteúdo dinâmico está configurado corretamente.

## Configuring text {#configuring-text}

Neste exemplo, o conteúdo dinâmico aplicado aos textos é configurado da seguinte maneira:

**Para direcionar perfis entre 18-27:**

1. Selecione o componente de estrutura desejado e adicione um conteúdo dinâmico.
1. Edite o conteúdo dinâmico e configure as expressões de definição de metas. Refer to [Configuring images](../../designing/using/example--email-personalization.md#configuring-images).
1. In the structure component, at the desired position, click the **[!UICONTROL Personalize]** icon from the contextual toolbar and select **[!UICONTROL Insert personalization field]**.

   ![](assets/delivery_content_53.png)

1. In the list that appears, select the **[!UICONTROL First name]** field and confirm.

   ![](assets/delivery_content_54.png)

1. O campo de personalização é inserido perfeitamente no conteúdo dinâmico selecionado.

**Para direcionar perfis de aged 7 e above::**

1. Selecione o componente de estrutura desejado e adicione um conteúdo dinâmico.
1. Edite o conteúdo dinâmico e configure as expressões de definição de metas. Refer to [Configuring images](../../designing/using/example--email-personalization.md#configuring-images).
1. In the structure component, at the desired position, click the **[!UICONTROL Personalize]** icon from the contextual toolbar and select **[!UICONTROL Insert personalization field]**.
1. Select **[!UICONTROL Title]** from the drop-down list.
1. Proceed similarly to add the **[!UICONTROL Last name]** field.

   ![](assets/delivery_content_56.png)

Seus campos de personalização agora devem ser perfeitamente inseridos no conteúdo dinâmico escolhido.

## Previewing emails {#previewing-emails}

Previewing allows you to check that the personalization fields and the dynamic contents are configured correctly before sending the **[!UICONTROL Proofs]**. Durante a visualização, é possível selecionar diferentes perfis de teste correspondentes aos direcionamentos de email.

Sem perfis de teste, o e-mail que aparece por padrão é:

![](assets/delivery_content_45.png)

O e-mail não tem campos de personalização no slogan e a imagem padrão é usada.

O primeiro perfil de teste corresponde a um cliente entre 18 e 27. Ao selecionar esse perfil, o seguinte email é exibido:

![](assets/delivery_content_46.png)

O campo de personalização que corresponde à expressão de 18a 27 anos, especificamente o primeiro nome do perfil, é configurado corretamente, e a imagem também mudou de acordo com o perfil.

O segundo perfil corresponde a um cliente acima de 27 e gera o seguinte email:

![](assets/delivery_content_47.png)

A imagem mudou graças ao conteúdo dinâmico, e o slogan que aparece é o slogan mais formal definido para este público-alvo.

**Tópicos relacionados:**

* [Criação de públicos-alvo](../../audiences/using/creating-audiences.md)
* [Preparação do envio](../../sending/using/preparing-the-send.md)

