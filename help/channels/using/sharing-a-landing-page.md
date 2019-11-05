---
title: Compartilhamento de uma página de aterrissagem
description: Saiba como testar e publicar uma página de aterrissagem no Adobe Campaign.
page-status-flag: nunca ativado
uuid: fb7b087a-3292-496c-bc41-2e3012bacf59
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: canais
content-type: referência
topic-tags: páginas de aterrissagem
discoiquuid: f7d4bb71-f957-4f86-97c7-8ac0a0030026
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Compartilhamento de uma página de aterrissagem{#sharing-a-landing-page}

## Sobre a publicação da página de aterrissagem {#about-landing-page-publication}

Antes de publicar uma página de aterrissagem, é necessário executar testes: valide a execução, configure o acesso e configure o fim da vida útil da página de aterrissagem. Essas etapas são pré-requisitos e precisam ser executadas com cautela.

## Teste da página de aterrissagem {#testing-the-landing-page-}

Como a página de aterrissagem afetará sua plataforma e seus dados, é necessário testar cuidadosamente sua execução. Para fazer isso:

1. Clique no **[!UICONTROL Test]** botão na barra de ação da página de aterrissagem.
1. Na tela de teste, selecione um perfil de teste e um serviço de teste se a página inicial for para gerenciar assinaturas.

   ![](assets/lp_test_2.png)

1. Insira os dados nos campos e selecione as opções.
1. Envie a página inicial e verifique as atualizações no banco de dados.

   >[!CAUTION]
   >
   >Quando o formulário é enviado, o serviço e o perfil usados são atualizados.

1. Repita isso com vários perfis e dados.

   Também é possível gerar a miniatura da página inicial a partir dessa tela.

## Configuração de parâmetros de validade {#setting-up-validity-parameters}

Antes de publicar, por motivos de segurança e desempenho da plataforma, recomendamos que você defina uma data de expiração nas propriedades da página inicial. Na data selecionada, a página inicial será automaticamente despublicada. Para fazer isso:

1. Edite as propriedades da página inicial acessadas pelo ![](assets/edit_darkgrey-24px.png) botão no painel da página inicial.

   ![](assets/lp_edit_properties_button.png)

1. Configure a data e a hora de expiração na **[!UICONTROL Publication]** seção: a página inicial será automaticamente despublicada na data especificada e, portanto, não estará mais disponível.

   Você pode selecionar o fuso horário a ser considerado para essa data e hora.

1. Defina um URL de redirecionamento para redirecionar os visitantes ao tentar acessar uma página de aterrissagem não ativa.

   ![](assets/lp_settings_general.png)

>[!CAUTION]
>
>Você também pode definir uma data e hora de implantação: a página inicial será publicada automaticamente na data especificada.

## Publicar uma página de aterrissagem {#publishing-a-landing-page}

Quando você publica uma página de aterrissagem, ela é colocada ao vivo e pode ser acessada pelos seus visitantes.

Você pode cancelar a publicação ou atualizar e republicar sua página inicial a qualquer momento, por meio do **[!UICONTROL Publish]** botão. No entanto, se a republicação falhar e você ainda não tiver despublicado sua página inicial, a primeira versão permanecerá online.
