---
title: Sobre modelos
seo-title: Sobre modelos
description: Sobre modelos
seo-description: '" Os modelos do Adobe Campaign permitem pré-configurar parâmetros, dependendo de suas necessidades: os modelos podem conter uma configuração completa ou parcial da atividade de marketing, a fim de simplificar o uso do Adobe Campaign para usuários finais não técnicos ".'
page-status-flag: nunca ativado
uuid: 018534 b 6-61 a 3-433 e-bb 60-49883 c 8 b 9386
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: gerenciando modelos
discoiquuid: 95218 ebe -5430-42 a 2-b 900-1 dadbbc 92 d 99
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 816c580d952848ac760c9a98c06f54bf260f3554

---


# Sobre modelos{#about-templates}

## Modelos de atividade de marketing {#marketing-activity-templates}

Quando você cria uma nova atividade de marketing, a primeira tela do assistente solicita que você selecione um tipo ou modelo. Os modelos permitem pré-configurar determinados parâmetros de acordo com suas necessidades. O modelo pode conter uma configuração completa ou parcial da atividade de marketing. O gerenciamento de modelo é realizado pelo administrador funcional.

O usuário final tem uma interface simplificada. Ao criar uma nova atividade de marketing, basta selecionar o modelo que você gostaria de usar. Não há necessidade de se preocupar com nenhuma configuração técnica. Isso já foi configurado previamente pelo administrador funcional no modelo.

Por exemplo, no caso de um modelo de email, você pode pré-preencher o conteúdo HTML, o público-alvo e qualquer outro parâmetro de sua entrega: agendamento, perfis de teste, propriedades gerais da entrega, os parâmetros avançados etc. Isso permite economizar tempo ao criar uma nova atividade.

![](assets/template_1.png)

Para cada tipo de atividade de marketing, um ou vários modelos prontos para uso estão disponíveis com configuração mínima. Esses modelos prontos para uso não podem ser modificados ou excluídos.

Os modelos estão disponíveis para as seguintes atividades de marketing:

* Programas
* Campanhas
* Entregas de email
* Entregas SMS
* Notificações por push
* Páginas de aterrissagem
* Fluxos de trabalho
* Serviços
* Importar
* Mensagens transacionais

Esses modelos são gerenciados na tela **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** .

>[!NOTE]
>
>A configuração da marca pode ser pré-configurada em um modelo de e-mail ou página de aterrissagem. Para obter mais informações, consulte a [seção Marca](../../administration/using/branding.md) .

## Modelos de conteúdo {#content-templates}

Os modelos de conteúdo HTML podem ser acessados na tela **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** do menu [Avançado](../../start/using/interface-description.md#advanced-menu). Nele, é possível gerenciar modelos de conteúdo da página inicial, modelos de conteúdo de email e também fragmentos.

![](assets/content_templates_list.png)

Os modelos de conteúdo predefinidos são somente leitura. Para editar um deles, primeiro duplique o modelo desejado.

É possível criar novos modelos ou fragmentos e definir seu próprio conteúdo. Para saber mais sobre isso, consulte [Criar um modelo de conteúdo](../../start/using/about-templates.md#creating-a-content-template) e [Criar um fragmento do conteúdo](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment).

Ao editar conteúdo com o Designer de email, você também pode criar modelos de conteúdo salvando seu conteúdo como um fragmento ou como um modelo. Para obter mais informações sobre isso, consulte [Salvar conteúdo como modelo](../../start/using/about-templates.md#saving-content-as-template) e [Salvar conteúdo como fragmento](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment).

### Modelos de conteúdo de email prontos {#email-content-templates}

Você pode gerenciar o conteúdo HTML que é oferecido na **[!UICONTROL Templates]** guia da página [inicial do Designer](../../designing/using/about-email-content-design.md#about-the-email-designer) de email.

Os modelos de conteúdo de email predefinidos incluem dezoito layouts otimizados para dispositivos móveis e quatro modelos responsivos melhores de classe projetados pelos artistas do Behance. Elas correspondem às utilizações mais atuais, como mensagens de boas-vindas do cliente, informativos e emails de reenvolvimento, entre outras. Eles podem ser facilmente personalizados com o conteúdo de suas marcas para facilitar o processo de desenvolvimento de emails do zero.

![](assets/content_templates.png)

**Tópicos relacionados:**

* Saiba como personalizar modelos de conteúdo [neste vídeo](https://helpx.adobe.com/campaign/kt/acs/using/acs-email_content_templates-feature-video-use.html).
* Para obter mais informações sobre a edição de conteúdo, consulte [Sobre o design de conteúdo de email](../../designing/using/about-email-content-design.md).

### Criação de um modelo de conteúdo {#creating-a-content-template}

Você pode criar seus próprios modelos de conteúdo para usá-los quantas vezes forem necessárias.

O exemplo a seguir mostra como criar um modelo de conteúdo de email.

1. Vá **[!UICONTROL Resources]** para &gt; **[!UICONTROL Content templates & fragments]** e clique **[!UICONTROL Create]** em.
1. Clique no rótulo do email para acessar **[!UICONTROL Properties]** a guia do Designer de email.
1. Especifique um rótulo reconhecível e selecione os seguintes parâmetros para poder usar este modelo em emails:

   * Selecione **[!UICONTROL Shared]** ou **[!UICONTROL Delivery]** na lista **[!UICONTROL Content type]** suspensa.
   * Selecione **[!UICONTROL Template]** na lista **[!UICONTROL HTML type]** suspensa.
   ![](assets/email_designer_create-template.png)

1. Se necessário, você pode definir uma imagem que será usada como miniatura para o modelo. Selecione-o na **[!UICONTROL Thumbnail]** guia das propriedades do modelo.

   ![](assets/email_designer_create-template_thumbnail.png)

   Essa miniatura será exibida na **[!UICONTROL Templates]** guia da página [inicial do Designer](../../designing/using/about-email-content-design.md#about-the-email-designer) de email.

1. Feche a **[!UICONTROL Properties]** guia para retornar à área de trabalho principal.
1. Adicione componentes de estrutura e componentes de conteúdo que você pode personalizar, conforme necessário.
   >[!NOTE]
   >
   > Não é possível inserir campos de personalização ou conteúdo condicional dentro de um modelo de conteúdo.
1. Depois de editado, salve o modelo.

Esse modelo agora pode ser usado em qualquer email criado com o Designer de email. Selecione-o na **[!UICONTROL Templates]** guia da página [inicial do Designer](../../designing/using/about-email-content-design.md#about-the-email-designer) de email.

![](assets/content_template_new.png)

### Salvar conteúdo como modelo {#saving-content-as-template}

Ao editar um email com o Designer de email, você pode salvar diretamente o conteúdo desse email como um modelo.

<!--[!CAUTION]
>
>You cannot save as template a structure containing personalization fields or dynamic content.-->

1. Selecione **[!UICONTROL Save as template]** na barra de ferramentas principal do Designer de email.

   ![](assets/email_designer_save-as-template.png)

1. Adicione um rótulo e uma descrição, se necessário, e clique **[!UICONTROL Save]** em.

   ![](assets/email_designer_save-as-template_creation.png)

1. Para encontrar o modelo recém-criado, vá **[!UICONTROL Resources]** para &gt; **[!UICONTROL Content templates & fragments]**.

1. Para usar o novo modelo, selecione-o na **[!UICONTROL Templates]** guia da página [inicial do Designer](../../designing/using/about-email-content-design.md#about-the-email-designer) de email.

   ![](assets/content_template_new.png)

