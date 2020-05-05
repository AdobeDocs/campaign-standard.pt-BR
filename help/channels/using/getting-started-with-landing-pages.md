---
title: Principais etapas para configurar uma página de aterrissagem
description: Saiba mais sobre as etapas principais para configurar uma landing page
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
source-git-commit: 0dd69cbad3e05a5a7eb36da80264e6eb6aae0e34

---


# Introdução às páginas de aterrissagem {#getting-started-with-landing-pages}

As principais etapas ao configurar o landing page são as seguintes:

![](assets/lp_steps.png)

Nesta página, você encontrará informações sobre cada uma dessas etapas, bem como referências às documentações dedicadas para obter mais detalhes.

**Tópicos relacionados:**

* [Vídeo de criação de um tutorial](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/landing-pages/landing-page-create-and-edit.html) de landing page
* [Criar um serviço](../../audiences/using/creating-a-service.md)
* [Configurar um processo de participação dupla](setting-up-a-double-opt-in-process.md)

## Limitações de Landing page{#landing-page-limitations}

A seção abaixo lista as limitações que devem ser observadas antes de iniciar a configuração do landing page.

**Gravação e atualização de dados**

* As Landings page são limitadas a **[!UICONTROL Profile]** e somente a **[!UICONTROL Subscription]** recursos. O registro pode ser salvo e atualizado de **[!UICONTROL Profile]** uma subscrição/unsubscription para uma **[!UICONTROL Service]**.
Para saber mais sobre a configuração de recursos, consulte [Configuração da estrutura](../../developing/using/configuring-the-resource-s-data-structure.md)de dados do recurso.

>[!CAUTION]
>
>Uma landing page não pode exibir ou atualizar dados de nenhum outro recurso além **[!UICONTROL Profile]** de e **[!UICONTROL Subscription]**.

**Pré-carregamento**

* A Landing page não pode exibir uma lista de registros automaticamente; não pode lista serviços aos quais os perfis já se inscreveram. For more information on services, refer to this [page](../../audiences/using/creating-a-service.md).

* A Landing page com um formulário pré-preenchido (os dados são pré-carregados com a página) só pode ser acessada de um e-mail de Adobe Campaign. Não é possível acessar esse formulário a partir de uma página do site.

**Reconciliação**

* O comportamento de reconciliação é o seguinte: assim que uma correspondência é encontrada, o processo de reconciliação é interrompido. Isso significa que a reconciliação só pode ser feita em um registro de perfil e não em vários registros quando houver duplicados.

Por exemplo, você deseja enviar a seguinte landing page de aquisição para seus perfis para atualizar seu banco de dados de Campanha com seus números móveis dos perfis.

![](assets/landing_page_limitation_1.png)

Se um de seus perfis preencher sua landing page com novas informações, mas já tiver um perfil duplicado, o perfil correspondente com a data de criação mais antiga será atualizado, pois os perfis são priorizados dependendo apenas da data de criação.

Aqui, apenas o primeiro perfil foi atualizado, pois era a entrada mais antiga.

![](assets/landing_page_limitation_2.png)

**Testando landings page**

* As Landings page funcionam somente em perfis e não em perfis de teste, o que significa que as landings page não podem ser testadas como parte de uma prova de email.

## Etapa 1 - Configurar o modelo de landing page {#configure-the-landing-page-template}

Antes de configurar uma landing page, a primeira etapa é configurar um modelo de landing page que corresponda às suas necessidades. Quando o modelo estiver pronto, todas as landings page baseadas nele serão pré-configuradas com os parâmetros desejados.

1. No menu avançado, pelo logotipo do Adobe Campaign, selecione **[!UICONTROL Resources]** / **[!UICONTROL Templates]** / **[!UICONTROL Landing page templates]** e duplicado o modelo que deseja usar.
1. Nas propriedades do modelo, especifique todos os parâmetros que suas landings page devem ter em comum. Por exemplo: o targeting dimension, os parâmetros de acesso à página para visitantes identificados ou não identificados, ações específicas para a validação do formulário por um visitante, a marca/logotipo a ser usado no conteúdo etc. Para obter mais informações sobre propriedades do landing page, consulte [esta seção](../../channels/using/configuring-landing-page.md)
1. Salve suas modificações.

