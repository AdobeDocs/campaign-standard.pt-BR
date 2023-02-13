---
title: Criação de emails do zero
description: Descubra como projetar emails do zero no conteúdo de email do Designer de email.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 052d24b7-d3e0-41d7-8b2c-92bd3addb3a2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 7%

---

# Criação de emails do zero {#designing-an-email-content-from-scratch}

Saiba como principal a edição de conteúdo de email. Com o Email Designer, você pode criar emails e modelos começando com ou sem seu próprio conteúdo predefinido.

Estas são as principais etapas para criar e projetar um conteúdo de email do zero usando o Designer de email:

1. Crie um email e abra seu conteúdo.
1. Adicione componentes de estrutura para moldar o email. Consulte [Edição da estrutura do email](#defining-the-email-structure).
1. Insira componentes de conteúdo e fragmentos nos componentes da estrutura. Consulte [Adição de fragmentos e componentes de conteúdo](#defining-the-email-structure).
1. Adicione imagens e edite o texto do email. Consulte [Inserção de imagens](../../designing/using/images.md#inserting-images).
1. Personalize seu email adicionando campos de personalização, links e assim por diante. Consulte [Inserção de um campo de personalização](../../designing/using/personalization.md#inserting-a-personalization-field), [Inserção de um link](../../designing/using/links.md#inserting-a-link) e [Definição de conteúdo dinâmico em um email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).
1. Defina a linha de assunto do email. Consulte [Personalização da linha de assunto de um email](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email).
1. Pré-visualizar seu email.
1. Salve o conteúdo e prossiga com a mensagem depois de garantir que você tenha definido um público-alvo e agendado o envio corretamente.

Você também pode fazer check-out [vídeo de introdução](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true).

>[!NOTE]
>
>Para evitar projetar o conteúdo de email do zero, é possível usar templates de conteúdo prontos para uso. Para obter mais informações, consulte [Modelos de conteúdo](../../designing/using/using-reusable-content.md#content-templates).

## Definir estrutura de email {#defining-the-email-structure}

>[!CONTEXTUALHELP]
>id="ac_structure_components"
>title="Sobre componentes da estrutura"
>abstract="Os componentes da estrutura definem o layout do email."

>[!CONTEXTUALHELP]
>id="ac_edition_columns"
>title="Definição de colunas de email"
>abstract="O Designer de email permite definir facilmente o layout do email definindo a estrutura da coluna."

O Designer de email permite que você defina facilmente a estrutura do seu email. Ao adicionar e mover elementos estruturais com ações simples de arrastar e soltar, você pode projetar a forma do seu email em segundos.

Para editar a estrutura de um email:

1. Abra um conteúdo existente ou crie um novo conteúdo de email.
1. Acesse o **[!UICONTROL Structure components]** selecionando o **+** à esquerda.

   ![](assets/email_designer_structure.png)

1. Arraste e solte os componentes de estrutura que você precisa para moldar seu email.

   ![](assets/email_designer_structure_components.png)

   Uma linha azul materializa o local exato dos componentes da estrutura antes de soltá-la. Você pode soltá-lo acima, entre ou abaixo de qualquer outro componente, mas não dentro.

   >[!NOTE]
   >
   >Observe que a pilha de colunas não é compatível com todos os programas de email. Quando não houver suporte, as colunas não serão empilhadas.
   >
   >Depois de colocado no email, não é possível mover nem remover seus componentes, a menos que já exista um componente de conteúdo ou um fragmento inserido dentro dele.

1. Vários componentes de estrutura compostos de uma ou mais colunas estão disponíveis.

   Selecione o **[!UICONTROL n:n column]** para definir o número de colunas de sua escolha (entre 3 e 10). Você também pode definir a largura de cada coluna, movendo as setas na parte inferior de cada coluna.

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >Cada tamanho de coluna não pode estar abaixo de 10% da largura total do componente de estrutura. Não é possível remover uma coluna que não esteja vazia.

Após definir a estrutura, é possível adicionar fragmentos de conteúdo e componentes ao email.

## Uso de um pré-cabeçalho {#preheader}

>[!CONTEXTUALHELP]
>id="ac_edition_preheader"
>title="Uso de um pré-cabeçalho"
>abstract="O pré-cabeçalho permite configurar um texto de resumo curto que fornecerá uma taxa de abertura mais alta para seu email."

Um precabeçalho é um texto resumido curto que segue a linha de assunto ao visualizar um email de sua caixa de entrada. O pré-cabeçalho oferece uma taxa de abertura mais alta.

Selecione o **[!UICONTROL Preheader]** editar e concluir o conteúdo.

![](assets/email_designer_preheader.png)

Você pode adicionar uma **[!UICONTROL Content block]**, a **[!UICONTROL Dynamic content]** ou **[!UICONTROL Personalization fields]** no conteúdo do pré-cabeçalho.

>[!NOTE]
>
>Observe que o pré-cabeçalho não é compatível com todos os programas de email. Quando este for o caso, o pré-cabeçalho não será exibido.

## Uso de componentes de conteúdo {#about-content-components}

>[!CONTEXTUALHELP]
>id="ac_content_components"
>title="Sobre componentes de conteúdo"
>abstract="Os componentes do conteúdo são espaços reservados vazios para o conteúdo que você pode editar para criar um email."

Os componentes do conteúdo são componentes brutos e vazios que podem ser editados depois de colocados no email.

Você pode adicionar quantos componentes de conteúdo desejar em um componente de estrutura. Também é possível movê-los para dentro do componente de estrutura ou para outro componente de estrutura.

Esta é a lista de componentes disponíveis no Designer de email:

### **[!UICONTROL Button]**

Se você precisar usar vários botões, em vez de editar cada botão do zero, poderá duplicar a variável **[!UICONTROL Button]** componente que usa a barra de ferramentas contextual.

Também é possível salvar botões em fragmentos que podem ser reutilizados. Para obter mais informações, consulte [Criação de um fragmento de conteúdo](../../designing/using/using-reusable-content.md#creating-a-content-fragment) e [Salvar conteúdo como fragmento](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).

Selecionar **[!UICONTROL Fallback view]** para exibir a imagem de fallback no Designer de email.

### **[!UICONTROL Text]**

Use esse componente para inserir texto no seu email. É possível ajustar a cor, o estilo e o tamanho do texto em **[!UICONTROL Component Settings]**.

### **[!UICONTROL Divider]**

Use esse componente para inserir uma linha divisória no seu email. Você pode selecionar a cor, o estilo e o tamanho da linha de quebra em **[!UICONTROL Component Settings]**.

### **[!UICONTROL HTML]**

Use esse componente para copiar e colar as diferentes partes do HTML existente. Isso permite criar componentes HTML modulares gratuitos.

>[!NOTE]
>
>Um componente HTML gratuito pode ser editado com opções limitadas. Se todos os estilos não estiverem embutidos, adicione o CSS correto na **cabeça** do código do HTML, caso contrário, o email não será responsivo. Use o **[!UICONTROL Preview]** para testar a capacidade de resposta do seu conteúdo (consulte [Pré-visualização de mensagens](../../sending/using/previewing-messages.md)).

Para simplesmente tornar um conteúdo externo compatível com o Designer de email, o Adobe recomenda criar uma mensagem do zero e copiar o conteúdo do email existente em fragmentos e componentes.

Quando você tem um conteúdo que não pode ser recriado, é possível copiar e colar o código do HTML do email original usando o **[!UICONTROL Html]** componente de conteúdo. Familiarize-se com o HTML antes de continuar.

>[!NOTE]
>
>O novo conteúdo não será a cópia exata do seu email original, mas as etapas abaixo guiarão você pela criação de uma mensagem que será a mais próxima possível.

**Antes de copiar o conteúdo**

1. No email original, identifique as seções reutilizáveis das seções que serão exclusivas para cada email que você enviará.
1. Salve todas as imagens e ativos que deseja usar.
1. Se você estiver familiarizado com o HTML, divida o conteúdo de HTML original em diferentes partes.

### Vídeo {#video-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_video"
>title="Configurações de vídeo"
>abstract="Use esse componente para inserir um vídeo no seu email. Observe que os vídeos não funcionam em todos os clientes de email. Recomendamos definir uma imagem de fallback."
>additional-url="https://www.emailonacid.com/blog/article/email-development/a_how_to_guide_to_embedding_html5_video_in_email/" text="Informações adicionais"

Insira o componente de vídeo em um componente de estrutura do email e insira o link de vídeo na **[!UICONTROL Component Settings]**.

>[!NOTE]
>
>Observe que o vídeo não é compatível com todos os programas de email. Quando este for o caso, o fallback será exibido.

### Imagem

Use esse componente para inserir uma imagem no seu email.

Insira o componente de imagem em um componente de estrutura e clique em Procurar para carregar um arquivo de imagem de seu computador.

### **[!UICONTROL Social]**

Use esse componente para inserir links às páginas de redes sociais no seu email. Você pode selecionar quais links deseja exibir e o tamanho do ícone em **[!UICONTROL Component Settings]**.

### Carrossel {#carousel-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_carousel"
>title="Configurações do carrossel"
>abstract="Saiba como inserir e configurar um carrossel no seu conteúdo.Observe que o carrossel não funciona em todo o cliente de email e a imagem de fallback será exibida caso não seja compatível."

1. Arraste e solte a **[!UICONTROL Carousel]** componente dentro de um componente de estrutura.
1. Navegue para selecionar imagens de seu computador.

   ![](assets/des_carousel_browse.png)

1. No **[!UICONTROL Settings]** , defina o número de miniaturas que deseja usar no carrossel.
1. Selecione uma imagem de fallback de seu computador.

   ![](assets/des_carousel_fallback.png)

O componente carrossel não é compatível com todos os programas de email. Carregue um fallback para exibir uma imagem, em vez disso, quando o carrossel não for suportado no email.

>[!NOTE]
>
>O componente carrossel é compatível com as seguintes plataformas de email: Apple Mail 7, Apple Mail 8, Outlook 2011 para Mac, Outlook 2016 para Mac, Mozilla Thunderbird, iPad e iPad mini iOS, iPhone iOS, Android, AOL (Chrome, Firefox e Safari).

**Tópicos relacionados**:

- [Criação de um email](../../channels/using/creating-an-email.md)
- [Seleção de um público em uma mensagem](../../audiences/using/selecting-an-audience-in-a-message.md)
- [Agendamento de mensagens](../../sending/using/about-scheduling-messages.md)
- [Visualização de mensagens](../../sending/using/previewing-messages.md)
- [Renderização de email](../../sending/using/email-rendering.md)
