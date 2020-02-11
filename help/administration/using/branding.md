---
title: Identidade visual
description: Descubra todas as ferramentas disponíveis para gerenciar suas identidades de marca.
page-status-flag: never-activated
uuid: d66ac5a2-2ae1-4870-b48e-7f276744ffdd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: cbb1dcec-3bc6-4013-87fa-27d0e5d32bf8
context-tags: branding,overview;branding,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 54612511de07edc3e6f3eea34ef095c26b35f4af

---


# Identidade visual{#branding}

## Sobre a identidade da marca {#about-brand-identity}

Toda empresa tem diretrizes visuais e técnicas de marca. Com o Adobe Campaign, você pode definir um conjunto de especificações para apresentar uma marca consistente aos seus clientes, de logotipos a aspectos técnicos, como remetente de email, URL ou domínios.

Os administradores técnicos podem definir uma ou várias marcas para centralizar os parâmetros que afetam a identidade de uma marca. Isso inclui o logotipo da marca, o domínio do URL de acesso das páginas iniciais ou as configurações de rastreamento de mensagens. Com o Adobe Campaign, você pode criar essas marcas e vinculá-las a mensagens ou páginas de aterrissagem. Essa configuração é gerenciada em modelos.

## Configuração e uso de marcas {#configuring-and-using-brands}

O princípio principal de configurar e usar marcas é:

1. Criar e configurar a marca - esta operação requer permissões específicas e é realizada pelo administrador técnico do Adobe Campaign.
1. Crie um ou vários modelos de entrega e página de aterrissagem para esta marca. Consulte a seção [Criação de um modelo](../../start/using/marketing-activity-templates.md) .
1. Crie mensagens e páginas iniciais com base neste modelo. Consulte as seções [Criar um email](../../channels/using/creating-an-email.md) e [Criar uma página](../../channels/using/designing-a-landing-page.md) de aterrissagem.

