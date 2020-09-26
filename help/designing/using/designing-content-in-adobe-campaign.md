---
title: Design de conteúdo no Adobe Campaign
description: Com o Campaign Email Designer, crie conteúdo de e-mail começando em uma página em branco ou aproveitando fragmentos ou modelos de conteúdo existentes.
page-status-flag: never-activated
uuid: 8f73407f-ab90-46bc-aeb6-bd87fcb0404c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: about-content-design
discoiquuid: 20800cde-50ad-4d2b-a2f9-812258bec665
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4ae70ca95cb282a694c41361d859b19385db5673
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 4%

---


# Designer de email do Campaign{#designing-content-in-adobe-campaign}

Depois de criar um email no Adobe Campaign, é necessário definir seu conteúdo.

O Designer de e-mail permite que você crie e-mails cativantes e adaptados individualmente por meio de uma interface de arrastar e soltar. Esteja você iniciando em branco ou aproveitando fragmentos ou modelos de conteúdo existentes, projete e refine todo o conteúdo de cada email, seja promocional ou transacional.

Criado para fornecer HTML otimizado para design responsivo, o Email Designer permite que você defina e aplique facilmente condições de visibilidade e conteúdo dinâmico a um email, modelo ou fragmento diretamente pela interface do usuário. Você pode alternar perfeitamente entre a interface de arrastar e soltar e o código HTML ao clicar em um botão.

O Designer de email permite que você crie conteúdo de email e modelos de conteúdo de email. Ele é compatível com e-mails simples, e-mails transacionais, e-mails de teste A/B, e-mails multilíngues e e e-mails recorrentes.

