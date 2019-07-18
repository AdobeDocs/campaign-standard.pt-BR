---
title: Marca
seo-title: Marca
description: Marca
seo-description: Descubra todas as ferramentas disponíveis para gerenciar suas identidades de marca.
page-status-flag: nunca ativado
uuid: d 66 ac 5 a 2-2 ae 1-4870-b 48 e -7 f 276744 ffdd
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: cbb 1 dcec -3 bc 6-4013-87 fa -27 d 0 e 5 d 32 bf 8
context-tags: marca, visão geral; marca, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 866567d63dd2798eb56d42d4e163e5484c9b4d68

---


# Branding{#branding}

## About brand identity {#about-brand-identity}

Todas as empresas possuem diretrizes visuais e técnicas de marca. Com o Adobe Campaign, você pode definir um conjunto de especificações para apresentar uma marca consistente aos seus clientes, desde logotipos a aspectos técnicos, como remetente de email, URL ou domínios.

Os administradores técnicos podem definir uma ou várias marcas para inserir centralmente os parâmetros que afetam a identidade de uma marca. Isso inclui o logotipo da marca, o domínio do URL de acesso das páginas iniciais ou as configurações de rastreamento de mensagens. Com o Adobe Campaign, você pode criar essas marcas e vinculá-las a mensagens ou páginas de aterrissagem. Essa configuração é gerenciada em modelos.

## Configuring and using brands {#configuring-and-using-brands}

O principal princípio de configuração e uso de marcas é:

1. Crie e configure a marca - esta operação requer permissões específicas e é executada pelo administrador técnico do Adobe Campaign.
1. Crie um ou vários modelos de entrega e página de aterrissagem para essa marca. Refer to the [Creating a template](../../start/using/about-templates.md) section.
1. Crie mensagens e páginas de aterrissagem com base neste modelo. Refer to the [Creating an email](../../channels/using/creating-an-email.md) and [Creating a landing page](../../channels/using/designing-a-landing-page.md) sections.

