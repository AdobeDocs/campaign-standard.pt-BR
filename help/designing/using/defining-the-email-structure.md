---
title: Definição da estrutura de email
seo-title: Definição da estrutura de email
description: Definição da estrutura de email
seo-description: Descobrir como usar o Designer de email no Campaign para formar seus e-mails e preenchê-los com componentes de conteúdo.
page-status-flag: nunca ativado
uuid: 6 ec 63 f 65-1425-4 c 28-84 e 8-b 09574458 db 3
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 207 fdf 6 d -165 a -41 af-ad 53-ba 97 d 3403 b 62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7de6436bbd4f1cc5032e13414f7337f637bf608a

---


# Defining the email structure{#defining-the-email-structure}

## Editing the email structure {#editing-the-email-structure}

O Designer de email permite que você defina facilmente a estrutura do seu e-mail. Ao adicionar e mover elementos estruturais com ações simples de arrastar e soltar, você pode projetar a forma de seu email em segundos.

Para editar a estrutura de um e-mail:

1. Abra um conteúdo existente ou crie um novo conteúdo de email.
1. Access the **[!UICONTROL Structure components]** by selecting the **+** icon on the left.

   ![](assets/email_designer_structure.png)

1. Arraste e solte os componentes da estrutura necessários para formar seu e-mail.

   ![](assets/email_designer_structure_components.png)

   Uma linha azul materializa a localização exata dos componentes da estrutura antes de soltar. É possível soltá-la acima, entre ou abaixo de qualquer outro componente, mas não dentro.

   >[!NOTE]
   >
   >Depois de colocado no email, não será possível mover nem remover seus componentes, a menos que já exista um componente de conteúdo ou um fragmento colocado dentro.

1. Vários componentes de estrutura compostos de uma ou mais colunas estão disponíveis.

   Select the **[!UICONTROL n:n column]** component to define the number of columns of your choice (between 3 and 10). Você também pode definir a largura de cada coluna movendo as setas na parte inferior de cada coluna.

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >Cada tamanho de coluna não pode ultrapassar 10% da largura total do componente de estrutura. Não é possível remover uma coluna que não esteja vazia.

Quando a estrutura estiver definida, você poderá adicionar fragmentos de conteúdo e componentes ao seu e-mail.

## Adding fragments and content components {#adding-fragments-and-content-components}

Com o Designer de email, depois de adicionar componentes de estrutura ao seu e-mail, você pode definir seu conteúdo. Para fazer isso, você precisa adicionar elementos dentro de cada componente de estrutura.

There are two categories of content elements that you can use: **fragments** and **content components**.

### About fragments {#about-fragments}

Um fragmento é um componente reutilizável que pode ser referenciado em um ou mais emails.

Para aproveitar o melhor uso de fragmentos no Designer de email:

* Crie seus próprios fragmentos. See [Creating a content fragment](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment) and [Saving content as a fragment](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment).
* Use-os quantas vezes forem necessárias em seus e-mails. See [Inserting elements into an email](../../designing/using/defining-the-email-structure.md#inserting-elements-into-an-email).
* Ao editar um fragmento, as alterações são sincronizadas: são propagados automaticamente para todos os emails (desde que ainda não tenham sido preparados ou enviados) contendo esse fragmento.

Quando adicionados a um e-mail, os fragmentos são bloqueados por padrão. Se quiser modificar um fragmento para um e-mail específico, é possível quebrar a sincronização com o fragmento original desbloqueando-o no e-mail onde ele é usado. As alterações não serão mais sincronizadas.

Para desbloquear um fragmento dentro de um e-mail, selecione-o e clique no ícone de bloqueio na barra de ferramentas contextual.

![](assets/des_unlocking_fragment.png)

Esse fragmento se torna um componente independente que não é mais vinculado ao fragmento original. Ele pode ser editado como qualquer outro componente de conteúdo. See [About content components](../../designing/using/defining-the-email-structure.md#about-content-components).

### About content components {#about-content-components}

Os componentes de conteúdo são componentes brutos e vazios que podem ser editados uma vez em um e-mail.

Você pode adicionar quantos componentes de conteúdo quiser em um componente de estrutura. Também é possível movê-los dentro do componente de estrutura ou para outro componente de estrutura.

Esta é a lista de componentes disponíveis no Email do Designer:

* **[!UICONTROL Button]**

   If you need to use multiple buttons, rather than editing each button from scratch, you can duplicate the **[!UICONTROL Button]** component using the contextual toolbar.

   Também é possível salvar botões em fragmentos que podem ser reutilizados. For more on this, see [Creating a content fragment](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment) and [Saving content as a fragment](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment).

* **[!UICONTROL Carousel]**

   For more on this, see [Using the carousel component](../../designing/using/defining-the-email-structure.md#using-the-carousel-component).

* **[!UICONTROL Divider]**
* **[!UICONTROL Html]**

   Use este componente para copiar as diferentes partes do HTML existente. Isso permite criar componentes HTML modulares gratuitos.

   >[!NOTE]
   >
   >Um componente HTML gratuito é editável com opções limitadas. If all styles are not inlined, make sure to add the proper CSS in the **head** section of the HTML code, otherwise the email will not be responsive. Use the **[!UICONTROL Preview]** button to test the responsiveness of your content (see [Previewing messages](../../sending/using/previewing-messages.md)).

* **[!UICONTROL Image]**
* **[!UICONTROL Social]**
* **[!UICONTROL Text]**

#### Using the carousel component {#using-the-carousel-component}

1. Drag and drop the **[!UICONTROL Carousel]** component inside a structure component.
1. Navegue para selecionar imagens do seu computador.

   ![](assets/des_carousel_browse.png)

1. From the **[!UICONTROL Settings]** pane, set the number of thumbnails that you want in the carousel.
1. Selecione uma imagem de fallback de seu computador.

   ![](assets/des_carousel_fallback.png)

   O componente carrossel não é compatível com todos os programas de email. Carregue um fallback para exibir uma imagem em vez de quando o carrossel não for suportado no e-mail.

   >[!NOTE]
   >
   >O componente de carrossel é compatível com as seguintes plataformas de email: Apple Mail 7, Apple Mail 8, Outlook 2011 para Mac, Outlook 2016 para Mac, Mozilla Thunderbird, ipad e ipad mini iOS, iphone iOS, Android, AOL (Chrome, Firefox e Safari).

1. Select **[!UICONTROL Fallback view]** to display the fallback image in the Email Designer.

### Inserting elements into an email {#inserting-elements-into-an-email}

Para definir o conteúdo do seu e-mail, você pode adicionar elementos de conteúdo aos componentes de estrutura inseridos anteriormente. See [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

1. Access the content elements by selecting the **+** icon on the left. Select [Fragments](../../designing/using/defining-the-email-structure.md#about-fragments) or [Content components](../../designing/using/defining-the-email-structure.md#about-content-components).
1. Se você já conhece o rótulo ou parte do rótulo do fragmento que deseja adicionar, você pode pesquisá-lo.

   ![](assets/email_designer_fragmentsearch.png)

1. Arraste e solte um fragmento ou componente de conteúdo da paleta até um componente de estrutura do email.

   ![](assets/email_designer_addfragment.png)

   Depois que um elemento é adicionado ao email, ele pode ser movido dentro do componente de estrutura ou para outro componente de estrutura no email.

   ![](assets/email_designer_movefragment.png)

1. Edite o elemento para corresponder às necessidades exatas desse email. Você pode adicionar texto, links, imagens e assim por diante.

   >[!NOTE]
   >
   >Os fragmentos são bloqueados por padrão quando adicionados a um e-mail. É possível quebrar a sincronização com o fragmento original se quiser modificar o fragmento para um e-mail específico ou fazer sua alteração diretamente no fragmento. See [About fragments](../../designing/using/defining-the-email-structure.md#about-fragments).

1. Repita esse procedimento para todos os elementos que você precisa adicionar ao seu e-mail.
1. Salve seu email.

Agora que a estrutura de email é preenchida, é possível editar o estilo de cada elemento de conteúdo. See [Editing an element](../../designing/using/editing-email-styles.md#editing-an-element).

>[!NOTE]
>
>Se um fragmento for modificado, as alterações serão propagadas automaticamente nos emails onde são usadas. For more on this, see [About fragments](../../designing/using/defining-the-email-structure.md#about-fragments).

### Creating a content fragment {#creating-a-content-fragment}

Você pode criar seus próprios fragmentos de conteúdo para usá-los conforme necessário em um ou mais emails.

1. Go to **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** and click **[!UICONTROL Create]**.
1. Click the email label to access the **[!UICONTROL Properties]** tab of the Email Designer.
1. Especifique um rótulo reconhecível e selecione os seguintes parâmetros para encontrar o fragmento mais tarde em novos e-mails:

   * Because fragments are only compatible with emails, select **[!UICONTROL Delivery]** from the **[!UICONTROL Content type]** drop-down list.
   * Select **[!UICONTROL Fragment]** from the **[!UICONTROL HTML type]** drop-down list to be able to use this content as a fragment in your emails.
   ![](assets/email_designer_createfragment.png)

1. Se necessário, é possível definir uma imagem que será usada como miniatura do fragmento. Select it from the **[!UICONTROL Thumbnail]** tab of the template properties.

   ![](assets/email_designer_createfragment_thumbnail.png)

   Essa miniatura será exibida ao lado do rótulo do fragmento ao editar um e-mail.

1. Salve as alterações para retornar à área de trabalho principal.
1. Adicione um componente de estrutura e um componente de conteúdo que você pode personalizar conforme necessário.
1. Depois de editado, salve o fragmento.

O fragmento agora pode ser usado em qualquer email criado com o Designer de email. It appears under the **[!UICONTROL Fragments]** section of the Palette.

>[!NOTE]
>
>Não é possível inserir campos de personalização dentro de um fragmento, a menos que seja usado em um e-mail. Para fazer isso, você precisa desbloquear esse fragmento. See [About fragments](../../designing/using/defining-the-email-structure.md#about-fragments).

### Saving content as a fragment {#saving-content-as-a-fragment}

Ao editar um email com o Designer de email, você pode salvar diretamente parte desse email como um fragmento.

>[!CAUTION]
>
>Não é possível salvar como fragmento uma estrutura contendo campos de personalização, conteúdo dinâmico ou outro fragmento.

1. When editing an email in the Email Designer, select **[!UICONTROL Save as fragment]** from the main toolbar.

   ![](assets/email_designer_save-as-fragment.png)

1. No espaço de trabalho, selecione as estruturas que compõem o fragmento.

   ![](assets/email_designer_save-as-fragment_select.png)

   >[!NOTE]
   >
   >Apenas é possível selecionar estruturas adjacentes entre si.

1. Click **[!UICONTROL Create]**.

1. Add a label and a description if needed, then click **[!UICONTROL Save]**.

   ![](assets/email_designer_save-as-fragment_popup.png)

1. To find the fragment that you just created, go to **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]**.

   ![](assets/email_designer_save-as-fragment_list.png)

1. Para usar o novo fragmento, abra qualquer conteúdo de email e selecione-o na lista de fragmentos.

![](assets/email_designer_save-as-fragment_in-new-email.png)

<!--You need to copy-paste the HTML corresponding to the section that you want to save into a new fragment.

>[!NOTE]
>
>To do this, you need to be familiar with HTML code.

To save as a fragment some email content that you created, follow the steps below.

1. When editing an email in the Email Designer, select **[!UICONTROL Edit]** > **[!UICONTROL HTML]** to open the HTML version of that email.
1. Select and copy the HTML corresponding to the part that you want to save.
1. Go to **[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]** and click **[!UICONTROL Create]**.
1. Click the email label to access the **[!UICONTROL Properties]** tab of the Email Designer and select **[!UICONTROL Fragment]** from the **[!UICONTROL HTML type]** drop-down list.
1. Select **[!UICONTROL Edit]** > **[!UICONTROL HTML]** to open the HTML version of the fragment.
1. Paste the HTML that you copied where appropriate.
1. Switch back to the **[!UICONTROL Edit]** view to check the result and save the new fragment.-->