Para começar a usar o Designer de email, assista a esse [conjunto de vídeos](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html#GettingStarted) que explicam a funcionalidade geral do Designer de email e como projetar um email do zero ou usando modelos.

<!--The Email Designer has more features than the Legacy Editor and is backward compatible.-->

* Para descobrir como criar conteúdo de email, consulte [Introdução ao Designer](../../designing/using/quick-start.md)de email.
* Para obter uma visão geral do Designer de email, consulte [Uso do Designer](../../designing/using/designing-content-in-adobe-campaign.md)de email.
* Para obter mais informações sobre como criar conteúdo:
   * Do zero, consulte [Criar e-mails do zero](../../designing/using/designing-from-scratch.md).
   * Usando o conteúdo existente, consulte [Design usando o conteúdo](../../designing/using/using-existing-content.md)existente.
   * Usando integrações de Creative Cloud, consulte Design [de e-mail com](../../designing/using/using-integrations.md)várias soluções.
* Para obter mais informações sobre personalização, consulte [Personalização](../../designing/using/personalization.md).

Ao criar um email, você pode optar por usar um modelo predefinido ou carregar um conteúdo existente de outra fonte. Consulte [Seleção de um conteúdo](../../designing/using/using-existing-content.md#selecting-an-existing-content)existente.

Para aumentar a eficiência de suas campanhas de marketing, personalize seu conteúdo. Consulte [Inserir um campo](../../designing/using/personalization.md#inserting-a-personalization-field) de personalização e [Adicionar um bloco](../../designing/using/personalization.md#adding-a-content-block)de conteúdo.

Você também pode definir um conteúdo dinâmico que varia dependendo de cada perfil. Consulte [Definição de conteúdo dinâmico em um email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) e [Definição de conteúdo dinâmico em uma landing page](../../channels/using/designing-a-landing-page.md#defining-dynamic-content-in-a-landing-page).

Melhore suas mensagens e landings page com links e imagens. Consulte [Inserir um link](../../designing/using/links.md#inserting-a-link) e [Inserir imagens](../../designing/using/images.md#inserting-images).

## Interface do Designer de email {#email-designer-interface}

O Designer de e-mail fornece várias opções que permitem criar, editar e personalizar cada aspecto do seu conteúdo.

A interface é composta por várias áreas que oferecem diferentes funcionalidades:

![](assets/email_designer_overview.png)

A partir dos elementos disponíveis na **Paleta** (1), arraste e solte os componentes da estrutura e os fragmentos de conteúdo para a **Área de trabalho** principal (2). Selecione um componente ou elemento na **Workspace** (2) e personalize seu estilo principal e suas características de exibição no painel **Configurações** (3).

Acesse opções e configurações mais gerais na **barra de ferramentas** principal (4).

>[!NOTE]
>
>O painel **Configurações** pode se mover para a esquerda de acordo com a resolução e a exibição da tela.

![](assets/email_designer_toolbar.png)

A barra de ferramentas **** Contextual da interface do editor oferta várias funcionalidades dependendo da zona selecionada. Ele contém botões de ação e botões que permitem alterar o estilo do texto. As modificações efetuadas aplicam-se sempre à zona selecionada.

### Home page do Designer de Email {#email-designer-home-page}

Ao [criar um email](../../channels/using/creating-an-email.md), o **[!UICONTROL Email Designer]** home page é exibido automaticamente ao selecionar o conteúdo do email.

![](assets/email_designer_home_page.png)

A **[!UICONTROL Properties]** guia permite que você edite detalhes do email, como o rótulo, o endereço e o nome do remetente ou o assunto do email. Você também pode acessar essa guia clicando no rótulo do e-mail na parte superior da tela.

![](assets/email_designer_home_properties.png)

A **[!UICONTROL Templates]** guia permite que você escolha entre o conteúdo HTML pronto para uso ou os modelos que você já criou para criar rapidamente o start do design de seu email. Consulte Modelos [de](../../designing/using/using-reusable-content.md#content-templates)conteúdo.

![](assets/email_designer_home_templates.png)

A **[!UICONTROL Learn & support]** guia fornece acesso fácil à documentação e aos tutoriais relacionados.

![](assets/email_designer_home_support.png)

Se você não selecionar um modelo, o home page Email Designer também permitirá que você escolha como deseja que o start projete seu conteúdo:

* Clique no **[!UICONTROL Create]** botão para start um novo conteúdo do zero. Consulte [Criar um conteúdo de email do zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
* Clique no **[!UICONTROL Upload]** botão para carregar um arquivo do seu computador. Consulte [Importar conteúdo de um arquivo](../../designing/using/using-existing-content.md#importing-content-from-a-file).
* Clique no **[!UICONTROL Import from URL]** botão para recuperar o conteúdo existente de um URL. Consulte [Importar conteúdo de um URL](../../designing/using/using-existing-content.md#importing-content-from-a-url).

## Terminologia {#terminology}

**Modelos**: Os modelos são estruturas de e-mail que você pode criar e reutilizar para vários delivery.

**Fragmentos**: Um fragmento é um componente reutilizável que pode ser referenciado em um ou mais emails.

**Componentes** da estrutura: Elementos estruturais que definem o layout do email.

**Componentes** do conteúdo: Os componentes do conteúdo são componentes brutos e vazios que podem ser editados depois de enviados por email.

## Content design best practices {#content-design-best-practices}

Para fazer o uso correto do Designer de e-mail e criar os melhores e-mails da maneira mais simples possível, recomendamos a aplicação dos seguintes princípios:

* Use o estilo em linha em vez de um CSS e CSS separados na seção &lt;head> do HTML. Ao usar o estilo em linha, é possível otimizar a gravação e a reutilização do fragmento do conteúdo.

   Consulte [Adicionar atributos](../../designing/using/styles.md#adding-inline-styling-attributes)de estilização em linha.

* Se você importar arquivos ZIP contendo seu conteúdo HTML, use o CSS normal. As folhas de estilos SCSS não são suportadas.

* Configure sua marca facilmente criando e reutilizando fragmentos de conteúdo para manter a consistência em todas as campanhas de marketing.

   Consulte [Criação de um fragmento](../../designing/using/using-reusable-content.md#creating-a-content-fragment)de conteúdo.

* Ao editar conteúdo **de** email:

   Pré-visualização suas mensagens antes de enviá-las. A Adobe Campaign oferta uma maneira de testar a renderização de email usando o Litmus. For more on this, see [Email rendering](../../sending/using/email-rendering.md).

Na seção a seguir, são apresentadas mais práticas recomendadas de design e gerais relacionadas a mensagens: [Práticas](../../sending/using/delivery-best-practices.md)recomendadas para o delivery.

### Atualização de fragmentos {#email-designer-updates}

O Designer de e-mail está em melhoria contínua. Se você criou um conteúdo de email do zero, de um modelo predefinido ou se criou fragmentos, poderá receber a seguinte mensagem de atualização na próxima vez que abrir o conteúdo:

![](assets/email_designer_fragment_patch_message.png)

O Adobe recomenda atualizar seu conteúdo para a versão mais recente para evitar problemas como problemas de colisão de CSS. Clique em **[!UICONTROL Update now]**.

Se ocorrer um erro durante a atualização do conteúdo, verifique seu HTML e corrija-o antes de executar esta atualização novamente.

No que diz respeito aos fragmentos, observe o seguinte:

* Se quiser adicionar um fragmento a um novo email ou modelo e se receber essa mensagem, atualize esse fragmento primeiro.

* Se você tiver vários fragmentos, será necessário atualizar cada fragmento que deseja usar em um conteúdo de email.

* Para evitar impacto nas mensagens de email atuais que ainda não estão preparadas, você pode optar por não atualizar alguns fragmentos.

* Você ainda pode enviar emails onde um fragmento que não é atualizado já é usado, mas esse fragmento não é editável.

* A atualização de fragmentos usados em emails que já estão preparados não afeta esses emails.

## Limitações do Email Designer {#email-designer-limitations}

* Não é possível usar campos de personalização em um fragmento. For more on fragments, see [this section](../../designing/using/using-reusable-content.md#about-fragments).

<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->

* Ao editar estilos, somente as fontes da Web oficialmente suportadas pela maioria dos clientes de email estarão disponíveis.
* Os estilos não podem ser salvos como um tema para reutilização futura. Entretanto, o estilo CSS pode ser salvo em um modelo de conteúdo ou em um email. For more on styles, see [this section](../../designing/using/styles.md).

**Tópicos relacionados**

* [Criação de email](../../channels/using/creating-an-email.md)
* [Design de uma landing page](../../channels/using/designing-a-landing-page.md)
* [Criar uma mensagem SMS](../../channels/using/creating-an-sms-message.md)
* [Criação e envio de uma notificação por push](../../channels/using/preparing-and-sending-a-push-notification.md)
