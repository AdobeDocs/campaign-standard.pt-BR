---
title: Principais etapas para configurar uma página de aterrissagem
seo-title: Principais etapas para configurar uma página de aterrissagem
description: Principais etapas para configurar uma página de aterrissagem
seo-description: Saiba mais sobre as principais etapas para configurar uma página de aterrissagem
page-status-flag: nunca ativado
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: limatório
products: SG_CAMPAIGN/STANDARD
audience: canais
content-type: referência
topic-tags: páginas de aterrissagem
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,assistente;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1f100f6b041c6dbb298113b4ecc7830951714131

---


# Principais etapas para configurar uma página de aterrissagem {#main-steps-create-a-landing-page}

## Sobre a criação da página inicial

As principais etapas ao configurar as páginas iniciais são as seguintes:

![](assets/lp_steps.png)

Nesta página, você encontrará informações sobre cada uma dessas etapas, bem como referências às documentações dedicadas para obter mais detalhes.

## Configurar o modelo de página inicial {#configure-the-landing-page-template}

Antes de configurar uma página inicial, a primeira etapa é configurar um modelo de página inicial que corresponda às suas necessidades. Quando o modelo estiver pronto, todas as páginas iniciais baseadas nele serão pré-configuradas com os parâmetros desejados.

1. No menu avançado, pelo logotipo do Adobe Campaign, selecione **[!UICONTROL Resources]** / **[!UICONTROL Templates]** / **[!UICONTROL Landing page templates]** e duplique o modelo que deseja usar.
1. Nas propriedades do modelo, especifique todos os parâmetros que suas páginas iniciais devem ter em comum.  Por exemplo: a dimensão de definição de metas, os parâmetros de acesso à página para visitantes identificados ou não, ações específicas para a validação do formulário por um visitante, a marca/logotipo a ser usado no conteúdo etc.
1. Salve suas modificações.

For more on landing page templates, refer to [this section](../../channels/using/about-landing-pages.md).

![](assets/lp-steps1.png)

## Criar e configurar a página de aterrissagem {#create-and-configure-the-landing-page}

No modelo definido na etapa anterior, crie uma nova página inicial em um programa ou campanha.

1. Crie a página inicial com base no modelo desejado.
1. Insira os parâmetros gerais da página inicial (rótulo, descrição etc.).
1. Em seguida, você acessará o painel da página inicial. Edite as propriedades da página inicial, se necessário. Por padrão, as propriedades são as configuradas no modelo de página inicial.
Por motivos de segurança e desempenho da plataforma, recomendamos que você defina uma data de expiração nas propriedades da página inicial. Depois de concluída, a página inicial será automaticamente despublicada na data selecionada. For more on validity parameters, refer to [this section](../../channels/using/sharing-a-landing-page.md#setting-up-validity-parameters).

   ![](assets/lp-steps3.png)

   >[!NOTE]
   >
   >Suas modificações só são eficazes para a página de aterrissagem que está sendo editada. Se quiser aplicar essas modificações a outras páginas iniciais, você pode executá-las em um modelo dedicado e criar outras páginas iniciais a partir desse modelo.

## Projetar a página de aterrissagem {#design-the-landing-page}

Agora é possível definir o conteúdo da página de aterrissagem. Por padrão, a página inicial contém três páginas que podem ser acessadas por meio de setas de rolagem: a página de conteúdo principal, uma página de confirmação e uma página de erro.

![](assets/lp-steps4.png)

Vários campos são configurados por padrão em cada página. Se necessário, você pode editar suas propriedades e mapeamento.

Você também pode configurar a forma como o botão de confirmação se comportará assim que um perfil clicar nele e personalizar o conteúdo de acordo com suas necessidades (imagem, campos de personalização etc.). Por exemplo, você pode inserir o nome de um perfil na página de confirmação da página de aterrissagem, para agradecer o registro.

Para obter mais informações sobre o design da página de aterrissagem, consulte [esta seção](../../channels/using/designing-a-landing-page.md).

## Testar a página de aterrissagem {#test-the-landing-page}

Assim que a página inicial for definida, você poderá simular a forma como ela será executada e se comportará quando ela estiver disponível online.

![](assets/lp-steps5.png)

>[!CAUTION]
>
>Os testes de página inicial só podem ser realizados com perfis, e não com perfis de teste. Quando o formulário for enviado, os dados do perfil selecionado serão atualizados para verdadeiro. Para evitar modificar perfis reais, use um perfil falso do cliente.

Se você estiver satisfeito com o comportamento da página de aterrissagem, poderá publicá-la para disponibilizá-la online.

Para obter mais informações sobre como testar uma página de aterrissagem, consulte [esta seção](../../channels/using/sharing-a-landing-page.md#testing-the-landing-page-).

## Publicar a página de aterrissagem {#publish-the-landing-page}

Depois que os testes forem bem-sucedidos, você poderá publicar a página de aterrissagem usando o **[!UICONTROL Publish]** botão da barra de ação no painel. Um bloco de monitoramento mostra a progressão e o status da publicação.

A publicação da página de aterrissagem o torna acessível online. Depois de publicada, você sempre pode atualizá-la: para fazer isso, é necessário republicá-lo após cada modificação. Você também pode cancelar a publicação de uma página de aterrissagem a qualquer momento para que não esteja mais disponível.

![](assets/lp-steps6.png)

Depois de publicada, sua página de aterrissagem está pronta para ser usada. Em seguida, você pode colocar diferentes mecanismos que permitem acessá-lo para adquirir novos perfis em seu banco de dados ou obter informações adicionais sobre perfis existentes.

Para obter mais informações sobre a publicação da página inicial, consulte [esta seção](../../channels/using/sharing-a-landing-page.md#publishing-a-landing-page).
