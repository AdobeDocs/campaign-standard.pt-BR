---
title: Gerenciamento de links
seo-title: Gerenciamento de links
description: 'Gerenciamento de links '
seo-description: Descubra como gerenciar links com o Designer de email.
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
source-git-commit: 14155f29492f66b070dd302c59bdd8e81008f281

---


# Links {#links}

## Inserir um link {#inserting-a-link}

O editor permite que você personalize um email ou uma página de aterrissagem inserindo links nos elementos de conteúdo HTML.

Você pode inserir um link em qualquer elemento de página: imagem, palavra, grupo de palavras, bloco de texto etc.

>[!NOTE]
>
>As imagens abaixo mostram como inserir um link usando o [Email Designer](../../designing/using/overview.md) em um email.

1. Selecione um elemento e clique **[!UICONTROL Insert link]** na barra de ferramentas contextual.

   ![](assets/des_insert_link.png)

1. Escolha o tipo de link que deseja criar:

   * **Link** externo: insira um link para um URL externo.

      Você pode definir a personalização para seus URLs. Consulte [Personalização de URLs](../../designing/using/using-reusable-content.md#creating-a-content-fragment).

   * **Página** de aterrissagem: dê acesso a uma página de aterrissagem do Adobe Campaign.
   * **Link** de assinatura: insira um link para assinar um serviço do Adobe Campaign.
   * **Link** de cancelamento de assinatura: insira um link para cancelar a assinatura de um serviço do Adobe Campaign.
   * **Link que define uma ação**: define uma ação quando um elemento na página inicial é clicado.

      >[!NOTE]
      >
      >Esse tipo de link só está disponível para páginas iniciais.

1. É possível modificar o texto exibido ao destinatário.
1. Você pode definir o comportamento do navegador quando o usuário clicar no link (por exemplo, abrir uma nova janela).

   >[!NOTE]
   >
   >A definição do comportamento do navegador se aplica somente às páginas iniciais.

1. Salve as alterações.

Depois que o link for criado, você ainda poderá modificá-lo do painel Configurações. Clique no ícone de lápis para editar seus parâmetros.

![](assets/des_link_edit.png)

Ao editar um email com o [Email Designer](../../designing/using/overview.md), você pode acessar e modificar facilmente os links criados na tabela que lista todos os URLs incluídos no email. Essa lista permite que você tenha uma exibição centralizada e localize cada URL no conteúdo do email. Para acessá-lo, consulte [Sobre URLs](../../designing/using/links.md#about-tracked-urls)rastreados.

![](assets/des_link_list.png)

>[!NOTE]
>
>URLs personalizados, como URL **da página** Espelho ou link **Cancelar assinatura** , não podem ser modificados nesta lista. Todos os outros links são editáveis.

**Tópicos** relacionados:

* [Inserir um campo de personalização](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Adicionar blocos de conteúdo](../../designing/using/personalization.md#adding-a-content-block)
* [Definição de conteúdo dinâmico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Sobre URLs rastreados {#about-tracked-urls}

O Adobe Campaign permite que você rastreie o comportamento de seus destinatários quando eles clicam em um URL incluído em um email. Para obter mais informações sobre o rastreamento, consulte [esta seção](../../sending/using/tracking-messages.md#about-tracking).

O **[!UICONTROL Links]** ícone na barra de ações exibe automaticamente a lista de todos os URLs do seu conteúdo que serão acompanhados.

![](assets/des_links.png)

>[!NOTE]
>
>O rastreamento é ativado por padrão. Essa funcionalidade só estará disponível para e-mails se o rastreamento tiver sido ativado no Adobe Campaign. Para obter mais informações sobre os parâmetros de rastreamento, consulte [esta seção](../../administration/using/configuring-email-channel.md#tracking-parameters).

O URL, a categoria, o rótulo e o tipo de rastreamento de cada link podem ser modificados nesta lista. Para editar um link, clique no ícone de lápis correspondente.

![](assets/des_links_tracking.png)

Para cada URL rastreado, é possível definir o modo de rastreamento como um destes valores:

* **Rastreado**: ativa o rastreamento neste URL.
* **Página** de espelhamento: considera que este URL é um URL de página espelhada.
* **Nunca**: nunca ativa o rastreamento deste URL. Essas informações são salvas: se o URL for exibido novamente em uma mensagem futura, seu rastreamento será automaticamente desativado.
* **Recusar**: considera este URL como um URL de não participação ou de cancelamento de assinatura.

![](assets/des_link_tracking_type.png)

Você também pode desativar ou ativar o rastreamento para cada URL.

>[!NOTE]
>
>Por padrão no Adobe Campaign, todos os URLs de conteúdo são rastreados, exceto o URL **da página** Espelho e o link **Cancelar assinatura** .

Você pode agrupar seus URLs editando o **[!UICONTROL Category]** campo, dependendo dos URLs usados na mensagem. Essas categorias podem ser exibidas nos relatórios, como por exemplo em [URLs e fluxos](../../reporting/using/urls-and-click-streams.md)de cliques.

![](assets/des_link_tracking_category.png)

Ao criar um relatório, na **[!UICONTROL Components]** guia, selecione **[!UICONTROL Dimension]** e role para baixo na lista para acessar os componentes de rastreamento. Por exemplo, arraste e solte **[!UICONTROL Tracking URL Category]** no espaço de trabalho para exibir resultados de acordo com a categoria de rastreamento de cada URL clicado.

![](assets/des_link_tracking_report.png)

Para obter mais informações sobre como criar relatórios personalizados, consulte [esta seção](../../reporting/using/about-dynamic-reports.md).
