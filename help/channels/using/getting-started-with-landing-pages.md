---
title: Principais etapas para configurar uma página de aterrissagem
description: Saiba mais sobre as principais etapas para configurar uma página de aterrissagem
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c71c207d724dac914935b3667527a3ce4403dd63

---


# Introdução às páginas de aterrissagem {#getting-started-with-landing-pages}

## Sobre as páginas de aterrissagem {#about-landing-pages}

A campanha vem com páginas de aterrissagem que são formulários da Web que podem ser usados para capturar informações em seus públicos-alvo, oferecer assinaturas para um serviço, exibir dados e aumentar seu banco de dados. As páginas iniciais também podem ser usadas para adquirir ou atualizar perfis existentes.

As páginas iniciais também podem ser usadas para configurar um mecanismo de aceitação dupla, permitindo que você proteja a plataforma de endereços de email errados ou inválidos, ou spambots. For more on this, refer to the [dedicated use case](../../channels/using/setting-up-a-double-opt-in-process.md).

As principais etapas ao configurar as páginas iniciais são as seguintes:

![](assets/lp_steps.png)

Nesta página, você encontrará informações sobre cada uma dessas etapas, bem como referências às documentações dedicadas para obter mais detalhes.

**Tópicos relacionados:**

* [Vídeo Criar um tutorial de página de aterrissagem](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/landing-pages/landing-page-create-and-edit.html)
* [Criar um serviço](../../audiences/using/creating-a-service.md)
* [Configurar um processo de participação dupla](setting-up-a-double-opt-in-process.md)

## Limitações da página inicial{#landing-page-limitations}

A seção abaixo lista as limitações que devem ser observadas antes de iniciar a configuração de páginas iniciais.

**Gravação e atualização de dados**

* As páginas de aterrissagem são limitadas apenas a **[!UICONTROL Profile]** e **[!UICONTROL Subscription]** recursos. O registro pode ser salvo e atualizado de uma assinatura **[!UICONTROL Profile]** ou cancelamento de assinatura para uma **[!UICONTROL Service]**.
Para saber mais sobre a configuração de recursos, consulte [Configuração da estrutura](../../developing/using/configuring-the-resource-s-data-structure.md)de dados do recurso.

>[!CAUTION]
>
>Uma página inicial não pode exibir ou atualizar dados de nenhum outro recurso além **[!UICONTROL Profile]** e **[!UICONTROL Subscription]**.

**Pré-carregamento**

* A página de aterrissagem não pode exibir uma lista de registros automaticamente, não pode listar os serviços aos quais os perfis já se inscreveram. For more information on services, refer to this [page](../../audiences/using/creating-a-service.md).

* A página de aterrissagem com um formulário pré-preenchido (os dados são pré-carregados com a página) só pode ser acessada de um email do Adobe Campaign. Não é possível acessar esse formulário a partir de uma página do site.

**Reconciliação**

* O comportamento de reconciliação é o seguinte: assim que uma correspondência é encontrada, o processo de reconciliação para. Isso significa que a reconciliação só pode ser feita em um registro de perfil e não em vários registros quando houver duplicatas.

Por exemplo, você deseja enviar a seguinte página inicial de aquisição para seus perfis para atualizar seu banco de dados do Campaign com os números de celular dos seus perfis.

![](assets/landing_page_limitation_1.png)

Se um de seus perfis preencher sua página inicial com novas informações, mas já tiver um perfil duplicado, o perfil correspondente com a data de criação mais antiga será atualizado, pois os perfis são priorizados dependendo apenas da data de criação.

Aqui, somente o primeiro perfil foi atualizado, pois era a entrada mais antiga.

![](assets/landing_page_limitation_2.png)

**Teste de páginas de aterrissagem**

* As páginas iniciais funcionam somente em perfis e não em perfis de teste, o que significa que as páginas iniciais não podem ser testadas como parte de uma prova de email.

## Etapa 1 - Configurar o modelo da página inicial {#configure-the-landing-page-template}

Antes de configurar uma página inicial, a primeira etapa é configurar um modelo de página inicial que corresponda às suas necessidades. Quando o modelo estiver pronto, todas as páginas iniciais baseadas nele serão pré-configuradas com os parâmetros desejados.

