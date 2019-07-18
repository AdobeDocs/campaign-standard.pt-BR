---
title: Práticas recomendadas de design de conteúdo
seo-title: Práticas recomendadas de design de conteúdo
description: Práticas recomendadas de design de conteúdo
seo-description: Leia sobre essas orientações para garantir a melhor operação do editor.
page-status-flag: nunca ativado
uuid: ad 74 f 49 d -999 f -4140-89 b 0-d 1 ead 8642 d 89
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: about-content-design
discoiquuid: d 33 f 5 f 14-a 4 e 3-4327-bd 16-eb 3135 a 32076
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Content design best practices{#content-design-best-practices}

Para garantir a melhor operação do editor, recomendamos observar as seguintes diretrizes:

* Folhas de estilos SCSS não são compatíveis. Use CSS regular se importar arquivos ZIP que contenham seu conteúdo HTML.
* When editing **email content**:

   Visualize suas mensagens antes de enviá-las. O Adobe Campaign oferece uma maneira de testar a renderização por email usando Litmus. For more on this, see [Email rendering](../../sending/using/email-rendering.md).

* When editing **landing page content**:

   * Antes de importar um modelo de página HTML no Adobe Campaign, verifique se o modelo abre e é exibido corretamente nos vários navegadores.
   * Se a página HTML contiver scripts javascript, eles precisarão ser executados sem erros fora do editor. Em geral, evite usar scripts no conteúdo da mensagem para garantir que eles sejam processados corretamente por clientes de email.
   * When building a template, we recommend adding a **'type'** attribute to  tags. Essas informações serão processadas pelo editor e ajudarão o usuário a vincular um campo de banco de dados ao campo do formulário ao configurar o aplicativo da Web.

      Exemplo de código HTML no modelo:

      ```
      <input id="email" type="email" name="email"/>
      ```

      The official list of 'type' attributes is available at the following address: [http://www.w3schools.com/tags/att_input_type.asp](http://www.w3schools.com/tags/att_input_type.asp)

More design and general best practices regarding messages are presented in the following Adobe Campaign step-by-step guide: [Delivery best practices with Adobe Campaign](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).
