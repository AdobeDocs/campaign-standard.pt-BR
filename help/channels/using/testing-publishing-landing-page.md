---
title: Compartilhamento de uma landing page
description: Saiba como testar e publicar uma landing page no Adobe Campaign.
page-status-flag: never-activated
uuid: fb7b087a-3292-496c-bc41-2e3012bacf59
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: f7d4bb71-f957-4f86-97c7-8ac0a0030026
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 32f3b8ac0108bbce10e443c39f1f766ddf97db84
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 100%

---


# Teste e publicação de uma landing page{#testing-publishing--landing-page}

## Sobre publicação de uma landing page {#about-landing-page-publication}

Antes de publicar uma landing page, faça testes: valide a execução, configure o acesso e configure o fim da vida da landing page. Essas etapas são pré-requisitos e precisam ser executadas com cuidado.

## Teste da landing page {#testing-the-landing-page-}

Como a landing page afetará a plataforma e os dados, é necessário testar cuidadosamente a execução. Para fazer isso:

1. Clique no botão **[!UICONTROL Test]** na barra de ação da landing page.
1. Na tela de teste, selecione um perfil de teste e um serviço de teste se a landing page for usada para gerenciar assinaturas.

   ![](assets/lp_test_2.png)

1. Insira os dados nos campos e selecione as opções.
1. Envie a landing page e confira se há atualizações no banco de dados.

   >[!IMPORTANT]
   >
   >Quando o formulário for enviado, o serviço e o perfil usados serão atualizados.

1. Repita isso com vários perfis e dados.

Você também pode gerar a miniatura da landing page desta tela.

>[!NOTE]
>
>Para exibir a pré-visualização da landing page na interface do usuário do Campaign, o URL do servidor do aplicativo deve estar protegido. Nesse caso, use https:// em vez de http:// para definir esse URL ao [configurar sua marca](../../administration/using/branding.md#configuring-and-using-brands).

## Configuração de parâmetros de validade {#setting-up-validity-parameters}

Antes da publicação, por motivos de segurança e desempenho da plataforma, recomendamos que você defina uma data de expiração nas propriedades da landing page. Na data selecionada, a publicação da landing page será automaticamente desfeita. Para fazer isso:

1. Edite as propriedades de landing page acessadas pelo botão ![](assets/edit_darkgrey-24px.png) no painel da landing page.

   ![](assets/lp_edit_properties_button.png)

1. Configure a data e a hora de expiração na seção **[!UICONTROL Publication]**. A publicação da landing page será automaticamente desfeita na data especificada e não estará mais disponível.

   Você pode selecionar o fuso horário a ser considerado para essa data e hora.

1. Defina um URL para redirecionar os visitantes quando eles tentarem acessar uma landing page inativa.

   ![](assets/lp_settings_general.png)

>[!IMPORTANT]
>
>Você também pode definir uma data e hora de implantação. A landing page será publicada automaticamente na data especificada.

## Publicação de uma landing page {#publishing-a-landing-page}

Ao publicar uma landing page, ela fica ativa e pode ser acessada pelos visitantes.

Você pode desfazer a publicação ou atualizar e republicar a landing page a qualquer momento usando o botão **[!UICONTROL Publish]**. No entanto, se a republicação falhar e você ainda não tiver desfeito a publicação da landing page, a primeira versão permanecerá online.
