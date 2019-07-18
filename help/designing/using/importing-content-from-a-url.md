---
title: Importação de conteúdo de um URL
seo-title: Importação de conteúdo de um URL
description: Importação de conteúdo de um URL
seo-description: Saiba como carregar o conteúdo de um URL existente ao criar um email.
page-status-flag: nunca ativado
uuid: 7 db 6 c 20 f -7004-4 fb 8-add 9-362 eab 3 d 2795
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: carregamento-conteúdo
discoiquuid: 738 b 7 c 8 a -88 eb -491 c-a 4 d 0-078 b 0959 b 973
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Importing content from a URL{#importing-content-from-a-url}

Antes de importar o conteúdo de um URL, verifique se ele segue os requisitos abaixo:

* O conteúdo precisa estar publicamente disponível por meio desse URL.
* For security reasons, only URLs beginning with **[!UICONTROL https]** are allowed.
* Verifique se todos os recursos (imagens, CSS) estão definidos em links absolutos e HTTPS. Caso contrário, após enviar o e-mail, a página espelhada será exibida sem seus recursos. Veja um exemplo de uma definição de link absoluta:

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>O carregamento de conteúdo de um URL está disponível apenas para o canal de email.

Para recuperar o conteúdo existente de um URL, siga as etapas abaixo:

1. From the Email Designer home page, select the **[!UICONTROL Import from URL]** button.

   ![](assets/email_designer_importfromurl.png)

1. Defina o URL a partir do qual o conteúdo será recuperado.
1. Click **[!UICONTROL Confirm]**.

**Tópico relacionado:**

[Importação de conteúdo de](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#Workingwithexistingcontent) um vídeo de URL

## Retrieving content from a URL automatically at preparation time {#retrieving-content-from-a-url-automatically-at-preparation-time}

A importação de conteúdo de um URL durante a preparação de mensagens permite recuperar o conteúdo HTML mais recente sempre que o e-mail estiver preparado. Dessa forma, o conteúdo de emails recorrentes é sempre atualizado no momento do envio. Esse recurso também permite que você crie uma mensagem programada em uma data específica, mesmo que o conteúdo ainda não esteja pronto.

Para recuperar conteúdo no tempo de preparação, siga as etapas abaixo:

1. Select the **[!UICONTROL Content imported during preparation]** option.

   ![](assets/email_designer_importfromurl2.png)

1. O conteúdo do URL é exibido no editor como somente leitura.

   >[!CAUTION]
   >
   >Nessa etapa, o HTML exibido no editor de conteúdo não deve ser levado em conta. Ela será recuperada na fase de preparação.

1. To preview the URL content that has been retrieved, open the message once it is created then click the **[!UICONTROL Preview]** button.

É possível personalizar o URL remoto a partir do qual o conteúdo será recuperado. Para fazer isso, siga as etapas abaixo:

1. Click the email label on top of the screen to acces the Email Designer **[!UICONTROL Properties]** tab.
1. Find the **[!UICONTROL Remote URL]** field.

   ![](assets/email_designer_importfromurl4.png)

1. Insira o campo de personalização, o bloco de conteúdo ou o texto dinâmico desejado.

   The **[!UICONTROL Current date - YYYYMMDD]** content block, for example, enables you to insert the date of the day.

   >[!NOTE]
   >
   >The available personalization fields are linked to **Delivery** attributes only (email creation date, status, campaign label...).

