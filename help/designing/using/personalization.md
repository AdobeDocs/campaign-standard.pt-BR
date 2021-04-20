---
solution: Campaign Standard
product: campaign
title: Personalização de conteúdo de email
description: Saiba como personalizar um email no Designer de email.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '2578'
ht-degree: 5%

---


# Personalização de conteúdo de email {#personalization}

O conteúdo e a exibição de mensagens entregues pelo Adobe Campaign podem ser personalizados de várias maneiras diferentes. Essas maneiras podem ser combinadas de acordo com critérios dependendo dos perfis. Em geral, o Adobe Campaign permite:

* Inserir campos de personalização dinâmicos. Consulte [Inserção de um campo de personalização](#inserting-a-personalization-field).
* Inserir blocos de personalização predefinidos. Consulte [Adição de um bloco de conteúdo](#adding-a-content-block).
* Personalize o remetente de um email. Consulte [Personalização do remetente](#personalizing-the-sender).
* Personalize o assunto de um email. Consulte [Personalizar a linha de assunto de um email](../../designing/using/subject-line.md#subject-line).
* Criar conteúdo condicional. Consulte [Definição de conteúdo dinâmico em um email](#defining-dynamic-content-in-an-email).

## Personalização do remetente {#personalizing-the-sender}

Para definir o nome do remetente que aparecerá no cabeçalho das mensagens enviadas, vá para a guia **[!UICONTROL Properties]** da página inicial do Designer de email (acessível pelo ícone inicial). Para obter mais informações, consulte [Definição do remetente de um email](../../designing/using/subject-line.md#email-sender).

Você pode alterar o nome do remetente clicando no bloco **Nome do remetente**. O campo se torna editável e você pode inserir o nome que deseja usar.

Esse campo pode ser personalizado. Para fazer isso, é possível adicionar campos de personalização, blocos de conteúdo e conteúdo dinâmico clicando nos ícones abaixo do nome do remetente.

>[!NOTE]
>
>Os parâmetros do cabeçalho não devem ficar vazios. O endereço do remetente é obrigatório para possibilitar o envio de um email (padrão RFC). O Adobe Campaign verifica a sintaxe dos endereços de email inseridos.

## Personalização de URLs{#personalizing-urls}

O Adobe Campaign permite personalizar um ou vários URLs na mensagem, adicionando campos de personalização, blocos de conteúdo ou conteúdo dinâmico a eles. Para fazer isso:

1. Insira uma URL externa e especifique seus parâmetros. Consulte [Inserir um link](../../designing/using/links.md#inserting-a-link).
1. Se não for exibido, clique no lápis ao lado do URL selecionado no painel Configurações para acessar as opções de personalização.
1. Adicione os campos de personalização, blocos de conteúdo e conteúdo dinâmico que deseja usar.

   ![](assets/des_personalize_links.png)

1. Salve as alterações.

>[!NOTE]
>
>A personalização de URLs não pode ser aplicada ao nome de domínio, nem à extensão de URL. Uma mensagem de erro será exibida durante a análise da mensagem se a personalização estiver incorreta. Ao selecionar um bloco de conteúdo, você não tem permissão para selecionar elementos como **Link to mirror page**. Esse tipo de bloco é proibido dentro de um link.

## Inserção de um campo de personalização{#inserting-a-personalization-field}

O Adobe Campaign permite inserir um campo do banco de dados na página, como o nome do perfil.

>[!NOTE]
>
>As imagens abaixo mostram como inserir um campo de personalização usando o [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md) para um email.

Para adicionar um campo de personalização ao conteúdo:

1. Clique dentro de um bloco de texto, clique no ícone **[!UICONTROL Personalize]** na barra de ferramentas contextual e selecione **[!UICONTROL Insert personalization field]**. Para obter mais informações sobre a interface do Designer de email, consulte [esta seção](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface).

   ![](assets/email_perso_field_1.png)

1. Selecione o campo que deseja inserir no conteúdo da página.

   ![](assets/email_perso_field_2.png)

1. Clique em **[!UICONTROL Confirm]**.

O nome do campo aparece no editor e é realçado.

![](assets/email_perso_field_3.png)

Quando a personalização for gerada (ao visualizar e preparar o email, por exemplo), esse campo será substituído pelo valor correspondente ao perfil direcionado.

>[!NOTE]
>
>Se o email for criado de um workflow, os dados adicionais calculados no workflow também estarão disponíveis nos campos de personalização. Para obter mais informações sobre como adicionar dados adicionais de um workflow, consulte a seção [Enriquecimento de dados](../../automating/using/about-targeting-activities.md#enriching-data) .

## Inclusão de um bloco de conteúdo{#adding-a-content-block}

O Adobe Campaign oferece uma lista de blocos de conteúdo pré-configurados. Esses blocos de conteúdo são dinâmicos, personalizados e têm uma renderização específica. Por exemplo, você pode adicionar uma saudação ou um link à mirror page.

>[!NOTE]
>
>As imagens abaixo mostram como inserir um bloco de conteúdo usando o [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md) para um email.

Para adicionar um bloco de conteúdo:

1. Clique dentro de um bloco de texto, clique no ícone **[!UICONTROL Personalize]** na barra de ferramentas contextual e selecione **[!UICONTROL Insert content block]**. Para obter mais informações sobre a interface do Designer de email, consulte [esta seção](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface).

   ![](assets/email_content_block_1.png)

1. Selecione o bloco de conteúdo que deseja inserir. Os blocos disponíveis variam de acordo com o contexto (email ou landing page).

   ![](assets/email_content_block_2.png)

1. Clique em **[!UICONTROL Save]**.

O nome do bloco de conteúdo aparece no editor e é realçado em amarelo. Ele se adaptará automaticamente ao perfil quando a personalização for gerada.

![](assets/email_content_block_3.png)

Os blocos de conteúdo prontos para uso são:

* **[!UICONTROL Database URL in emails (EmailUrlBase)]**: Este bloco de conteúdo só pode ser usado em um  **delivery**.
* **[!UICONTROL Mirror page URL (MirrorPageUrl)]**: Este bloco de conteúdo só pode ser usado em um  **delivery**.
* **[!UICONTROL Link to mirror page (MirrorPage)]**: Este bloco de conteúdo só pode ser usado em um  **delivery**.
* **[!UICONTROL Greetings (Greetings)]**
* **[!UICONTROL Unsubscription link (UnsubscriptionLink)]**: Este bloco de conteúdo só pode ser usado em um  **delivery**.
* **[!UICONTROL Social network sharing links (LandingPageViralLinks)]**: Esse bloco de conteúdo só pode ser usado em uma  **landing page**.
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

Você pode definir novos blocos de conteúdo que serão inseridos em uma mensagem ou página de aterrissagem.

Para criar um bloco de conteúdo, siga estas etapas:

1. Clique em **[!UICONTROL Resources > Content blocks]** no menu avançado para acessar a lista de blocos de conteúdo.
1. Clique no botão **[!UICONTROL Create]** ou duplique um bloco de conteúdo pré-existente.

   ![](assets/content_bloc_01.png)

1. Insira um rótulo.
1. Selecione o **[!UICONTROL Content type]** do bloco. Há três opções disponíveis:

   * **[!UICONTROL Shared]**: O bloco de conteúdo pode ser usado em um delivery ou uma landing page.
   * **[!UICONTROL Delivery]**: O bloco de conteúdo só pode ser usado em um delivery.
   * **[!UICONTROL Landing page]**: O bloco de conteúdo só pode ser usado em uma landing page.

   ![](assets/content_bloc_02.png)

1. Você pode selecionar um **[!UICONTROL Targeting dimension]**. Para obter mais informações, consulte [Sobre o targeting dimension](#about-targeting-dimension).

   ![](assets/content_bloc_04.png)

1. Você pode selecionar a opção **[!UICONTROL Depends on format]** para definir dois blocos diferentes: um para emails HTML e outro para emails em formato de texto. Duas guias serão exibidas no editor (HTML e Texto) para definir o conteúdo correspondente.

   ![](assets/content_bloc_03.png)

1. Insira o conteúdo do(s) bloco(s) de conteúdo e clique no botão **[!UICONTROL Create]** .

O bloco de conteúdo agora pode ser usado no editor de conteúdo de uma mensagem ou página de aterrissagem.

>[!CAUTION]
>
>Ao editar o conteúdo de um bloco, verifique se não há espaços em branco extras entre o início e o fim de suas instruções *if*. Em HTML, os espaços em branco são exibidos na tela e, portanto, afetarão o layout do conteúdo.

### Sobre o targeting dimension {#about-targeting-dimension}

O targeting dimension permite definir em qual tipo de mensagem você pode usar o bloco de conteúdo. Isso é para evitar o uso de blocos inadequados em uma mensagem, o que pode levar a erros.

Na verdade, ao editar uma mensagem, você só pode selecionar blocos de conteúdo com um targeting dimension que seja compatível com o targeting dimension dessa mensagem.

Por exemplo, o targeting dimension do bloco **[!UICONTROL Unsubscription link]** é **[!UICONTROL Profiles]** porque contém campos de personalização específicos ao recurso **[!UICONTROL Profiles]**. Portanto, você não pode usar um bloco **[!UICONTROL Unsubscription link]** em uma [mensagem transacional de evento](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types), porque o targeting dimension desse tipo de mensagem é **[!UICONTROL Real-time events]**. No entanto, você pode usar o bloco **Unsubscription link** em um [profile transactional message](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types), porque o targeting dimension desse tipo de mensagem é **Profiles**. Finalmente, o bloco **[!UICONTROL Link to mirror page]** não tem um targeting dimension, portanto, você pode usá-lo em qualquer mensagem.

Se deixar esse campo vazio, o bloco de conteúdo será compatível com todas as mensagens, independentemente do targeting dimension. Se você definir um targeting dimension, esse bloco só será compatível com mensagens que tenham o mesmo targeting dimension.

Para saber mais, consulte [Targeting dimensions e recursos](../../automating/using/query.md#targeting-dimensions-and-resources).

**Tópicos relacionados:**

* [Inserção de um campo de personalização](#inserting-a-personalization-field)
* [Inclusão de um bloco de conteúdo](#adding-a-content-block)
* [Definição de conteúdo dinâmico em um email](#defining-dynamic-content-in-an-email)

## Personalização de uma fonte de imagem{#personalizing-an-image-source}

O Adobe Campaign permite personalizar uma ou várias imagens em sua mensagem de acordo com um critério específico ou usar o rastreamento. Isso é feito inserindo campos de personalização, blocos de conteúdo ou conteúdo dinâmico na fonte de imagem. Para fazer isso:

1. Insira uma imagem no conteúdo da mensagem ou selecione uma imagem que já esteja presente.
1. Na paleta propriedades da imagem, marque a opção **[!UICONTROL Enable personalization]**.

   ![](assets/des_personalize_images_1.png)

   O campo **[!UICONTROL Source]** é exibido e a imagem selecionada é mostrada como **personalizada** no editor.

1. Clique no lápis ao lado do botão **[!UICONTROL Source]** do campo para acessar as opções de personalização.
1. Após adicionar a fonte de imagem, adicione os campos de personalização, blocos de conteúdo e conteúdo dinâmico desejados.

   ![](assets/des_personalize_images_2.png)

   >[!NOTE]
   >
   >O nome de domínio (http://mydomain.com) não pode ser personalizado, ele deve ser inserido manualmente. O restante do URL pode ser personalizado. Por exemplo: http://mydomain.com/ `[Gender]` .jpg

1. Confirme as alterações.

## Conteúdo condicional {#conditional-content}

### Definição de uma condição de visibilidade{#defining-a-visibility-condition}

Você pode especificar uma condição de visibilidade em qualquer elemento. Ele só será visível se a condição for respeitada.

Para adicionar uma condição de visibilidade, selecione um bloco e insira a condição a ser respeitada no campo **[!UICONTROL Visibility condition]** de suas configurações.

![](assets/delivery_content_5.png)

Essa opção só está disponível para os seguintes elementos: ENDEREÇO, BLOQUEIO, CENTRO, DIR, DIV, DL, FIELDSET, FORM, H1, H2, H3, H4, H5, H6, NOSCRIPT, OL, P, PRE, UL, TR, TD.

O editor de expressão é apresentado na seção [Advanced expression editing](../../automating/using/editing-queries.md#about-query-editor).

Essas condições adotam a sintaxe da expressão XTK (por exemplo, **context.profile.email !=&#39;&#39;** ou **context.profile.status=&#39;0&#39;**). Por padrão, todos os campos são visíveis.

>[!NOTE]
>
>Uma condição não pode ser definida para um bloco que já contém um subelemento com um conteúdo dinâmico ou um bloco que já compõe um conteúdo dinâmico. Blocos dinâmicos não visíveis, como listas suspensas, não podem ser editados.

### Definição de conteúdo dinâmico em um email{#defining-dynamic-content-in-an-email}

>[!CONTEXTUALHELP]
>id="ac_dynamic_content"
>title="Definição do conteúdo dinâmico"
>abstract="Defina conteúdos diferentes que serão exibidos para alguns perfis somente de acordo com as condições que você definirá."

Em um email, você pode definir conteúdos diferentes que serão exibidos dinamicamente para os recipients, de acordo com as condições definidas pelo editor de expressão. Por exemplo, a partir do mesmo email, você pode garantir que cada perfil receba uma mensagem diferente de acordo com sua faixa etária.

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

1. Defina as condições do filtro. Por exemplo, você deseja que um conteúdo diferente seja exibido para pessoas com idade entre 18 e 25 anos.

   ![](assets/dynamic_content_6.png)

1. Depois que todas as condições forem definidas, defina a ordem de prioridade na qual a condição será aplicada e salve as alterações.

   ![](assets/dynamic_content_7.png)

   O conteúdo será exibido na paleta em ordem de prioridade, de cima para baixo. Para obter mais informações sobre prioridades, consulte [esta seção](#defining-dynamic-content-in-an-email).

1. Carregue uma nova imagem para a variante que você acabou de definir.

   ![](assets/dynamic_content_8.png)

   Os recipients com idade entre 18 e 25 anos verão a nova imagem.

   ![](assets/dynamic_content_10.png)

1. Clique em **[!UICONTROL Add a condition]** para adicionar um novo conteúdo e sua regra vinculada.

   ![](assets/dynamic_content_9.png)

   Por exemplo, você pode adicionar uma imagem diferente a ser exibida para pessoas com idade entre 26 e 35 anos.

1. Continue de forma semelhante para qualquer outro elemento do email que você deseja que seja exibido dinamicamente. Pode ser texto, botão, fragmento etc. Salve as alterações.

>[!CAUTION]
>
>Depois de preparar sua mensagem e antes de enviá-la, teste-a usando uma prova. Se você não fizer isso, alguns erros poderão não ser detectados e o email poderá não ser enviado.

**Tópicos relacionados:**

* [Envio de provas](../../sending/using/sending-proofs.md)
* [Edição de expressão avançada](../../automating/using/editing-queries.md#about-query-editor)

### Ordem de prioridade {#order-of-priority}

No editor de expressão, ao definir um conteúdo dinâmico, a ordem de prioridade é a seguinte.

1. Você define dois conteúdos dinâmicos diferentes com **duas condições diferentes**, por exemplo:

   **Condição 1:** o gênero do perfil é masculino,

   **Condição 2:** o perfil tem entre 20 e 30 anos.

   ![](assets/delivery_content_61.png)

   Alguns perfis no banco de dados correspondem às duas condições, mas apenas um email com um conteúdo dinâmico pode ser enviado.

1. Portanto, é necessário definir a prioridade do conteúdo dinâmico. Uma condição com uma ordem de prioridade **1** (e, portanto, o conteúdo dinâmico correspondente) será enviada a um perfil mesmo se outra condição cuja ordem de prioridade é **2** ou **3** também for atendida por esse perfil.

   ![](assets/delivery_content_62.png)

Você só pode definir uma ordem de prioridade por conteúdo dinâmico.

## Exemplo: Personalização de email{#example-email-personalization}

Neste exemplo, um membro da equipe do serviço de marketing criou um email para informar alguns de seus clientes que há uma oferta especial apenas para eles. O membro da equipe decidiu personalizar o email de acordo com as respectivas idades dos clientes. Os clientes com idade entre 18 e 27 anos receberão um email contendo uma imagem e um slogan diferentes daqueles que os clientes com mais de 27 anos receberão.

O email é criado da seguinte maneira:

* O conteúdo dinâmico é aplicado à imagem e esse conteúdo dinâmico é configurado de acordo com a faixa etária.

   ![](assets/delivery_content_43.png)

   A adição e configuração de conteúdo dinâmico está detalhada na seção [Definição de conteúdo dinâmico em um email](#defining-dynamic-content-in-an-email) .

* Campos de personalização e conteúdo dinâmico são aplicados ao texto. Dependendo da faixa etária do perfil, o email começa com o nome do perfil ou o título e sobrenome do perfil.

   ![](assets/delivery_content_44.png)

   A adição e configuração dos campos de personalização está detalhada na seção [Inserting a personalization field](#inserting-a-personalization-field) .

### Configuração de imagens {#configuring-images}

>[!CONTEXTUALHELP]
>id="ac_dynamic_image"
>title="Gerenciamento de imagens dinâmicas"
>abstract="Personalize seu email com imagens dinâmicas de acordo com as condições que você definirá."

Neste exemplo, o conteúdo dinâmico aplicado às imagens é configurado da seguinte maneira:

**Para atingir o objetivo de 18-27 anos de idade:**

1. Selecione o conteúdo dinâmico na paleta **[!UICONTROL Properties]** e clique no botão **[!UICONTROL Edit]**.

   ![](assets/delivery_content_48.png)

1. Edite o rótulo e selecione o campo **[!UICONTROL Age]** no nó **[!UICONTROL Profile]**.

   ![](assets/delivery_content_49.png)

1. Selecione o operador **Greater than or equal to** e depois insira **18** para criar a expressão **older than 18**.

   ![](assets/delivery_content_50.png)

1. Adicione uma nova condição **[!UICONTROL Age]**.

   Selecione o operador **Less than or equal to** seguido por 27 no campo de valor para criar a expressão **less than 27**.

   ![](assets/delivery_content_51.png)

1. Confirme as alterações.

**Para direcionar perfis com idade igual ou superior a 27 anos:**

1. Selecione o conteúdo dinâmico da paleta e edite-o.
1. Edite o rótulo e selecione o campo **[!UICONTROL Age]** no nó **[!UICONTROL Profile]**.
1. Adicione o operador **Greater than** seguido por 27 no campo de valor para criar a expressão **greater than 27**.

   ![](assets/delivery_content_52.png)

1. Confirme as alterações.

Seu conteúdo dinâmico está configurado corretamente.

### Configurar texto {#configuring-text}

Neste exemplo, o conteúdo dinâmico aplicado aos textos é configurado da seguinte maneira:

**Para direcionar perfis com idade entre 18 e 27 anos:**

1. Selecione o componente de estrutura desejado e adicione um conteúdo dinâmico.
1. Edite o conteúdo dinâmico e configure as expressões de definição de metas. Consulte [Configuração de imagens](#configuring-images).
1. No componente de estrutura, na posição desejada, clique no ícone **[!UICONTROL Personalize]** na barra de ferramentas contextual e selecione **[!UICONTROL Insert personalization field]**.

   ![](assets/delivery_content_53.png)

1. Na lista que aparece, selecione o campo **[!UICONTROL First name]** e confirme.

   ![](assets/delivery_content_54.png)

1. O campo de personalização é então perfeitamente inserido no conteúdo dinâmico selecionado.

**Para direcionar perfis com idade igual ou superior a 27 anos:**

1. Selecione o componente de estrutura desejado e adicione um conteúdo dinâmico.
1. Edite o conteúdo dinâmico e configure as expressões de definição de metas. Consulte [Configuração de imagens](#configuring-images).
1. No componente de estrutura, na posição desejada, clique no ícone **[!UICONTROL Personalize]** na barra de ferramentas contextual e selecione **[!UICONTROL Insert personalization field]**.
1. Selecione **[!UICONTROL Title]** na lista suspensa.
1. Continue de forma semelhante para adicionar o campo **[!UICONTROL Last name]**.

   ![](assets/delivery_content_56.png)

Seus campos de personalização agora devem ser perfeitamente inseridos no conteúdo dinâmico escolhido.

### Pré-visualização de emails {#previewing-emails}

A visualização permite verificar se os campos de personalização e o conteúdo dinâmico estão configurados corretamente antes de enviar o **[!UICONTROL Proofs]**. Durante a visualização, é possível selecionar perfis de teste diferentes correspondentes aos destinos do email.

Sem perfis de teste, o email exibido por padrão é:

![](assets/delivery_content_45.png)

O email não tem campos de personalização no slogan e a imagem padrão é usada.

O primeiro perfil de teste corresponde a um cliente com idade entre 18 e 27 anos. Ao selecionar esse perfil, o seguinte email é exibido:

![](assets/delivery_content_46.png)

O campo de personalização que corresponde à expressão de 18-27 anos, especificamente o nome do perfil, é configurado corretamente e a imagem também foi alterada de acordo com o perfil.

O segundo perfil corresponde a um cliente com mais de 27 anos e gera o seguinte email:

![](assets/delivery_content_47.png)

A imagem mudou graças ao conteúdo dinâmico, e o slogan que aparece é o slogan mais formal definido para esse público alvo.

**Tópicos relacionados:**

* [Criação de públicos-alvo](../../audiences/using/creating-audiences.md)
* [Preparação do envio](../../sending/using/preparing-the-send.md)