1. No menu avançado, pelo logotipo do Adobe Campaign, selecione **[!UICONTROL Resources]** / **[!UICONTROL Templates]** / **[!UICONTROL Landing page templates]** e duplique o modelo que deseja usar.
1. Nas propriedades do modelo, especifique todos os parâmetros que suas páginas iniciais devem ter em comum. Por exemplo: a dimensão de definição de metas, os parâmetros de acesso à página para visitantes identificados ou não, ações específicas para a validação do formulário por um visitante, a marca/logotipo a ser usado no conteúdo etc. Para obter mais informações sobre as propriedades das páginas iniciais, consulte [esta seção](../../channels/using/configuring-landing-page.md)
1. Salve suas modificações.

For more on landing page templates, refer to [this section](../../channels/using/getting-started-with-landing-pages.md).

![](assets/lp-steps1.png)

## Etapa 2 - Criar e configurar a página inicial {#create-and-configure-the-landing-page}

No modelo definido na etapa anterior, crie uma nova página inicial em um programa ou campanha.

1. Crie a página inicial com base no modelo desejado.
1. Insira os parâmetros gerais da página inicial (rótulo, descrição etc.).
1. Em seguida, você acessará o painel da página inicial. Edite as propriedades da página inicial, se necessário (consulte [Configuração de uma página](../../channels/using/configuring-landing-page.md)de aterrissagem). Por padrão, as propriedades são as configuradas no modelo de página inicial.
Por motivos de segurança e desempenho da plataforma, recomendamos que você defina uma data de expiração nas propriedades da página inicial. Depois de concluída, a página inicial será automaticamente despublicada na data selecionada. For more on validity parameters, refer to [this section](../../channels/using/testing-publishing-landing-page.md#setting-up-validity-parameters).

   ![](assets/lp-steps3.png)

   >[!NOTE]
   >
   >Suas modificações só são eficazes para a página de aterrissagem que está sendo editada. Se quiser aplicar essas modificações a outras páginas iniciais, você pode executá-las em um modelo dedicado e criar outras páginas iniciais a partir desse modelo.

## Etapa 3 - Design da página de aterrissagem {#design-the-landing-page}

Agora é possível definir o conteúdo da página de aterrissagem. Por padrão, a página inicial contém três páginas que podem ser acessadas por meio de setas de rolagem: a página de conteúdo principal, uma página de confirmação e uma página de erro.

![](assets/lp-steps4.png)

Vários campos são configurados por padrão em cada página. Se necessário, você pode editar suas propriedades e mapeamento.

Você também pode configurar a forma como o botão de confirmação se comportará assim que um perfil clicar nele e personalizar o conteúdo de acordo com suas necessidades (imagem, campos de personalização etc.). Por exemplo, você pode inserir o nome de um perfil na página de confirmação da página de aterrissagem, para agradecer o registro.

Para obter mais informações sobre o design da página de aterrissagem, consulte [esta seção](../../channels/using/designing-a-landing-page.md).

## Etapa 4 - Testar a página de aterrissagem {#test-the-landing-page}

Assim que a página inicial for definida, você poderá simular a forma como ela será executada e se comportará quando ela estiver disponível online.

![](assets/lp-steps5.png)

>[!CAUTION]
>
>Os testes de página inicial só podem ser realizados com perfis, e não com perfis de teste. Quando o formulário for enviado, os dados do perfil selecionado serão atualizados para verdadeiro. Para evitar modificar perfis reais, use um perfil falso do cliente.

Se você estiver satisfeito com o comportamento da página de aterrissagem, poderá publicá-la para disponibilizá-la online.

Para obter mais informações sobre como testar uma página de aterrissagem, consulte [esta seção](../../channels/using/testing-publishing-landing-page.md#testing-the-landing-page-).

## Etapa 5 - Publicar a página inicial {#publish-the-landing-page}

Depois que os testes forem bem-sucedidos, você poderá publicar a página de aterrissagem usando o **[!UICONTROL Publish]** botão da barra de ação no painel. Um bloco de monitoramento mostra a progressão e o status da publicação.

A publicação da página de aterrissagem o torna acessível online. Depois de publicada, você sempre pode atualizá-la: para fazer isso, é necessário republicá-lo após cada modificação. Você também pode cancelar a publicação de uma página de aterrissagem a qualquer momento para que não esteja mais disponível.

![](assets/lp-steps6.png)

Depois de publicada, sua página de aterrissagem está pronta para ser usada. Em seguida, você pode colocar diferentes mecanismos que permitem acessá-lo para adquirir novos perfis em seu banco de dados ou obter informações adicionais sobre perfis existentes.

Para obter mais informações sobre a publicação da página inicial, consulte [esta seção](../../channels/using/testing-publishing-landing-page.md#publishing-a-landing-page).
