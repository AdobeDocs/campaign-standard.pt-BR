---
solution: Campaign Standard
product: campaign
title: Adição de links
description: Saiba como gerenciar links com o Designer de email.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 10%

---


# Adicionar links {#links}

## Inserção de um link {#inserting-a-link}

O editor permite personalizar um email ou uma landing page inserindo links nos elementos de conteúdo HTML.

Você pode inserir um link em qualquer elemento de página: imagem, palavra, grupo de palavras, bloco de texto, etc.

>[!NOTE]
>
>As imagens abaixo mostram como inserir um link usando o [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md) em um email.

1. Selecione um elemento e clique em **[!UICONTROL Insert link]** na barra de ferramentas contextual.

   ![](assets/des_insert_link.png)

1. Escolha o tipo de link que deseja criar:

   * **Link** externo: insira um link para um URL externo.

      Você pode definir a personalização para seus URLs. Consulte [Personalizando URLs](../../designing/using/using-reusable-content.md#creating-a-content-fragment).

   * **Página** de aterrissagem: dê acesso a uma página de aterrissagem do Adobe Campaign.
   * **Link** de subscrição: insira um link para assinar um serviço Adobe Campaign.
   * **Link** de cancelamento de subscrição: insira um link para cancelar a assinatura de um serviço do Adobe Campaign.
   * **Link que define uma ação**: defina uma ação quando um elemento na landing page for clicado.

      >[!NOTE]
      >
      >Esse tipo de link só está disponível para landing pages.

1. Você pode modificar o texto exibido ao recipient.
1. Você pode definir o comportamento do navegador quando o usuário clicar no link (por exemplo, abrir uma nova janela).

   >[!NOTE]
   >
   >A definição do comportamento do navegador se aplica somente às páginas de aterrissagem.

1. Salve as alterações.

Depois que o link for criado, você ainda poderá modificá-lo no painel Configurações . Clique no ícone de lápis para editar seus parâmetros.

![](assets/des_link_edit.png)

Ao editar um email com o [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md), é possível acessar e modificar facilmente os links criados na tabela, listando todos os URLs incluídos no email. Essa lista permite que você tenha uma visualização centralizada e localize cada URL no conteúdo do email. Para acessá-lo, consulte [Sobre URLs rastreados](#about-tracked-urls).

![](assets/des_link_list.png)

>[!NOTE]
>
>URLs personalizados, como **Mirror page URL** ou **Unsubscription**, não podem ser modificados nessa lista. Todos os outros links são editáveis.

**Tópicos relacionados**:

* [Inserção de um campo de personalização](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Adição de blocos de conteúdo](../../designing/using/personalization.md#adding-a-content-block)
* [Definição do conteúdo dinâmico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Sobre URLs rastreados {#about-tracked-urls}

O Adobe Campaign permite rastrear o comportamento dos recipients ao clicar em um URL incluído em um email. Para obter mais informações sobre rastreamento, consulte [esta seção](../../sending/using/tracking-messages.md#about-tracking).

O ícone **[!UICONTROL Links]** na barra de ações exibe automaticamente a lista de todos os URLs do seu conteúdo que serão rastreados.

![](assets/des_links.png)

>[!NOTE]
>
>O rastreamento é ativado por padrão. Essa funcionalidade só estará disponível para emails, se o rastreamento tiver sido ativado no Adobe Campaign. Para obter mais informações sobre os parâmetros de rastreamento, consulte [esta seção](../../administration/using/configuring-email-channel.md#tracking-parameters).

O URL, a categoria, o rótulo e o tipo de rastreamento de cada link podem ser modificados na lista. Para editar um link, clique no ícone de lápis correspondente.

![](assets/des_links_tracking.png)

Para cada URL rastreado, é possível definir o modo de rastreamento para um destes valores:

* **Rastreado**: ativa o rastreamento nesse URL.
* **Mirror page**: considera esse URL como sendo de mirror page.
* **Never**: nunca ativa o rastreamento desse URL. Essas informações são salvas: se o URL aparecer novamente em uma mensagem futura, o rastreamento será desativado automaticamente.
* **Opt-out**: considera esse URL como recusa ou cancelamento de subscrição.

![](assets/des_link_tracking_type.png)

Você também pode desativar ou ativar o rastreamento para cada URL.

>[!NOTE]
>
>Por padrão no Adobe Campaign, todos os URLs de conteúdo são rastreados, exceto o link **Mirror page URL** e **Unsubscription**.

Você pode agrupar seus URLs editando o campo **[!UICONTROL Category]** , dependendo dos URLs usados na mensagem. Essas categorias podem ser relatórios, como em [URLs and click streams](../../reporting/using/urls-and-click-streams.md).

![](assets/des_link_tracking_category.png)

Ao criar um relatório, na guia **[!UICONTROL Components]** , selecione **[!UICONTROL Dimension]** e role para baixo na lista para acessar os componentes de rastreamento. Por exemplo, arraste e solte **[!UICONTROL Tracking URL Category]** no espaço de trabalho para exibir resultados de acordo com a categoria de rastreamento de cada URL clicado.

![](assets/des_link_tracking_report.png)

Para obter mais informações sobre criação de relatórios personalizados, consulte [esta seção](../../reporting/using/about-dynamic-reports.md).
