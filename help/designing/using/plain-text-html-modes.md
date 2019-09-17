---
title: Modos de texto sem formatação e HTML
seo-title: Modos de texto sem formatação e HTML
description: Modos de texto sem formatação e HTML
seo-description: Descubra os modos Texto simples e HTML
page-status-flag: nunca ativado
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: concepção
content-type: referência
topic-tags: edição-email-conteúdo
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2045c69398902a8e942e20c70287d7f3e9570837

---


# Modos de texto sem formatação e HTML {#plain-text-and-html-modes}

## Gerando uma versão de texto do email {#generating-a-text-version-of-the-email}

Por padrão, a **[!UICONTROL Plain text]** versão do seu email é gerada e sincronizada automaticamente com a **[!UICONTROL Edit]** versão.

Campos de personalização e blocos de conteúdo adicionados à versão HTML também são sincronizados com a versão em texto simples.

>[!NOTE]
>
>Para usar blocos de conteúdo em uma versão de texto sem formatação, verifique se eles não contêm código HTML.

Para ter uma versão de texto sem formatação diferente da versão HTML, você pode desativar essa sincronização clicando na **[!UICONTROL Sync with HTML]** opção na **[!UICONTROL Plain text]** exibição do email.

![](assets/email_designer_textversion.png)

Em seguida, é possível editar a versão de texto sem formatação, conforme desejado.

>[!NOTE]
>
>Se você editar a **[!UICONTROL Plain text]** versão enquanto a sincronização estiver desativada, na próxima vez que você ativar a **[!UICONTROL Sync with HTML]** opção, todas as alterações feitas na versão em texto simples serão substituídas pela versão em HTML. As alterações feitas na **[!UICONTROL Plain text]** exibição não podem ser refletidas na **[!UICONTROL HTML]** exibição.

## Editar uma fonte de conteúdo de email em HTML {#editing-an-email-content-source-in-html}

Para os usuários mais avançados e a depuração, você pode exibir e editar o conteúdo de email diretamente em HTML.

Você tem duas maneiras de editar a versão HTML do email:

* Selecione **[!UICONTROL Edit]** &gt; **[!UICONTROL HTML]** para abrir a versão HTML do email inteiro.

   ![](assets/email_designer_html1.png)

* Na interface WYSIWYG, selecione um elemento e clique no **[!UICONTROL Source code]** ícone.

   Somente a fonte do elemento selecionado é exibida. Você pode editar o código fonte se o elemento selecionado for um componente **[!UICONTROL HTML]** de conteúdo. Outros componentes estão no modo somente leitura, mas ainda podem ser editados na versão HTML completa do email.

   ![](assets/email_designer_html2.png)

Se você modificar o código HTML, a capacidade de resposta do e-mail poderá ser interrompida. Teste usando o **[!UICONTROL Preview]** botão. Consulte [Visualizar mensagens](../../sending/using/previewing-messages.md).
