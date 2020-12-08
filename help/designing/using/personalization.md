---
solution: Campaign Standard
product: campaign
title: Personalização de conteúdo de e-mail
description: Descubra como personalizar um email no Designer de email.
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: a51943e4da04f5d19aaecdfcf956f5c4f3d804c8
workflow-type: tm+mt
source-wordcount: '2573'
ht-degree: 5%

---


# Personalização de conteúdo de e-mail {#personalization}

O conteúdo e a exibição de mensagens entregues pela Adobe Campaign podem ser personalizados de várias maneiras diferentes. Essas maneiras podem ser combinadas de acordo com critérios dependendo dos perfis. Em geral, o Adobe Campaign permite:

* Inserir campos de personalização dinâmicos. Consulte [Inserção de um campo de personalização](#inserting-a-personalization-field).
* Inserir blocos de personalização predefinidos. Consulte [Adição de um bloco de conteúdo](#adding-a-content-block).
* Personalize o remetente de um email. Consulte [Personalizar o remetente](#personalizing-the-sender).
* Personalize o assunto de um email. Consulte [Personalizar a linha de assunto de um email](../../designing/using/subject-line.md#subject-line).
* Criar conteúdo condicional. Consulte [Definição de conteúdo dinâmico em um email](#defining-dynamic-content-in-an-email).

## Personalização do remetente {#personalizing-the-sender}

Para definir o nome do remetente que aparecerá no cabeçalho das mensagens enviadas, vá para a guia **[!UICONTROL Properties]** do home page do Email Designer (acessível por meio do ícone inicial). Para obter mais informações, consulte [Definição do remetente de um email](../../designing/using/subject-line.md#email-sender).

Você pode alterar o nome do remetente clicando no bloco **Nome do remetente**. O campo se torna editável e você pode inserir o nome que deseja usar.

Este campo pode ser personalizado. Para fazer isso, você pode adicionar campos de personalização, blocos de conteúdo e conteúdo dinâmico clicando nos ícones abaixo do nome do remetente.

>[!NOTE]
>
>Os parâmetros do cabeçalho não devem ficar vazios. O endereço do remetente é obrigatório para possibilitar o envio de um email (padrão RFC). O Adobe Campaign verifica a sintaxe dos endereços de email inseridos.

## Personalizando URLs{#personalizing-urls}

A Adobe Campaign permite que você personalize um ou vários URLs em sua mensagem adicionando campos de personalização, blocos de conteúdo ou conteúdo dinâmico a eles. Para fazer isso:

1. Insira um URL externo e especifique seus parâmetros. Consulte [Inserir um link](../../designing/using/links.md#inserting-a-link).
1. Se não for exibido, clique no lápis ao lado do URL selecionado no painel Configurações para acessar as opções de personalização.
1. Adicione os campos de personalização, blocos de conteúdo e conteúdo dinâmico que você deseja usar.

   ![](assets/des_personalize_links.png)

1. Salve as alterações.

>[!NOTE]
>
>A personalização de URLs não pode ser aplicada ao nome do domínio nem à extensão do URL. Uma mensagem de erro será exibida durante a análise da mensagem se a personalização estiver incorreta. Ao selecionar um bloco de conteúdo, você não tem permissão para selecionar elementos como **Link para o mirror page**. Este tipo de blocos é proibido dentro de um link.

## Inserção de um campo de personalização{#inserting-a-personalization-field}

A Adobe Campaign permite que você insira um campo do banco de dados em sua página, como o nome do perfil.

>[!NOTE]
>
>As imagens abaixo mostram como inserir um campo de personalização usando o [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md) para um email.

Para adicionar um campo de personalização ao conteúdo:

1. Clique dentro de um bloco de texto, clique no ícone **[!UICONTROL Personalize]** na barra de ferramentas contextual e selecione **[!UICONTROL Insert personalization field]**. Para obter mais informações sobre a interface do Email Designer, consulte [esta seção](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface).

   ![](assets/email_perso_field_1.png)

1. Selecione o campo que deseja inserir no conteúdo da página.

   ![](assets/email_perso_field_2.png)

1. Clique em **[!UICONTROL Confirm]**.

O nome do campo aparece no editor e é realçado.

![](assets/email_perso_field_3.png)

Quando a personalização for gerada (ao visualizar e preparar o email, por exemplo), esse campo será substituído pelo valor correspondente ao perfil direcionado.

>[!NOTE]
>
>Se o email for criado a partir de um fluxo de trabalho, os dados adicionais calculados no fluxo de trabalho também estarão disponíveis nos campos de personalização. Para obter mais informações sobre como adicionar dados adicionais de um fluxo de trabalho, consulte a seção [Enriquecendo dados](../../automating/using/about-targeting-activities.md#enriching-data).

## Inclusão de um bloco de conteúdo{#adding-a-content-block}

A Adobe Campaign oferta uma lista de blocos de conteúdo pré-configurados. Esses blocos de conteúdo são dinâmicos, personalizados e têm uma renderização específica. Por exemplo, você pode adicionar uma saudação ou um link ao mirror page.

>[!NOTE]
>
>As imagens abaixo mostram como inserir um bloco de conteúdo usando o [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md) para um email.

Para adicionar um bloco de conteúdo:

1. Clique dentro de um bloco de texto, clique no ícone **[!UICONTROL Personalize]** na barra de ferramentas contextual e selecione **[!UICONTROL Insert content block]**. Para obter mais informações sobre a interface do Email Designer, consulte [esta seção](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface).

   ![](assets/email_content_block_1.png)

1. Selecione o bloco de conteúdo que deseja inserir. Os blocos disponíveis variam dependendo do contexto (email ou landing page).

   ![](assets/email_content_block_2.png)

1. Clique em **[!UICONTROL Save]**.

O nome do bloco de conteúdo aparece no editor e é realçado em amarelo. Ele se adapta automaticamente ao perfil quando a personalização é gerada.

![](assets/email_content_block_3.png)

Os blocos de conteúdo prontos para uso são:

* **[!UICONTROL Database URL in emails (EmailUrlBase)]**: Este bloco de conteúdo só pode ser usado em um  **delivery**.
* **[!UICONTROL Mirror page URL (MirrorPageUrl)]**: Este bloco de conteúdo só pode ser usado em um  **delivery**.
* **[!UICONTROL Link to mirror page (MirrorPage)]**: Este bloco de conteúdo só pode ser usado em um  **delivery**.
* **[!UICONTROL Greetings (Greetings)]**
* **[!UICONTROL Unsubscription link (UnsubscriptionLink)]**: Este bloco de conteúdo só pode ser usado em um  **delivery**.
* **[!UICONTROL Social network sharing links (LandingPageViralLinks)]**: Este bloco de conteúdo só pode ser usado em uma  **landing page**.
* **[!UICONTROL Default sender name (DefaultSenderName)]**: Este bloco de conteúdo só pode ser usado em um  **delivery**.
* **[!UICONTROL Name of default reply-to email address (DefaultReplyName)]**: Este bloco de conteúdo só pode ser usado em um  **delivery**.
* **[!UICONTROL Email address of default sender (DefaultSenderAddress)]**: Este bloco de conteúdo só pode ser usado em um  **delivery**.
* **[!UICONTROL Default error email address (DefaultErrorAddress)]**: Este bloco de conteúdo só pode ser usado em um  **delivery**.
* **[!UICONTROL Default reply-to email address (DefaultReplyAddress)]**: Este bloco de conteúdo só pode ser usado em um  **delivery**.
* **[!UICONTROL Brand name (BrandingUsualName)]**
* **[!UICONTROL Link to the brand website (BrandingWebSiteLink)]**
* **[!UICONTROL Brand logo (BrandingLogo)]**
* **[!UICONTROL Notification style (notificationStyle)]**

### Criação de blocos de conteúdo personalizados {#creating-custom-content-blocks}

Você pode definir novos blocos de conteúdo que serão inseridos em uma mensagem ou landing page.

Para criar um bloco de conteúdo, siga estas etapas:

1. Clique em **[!UICONTROL Resources > Content blocks]** no menu avançado para acessar a lista dos blocos de conteúdo.
1. Clique no botão **[!UICONTROL Create]** ou em duplicado de um bloco de conteúdo pré-existente.

   ![](assets/content_bloc_01.png)

1. Insira um rótulo.
1. Selecione **[!UICONTROL Content type]** do bloco. Há três opções disponíveis:

   * **[!UICONTROL Shared]**: O bloco de conteúdo pode ser usado em um delivery ou landing page.
   * **[!UICONTROL Delivery]**: O bloco de conteúdo só pode ser usado em um delivery.
   * **[!UICONTROL Landing page]**: O bloco de conteúdo só pode ser usado em uma landing page.

   ![](assets/content_bloc_02.png)

1. Você pode selecionar um **[!UICONTROL Targeting dimension]**. Para obter mais informações, consulte [Sobre o targeting dimension](#about-targeting-dimension).

   ![](assets/content_bloc_04.png)

1. Você pode selecionar a opção **[!UICONTROL Depends on format]** para definir dois blocos diferentes: um para e-mails HTML e outro para e-mails em formato de texto. Duas guias serão exibidas no editor (HTML e Texto) para definir o conteúdo correspondente.

   ![](assets/content_bloc_03.png)

1. Insira o conteúdo dos blocos de conteúdo e clique no botão **[!UICONTROL Create]**.

Seu bloco de conteúdo agora pode ser usado no editor de conteúdo de uma mensagem ou landing page.

>[!CAUTION]
>
>Ao editar o conteúdo de um bloco, verifique se não há espaços em branco extras entre o início e o fim das instruções *if*. Em HTML, os espaços em branco são exibidos na tela e, portanto, afetarão seu layout de conteúdo.

### Sobre o targeting dimension {#about-targeting-dimension}

O targeting dimension permite definir em qual tipo de mensagem você pode usar o bloco de conteúdo. Isso impede o uso de blocos inadequados em uma mensagem, o que pode levar a erros.

Na verdade, ao editar uma mensagem, você só pode selecionar blocos de conteúdo com um targeting dimension que seja compatível com o targeting dimension dessa mensagem.

Por exemplo, o targeting dimension do bloco **[!UICONTROL Unsubscription link]** é **[!UICONTROL Profiles]** porque contém campos de personalização específicos do recurso **[!UICONTROL Profiles]**. Portanto, você não pode usar um bloco **[!UICONTROL Unsubscription link]** em um mensagen transacional [evento](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types), pois o targeting dimension desse tipo de mensagem é **[!UICONTROL Real-time events]**. No entanto, você pode usar o bloco **link de Unsubscription** em um mensagen transacional [perfil](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types), pois o targeting dimension desse tipo de mensagem é **Perfis**. Finalmente, o bloco **[!UICONTROL Link to mirror page]** não tem um targeting dimension, portanto, você pode usá-lo em qualquer mensagem.

Se você deixar esse campo vazio, o bloco de conteúdo será compatível com todas as mensagens, independentemente do targeting dimension. Se você definir um targeting dimension, esse bloco só será compatível com mensagens que tenham o mesmo targeting dimension.

Para saber mais, consulte [Targeting dimensions e recursos](../../automating/using/query.md#targeting-dimensions-and-resources).

**Tópicos relacionados:**

* [Inserção de um campo de personalização](#inserting-a-personalization-field)
* [Inclusão de um bloco de conteúdo](#adding-a-content-block)
* [Definição de conteúdo dinâmico em um email](#defining-dynamic-content-in-an-email)

## Personalização de uma fonte de imagem{#personalizing-an-image-source}

A Adobe Campaign permite que você personalize uma ou várias imagens em sua mensagem de acordo com um critério específico ou use o rastreamento. Isso é feito inserindo campos de personalização, blocos de conteúdo ou conteúdo dinâmico na fonte de imagem. Para fazer isso:

1. Insira uma imagem no conteúdo da mensagem ou selecione uma imagem que já esteja presente.
1. Na paleta Propriedades de imagens, marque a opção **[!UICONTROL Enable personalization]**.

   ![](assets/des_personalize_images_1.png)

   O campo **[!UICONTROL Source]** é exibido e a imagem selecionada é mostrada como **personalizada** no editor.

1. Clique no lápis ao lado do botão **[!UICONTROL Source]** para acessar as opções de personalização.
1. Depois de adicionar a fonte de imagem, adicione os campos de personalização, blocos de conteúdo e o conteúdo dinâmico que desejar.

   ![](assets/des_personalize_images_2.png)

   >[!NOTE]
   >
   >O nome de domínio (http://mydomain.com) não pode ser personalizado, ele deve ser inserido manualmente. O restante do URL pode ser personalizado. Por exemplo: http://mydomain.com/ `[Gender]` .jpg

1. Confirme as alterações.

## Conteúdo condicional {#conditional-content}

### Definição de uma condição de visibilidade{#defining-a-visibility-condition}

Você pode especificar uma condição de visibilidade em qualquer elemento. Só será visível se a condição for respeitada.

Para adicionar uma condição de visibilidade, selecione um bloco e insira a condição a ser respeitada no campo **[!UICONTROL Visibility condition]** de suas configurações.

![](assets/delivery_content_5.png)

Essa opção só está disponível para os seguintes elementos: ENDEREÇO, BLOQUEIO, CENTRO, DIR, DIV, DL, FIELDSET, FORM, H1, H2, H3, H4, H5, H6, NOSCRIPT, OL, P, PRE, UL, TR, TD.

O editor de expressões é apresentado na seção [Edição avançada de expressões](../../automating/using/editing-queries.md#about-query-editor).

Essas condições adotam a sintaxe de expressão XTK (por exemplo, **context.perfil.email !=&#39;&#39;** ou **context.perfil.status=&#39;0&#39;**). Por padrão, todos os campos são visíveis.

>[!NOTE]
>
>Não é possível definir uma condição para um bloco que já contenha um subelemento com um conteúdo dinâmico ou um bloco que já compõe um conteúdo dinâmico. Não é possível editar blocos dinâmicos não visíveis, como listas suspensas.

### Definição de conteúdo dinâmico em um email{#defining-dynamic-content-in-an-email}

>[!CONTEXTUALHELP]
>id="ac_dynamic_content"
>title="Definição de conteúdo dinâmico"
>abstract="Defina conteúdos diferentes que serão exibidos para alguns perfis somente de acordo com as condições que você definirá."

Em um email, você pode definir conteúdos diferentes que serão exibidos dinamicamente para os recipient, de acordo com as condições definidas pelo editor de expressões. Por exemplo, a partir do mesmo email, você pode garantir que cada perfil receba uma mensagem diferente de acordo com o intervalo de idade.

A definição de conteúdo dinâmico é diferente de [definindo condições de visibilidade](#defining-a-visibility-condition).

1. Selecione um fragmento, um componente ou um elemento. Neste exemplo, selecione uma imagem.
1. Clique no ícone **[!UICONTROL Dynamic content]** na barra de ferramentas contextual.

   ![](assets/dynamic_content_2.png)

   A seção **[!UICONTROL Dynamic content]** é exibida na paleta à esquerda.

   ![](assets/dynamic_content_3.png)

   Por padrão, esta seção contém dois elementos: a variante padrão e uma nova variante.

   >[!NOTE]
   >
   >O conteúdo deve sempre ter uma variante padrão. Não é possível excluí-lo.

1. Clique no botão **[!UICONTROL Edit]** para definir as condições de exibição para a primeira variante alternativa.

   ![](assets/dynamic_content_4.png)

1. Especifique um rótulo e selecione os campos que deseja definir como condições. Por exemplo, no nó **[!UICONTROL General]**, selecione o campo **[!UICONTROL Age]**

   ![](assets/dynamic_content_5.png)

1. Defina as condições de filtragem. Por exemplo, você deseja que um conteúdo diferente seja exibido para pessoas com idade entre 18 e 25 anos.

   ![](assets/dynamic_content_6.png)

1. Depois que todas as condições forem definidas, defina a ordem de prioridade na qual a condição será aplicada e salve as alterações.

   ![](assets/dynamic_content_7.png)

   O conteúdo será exibido na paleta em ordem de prioridade, de cima para baixo. Para obter mais informações sobre prioridades, consulte [esta seção](#defining-dynamic-content-in-an-email).

1. Carregue uma nova imagem para a variante que você acabou de definir.

   ![](assets/dynamic_content_8.png)

   Os recipient com idade entre 18 e 25 anos verão a nova imagem.

   ![](assets/dynamic_content_10.png)

1. Clique em **[!UICONTROL Add a condition]** para adicionar um novo conteúdo e sua regra vinculada.

   ![](assets/dynamic_content_9.png)

   Por exemplo, você pode adicionar uma imagem diferente para ser exibida a pessoas com idade entre 26 e 35 anos.

1. Proceda de forma semelhante para qualquer outro elemento do seu email que você deseja que seja exibido dinamicamente. Pode ser texto, botão, fragmento etc. Salve as alterações.

>[!CAUTION]
>
>Depois de preparar sua mensagem e antes de enviá-la, teste-a usando uma prova. Se você não fizer isso, alguns erros podem não ser detectados e o email pode não ser enviado.

**Tópicos relacionados:**

* [Envio de provas](../../sending/using/sending-proofs.md)
* [Edição de expressão avançada](../../automating/using/editing-queries.md#about-query-editor)

### Ordem de prioridade {#order-of-priority}

No editor de expressões, ao definir um conteúdo dinâmico, a ordem de prioridade é a seguinte.

1. Você define dois conteúdos dinâmicos diferentes com **duas condições diferentes**, por exemplo:

   **Condição 1:** o sexo do perfil é masculino,

   **Condição 2:** o perfil tem entre 20 e 30 anos.

   ![](assets/delivery_content_61.png)

   Alguns perfis em seu banco de dados correspondem às duas condições, mas apenas um email com um conteúdo dinâmico pode ser enviado.

1. Portanto, é necessário definir a prioridade para o conteúdo dinâmico. Uma condição com uma ordem de prioridade de **1** (e, portanto, o conteúdo dinâmico correspondente) será enviada para um perfil mesmo se outra condição cuja ordem de prioridade seja **2** ou **3** também for atendida por esse perfil.

   ![](assets/delivery_content_62.png)

Você só pode definir uma ordem de prioridade por conteúdo dinâmico.

## Exemplo: Personalização de email{#example-email-personalization}

Neste exemplo, um membro da equipe do serviço de marketing criou um email para informar alguns de seus clientes que existe uma oferta especial apenas para eles. O membro da equipe decidiu personalizar o e-mail de acordo com as respectivas idades dos clientes. Os clientes com idade entre 18 e 27 anos receberão um email contendo uma imagem e um slogan diferentes daqueles que os clientes com mais de 27 anos receberão.

O email é criado da seguinte maneira:

* O conteúdo dinâmico é aplicado à imagem e esse conteúdo dinâmico é configurado de acordo com o intervalo de idades.

   ![](assets/delivery_content_43.png)

   A adição e configuração de conteúdo dinâmico está detalhada na seção [Definição de conteúdo dinâmico em um email](#defining-dynamic-content-in-an-email).

* Campos de personalização e conteúdo dinâmico são aplicados ao texto. Dependendo da faixa etária do perfil, o e-mail é start com o nome do perfil ou o título e sobrenome do perfil.

   ![](assets/delivery_content_44.png)

   A adição e configuração dos campos de personalização está detalhada na seção [Inserir um campo de personalização](#inserting-a-personalization-field).

### Configuração de imagens {#configuring-images}

>[!CONTEXTUALHELP]
>id="ac_dynamic_image"
>title="Gerenciamento de imagens dinâmicas"
>abstract="Personalize seu email com imagens dinâmicas de acordo com as condições que você definirá."

Neste exemplo, o conteúdo dinâmico aplicado às imagens é configurado da seguinte forma:

**Ao público alvo de 18 a 27 anos:**

1. Selecione o conteúdo dinâmico na paleta **[!UICONTROL Properties]** e clique no botão **[!UICONTROL Edit]**.

   ![](assets/delivery_content_48.png)

1. Edite o rótulo e selecione o campo **[!UICONTROL Age]** no nó **[!UICONTROL Profile]**.

   ![](assets/delivery_content_49.png)

1. Selecione o operador **Maior que ou igual a** e digite **18** para criar a expressão **mais antiga que 18**.

   ![](assets/delivery_content_50.png)

1. Adicione uma nova condição **[!UICONTROL Age]**.

   Selecione o operador **Menor que ou igual a** seguido por 27 no campo de valor para criar a expressão **menor que 27**.

   ![](assets/delivery_content_51.png)

1. Confirme as alterações.

**Para perfis públicos alvos com idade igual ou superior a 27 anos:**

1. Selecione o conteúdo dinâmico da paleta e edite-o.
1. Edite o rótulo e selecione o campo **[!UICONTROL Age]** no nó **[!UICONTROL Profile]**.
1. Adicione o operador **Maior que** seguido por 27 no campo de valor para criar a expressão **mais antiga que 27**.

   ![](assets/delivery_content_52.png)

1. Confirme as alterações.

Seu conteúdo dinâmico está configurado corretamente.

### Configuração de texto {#configuring-text}

Neste exemplo, o conteúdo dinâmico aplicado aos textos é configurado da seguinte forma:

**Para perfis públicos alvos com idade entre 18 e 27 anos:**

1. Selecione o componente de estrutura desejado e adicione um conteúdo dinâmico.
1. Edite o conteúdo dinâmico e configure as expressões de definição de metas. Consulte [Configuração de imagens](#configuring-images).
1. No componente de estrutura, na posição desejada, clique no ícone **[!UICONTROL Personalize]** na barra de ferramentas contextual e selecione **[!UICONTROL Insert personalization field]**.

   ![](assets/delivery_content_53.png)

1. Na lista que é exibida, selecione o campo **[!UICONTROL First name]** e confirme.

   ![](assets/delivery_content_54.png)

1. Seu campo de personalização é então perfeitamente inserido no conteúdo dinâmico selecionado.

**Para perfis públicos alvos com idade igual ou superior a 27 anos:**

1. Selecione o componente de estrutura desejado e adicione um conteúdo dinâmico.
1. Edite o conteúdo dinâmico e configure as expressões de definição de metas. Consulte [Configuração de imagens](#configuring-images).
1. No componente de estrutura, na posição desejada, clique no ícone **[!UICONTROL Personalize]** na barra de ferramentas contextual e selecione **[!UICONTROL Insert personalization field]**.
1. Selecione **[!UICONTROL Title]** na lista suspensa.
1. Proceda de forma semelhante para adicionar o campo **[!UICONTROL Last name]**.

   ![](assets/delivery_content_56.png)

Seus campos de personalização agora devem estar perfeitamente inseridos no conteúdo dinâmico escolhido.

### Visualizar emails {#previewing-emails}

A visualização permite verificar se os campos de personalização e o conteúdo dinâmico estão configurados corretamente antes de enviar o **[!UICONTROL Proofs]**. Durante a pré-visualização, você pode selecionar perfis de teste diferentes correspondentes aos públicos alvos de email.

Sem perfis de teste, o email que aparece por padrão é:

![](assets/delivery_content_45.png)

O e-mail não tem campos de personalização no slogan e a imagem padrão é usada.

O primeiro perfil de teste corresponde a um cliente com idade entre 18 e 27 anos. Ao selecionar esse perfil, o seguinte email é exibido:

![](assets/delivery_content_46.png)

O campo de personalização que corresponde à expressão de 18 a 27 anos, especificamente o nome do perfil, está configurado corretamente e a imagem também foi alterada de acordo com o perfil.

O segundo perfil corresponde a um cliente com mais de 27 anos e gera o seguinte email:

![](assets/delivery_content_47.png)

A imagem mudou graças ao conteúdo dinâmico, e o slogan que aparece é o slogan mais formal definido para esse público-alvo.

**Tópicos relacionados:**

* [Criação de públicos-alvo](../../audiences/using/creating-audiences.md)
* [Preparação do envio](../../sending/using/preparing-the-send.md)

