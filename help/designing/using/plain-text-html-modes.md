---
title: Edição de texto sem formatação, HTML e formatos de email móveis
description: Descubra os modos Texto simples e HTML
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 760c3c30-c899-4cf4-ba59-fb2fade9fc5e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 0%

---

# Edição de texto sem formatação, HTML e formatos de email móveis {#plain-text-and-html-modes}

O Designer de email permite que você edite várias renderizações de seus emails. Você pode gerar uma versão de texto de seu email, editar a fonte de HTML de um email e criar emails para visualização móvel.

## Gerar uma versão de texto do email {#generating-a-text-version-of-the-email}

Por padrão, a variável **[!UICONTROL Plain text]** A versão do seu email é gerada automaticamente e sincronizada com a variável **[!UICONTROL Edit]** versão.

Campos de personalização e blocos de conteúdo adicionados à versão do HTML também são sincronizados com a versão de texto sem formatação.

>[!NOTE]
>
>Para usar blocos de conteúdo em uma versão de texto sem formatação, verifique se eles não contêm o código HTML.

Para ter uma versão de texto simples diferente da versão do HTML, você pode desativar esta sincronização clicando no botão **[!UICONTROL Sync with HTML]** alterne da **[!UICONTROL Plain text]** exibição do seu email.

![](assets/email_designer_textversion.png)

Em seguida, você pode editar a versão de texto simples, conforme desejado.

>[!NOTE]
>
>Se você editar o **[!UICONTROL Plain text]** enquanto a sincronização estiver desativada, na próxima vez que você ativar a variável **[!UICONTROL Sync with HTML]** , todas as alterações feitas na versão de texto sem formatação serão substituídas pela versão HTML. As alterações feitas em **[!UICONTROL Plain text]** não pode ser refletida em **[!UICONTROL HTML]** exibir.

## Edição de uma fonte de conteúdo de email no HTML {#editing-an-email-content-source-in-html}

Para os usuários e a depuração mais avançados, é possível visualizar e editar o conteúdo de email diretamente no HTML.

Você tem duas maneiras de editar a versão do HTML do email:

* Selecionar **[!UICONTROL Edit]** > **[!UICONTROL HTML]** para abrir a versão do HTML de todo o email.

   ![](assets/email_designer_html1.png)

* Na interface WYSIWYG, selecione um elemento e clique no botão **[!UICONTROL Source code]** ícone .

   Somente a origem do elemento selecionado é exibida. Você pode editar o código-fonte se o elemento selecionado for um **[!UICONTROL HTML]** componente de conteúdo. Outros componentes estão no modo somente leitura, mas ainda podem ser editados na versão completa do HTML do email.

   ![](assets/email_designer_html2.png)

Se você modificar o HTML do código, a capacidade de resposta do email pode ser interrompida. Teste-o usando a variável **[!UICONTROL Preview]** botão. Consulte [Pré-visualização de mensagens](../../sending/using/previewing-messages.md).

## Criar emails para renderização móvel {#switching-to-mobile-view}

Você pode ajustar o design responsivo de um email editando separadamente todas as opções de estilo para exibição em dispositivos móveis. Por exemplo, você pode adaptar margens e preenchimento, usar tamanhos de fonte menores ou maiores, alterar botões ou aplicar cores de fundo diferentes que serão específicas para a versão móvel do seu email.

Todas as opções de estilo estão disponíveis na exibição móvel. As configurações de estilo do Designer de email são apresentadas anteriormente nesta página.

1. Crie um email e comece a editar o conteúdo. Para obter mais informações, consulte [Criar um conteúdo de email do zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Para acessar a visualização móvel dedicada, selecione o **[!UICONTROL Switch to mobile view]** botão.

   ![](assets/email_designer_mobile_view_switch.png)

   A versão móvel do email é exibida. Ele contém todos os componentes e estilos que foram definidos na exibição de desktop.

1. Edite independentemente todas as configurações de estilo, como cor do plano de fundo, alinhamento, preenchimento, margem, família de fontes, cor do texto e assim por diante.

   ![](assets/email_designer_mobile_view.png)

1. Ao editar qualquer configuração de estilo na exibição móvel, as modificações são aplicadas apenas à exibição móvel.

   Por exemplo, reduza o tamanho de uma imagem, adicione um plano de fundo verde e altere o preenchimento na visualização móvel.

   ![](assets/email_designer_mobile_view_change.png)

1. Você pode ocultar um componente quando exibido em um dispositivo móvel. Para fazer isso, selecione **[!UICONTROL Show only on desktop devices]** do **[!UICONTROL Display options]**.

   Você também pode optar por ocultar esse componente em dispositivos de desktop, o que significa que ele será exibido somente em dispositivos móveis. Para fazer isso, selecione **[!UICONTROL Show only on mobile devices]**.

   Por exemplo, essa opção permite exibir uma imagem específica em dispositivos móveis e outra imagem em dispositivos de desktop.

   Você pode definir essa opção na visualização móvel ou desktop.

   ![](assets/email_designer_mobile_hide.png)

1. Clique novamente no botão **[!UICONTROL Switch to mobile view]** para voltar para a exibição padrão da área de trabalho. As mudanças de estilo que você acabou de fazer não são refletidas.

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >A única exceção é a **[!UICONTROL Style inline]** configurações. Qualquer alteração na configuração de estilo em linha também é aplicada à exibição de desktop padrão.

1. Qualquer outra alteração na estrutura ou no conteúdo do email, como edições de texto, upload de uma nova imagem, adição de um novo componente etc. também é aplicada à exibição padrão.

   Por exemplo, volte para a exibição móvel, edite algum texto e substitua uma imagem.

   ![](assets/email_designer_mobile_view_change_content.png)

1. Clique novamente no botão **[!UICONTROL Switch to mobile view]** para voltar para a exibição padrão da área de trabalho. As alterações são refletidas.

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. Remover um estilo na exibição móvel leva você de volta ao estilo aplicado no modo de desktop.

   Por exemplo, na exibição móvel, aplique uma cor de plano de fundo verde a um botão.

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. Alterne para a exibição da área de trabalho e aplique um plano de fundo cinza ao mesmo botão.

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. Alterne novamente para exibição móvel e agora desative o **[!UICONTROL Background color]** configuração.

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   A cor de fundo definida na exibição de desktop agora é aplicada: fica cinza (não em branco).

   A única exceção é a **[!UICONTROL Border color]** configuração. Quando desativado na exibição móvel, nenhuma borda é mais aplicada, mesmo se uma cor de borda for definida na exibição de desktop.

>[!NOTE]
>
>A exibição móvel não está disponível em [fragmentos](../../designing/using/using-reusable-content.md#about-fragments).
