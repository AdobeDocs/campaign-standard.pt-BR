---
title: 'Criação e uso de conteúdo reutilizável '
description: Comece a criar conteúdo de email reutilizável com o Designer de email.
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
source-git-commit: d0d5b19ad272c406f1081ed364193c7fb793de07

---

# Criação e uso de conteúdo reutilizável {#using-reusable-content}

Saiba mais sobre como dominar a edição de conteúdo de email. Com o Email Designer, você pode criar modelos e fragmentos com seu próprio conteúdo predefinido e reutilizá-los nas entregas a seguir.

## Criar e-mails usando modelos {#designing-templates}

>[!NOTE]
>
> No Adobe Campaign Standard, você pode criar diferentes tipos de modelos que podem ser acessados no menu **Recursos** &gt; **Modelos** . Os modelos usados no Designer de email são modelos de conteúdo. Para obter mais informações, consulte [Sobre modelos](../../start/using/about-templates.md).

### Modelos de conteúdo {#content-templates}

Você pode gerenciar o conteúdo HTML que será oferecido na **[!UICONTROL Templates]** guia da página inicial do [Email Designer](../../designing/using/overview.md) . Os diferentes modelos apresentam várias combinações de vários tipos de elementos. Por exemplo, os modelos 'Difusão' têm margens, enquanto os modelos 'Astro' não têm. Para obter mais informações, consulte Modelos [de](#content-templates)conteúdo.

![](assets/template_content.png)

Para saber como criar um email a partir de um modelo predefinido, consulte Designer [de](../../designing/using/quick-start.md#building-content-from-an-out-of-the-box-template)email.

### Creating a content template {#creating-a-content-template}

Você pode criar seus próprios modelos de conteúdo para usá-los quantas vezes forem necessárias.

O exemplo a seguir mostra como criar um modelo de conteúdo de email.

1. Vá até **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** e clique em **[!UICONTROL Create]**.
1. Clique no rótulo do email para acessar a **[!UICONTROL Properties]** guia do Designer de email.
1. Especifique um rótulo reconhecível e selecione os seguintes parâmetros para poder usar este modelo em emails:

   * Selecione **[!UICONTROL Shared]** ou **[!UICONTROL Delivery]** na lista **[!UICONTROL Content type]** suspensa.
   * Selecione **[!UICONTROL Template]** na lista **[!UICONTROL HTML type]** suspensa.
   ![](assets/email_designer_create-template.png)

1. Se necessário, é possível definir uma imagem que será usada como miniatura do modelo. Selecione-o na **[!UICONTROL Thumbnail]** guia das propriedades do modelo.

   ![](assets/email_designer_create-template_thumbnail.png)

   Essa miniatura será exibida na guia **[!UICONTROL Templates]** da página inicial do [Email Designer](../../designing/using/overview.md#about-the-email-designer) .

1. Feche a **[!UICONTROL Properties]** guia para retornar à área de trabalho principal.
1. Adicione componentes de estrutura e componentes de conteúdo que podem ser personalizados conforme necessário.
   >[!NOTE]
   >
   > Não é possível inserir campos de personalização ou conteúdo condicional dentro de um modelo de conteúdo.
1. Depois de editado, salve o modelo.

Esse modelo agora pode ser usado em qualquer email criado com o Designer de email. Selecione-o na **[!UICONTROL Templates]** guia da página inicial do [Email Designer](../../designing/using/overview.md#about-the-email-designer) .

![](assets/content_template_new.png)

### Salvar conteúdo como modelo {#saving-content-as-template}

Ao editar um email com o Designer de email, você pode salvar diretamente o conteúdo desse email como um modelo.

<!--[!CAUTION]
>
>You cannot save as template a structure containing personalization fields or dynamic content.-->

1. Selecione **[!UICONTROL Save as template]** na barra de ferramentas principal do Email Designer.

   ![](assets/email_designer_save-as-template.png)

1. Adicione um rótulo e uma descrição, se necessário, e clique em **[!UICONTROL Save]**.

   ![](assets/email_designer_save-as-template_creation.png)

1. Para encontrar o modelo que você acabou de criar, vá para **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]**.

1. Para usar seu novo modelo, selecione-o na **[!UICONTROL Templates]** guia da página inicial do [Email Designer](../../designing/using/overview.md#about-the-email-designer) .

   ![](assets/content_template_new.png)

### Criação de um modelo com fragmentos e componentes {#template-fragments-components}

Agora você pode criar um modelo de email com o Designer de email. Use os componentes de conteúdo para refletir as diferentes seções do seu email e ajustar as configurações para torná-las o mais próximas possível do seu boletim informativo original. Por fim, insira os fragmentos que você acabou de criar.

1. Usando o Designer de email, crie um modelo. Para obter mais informações, consulte Modelos [de](#content-templates)conteúdo.
1. Insira vários componentes de estrutura no modelo - correspondentes ao cabeçalho, rodapé e corpo do email. Para obter mais informações sobre como adicionar componentes de estrutura, consulte [Editar a estrutura de email com o Designer](../../designing/using/designing-from-scratch.md#defining-the-email-structure)de email.
1. Insira quantos componentes de conteúdo forem necessários para criar o corpo de seu boletim informativo. Este será o conteúdo editável do seu email que você atualizará todos os meses.

   ![](assets/des_loading_compatible_fragment_5.png)

   Se você estiver familiarizado com o código HTML, a Adobe recomenda aproveitar **[!UICONTROL Html]** os componentes onde você pode copiar e colar os elementos mais complexos do email original. Use outros componentes, como **[!UICONTROL Button]**, **[!UICONTROL Image]** ou **[!UICONTROL Text]** para o restante do conteúdo. Para obter mais informações, consulte [Sobre componentes](../../designing/using/designing-from-scratch.md#about-content-components)de conteúdo.

   >[!NOTE]
   >
   >O uso do **[!UICONTROL Html]** componente resulta na criação de componentes editáveis com opções limitadas. Certifique-se de saber como lidar com o código HTML antes de selecionar esse componente.

1. Ajuste os componentes de conteúdo para corresponder ao seu email original o máximo possível.

   ![](assets/des_loading_compatible_fragment_6.png)

   Para obter mais informações sobre como gerenciar configurações de estilo e atributos incorporados, consulte [Edição de estilos](../../designing/using/styles.md)de email.

1. Insira os dois fragmentos (cabeçalho e rodapé) criados anteriormente nos componentes de estrutura desejados.

   ![](assets/des_loading_compatible_fragment_10.png)

1. Salve o modelo.

Agora você pode gerenciar totalmente esse modelo no Email Designer para criar e atualizar o boletim informativo que você enviará mensalmente para seus destinatários.

Para usá-lo, crie um email e selecione o modelo de conteúdo que você acabou de criar.

**Tópico** relacionado:

* [Criação de um de email](../../channels/using/creating-an-email.md)
* [Vídeo de introdução ao Email Designer](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=por_br)
* [Criar um conteúdo de email do zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## Sobre fragmentos {#about-fragments}

 Um fragmento é um componente reutilizável que pode ser referenciado em um ou mais emails.
Eles podem ser encontrados na interface em **Recursos** &gt; Fragmentos e modelos **** de conteúdo.

Para usar melhor os fragmentos no Designer de email:

* Crie seus próprios fragmentos. Consulte [Criar um fragmento](#creating-a-content-fragment) de conteúdo e [Salvar conteúdo como um fragmento](#saving-content-as-a-fragment).
* Use-os quantas vezes forem necessárias em seus emails. Consulte [Inserir elementos em um email](#inserting-elements-into-an-email).
* Ao editar um fragmento, as alterações são sincronizadas: são propagados automaticamente para todos os emails (desde que ainda não tenham sido preparados ou enviados) que contenham esse fragmento.

Quando adicionados a um email, os fragmentos são bloqueados por padrão. Se quiser modificar um fragmento para um email específico, você pode interromper a sincronização com o fragmento original desbloqueando-o no email em que ele é usado. As alterações não serão mais sincronizadas.

Para desbloquear um fragmento dentro de um email, selecione-o e clique no ícone de cadeado na barra de ferramentas contextual.

![](assets/des_unlocking_fragment.png)

Esse fragmento se torna um componente independente que não está mais vinculado ao fragmento original. Em seguida, ele pode ser editado como qualquer outro componente de conteúdo. Consulte [Sobre componentes](../../designing/using/designing-from-scratch.md#about-content-components)de conteúdo.

### Inserir fragmentos em um email {#inserting-elements-into-an-email}

Para definir o conteúdo de seu email, é possível adicionar elementos de conteúdo nos componentes de estrutura que você colocou anteriormente. Consulte [Editar a estrutura](../../designing/using/designing-from-scratch.md#defining-the-email-structure)de email.

1. Acesse os elementos de conteúdo selecionando o ícone **+** à esquerda. Selecione [Fragmentos](#about-fragments) ou componentes [](../../designing/using/designing-from-scratch.md#about-content-components)de conteúdo.
1. Se você já souber o rótulo ou parte do rótulo do fragmento que deseja adicionar, poderá pesquisá-lo.

   ![](assets/email_designer_fragmentsearch.png)

1. Arraste e solte um fragmento ou componente de conteúdo da paleta para um componente de estrutura do email.

   ![](assets/email_designer_addfragment.png)

   Depois que um elemento é adicionado ao email, ele pode ser movido dentro do componente de estrutura ou para outro componente de estrutura no email.

   ![](assets/email_designer_movefragment.png)

1. Edite o elemento para corresponder às necessidades exatas deste email. Você pode adicionar texto, links, imagens e assim por diante.

   >[!NOTE]
   >
   >Os fragmentos são bloqueados por padrão quando adicionados a um email. Você pode interromper a sincronização com o fragmento original se quiser modificar o fragmento para um email específico ou fazer a alteração diretamente no fragmento. Consulte [Sobre fragmentos](#about-fragments).

1. Repita este procedimento para todos os elementos que você precisa adicionar ao seu email.
1. Salve seu email.

Agora que sua estrutura de email está preenchida, você pode editar o estilo de cada elemento de conteúdo. Consulte [Edição de um elemento](../../designing/using/styles.md#editing-an-element).

>[!NOTE]
>
>Se um fragmento for modificado, as alterações serão propagadas automaticamente nos e-mails em que são usadas. Para obter mais informações, consulte [Sobre fragmentos](#about-fragments).

### Criação de um fragmento de conteúdo {#creating-a-content-fragment}

Você pode criar seus próprios fragmentos de conteúdo para usá-los conforme necessário em um ou mais emails.

1. Vá até **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** e clique em **[!UICONTROL Create]**.
1. Clique no rótulo do email para acessar a **[!UICONTROL Properties]** guia do Designer de email.
1. Especifique um rótulo reconhecível e selecione os seguintes parâmetros para localizar o fragmento ao editar o conteúdo de email:

   * Como os fragmentos são compatíveis apenas com emails, selecione **[!UICONTROL Delivery]** na lista **[!UICONTROL Content type]** suspensa.
   * Selecione **[!UICONTROL Fragment]** na lista **[!UICONTROL HTML type]** suspensa para poder usar esse conteúdo como um fragmento.
   ![](assets/email_designer_createfragment.png)

1. Se necessário, é possível definir uma imagem que será usada como miniatura do fragmento. Selecione-o na **[!UICONTROL Thumbnail]** guia das propriedades do modelo.

   ![](assets/email_designer_createfragment_thumbnail.png)

   Essa miniatura será exibida ao lado do rótulo do fragmento ao editar um email.

1. Feche a **[!UICONTROL Properties]** guia para retornar à área de trabalho principal.
1. Adicione componentes de estrutura e componentes de conteúdo que podem ser personalizados conforme necessário.

   >[!CAUTION]
   >
   >Os fragmentos não podem incluir campos de personalização, conteúdo dinâmico ou outro fragmento.
   >
   >Evite salvar como um conteúdo de fragmento com componentes de estrutura vazios. Depois que o fragmento &gt;for inserido, eles não poderão ser editados.
   >
   >A exibição [](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view) móvel não está disponível em fragmentos.

1. Depois de editado, salve o fragmento.

Esse fragmento agora pode ser usado em qualquer email criado com o Designer de email. É exibido sob a **[!UICONTROL Fragments]** seção Paleta.

>[!NOTE]
>
>Não é possível inserir campos de personalização dentro de um fragmento, a menos que sejam usados em um email e desbloqueados. Consulte [Sobre fragmentos](#about-fragments).

### Salvar conteúdo como um fragmento {#saving-content-as-a-fragment}

Ao editar um email com o Designer de email, você pode salvar diretamente parte desse email como um fragmento.

* Não é possível salvar como fragmento uma estrutura que contém campos de personalização, conteúdo dinâmico ou outro fragmento.
* Você só pode selecionar estruturas adjacentes.
<!-- - You cannot select an empty structure.-->

1. Ao editar um email no Designer de email, selecione **[!UICONTROL Save as fragment]** na barra de ferramentas principal.

   ![](assets/email_designer_save-as-fragment.png)

1. No espaço de trabalho, selecione as estruturas que irão compor o fragmento.

   ![](assets/email_designer_save-as-fragment_select.png)

   >[!NOTE]
   >
   >Certifique-se de selecionar estruturas adjacentes e que não incluem campos de personalização, conteúdo dinâmico ou outro fragmento.
   <!--You cannot select an empty structure.-->

1. Click **[!UICONTROL Create]**.

1. Adicione um rótulo e uma descrição, se necessário, e clique em **[!UICONTROL Save]**.

   ![](assets/email_designer_save-as-fragment_popup.png)

1. Para localizar o fragmento que você acabou de criar, vá para **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]**.

   ![](assets/email_designer_save-as-fragment_list.png)

1. Para usar o novo fragmento, abra qualquer conteúdo de email e selecione-o na lista de fragmentos.

![](assets/email_designer_save-as-fragment_in-new-email.png)

>[!NOTE]
>A exibição [](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view) móvel não está disponível em fragmentos. Se quiser editar uma exibição móvel de email, faça-a antes de salvar seu conteúdo como um fragmento.

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

## Criação de cabeçalhos e rodapés reutilizáveis usando fragmentos {#header-footer-fragments}

Usando o Designer de email, crie um fragmento para cada seção reutilizável. Neste exemplo, você criará dois fragmentos: um para o cabeçalho e outro para o rodapé. Em seguida, é possível copiar as partes relevantes do conteúdo existente nesses fragmentos.

Para fazer isso, siga as etapas abaixo:

1. No Adobe Campaign, acesse **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** e crie um fragmento para o cabeçalho. Para obter mais informações, consulte [Criação de um fragmento](#creating-a-content-fragment)de conteúdo.
1. Adicione quantos componentes de estrutura forem necessários ao fragmento.

![](assets/des_loading_compatible_fragment_1.png)

1. Insira componentes de imagem e texto na sua estrutura.

![](assets/des_loading_compatible_fragment_2.png)

1. Carregue a imagem correspondente, insira o texto e ajuste as configurações.

![](assets/des_loading_compatible_fragment_3.png)

1. Salve o fragmento.
1. Proceda de forma semelhante para criar seu rodapé e salvá-lo.

![](assets/des_loading_compatible_fragment_4.png)

Seus fragmentos estão prontos para serem usados em um modelo.