>[!CAUTION]
>
>As marcas não podem ser criadas ou modificadas por usuários finais: essas operações devem ser executadas pelo administrador técnico do Adobe Campaign. Para qualquer solicitação, entre em contato com o Atendimento ao cliente da Adobe. A multi-marca não pode ser usada no contexto de mensagens transacionais. For more on this, see [Transactional messages and branding](../../channels/using/about-transactional-messaging.md#permissions-and-branding).

Brands can be found in the **[!UICONTROL Administration > Instance settings > Brand configuration]** menu.

Por padrão, uma marca recém-criada fica visível somente para usuários atribuídos com os direitos correspondentes pelo administrador.

A **Brand** is defined by the following characteristics:

* **Uma Identidade**, que define e personaliza sua marca. Esta seção contém os seguintes campos:

   ![](assets/branding_01.png)

   * **Etiqueta** visível na interface
   * **Nome da marca**
   * **URL do site** e **rótulo do site** da marca
   * **Logotipo da marca**

* **[!UICONTROL Header parameters of sent emails]** que personaliza o que os destinatários de suas campanhas verão. Esta seção contém os seguintes campos:

   ![](assets/branding_04_header.png)

   * **Remetente (endereço de email)** com o endereço de email da marca.
   * **Remetente (nome)** com o nome da marca.
   * **Responder (endereço de email)** com o endereço de email para o qual o cliente pode responder.
   * **Responder (nome)** com o nome da marca.
   * **Erro (endereço de email)** com o endereço de email para usar no caso de um erro.
   >[!CAUTION]
   >
   >Depois de atualizar os parâmetros de cabeçalho dos emails, se o nome e endereço de e-mail do remetente não tiver sido alterado no e-mail criado a partir do modelo, verifique as configurações avançadas do modelo.

* **Os servidores expostos na Internet** definem os servidores usados para rastreamento, mas também para acesso à página inicial. Esta seção contém os seguintes campos:

   ![](assets/configure_branding_04.png)

   * **URL externo do servidor de aplicativos** usado para hospedar e acessar as diferentes páginas de aterrissagem criadas.
   * **URL externo do servidor de rastreamento** usado como URL rastreado durante as entregas.
   * **URL externo do servidor de página espelho** usado como a página de espelho padrão em suas entregas.

* **[!UICONTROL Tracking URL configuration (Web Analytics)]**, que define a configuração do rastreamento de urls para sua marca.

   Os parâmetros adicionais que permitem que os links sejam rastreados em sistemas externos, como ferramentas do Web Analytics, como o Adobe Analytics ou o Google Analytics, estão definidos aqui.

   ![](assets/branding_05.png)

## Assigning a brand to an email {#assigning-a-brand-to-an-email}

### Linking a brand to a template {#linking-a-brand-to-a-template}

Para usar os parâmetros definidos para uma marca, ela deve estar vinculada a um modelo de entrega ou modelo de página de aterrissagem. Para fazer isso, você precisa criar ou editar um modelo.

>[!NOTE]
>
>For more information about creating a template, refer to the [Creating a template](../../start/using/about-templates.md) section.

Depois que o modelo é criado, você pode vinculá-lo a uma marca. Para fazer isso:

1. Click the **[!UICONTROL Edit properties]** button to access the template properties.

   ![](assets/branding_04.png)

1. Use a lista suspensa para selecionar a marca que deseja vincular ao modelo.

   >[!NOTE]
   >
   >By default, the **[!UICONTROL Default brand (branding)]** is selected.

   ![](assets/branding_05.png)

   To view how the brand selected is configured, click the **[!UICONTROL Navigate to the detail of the element selected]** icon.

   ![](assets/branding_06.png)

1. Confirme sua seleção e salve seu modelo.

Seu modelo está vinculado à marca. In the email editor, the elements such as the **Email address of default sender**, the **Default sender name**, or the **Logo** will use the configured brand data.

### Branding use case {#branding-use-case}

Neste exemplo, vamos criar uma nova marca relacionada à viagem e usá-la em um email.

#### Configure a new brand {#configure-a-new-brand}

>[!CAUTION]
>
>A configuração da marca é gerenciada pela Adobe somente pois requer permissões e configurações técnicas específicas.

1. The Adobe Campaign administrator creates the brand in **[!UICONTROL Administration > Instance settings > Brand configuration]**. He adds the **Vacations in the Tropics** element from the advanced menu and configures the **[!UICONTROL ID]** and the **[!UICONTROL Header parameters of sent emails]** of the brand.

   ![](assets/branding_07.png)

1. The administrator then configures the URL of the **Server(s) exposed on the Internet** so that landing pages can be used, then the tracking URLs.

   In this example, the **Web Analytics** tool used is **Google Analytics**. O administrador configura o URL de rastreamento da seguinte maneira:

   ![](assets/branding_12.png)

A marca é criada e configurada corretamente. Agora pode ser usado pelas equipes de marketing.

#### Implement a new brand {#implement-a-new-brand}

Como gerente de entrega, você é responsável pela criação dos modelos de entrega para usar a nova marca. Para isso, siga as etapas abaixo:

1. In the advanced menu **[!UICONTROL Resources > Templates > Delivery templates]**, duplicate a built-in template to configure a new delivery template.

   ![](assets/branding_08.png)

1. To link this template to the **Vacations in the Tropics** brand, edit the template properties and select the brand from the drop-down list.

   ![](assets/branding_09.png)

1. Configure este modelo de e-mail para refletir a identidade da marca.
1. Assim que o modelo for concluído, você poderá salvá-lo.

   ![](assets/branding_10.png)

   O modelo de entrega agora pode ser usado para criar e-mails que serão enviados para um público-alvo.

#### Use the new brand in a delivery {#use-the-new-brand-in-a-delivery}

Para criar um e-mail vinculado a uma marca, siga as etapas abaixo:

1. Click the **[!UICONTROL Create]** button from the **[!UICONTROL Marketing activities]** menu.

   ![](assets/branding_14.png)

1. Select the **[!UICONTROL Email]** activity, then choose the template linked to the new brand.

   ![](assets/branding_15.png)

1. Seu e-mail já está configurado. Você pode verificar as informações antes de testá-las usando os perfis de teste e enviá-las ao seu público-alvo.

   ![](assets/branding_16.png)

