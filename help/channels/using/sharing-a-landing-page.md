---
title: Compartilhamento de uma página de aterrissagem
seo-title: Compartilhamento de uma página de aterrissagem
description: Compartilhamento de uma página de aterrissagem
seo-description: Saiba como testar e publicar uma página de aterrissagem no Adobe Campaign.
page-status-flag: nunca ativado
uuid: fb 7 b 087 a -3292-496 c-bc 41-2 e 3012 bacf 59
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: páginas de aterrissagem
discoiquuid: f 7 d 4 bb 71-f 957-4 f 86-97 c 7-8 ac 0 a 0030026
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Sharing a landing page{#sharing-a-landing-page}

## About landing page publication {#about-landing-page-publication}

Antes de publicar uma página de aterrissagem, você precisa executar testes: valide a execução, configure o acesso e configure o fim da sua página inicial. Essas etapas são pré-requisitos e precisam ser executadas com cautela.

## Testing the landing page {#testing-the-landing-page-}

Como a página de aterrissagem afetará a plataforma e os dados, você precisa testar cuidadosamente sua execução. Para fazer isso:

1. Click the **[!UICONTROL Test]** button in the action bar of the landing page.
1. Na tela de teste, selecione um perfil de teste e um serviço de teste se a página de aterrissagem for gerenciar assinaturas.

   ![](assets/lp_test_2.png)

1. Insira os dados nos campos e selecione opções.
1. Envie a página de aterrissagem e verifique as atualizações no banco de dados.

   >[!CAUTION]
   >
   >Quando o formulário é enviado, o serviço e o perfil usados são atualizados.

1. Repita isso com vários perfis e dados.

   Também é possível gerar a miniatura da página de aterrissagem nessa tela.

## Setting up validity parameters {#setting-up-validity-parameters}

Antes de publicar, por motivos de segurança e desempenho da plataforma, recomendamos que você defina uma data de expiração nas propriedades da página de aterrissagem. Na data selecionada, a página de aterrissagem é automaticamente desfeita. Para fazer isso:

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) button in the landing page dashboard.

   ![](assets/lp_edit_properties_button.png)

1. Set up expiration date and time in the **[!UICONTROL Publication]** section: the landing page will automatically be unpublished on the specified date and therefore no longer be available.

   Você pode selecionar o fuso horário a ser considerado para esta data e hora.

1. Defina um URL de redirecionamento para redirecionar os visitantes ao tentar acessar uma página de aterrissagem não ativa.

   ![](assets/lp_settings_general.png)

>[!CAUTION]
>
>Você também pode definir uma data e hora de implantação: a página de aterrissagem será publicada automaticamente na data especificada.

## Publishing a landing page {#publishing-a-landing-page}

Quando você publica uma página de aterrissagem, ela fica ativa e pode ser acessada pelos seus visitantes.

You can unpublish or update and republish your landing page at any time, via the **[!UICONTROL Publish]** button. Entretanto, se a republicação falhar e você ainda não tiver cancelado a publicação da página de aterrissagem, a primeira versão permanecerá online.
