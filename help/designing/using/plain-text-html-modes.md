---
title: Editar formatos de texto sem formatação, HTML e e-mail para dispositivos móveis
description: Descubra os modos Texto simples e HTML
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e2ea8020c82f578b2cf8c00fa7b9f55b6ce2edd

---


# Editar formatos de texto sem formatação, HTML e e-mail para dispositivos móveis {#plain-text-and-html-modes}

O Designer de email permite que você edite várias renderizações de seus emails. Você pode gerar uma versão de texto de seu email, editar a fonte HTML de um email e criar emails para exibição móvel.

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

## Criar emails para renderização móvel {#switching-to-mobile-view}

Você pode ajustar o design responsivo de um email editando separadamente todas as opções de estilo para exibição móvel. Por exemplo, você pode adaptar margens e preenchimento, usar tamanhos de fonte menores ou maiores, alterar botões ou aplicar cores de fundo diferentes que serão específicas para a versão móvel do seu email.

Todas as opções de estilo estão disponíveis na exibição móvel. As configurações de estilo do Email Designer são apresentadas anteriormente nesta página.

1. Crie um email e comece a editar o conteúdo. Para obter mais informações, consulte [Criar um conteúdo de email do zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Para acessar a exibição móvel dedicada, selecione o **[!UICONTROL Switch to mobile view]** botão.

   ![](assets/email_designer_mobile_view_switch.png)

   A versão móvel do email é exibida. Ele contém todos os componentes e estilos definidos na exibição da área de trabalho.

1. Edite independentemente todas as configurações de estilo, como cor do plano de fundo, alinhamento, preenchimento, margem, família de fontes, cor do texto e assim por diante.

   ![](assets/email_designer_mobile_view.png)

1. Ao editar qualquer configuração de estilo na exibição móvel, as modificações são aplicadas somente à exibição móvel.

   Por exemplo, reduza o tamanho de uma imagem, adicione um plano de fundo verde e altere o preenchimento na exibição móvel.

   ![](assets/email_designer_mobile_view_change.png)

1. Você pode ocultar um componente quando exibido em um dispositivo móvel. Para fazer isso, selecione **[!UICONTROL Show only on desktop devices]** no **[!UICONTROL Display options]**.

   Você também pode ocultar esse componente em dispositivos de desktop, o que significa que ele será exibido somente em dispositivos móveis. Para fazer isso, selecione **[!UICONTROL Show only on mobile devices]**.

   Por exemplo, essa opção permite que você exiba uma imagem específica em dispositivos móveis e outra imagem em dispositivos desktop.

   Você pode definir essa opção na exibição móvel ou na exibição da área de trabalho.

   ![](assets/email_designer_mobile_hide.png)

1. Clique novamente no **[!UICONTROL Switch to mobile view]** botão para voltar à exibição padrão da área de trabalho. As mudanças de estilo que você acabou de fazer não são refletidas.

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >A única exceção são as **[!UICONTROL Style inline]** configurações. Qualquer alteração na configuração em linha de estilo também é aplicada à exibição padrão da área de trabalho.

1. Qualquer outra alteração na estrutura ou no conteúdo do email, como edições de texto, upload de uma nova imagem, adição de um novo componente etc. também é aplicado à exibição padrão.

   Por exemplo, volte para a exibição móvel, edite algum texto e substitua uma imagem.

   ![](assets/email_designer_mobile_view_change_content.png)

   Clique novamente no **[!UICONTROL Switch to mobile view]** botão para voltar à exibição padrão da área de trabalho. As mudanças são refletidas.

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. Remover um estilo na exibição móvel leva você de volta ao estilo que foi aplicado no modo desktop.

   Por exemplo, na exibição móvel, aplique uma cor de plano de fundo verde a um botão.

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. Alterne para a exibição da área de trabalho e aplique um plano de fundo cinza ao mesmo botão.

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. Alterne novamente para exibição móvel e desative a **[!UICONTROL Background color]** configuração.

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   A cor de fundo definida na exibição da área de trabalho agora é aplicada: fica cinza (não em branco).

   A única exceção é a **[!UICONTROL Border color]** configuração. Quando desativada na exibição móvel, nenhuma borda é mais aplicada, mesmo se uma cor de borda for definida na exibição da área de trabalho.

>[!NOTE]
>
>A exibição móvel não está disponível em [fragmentos](../../designing/using/using-reusable-content.md#about-fragments).
