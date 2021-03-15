---
solution: Campaign Standard
product: campaign
title: Introdução ao Email Designer
description: Comece a criar conteúdo de email com o Designer de email.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Design de email
role: Profissional
level: Iniciante
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 6%

---

# Introdução ao Email Designer {#quick-start}

O Designer de email fornece quatro maneiras de criar emails.

Você pode criar um email [começando no Designer de email](#without-existing-content):

1. Você pode **criar um email a partir de uma tela em branco** adicionando facilmente componentes de estrutura e conteúdo e personalize seu conteúdo para enviar uma delivery rapidamente. Você também pode gerenciar totalmente os elementos de estilo. Para obter mais informações, [comece rapidamente](#from-scratch-email) ou consulte a [documentação completa](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

1. Você pode **criar um email a partir de um modelo predefinido** selecionando um modelo e criando seu novo conteúdo de email a partir daqui. [Saiba mais](#building-content-from-an-out-of-the-box-template)

Você também pode criar um email [com conteúdo existente](#with-existing-content):

1. Você pode **converter um conteúdo HTML existente** (criado externamente ou no editor herdado). [Saiba mais](#converting-an-html-content)
1. Você pode **importar um conteúdo HTML existente** imediatamente no modo de compatibilidade. [Saiba mais](#compatibility-mode)

| Sem conteúdo | Com conteúdo |
|---|---|
| [Criar um email do zero](#from-scratch-email) | [Conversão de um conteúdo HTML existente](#converting-an-html-content) |
| [Criação de conteúdo a partir de um template pronto para uso](#building-content-from-an-out-of-the-box-template) | [Importação de um HTML existente](#compatibility-mode) |

## Criar emails com o editor {#without-existing-content}

>[!NOTE]
>
>Em ambas as estratégias de criação, é fundamental preencher a linha de assunto antes de enviar seu email. Saiba como [Adicionar uma linha de assunto](#add-a-subject-line).

### Criar um email do zero {#from-scratch-email}

Você pode criar um email facilmente, adicionar componentes e personalizar seu conteúdo para enviar um delivery rapidamente. Você pode adaptar as opções de estilo ao seu conteúdo, se necessário. Para obter mais informações sobre gerenciamento de configurações de estilo e atributos em linha, consulte [Edição de estilos de email](../../designing/using/styles.md).

1. Criar um email.
1. Fechar página inicial.

### Adicionar uma linha de assunto {#add-a-subject-line}

As linhas de assunto são obrigatórias ao enviar um email. Para obter mais informações, consulte [Definição da linha de assunto de um email](../../designing/using/subject-line.md).

1. Acesse a guia **[!UICONTROL Properties]** da página inicial do Designer de email (acessível pelo ícone inicial) e preencha a seção **[!UICONTROL Subject]**.

![](assets/subject-line-quick-start.png)

### Adicionar componentes de estrutura {#add-structure-components}

Os componentes da estrutura definirão o layout do seu email. Para obter mais informações, consulte [Definição da estrutura de um email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

Nos componentes da Estrutura, arraste e solte os componentes do layout que deseja usar.

>[!NOTE]
>
>Você pode selecionar diferentes layouts de conteúdo que serão adicionados ao seu email.

![](assets/structure-components-quick-start.png)

### Adicionar componentes de conteúdo {#add-content-components}

Você pode adicionar vários componentes de conteúdo ao seu email, como imagem, texto e botões. Para obter mais informações, consulte [Componentes de conteúdo](../../designing/using/designing-from-scratch.md#about-content-components).

* **Imagem**

   1. Em **Componentes de conteúdo**, arraste e solte a imagem em um dos componentes da estrutura.
   1. Clique em **Procurar**.
   1. Selecione o arquivo de imagem do computador.

   ![](assets/browse-image-quick-start.png)

* **Texto com personalização**

   1. Em **Componentes de conteúdo**, arraste e solte o texto em um dos componentes da estrutura.
   1. Clique no componente e insira o texto.
   1. Para adicionar um campo de personalização, clique em **Insert personalization field** na barra de ferramentas.
   1. Selecione o campo necessário, como Nome.

   ![](assets/edit-text-quick-start.png)

* **HTML**

   1. Em **Componentes de conteúdo**, arraste e solte o HTML em um dos componentes da estrutura.
   1. Clique em **Mostrar o código-fonte**.
   1. Insira seu conteúdo HTML.
   1. Clique em **Save**.

   ![](assets/html-component-source-code.png)

   Se você estiver familiarizado com HTML, poderá copiar e colar o código HTML do rodapé original usando o componente de conteúdo **[!UICONTROL Html]** . Para obter mais informações, consulte [Sobre componentes de conteúdo](../../designing/using/designing-from-scratch.md#about-content-components).

   ![](assets/des_loading_compatible_fragment_9.png)

### Estilo do seu componente de email

É possível ajustar o estilo do email, por exemplo, alterando o preenchimento de um componente. Para obter mais informações sobre gerenciamento de configurações de estilo e atributos em linha, consulte [Edição de estilos de email](../../designing/using/styles.md).

1. Clique em seu **Componente de texto**.
1. À direita, na paleta, vá para **Preenchimento**.
1. Clique no ícone de bloqueio para interromper a sincronização entre os parâmetros superior e inferior ou direita e esquerda.
1. Ajuste **Preenchimento** conforme necessário.
1. Clique em **Save**.

![](assets/padding-quick-start.png)

Agora você pode salvar e enviar seu email.

### Criar conteúdo de um modelo pronto para uso {#building-content-from-an-out-of-the-box-template}

Você pode criar um email a partir de templates prontos para uso, como mensagens de boas-vindas do cliente, informativos e emails de reengajamento e personalizá-los.

1. Crie um email e abra seu conteúdo. Para obter mais informações, consulte [Criação de email](../../channels/using/creating-an-email.md).
1. Clique no ícone inicial para acessar a página inicial **[!UICONTROL Email Designer]**.
1. Clique na guia **[!UICONTROL Templates]**.
1. Escolha um template HTML pronto para uso.
Os diferentes templates apresentam várias combinações de vários tipos de elementos. Por exemplo, os modelos &quot;Pele&quot; têm margens, enquanto os modelos &quot;Astro&quot; não têm. Para obter mais informações, consulte [Modelos de conteúdo](../../designing/using/using-reusable-content.md#content-templates).
1. Acesse a guia **[!UICONTROL Properties]** da página inicial do Designer de email (acessível pelo ícone inicial) e preencha a seção **[!UICONTROL Subject]**.
1. É possível combinar esses elementos para criar várias variantes de email. Por exemplo, você pode duplicar uma seção de email selecionando um componente de estrutura e clicando em **[!UICONTROL Duplicate]** na barra de ferramentas contextual.
1. Você pode mover os elementos ao redor usando a seta azul à esquerda para arrastar um componente de estrutura abaixo ou acima de outro. Para obter mais informações, consulte [Edição da estrutura do email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Você também pode mover componentes para alterar a organização de cada elemento de estrutura. Para obter mais informações, consulte [Inclusão de fragmentos e componentes](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Modifique o conteúdo de cada elemento de acordo com suas necessidades: imagens, texto, links.
1. Adapte as opções de estilo ao seu conteúdo, se necessário. Para obter mais informações, consulte [Edição de estilos de email](../../designing/using/styles.md).

## Uso de um conteúdo de email existente {#with-existing-content}

Se quiser criar uma estrutura de modelos e fragmentos modulares que podem ser combinados para reutilização em vários emails, considere converter seu HTML de email em um modelo do Designer de email.

### Conversão de conteúdo HTML {#converting-an-html-content}

Esse caso de uso oferece uma maneira rápida de converter emails HTML em componentes do Designer de email. Para obter mais informações sobre este tópico, consulte [Conversão de conteúdo HTML](../../designing/using/using-existing-content.md#converting-an-html-content).

>[!CAUTION]
>
>Esta seção é para usuários familiarizados com o código HTML.

>[!NOTE]
>
>Como o modo de compatibilidade, um componente HTML é editável com opções limitadas: só é possível executar edição no local.


### Importação e edição de um email HTML {#compatibility-mode}

Ao fazer upload de um conteúdo, ele deve conter uma marcação específica para ser totalmente compatível e editável com o editor WYSIWYG do Designer de email.

Para obter mais informações sobre como converter um email existente em um email compatível com o Designer de email, consulte [esta seção](../../designing/using/using-existing-content.md#compatibility-mode).
