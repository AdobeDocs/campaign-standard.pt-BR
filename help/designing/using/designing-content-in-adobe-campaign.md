---
title: Criação de conteúdo no Adobe Campaign
description: Crie conteúdo de e-mail começando do zero, importando HTML ou aproveitando modelos existentes.
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
source-git-commit: 97760e8b5fe0eb4905dcae69e8bbbefa837a461f
workflow-type: tm+mt
source-wordcount: '1208'
ht-degree: 90%

---


# Designer de email do Campaign{#designing-content-in-adobe-campaign}

Após a criação de um email no Adobe Campaign, é necessário definir seu conteúdo.

O Designer de e-mail permite que você crie e-mails cativantes e adaptados individualmente por meio de uma interface de arrastar e soltar. Esteja você iniciando do zero ou a partir de fragmentos e modelos de conteúdo existentes, projete e refine todo o conteúdo para cada email, seja ele promocional ou transacional.

Criado para fornecer HTML otimizado para design responsivo, o Designer de email permite definir e aplicar facilmente condições de visibilidade e conteúdo dinâmico a um email, modelo ou fragmento diretamente pela interface do usuário. Você pode alternar facilmente entre a interface de arrastar e soltar e o código HTML clicando em um botão.

O Designer de email permite a criação de conteúdo de email e modelos de conteúdo de email. Ele é compatível com emails simples, transacionais, de teste A/B, multilíngues e recorrentes.