>[!IMPORTANT]
>
>As marcas não podem ser criadas ou modificadas pelos usuários finais: essas operações devem ser executadas pelo administrador técnico do Adobe Campaign. Para receber qualquer solicitação, entre em contato com o Atendimento ao cliente da Adobe. A multimarca não pode ser usada no contexto de mensagens transacionais. Para obter mais informações, consulte Mensagens [transacionais e marcas](../../channels/using/about-transactional-messaging.md#permissions-and-branding).

As marcas podem ser encontradas no **[!UICONTROL Administration > Instance settings > Brand configuration]** menu.

Por padrão, uma marca recém-criada fica visível somente para usuários atribuídos com os direitos correspondentes pelo administrador.

Uma **marca** é definida pelas seguintes características:

* Uma **identidade**, que define e personaliza sua marca. Esta seção contém os seguintes campos:

   ![](assets/branding_01.png)

   * **Etiqueta** visível na interface
   * **Nome da marca**
   * **URL** do site e rótulo **do** site da marca
   * **Logotipo da marca**

* **[!UICONTROL Header parameters of sent emails]** que personaliza o que os destinatários de suas campanhas verão. Esta seção contém os seguintes campos:

   ![](assets/branding_04_header.png)

   * **Remetente (endereço de email)** com o endereço de email da marca.
   * **Remetente (nome)** com o nome da marca.
   * **Responder (endereço de email)** com o endereço de email ao qual o cliente pode responder.
   * **Responder (nome)** com o nome da marca.
   * **Erro (endereço de email)** com o endereço de email a ser usado em caso de erro.
   >[!IMPORTANT]
   >
   >Depois de atualizar os parâmetros de cabeçalho dos e-mails, se o nome e o endereço de e-mail do remetente não tiverem sido alterados no e-mail criado a partir do modelo, verifique as configurações avançadas do modelo.

* **Os servidores expostos na Internet** definem os servidores usados para rastreamento, mas também para acesso à página de aterrissagem. Esta seção contém os seguintes campos:

   ![](assets/configure_branding_04.png)

   * **URL externo do servidor** de aplicativos usado para hospedar e acessar as diferentes páginas iniciais que você cria.
   * **URL externo do servidor** de rastreamento usado como o URL rastreado durante as entregas.
   * **URL externo do servidor** de página espelhada usado como a página espelhada padrão em suas entregas.
   >[!NOTE]
   >
   >Para exibir a visualização da página inicial e a renderização da página espelhada na interface do usuário da Campanha, os URLs do servidor de aplicativos e do servidor de páginas espelhadas devem estar protegidos. Nesse caso, use https:// em vez de http:// ao configurar esses URLs.

* **[!UICONTROL Tracking URL configuration (Web Analytics)]**, que define a configuração do rastreamento de URLs para sua marca.

   Os parâmetros adicionais que permitem que os links sejam rastreados em sistemas externos, como ferramentas do Web Analytics, como o Adobe Analytics ou o Google Analytics, estão definidos aqui.

   ![](assets/branding_05.png)

## Atribuindo uma marca a um email {#assigning-a-brand-to-an-email}

### Vincular uma marca a um modelo {#linking-a-brand-to-a-template}

Para usar os parâmetros definidos para uma marca, ele deve estar vinculado a um modelo de entrega ou modelo de página inicial. Para fazer isso, é necessário criar ou editar um modelo.

>[!NOTE]
>
>Para obter mais informações sobre como criar um modelo, consulte a seção [Criação de um modelo](../../start/using/marketing-activity-templates.md) .

Depois que o modelo for criado, você poderá vinculá-lo a uma marca. Para fazer isso:

1. Clique no **[!UICONTROL Edit properties]** botão para acessar as propriedades do modelo.

   ![](assets/branding_04.png)

1. Use a lista suspensa para selecionar a marca que deseja vincular ao modelo.

   >[!NOTE]
   >
   >Por padrão, a opção **[!UICONTROL Default brand (branding)]** é selecionada.

   ![](assets/branding_05.png)

   Para ver como a marca selecionada está configurada, clique no **[!UICONTROL Navigate to the detail of the element selected]** ícone.

   ![](assets/branding_06.png)

1. Confirme sua seleção e salve seu modelo.

Seu modelo está vinculado à marca. No editor de email, os elementos como o endereço de **email do remetente** padrão, o nome **do remetente** padrão ou o **logotipo** usarão os dados da marca configurados.

### Caso de uso da marca {#branding-use-case}

Neste exemplo, vamos criar uma nova marca relacionada a viagens, e usá-la em um email.

#### Configurar uma nova marca {#configure-a-new-brand}

>[!IMPORTANT]
>
>A configuração da marca é gerenciada pela Adobe somente porque requer permissões específicas e configurações técnicas.

1. O administrador do Adobe Campaign cria a marca em **[!UICONTROL Administration > Instance settings > Brand configuration]**. Ele acrescenta as **Férias no elemento Trópicos** do menu avançado e configura as **[!UICONTROL ID]** e as **[!UICONTROL Header parameters of sent emails]** da marca.

   ![](assets/branding_07.png)

1. Em seguida, o administrador configura o URL do(s) **Servidor(es) exposto(s) na Internet** para que as páginas iniciais possam ser usadas e, em seguida, os URLs de rastreamento.

   Neste exemplo, a ferramenta **Web Analytics** usada é o **Google Analytics**. O administrador configura o URL de rastreamento da seguinte maneira:

   ![](assets/branding_12.png)

A marca foi criada e configurada corretamente. Agora, ele pode ser usado pelas equipes de marketing.

#### Implementar uma nova marca {#implement-a-new-brand}

Como gerente de entrega, você é responsável pela criação dos modelos de entrega para usar a nova marca. Para isso, siga as etapas abaixo:

1. No menu avançado **[!UICONTROL Resources > Templates > Delivery templates]**, duplique um modelo incorporado para configurar um novo modelo de entrega.

   ![](assets/branding_08.png)

1. Para vincular esse modelo às **Férias na marca Trópicos** , edite as propriedades do modelo e selecione a marca na lista suspensa.

   ![](assets/branding_09.png)

1. Configure este modelo de email para refletir a identidade da marca.
1. Quando o modelo for concluído, você poderá salvá-lo.

   ![](assets/branding_10.png)

   O modelo de entrega agora pode ser usado para criar emails que serão enviados para um público-alvo.

#### Usar a nova marca em uma entrega {#use-the-new-brand-in-a-delivery}

Para criar um email vinculado a uma marca, siga as etapas abaixo:

1. Clique no **[!UICONTROL Create]** botão do **[!UICONTROL Marketing activities]** menu.

   ![](assets/branding_14.png)

1. Selecione a **[!UICONTROL Email]** atividade e escolha o modelo vinculado à nova marca.

   ![](assets/branding_15.png)

1. Seu email já está configurado. Você pode verificar as informações antes de testá-las usando os perfis de teste e enviá-las ao seu público-alvo.

   ![](assets/branding_16.png)

