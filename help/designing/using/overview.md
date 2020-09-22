---
title: Uso do Designer de email
description: Descubra o Designer de email e como ele ativa o conteúdo de design de email.
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
source-git-commit: 9ab3cc5a23b9b31b463bc3557b8164307d367d25
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 3%

---


# Uso do Designer de email {#email-designer}

## Visão geral do Designer de email {#about-the-email-designer}

O Designer de email permite que você crie conteúdo de email e modelos de conteúdo de email. Ele é compatível com e-mails simples, e-mails transacionais, e-mails de teste A/B, e-mails multilíngues e e e-mails recorrentes.

Para começar a usar o Designer de email, assista a esse [conjunto de vídeos](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html#GettingStarted) que explicam a funcionalidade geral do Designer de email e como projetar um email do zero ou usando modelos.

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

### Interface do Designer de email {#email-designer-interface}

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

### Terminologia {#terminology}

**Modelos**: Os modelos são estruturas de e-mail que você pode criar e reutilizar para vários delivery.

**Fragmentos**: Um fragmento é um componente reutilizável que pode ser referenciado em um ou mais emails.

**Componentes** da estrutura: Elementos estruturais que definem o layout do email

**Componentes** do conteúdo: Os componentes do conteúdo são componentes brutos e vazios que podem ser editados depois de enviados por email.

### Content design best practices {#content-design-best-practices}

Para fazer o uso correto do Designer de e-mail e criar os melhores e-mails da maneira mais simples possível, recomendamos a aplicação dos seguintes princípios:

* Use o estilo em linha em vez de um CSS e CSS separados na seção &lt;head> do HTML. Ao usar o estilo em linha, é possível otimizar a gravação e a reutilização do fragmento do conteúdo.

   Consulte [Adicionar atributos](../../designing/using/styles.md#adding-inline-styling-attributes)de estilização em linha.

* Se você importar arquivos ZIP contendo seu conteúdo HTML, use o CSS normal. As folhas de estilos SCSS não são suportadas.

* Configure sua marca facilmente criando e reutilizando fragmentos de conteúdo para manter a consistência em todas as campanhas de marketing.

   Consulte [Criação de um fragmento](../../designing/using/using-reusable-content.md#creating-a-content-fragment)de conteúdo.

* Ao editar conteúdo **de** email:

   Pré-visualização suas mensagens antes de enviá-las. A Adobe Campaign oferta uma maneira de testar a renderização de email usando o Litmus. For more on this, see [Email rendering](../../sending/using/email-rendering.md).

Na seção a seguir, são apresentadas mais práticas recomendadas de design e gerais relacionadas a mensagens: [Práticas recomendadas para o delivery](../../sending/using/delivery-best-practices.md)

### Limitações do Email Designer {#email-designer-limitations}

* Não é possível usar campos de personalização em um fragmento. For more on fragments, see [this section](../../designing/using/using-reusable-content.md#about-fragments).

<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->
* Ao editar estilos, somente as fontes da Web oficialmente suportadas pela maioria dos clientes de email estarão disponíveis.
* Os estilos não podem ser salvos como um tema para reutilização futura. Entretanto, o estilo CSS pode ser salvo em um modelo de conteúdo ou em um email. For more on styles, see [this section](../../designing/using/styles.md).
* A tag meta de quem indicou não é compatível com o Designer de email.
* Os pares de substitutos, caracteres não incluídos no Plano Multilingue Básico do conjunto de caracteres Unicode, não podem ser armazenados em 2 bytes (16 bits) e precisam ser codificados em 2 caracteres UTF-16. Esses caracteres incluem algumas ideografias CJK, a maioria dos emojis e alguns idiomas.
Esses caracteres podem causar alguns problemas de incompatibilidade no texto dinâmico. É necessário realizar testes fortes antes de enviar suas mensagens.

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