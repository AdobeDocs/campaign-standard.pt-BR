---
title: Uso do Designer de email
seo-title: Uso do Designer de email
description: Uso do Designer de email
seo-description: Descubra o Designer de email e como ele ativa o conteúdo de design de email.
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
source-git-commit: a7de545e9eec675444245576cddc6eaf8dce05f4

---


# Uso do Designer de email {#email-designer}

## Visão geral do Designer de email {#about-the-email-designer}

O Designer de email permite que você crie conteúdo de email e modelos de conteúdo de email. Ele é compatível com e-mails simples, e-mails transacionais, e-mails de teste A/B, e-mails multilíngues e e e-mails recorrentes.

Para começar a usar o Designer de email, assista a esse [conjunto de vídeos](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#GettingStarted) que explicam a funcionalidade geral do Designer de email e como projetar um email do zero ou usando modelos.

### Página inicial do Designer de email {#email-designer-home-page}

Ao [criar um email](../../channels/using/creating-an-email.md)**[!UICONTROL Email Designer]** , a página inicial é exibida automaticamente ao selecionar o conteúdo do email.

![](assets/email_designer_home_page.png)

A **[!UICONTROL Properties]** guia permite que você edite detalhes do email, como o rótulo, o endereço e o nome do remetente ou o assunto do email. Você também pode acessar essa guia clicando no rótulo do email na parte superior da tela.

![](assets/email_designer_home_properties.png)

A **[!UICONTROL Templates]** guia permite escolher entre o conteúdo HTML predefinido ou os modelos que você já criou para iniciar rapidamente a criação do seu email. Consulte Modelos [de](../../designing/using/using-reusable-content.md#content-templates)conteúdo.

![](assets/email_designer_home_templates.png)

A **[!UICONTROL Learn & support]** guia fornece acesso fácil à documentação e aos tutoriais relacionados.

![](assets/email_designer_home_support.png)

Se você não selecionar um modelo, a página inicial do Email Designer também permitirá que você escolha como deseja começar a criar seu conteúdo:

* Clique no **[!UICONTROL Create]** botão para iniciar um novo conteúdo do zero. Consulte [Criar um conteúdo de email do zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
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

A barra de ferramentas **** Contextual da interface do editor oferece várias funcionalidades dependendo da zona selecionada. Ele contém botões de ação e botões que permitem alterar o estilo do texto. As modificações efetuadas aplicam-se sempre à zona selecionada.

### Terminologia {#terminology}

**Modelos**: Os modelos são estruturas de e-mail que você pode criar e reutilizar para várias entregas.

**Fragmentos**:Um fragmento é um componente reutilizável que pode ser referenciado em um ou mais emails.

**Componentes** da estrutura: Elementos estruturais que definem o layout do email

**Componentes** do conteúdo:Os componentes do conteúdo são componentes brutos e vazios que podem ser editados depois de enviados por email.

### Práticas recomendadas de design de conteúdo {#content-design-best-practices}

Para fazer o uso correto do Designer de e-mail e criar os melhores e-mails da maneira mais simples possível, recomendamos a aplicação dos seguintes princípios:

* Use o estilo em linha em vez de um CSS e CSS separados na seção &lt;head&gt; do HTML. Ao usar o estilo em linha, é possível otimizar a gravação e a reutilização do fragmento do conteúdo.

   Consulte [Adicionar atributos](../../designing/using/styles.md#adding-inline-styling-attributes)de estilização em linha.

* Se você importar arquivos ZIP contendo seu conteúdo HTML, use o CSS normal. As folhas de estilos SCSS não são suportadas.

* Configure sua marca facilmente criando e reutilizando fragmentos de conteúdo para manter a consistência em todas as campanhas de marketing.

   Consulte [Criação de um fragmento](../../designing/using/using-reusable-content.md#creating-a-content-fragment)de conteúdo.

* Ao editar conteúdo **de** email:

   Visualize suas mensagens antes de enviá-las. O Adobe Campaign oferece uma maneira de testar a renderização de email usando o Litmus. Para obter mais informações, consulte Renderização [por](../../sending/using/email-rendering.md)email.

As práticas recomendadas gerais e de design referentes a mensagens são apresentadas no seguinte guia passo a passo do Adobe Campaign: Práticas recomendadas [de entrega com o Adobe Campaign](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).

### Limitações do Email Designer {#email-designer-limitations}

* Não é possível usar campos de personalização em um fragmento. Para obter mais informações sobre fragmentos, consulte [esta seção](../../designing/using/using-reusable-content.md#about-fragments).
<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->
* Ao editar estilos, somente as fontes da Web oficialmente suportadas pela maioria dos clientes de email estarão disponíveis.
* Os estilos não podem ser salvos como um tema para reutilização futura. Entretanto, o estilo CSS pode ser salvo em um modelo de conteúdo ou em um email. Para obter mais informações sobre estilos, consulte [esta seção](../../designing/using/styles.md).

### Atualização de fragmentos {#email-designer-updates}

O Designer de e-mail está em melhoria contínua. Se você criou um conteúdo de email do zero, de um modelo predefinido ou se criou fragmentos, poderá receber a seguinte mensagem de atualização na próxima vez que abrir o conteúdo:

![](assets/email_designer_fragment_patch_message.png)

A Adobe recomenda atualizar seu conteúdo para a versão mais recente para evitar problemas como problemas de colisão de CSS. Click **[!UICONTROL Update now]**.

Se ocorrer um erro durante a atualização do conteúdo, verifique seu HTML e corrija-o antes de executar esta atualização novamente.

No que diz respeito aos fragmentos, observe o seguinte:

* Se quiser adicionar um fragmento a um novo email ou modelo e se receber essa mensagem, atualize esse fragmento primeiro.

* Se você tiver vários fragmentos, será necessário atualizar cada fragmento que deseja usar em um conteúdo de email.

* Para evitar impacto nas mensagens de email atuais que ainda não estão preparadas, você pode optar por não atualizar alguns fragmentos.

* Você ainda pode enviar emails onde um fragmento que não é atualizado já é usado, mas esse fragmento não é editável.

* A atualização de fragmentos usados em emails que já estão preparados não afeta esses emails.