For more on landing page templates, refer to [this section](../../channels/using/getting-started-with-landing-pages.md).

![](assets/lp-steps1.png)

## Etapa 2 - Criar e configurar a landing page {#create-and-configure-the-landing-page}

No modelo definido na etapa anterior, crie uma nova landing page em um programa ou campanha.

1. Crie a landing page com base no modelo desejado.
1. Insira os parâmetros gerais da landing page (etiqueta, descrição etc.).
1. Você então acessará a painel da landing page. Edite as propriedades da landing page, se necessário (consulte [Configuração de uma landing page](../../channels/using/configuring-landing-page.md)). Por padrão, as propriedades são as configuradas no modelo de landing page.
Por motivos de segurança e desempenho da plataforma, recomendamos que você defina uma data de expiração nas propriedades da landing page. Depois de concluída, a landing page será automaticamente despublicada na data selecionada. For more on validity parameters, refer to [this section](../../channels/using/testing-publishing-landing-page.md#setting-up-validity-parameters).

   ![](assets/lp-steps3.png)

   >[!NOTE]
   >
   >Suas modificações só são eficazes para a landing page que está sendo editada. Se quiser aplicar essas modificações a outras landings page, você pode executá-las em um modelo dedicado e criar outras landings page a partir desse modelo.

## Etapa 3 - Design da landing page {#design-the-landing-page}

Agora é possível definir o conteúdo da landing page. Por padrão, a landing page contém três páginas que podem ser acessadas por meio de setas de rolagem: a página de conteúdo principal, uma página de confirmação e uma página de erro.

![](assets/lp-steps4.png)

Vários campos são configurados por padrão em cada página. Se necessário, você pode editar suas propriedades e mapeamento.

Você também pode configurar a forma como o botão de confirmação se comportará quando um perfil clicar nele e personalizar o conteúdo de acordo com suas necessidades (imagem, campos de personalização etc.). Por exemplo, você pode inserir um nome de perfil na página de confirmação da landing page, para agradecer o registro.

Para obter mais informações sobre o design da landing page, consulte [esta seção](../../channels/using/designing-a-landing-page.md).

## Etapa 4 - Testar a landing page {#test-the-landing-page}

Assim que a landing page for definida, você poderá simular a forma como ela será executada e se comportará quando ela estiver disponível online.

![](assets/lp-steps5.png)

>[!CAUTION]
>
>Os testes de landing page só podem ser realizados com perfis, e não com perfis. Quando o formulário for enviado, os dados do perfil selecionado serão atualizados para verdadeiro. Para evitar modificar perfis reais, use um perfil falso do cliente.

Se você estiver satisfeito com o comportamento da landing page, poderá publicá-la para disponibilizá-la online.

Para obter mais informações sobre como testar uma landing page, consulte [esta seção](../../channels/using/testing-publishing-landing-page.md#testing-the-landing-page-).

## Etapa 5 - Publicar a landing page {#publish-the-landing-page}

Depois que os testes forem bem-sucedidos, você poderá publicar a landing page usando o **[!UICONTROL Publish]** botão da barra de ação no painel. Um bloco de monitoramento mostra a progressão e o status da publicação.

Publicar a landing page a torna acessível online. Depois de publicada, você sempre pode atualizá-la: para fazer isso, é necessário republicá-lo após cada modificação. Você também pode cancelar a publicação de uma landing page a qualquer momento para que ela não esteja mais disponível.

![](assets/lp-steps6.png)

Depois de publicada, sua landing page está pronta para ser usada. Em seguida, você pode colocar diferentes mecanismos que permitem acessá-lo para adquirir novos perfis em seu banco de dados ou obter informações adicionais sobre perfis existentes.

Para obter mais informações sobre a publicação de landings page, consulte [esta seção](../../channels/using/testing-publishing-landing-page.md#publishing-a-landing-page).