Para começar a usar o Designer de email, assista a esse [conjunto de vídeos](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html#GettingStarted) que explicam a funcionalidade geral do Designer de email e como projetar um email do zero ou utilizando modelos.

<!--The Email Designer has more features than the Legacy Editor and is backward compatible.-->

* Para descobrir como criar conteúdo de email, consulte [Introdução ao Designer de email](../../designing/using/quick-start.md).
* Para obter uma visão geral do Designer de email, consulte [Uso do Designer de email](../../designing/using/designing-content-in-adobe-campaign.md).
* Para obter mais informações sobre criação de conteúdo:
   * Do zero, consulte [Criação de emails do zero](../../designing/using/designing-from-scratch.md).
   * A partir de conteúdo existente, consulte [Criação a partir de conteúdo existente](../../designing/using/using-existing-content.md).
   * Usando integrações da Creative Cloud, consulte [Criação de email multissoluções](../../designing/using/using-integrations.md).
* Para obter mais informações sobre personalização, consulte [Personalização](../../designing/using/personalization.md).

Ao criar um email, você pode optar por usar um modelo predefinido ou carregar um conteúdo existente de outra fonte. Consulte [Seleção de conteúdo existente](../../designing/using/using-existing-content.md#selecting-an-existing-content).

Personalize o conteúdo para aumentar a eficiência de suas campanhas de marketing. Consulte [Inserir um campo de personalização](../../designing/using/personalization.md#inserting-a-personalization-field) e [Adicionar um bloco de conteúdo](../../designing/using/personalization.md#adding-a-content-block).

Você também pode definir um conteúdo dinâmico que varia dependendo de cada perfil. Consulte [Definição de conteúdo dinâmico em um email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) e [Definição de conteúdo dinâmico em uma landing page](../../channels/using/designing-a-landing-page.md#defining-dynamic-content-in-a-landing-page).

Melhore suas mensagens e landing pages com links e imagens. Consulte [Inserir um link](../../designing/using/links.md#inserting-a-link) e [Inserir imagens](../../designing/using/images.md#inserting-images).

## Interface do Designer de email {#email-designer-interface}

O Designer de email fornece várias opções que permitem criar, editar e personalizar cada aspecto do seu conteúdo.

A interface é composta por várias áreas que oferecem diferentes funcionalidades:

![](assets/email_designer_overview.png)

A partir dos elementos disponíveis na **Paleta** (1), arraste e solte componentes da estrutura e fragmentos de conteúdo no **espaço de trabalho** principal (2). Selecione um componente ou elemento no **espaço de trabalho** (2) e personalize seu estilo principal e suas características de exibição no painel **Configurações** (3).

Acesse opções e configurações genéricas na **Barra de ferramentas** principal (4).

>[!NOTE]
>
>O painel **Configurações** pode se mover para a esquerda de acordo com a resolução e a exibição da tela.

![](assets/email_designer_toolbar.png)

A **barra de ferramentas Contextual** da interface do editor oferece várias funcionalidades dependendo da zona selecionada. Ela contém botões de ação e botões que permitem alterar o estilo do texto. As modificações efetuadas aplicam-se sempre à zona selecionada.

### Home page do Designer de email {#email-designer-home-page}

Ao [criar um email](../../channels/using/creating-an-email.md), a **[!UICONTROL Email Designer]** home page é exibida automaticamente a partir da seleção do conteúdo do email.

![](assets/email_designer_home_page.png)

A guia **[!UICONTROL Properties]** permite editar detalhes do email, como rótulo, endereço e nome do remetente, ou o assunto do email. Você também pode acessar essa guia clicando no rótulo do email na parte superior da tela.

![](assets/email_designer_home_properties.png)

A guia **[!UICONTROL Templates]** permite escolher entre o conteúdo HTML pronto para o uso ou os modelos já criados por você para iniciar rapidamente a criação do seu email. Consulte [Modelos de conteúdo](../../designing/using/using-reusable-content.md#content-templates).

![](assets/email_designer_home_templates.png)

A guia **[!UICONTROL Learn & support]** fornece acesso fácil à documentação e aos tutoriais relacionados.

![](assets/email_designer_home_support.png)

Se você não selecionar um modelo, a página inicial do Designer de email também permitirá a escolha do início da criação de conteúdo:

* Clique no botão **[!UICONTROL Create]** para iniciar um novo conteúdo do zero. Consulte [Criar um conteúdo de email do zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
* Clique no botão **[!UICONTROL Upload]** para carregar um arquivo do seu computador. Consulte [Importar conteúdo de um arquivo](../../designing/using/using-existing-content.md#importing-content-from-a-file).
* Clique no botão **[!UICONTROL Import from URL]** para recuperar o conteúdo existente de um URL. Consulte [Importar conteúdo de um URL](../../designing/using/using-existing-content.md#importing-content-from-a-url).

## Terminologia {#terminology}

**Modelos**: os modelos são estruturas de email que podem ser criadas e reutilizadas para vários deliveries.

**Fragmentos**: um fragmento é um componente reutilizável que pode ser referenciado em um ou mais emails.

**Componentes da estrutura**: elementos estruturais que definem o layout do email.

**Componentes do conteúdo**: os componentes do conteúdo são componentes brutos e vazios que podem ser editados depois de colocados no email.

## Práticas recomendadas de criação de conteúdo {#content-design-best-practices}

Para fazer o uso correto do Designer de email e criar os melhores emails da maneira mais simples possível, recomendamos a aplicação dos seguintes princípios:

* Use o estilo em linha em vez de CSS separado e CSS na seção &lt;head> do HTML. Ao usar o estilo em linha, é possível otimizar o fragmento de conteúdo salvar e reutilizar.

   Consulte [Adicionar atributos de estilo em linha](../../designing/using/styles.md#adding-inline-styling-attributes).

* Se você importar arquivos ZIP contendo seu conteúdo HTML, use o CSS regular. As folhas de estilos SCSS não são compatíveis.

* Configure facilmente sua identidade visual criando e reutilizando fragmentos de conteúdo para manter a consistência em todas as campanhas de marketing.

   Consulte [Criação de um fragmento de conteúdo](../../designing/using/using-reusable-content.md#creating-a-content-fragment).

* Ao editar **conteúdo de email**:

   Pré-visualização de mensagens antes do envio. O Adobe Campaign oferece uma maneira de testar a renderização de email usando o Litmus. Para obter mais informações, consulte [Renderização de email](../../sending/using/email-rendering.md).

Na seção a seguir, são apresentadas mais práticas recomendadas de design e gerais relacionadas a mensagens: [Práticas](../../sending/using/delivery-best-practices.md)recomendadas para o delivery.

### Atualização de fragmentos {#email-designer-updates}

O Designer de email está em melhoria contínua. Se você criou um conteúdo de email do zero, a partir de um modelo predefinido ou se criou fragmentos, será possível receber a seguinte mensagem de atualização da próxima vez que abrir o conteúdo:

![](assets/email_designer_fragment_patch_message.png)

A Adobe recomenda atualizar seu conteúdo para a versão mais recente para evitar contratempos, como problemas de falha de CSS. Clique em **[!UICONTROL Update now]**.

Se ocorrer um erro durante a atualização do conteúdo, verifique seu HTML e corrija-o antes de executar esta atualização novamente.

Quanto aos fragmentos, observe o seguinte:

* Se quiser adicionar um fragmento a um novo email ou modelo e se receber essa mensagem, atualize esse fragmento antes.

* Se você tiver vários fragmentos, será necessário atualizar cada fragmento que deseja usar em um conteúdo de email.

* Para evitar impacto nas mensagens de email atuais ainda não preparadas, você pode optar por não atualizar alguns fragmentos.

* Você ainda pode enviar emails quando um fragmento não atualizado já estiver sendo usado, mas esse fragmento não é editável.

* A atualização de fragmentos usados em emails já preparados não afeta esses emails.

## Limitações do Designer de email {#email-designer-limitations}

* Não é possível usar campos de personalização em um fragmento. Para obter mais informações sobre fragmentos, consulte [esta seção](../../designing/using/using-reusable-content.md#about-fragments).

<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->

* Ao editar estilos, somente as fontes da web oficialmente compatíveis pela maioria dos clientes de email estarão disponíveis.
* Os estilos não podem ser salvos como um tema para futura reutilização. Entretanto, o estilo CSS pode ser salvo em um modelo de conteúdo ou em um email. Para obter mais informações sobre estilos, consulte [esta seção](../../designing/using/styles.md).
* A tag meta de quem indicou não é compatível com o Designer de email.
* Os pares de substitutos, caracteres não incluídos no Plano Multilingue Básico do conjunto de caracteres Unicode, não podem ser armazenados em 2 bytes (16 bits) e precisam ser codificados em 2 caracteres UTF-16. Esses caracteres incluem algumas ideografias CJK, a maioria dos emojis e alguns idiomas.<br>Esses caracteres podem causar alguns problemas de incompatibilidade no texto dinâmico. É necessário realizar testes fortes antes de enviar suas mensagens.

**Tópicos relacionados**

* [Criação de email](../../channels/using/creating-an-email.md)
* [Design de uma landing page](../../channels/using/designing-a-landing-page.md)
* [Criar uma mensagem SMS](../../channels/using/creating-an-sms-message.md)
* [Criação e envio de uma notificação por push](../../channels/using/preparing-and-sending-a-push-notification.md)
