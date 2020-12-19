---
solution: Campaign Standard
product: campaign
title: Adicionar links
description: Descubra como gerenciar links com o Designer de email.
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 10%

---


# Adicionar links {#links}

## Inserção de um link {#inserting-a-link}

O editor permite que você personalize um email ou uma landing page inserindo links nos elementos de conteúdo HTML.

Você pode inserir um link em qualquer elemento de página: imagem, palavra, grupo de palavras, bloco de texto, etc.

>[!NOTE]
>
>As imagens abaixo mostram como inserir um link usando o [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md) em um email.

1. Selecione um elemento e clique em **[!UICONTROL Insert link]** na barra de ferramentas contextual.

   ![](assets/des_insert_link.png)

1. Escolha o tipo de link que deseja criar:

   * **Link** externo: insira um link para um URL externo.

      Você pode definir a personalização para seus URLs. Consulte [Personalizando URLs](../../designing/using/using-reusable-content.md#creating-a-content-fragment).

   * **Landing page**: dê acesso a uma landing page Adobe Campaign.
   * **Link** de subscrição: insira um link para assinar um serviço Adobe Campaign.
   * **Link** de unsubscription: insira um link para cancelar a assinatura de um serviço Adobe Campaign.
   * **Link que define uma ação**: define uma ação quando um elemento na landing page é clicado.

      >[!NOTE]
      >
      >Esse tipo de link só está disponível para landing page.

1. É possível modificar o texto exibido no recipient.
1. Você pode definir o comportamento do navegador quando o usuário clicar no link (por exemplo, abrir uma nova janela).

   >[!NOTE]
   >
   >A definição do comportamento do navegador se aplica somente às landings page.

1. Salve as alterações.

Depois que o link for criado, você ainda poderá modificá-lo do painel Configurações. Clique no ícone de lápis para editar seus parâmetros.

![](assets/des_link_edit.png)

Ao editar um email com o [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md), você pode acessar e modificar facilmente os links criados na tabela que listam todos os URLs incluídos no email. Essa lista permite que você tenha uma visualização centralizada e localize cada URL no conteúdo do email. Para acessá-lo, consulte [Sobre URLs rastreados](#about-tracked-urls).

![](assets/des_link_list.png)

>[!NOTE]
>
>URLs personalizados, como o link **URL do Mirror page** ou **Unsubscription**, não podem ser modificados desta lista. Todos os outros links são editáveis.

**Tópicos relacionados**:

* [Inserção de um campo de personalização](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Adicionar blocos de conteúdo](../../designing/using/personalization.md#adding-a-content-block)
* [Definição de conteúdo dinâmico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Sobre URLs rastreados {#about-tracked-urls}

A Adobe Campaign permite que você rastreie o comportamento de seus recipient quando eles clicam em um URL incluído em um email. Para obter mais informações sobre rastreamento, consulte [esta seção](../../sending/using/tracking-messages.md#about-tracking).

O ícone **[!UICONTROL Links]** na barra de ações exibe automaticamente a lista de todos os URLs do seu conteúdo que serão acompanhados.

![](assets/des_links.png)

>[!NOTE]
>
>O rastreamento é ativado por padrão. Esta funcionalidade só está disponível para e-mails se o rastreamento tiver sido ativado no Adobe Campaign. Para obter mais informações sobre os parâmetros de rastreamento, consulte [esta seção](../../administration/using/configuring-email-channel.md#tracking-parameters).

O URL, a categoria, o rótulo e o tipo de rastreamento de cada link podem ser modificados a partir dessa lista. Para editar um link, clique no ícone de lápis correspondente.

![](assets/des_links_tracking.png)

Para cada URL rastreado, é possível definir o modo de rastreamento como um destes valores:

* **Rastreado**: ativa o rastreamento neste URL.
* **Mirror page**: considera esse URL como sendo de mirror page.
* **Never**: nunca ativa o rastreamento desse URL. Essas informações são salvas: se o URL for exibido novamente em uma mensagem futura, seu rastreamento será automaticamente desativado.
* **Opt-out**: considera esse URL como recusa ou cancelamento de subscrição.

![](assets/des_link_tracking_type.png)

Você também pode desativar ou ativar o rastreamento para cada URL.

>[!NOTE]
>
>Por padrão no Adobe Campaign, todos os URLs de conteúdo são rastreados, exceto pelo link **URL do Mirror page** e **Unsubscription**.

Você pode agrupar seus URLs editando o campo **[!UICONTROL Category]**, dependendo dos URLs usados na mensagem. Essas categorias podem ser exibidas nos relatórios, como por exemplo em [URLs e em streams](../../reporting/using/urls-and-click-streams.md).

![](assets/des_link_tracking_category.png)

Ao criar um relatório, na guia **[!UICONTROL Components]**, selecione **[!UICONTROL Dimension]** e role para baixo na lista para acessar os componentes de rastreamento. Por exemplo, arraste e solte **[!UICONTROL Tracking URL Category]** no espaço de trabalho para exibir os resultados de acordo com a categoria de rastreamento de cada URL clicado.

![](assets/des_link_tracking_report.png)

Para obter mais informações sobre como criar relatórios personalizados, consulte [esta seção](../../reporting/using/about-dynamic-reports.md).
