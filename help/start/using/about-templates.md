---
title: Sobre os modelos
description: '"Os modelos do Adobe Campaign permitem pré-configurar parâmetros dependendo de suas necessidades: os modelos podem conter uma configuração completa ou parcial da atividade de marketing, para simplificar o uso do Adobe Campaign para usuários finais não técnicos."'
page-status-flag: nunca ativado
uuid: 018534b6-61a3-433e-bb60-49883c8b9386
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: referência
topic-tags: gerenciar modelos
discoiquuid: 95218ebe-5430-42a2-b900-1dadbc92d99
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Sobre os modelos{#about-templates}

## Modelos de atividades de marketing {#marketing-activity-templates}

Quando você cria uma nova atividade de marketing, a primeira tela do assistente solicita que você selecione um tipo ou modelo. Os modelos permitem pré-configurar certos parâmetros de acordo com suas necessidades. O modelo pode conter uma configuração total ou parcial da atividade de marketing. O gerenciamento de modelos é executado pelo administrador funcional.

O usuário final tem uma interface simplificada. Ao criar uma nova atividade de marketing, basta selecionar o modelo que deseja usar. Não há necessidade de se preocupar com configurações técnicas. Isso já foi pré-configurado pelo administrador funcional no modelo.

Por exemplo, no caso de um modelo de email, você pode preencher previamente o conteúdo HTML, o público-alvo e qualquer outro parâmetro da entrega: agendamento, perfis de teste, as propriedades gerais da entrega, os parâmetros avançados etc. Isso permite economizar tempo ao criar uma nova atividade.

![](assets/template_1.png)

Para cada tipo de atividade de marketing, um ou vários modelos prontos para uso estão disponíveis com configuração mínima. Esses modelos predefinidos não podem ser modificados ou excluídos.

Os modelos estão disponíveis para as seguintes atividades de marketing:

* Programas
* Campanhas
* Deliveries de email
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
>A configuração da marca pode ser pré-configurada em um modelo de email ou página de aterrissagem. For more information, refer to the [Branding](../../administration/using/branding.md) section.

## Modelos de conteúdo {#content-templates}

Os modelos de conteúdo HTML podem ser acessados na tela **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** do menu [](../../start/using/interface-description.md#advanced-menu)Avançado. A partir daí, você pode gerenciar modelos de conteúdo de página inicial, modelos de conteúdo de email e também fragmentos.

![](assets/content_templates_list.png)

Os modelos de conteúdo prontos para uso são somente leitura. Para editar um deles, é necessário primeiro duplicar o modelo desejado.

Você pode criar novos modelos ou fragmentos e definir seu próprio conteúdo. Para obter mais informações, consulte [Criar um modelo](#creating-a-content-template) de conteúdo e [Criar um fragmento](../../designing/using/using-reusable-content.md#creating-a-content-fragment)de conteúdo.

Ao editar conteúdo com o Designer de email, você também pode criar modelos de conteúdo salvando o conteúdo como fragmento ou modelo. Para obter mais informações, consulte [Salvar conteúdo como modelo](#saving-content-as-template) e [Salvar conteúdo como fragmento](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).

### Modelos de conteúdo de email prontos para uso {#email-content-templates}

Você pode gerenciar o conteúdo HTML oferecido na guia da página inicial do **[!UICONTROL Templates]** Email Designer [](../../designing/using/overview.md) .

Os modelos prontos para uso de conteúdo de e-mail incluem dezoito layouts otimizados para dispositivos móveis e quatro modelos responsivos melhores do setor projetados por artistas Behance. Eles correspondem aos usos mais atuais, como mensagens de boas-vindas ao cliente, boletins informativos e e-mails de reenvolvimento, entre outros. Eles podem ser facilmente personalizados com o conteúdo de suas marcas para facilitar o processo de criação de emails do zero.

![](assets/content_templates.png)

**Tópicos relacionados:**

* Saiba como personalizar modelos de conteúdo [neste vídeo](https://helpx.adobe.com/campaign/kt/acs/using/acs-email_content_templates-feature-video-use.html).
* Para obter mais informações sobre edição de conteúdo, consulte [Sobre design](../../designing/using/overview.md)de conteúdo de email.

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

   Essa miniatura será exibida na guia **[!UICONTROL Templates]** da página inicial do [Email Designer](../../designing/using/overview.md) .

1. Feche a **[!UICONTROL Properties]** guia para retornar à área de trabalho principal.
1. Adicione componentes de estrutura e componentes de conteúdo que podem ser personalizados conforme necessário.
   >[!NOTE]
   >
   > Não é possível inserir campos de personalização ou conteúdo condicional dentro de um modelo de conteúdo.
1. Depois de editado, salve o modelo.

Esse modelo agora pode ser usado em qualquer email criado com o Designer de email. Selecione-o na **[!UICONTROL Templates]** guia da página inicial do [Email Designer](../../designing/using/overview.md) .

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

1. Para usar seu novo modelo, selecione-o na **[!UICONTROL Templates]** guia da página inicial do [Email Designer](../../designing/using/overview.md) .

   ![](assets/content_template_new.png)

