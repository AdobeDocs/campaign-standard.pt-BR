---
title: Compartilhamento de uma página de destino
description: Saiba como testar e publicar uma página de destino no Adobe Campaign.
audience: channels
content-type: reference
topic-tags: landing-pages
feature: Landing Pages
role: User
level: Intermediate
exl-id: af849377-686f-45b3-bf6e-5069a8966987
TQID: https://experienceleague.adobe.com/8RZopDxY3R2f-67RtWyh7xRwD6-c2BhR-tEmEeLGO3Y
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 386
ht-degree: 95%

---

# Teste e publicação de uma página de destino{#testing-publishing--landing-page}

## Sobre publicação de uma landing page {#about-landing-page-publication}

Antes de publicar uma página de destino, faça testes: valide a execução, configure o acesso e configure o fim da vida da página de destino. Essas etapas são pré-requisitos e precisam ser executadas com cuidado.

## Teste da landing page {#testing-the-landing-page-}

Como a página de destino afetará a plataforma e os dados, é necessário testar cuidadosamente a execução. Para fazer isso:

1. Clique no botão **[!UICONTROL Test]** na barra de ação da página de destino.
1. Na tela de teste, selecione um perfil de teste e um serviço de teste se a página de destino for usada para gerenciar assinaturas.

   ![](assets/lp_test_2.png)

1. Insira os dados nos campos e selecione as opções.
1. Envie a página de destino e confira se há atualizações no banco de dados.

   >[!IMPORTANT]
   >
   >Quando o formulário for enviado, o serviço e o perfil usados serão atualizados.

1. Repita isso com vários perfis e dados.

Você também pode gerar a miniatura da página de destino desta tela.

>[!NOTE]
>
>Para exibir a pré-visualização da página de destino na interface do usuário do Campaign, o URL do servidor de aplicativos deve estar protegido. Nesse caso, use https:// em vez de http:// para definir esse URL ao [configurar sua marca](../../administration/using/branding.md#configuring-and-using-brands).

## Configuração de parâmetros de validade {#setting-up-validity-parameters}

Antes da publicação, por motivos de segurança e desempenho da plataforma, recomendamos que você defina uma data de expiração nas propriedades da página de destino. Na data selecionada, a publicação da página de destino será automaticamente desfeita. Para fazer isso:

1. Edite as propriedades de página de destino acessadas pelo botão ![](assets/edit_darkgrey-24px.png) no painel da página de destino.

   ![](assets/lp_edit_properties_button.png)

1. Configure a data e a hora de expiração na seção **[!UICONTROL Publication]**. A publicação da página de destino será automaticamente desfeita na data especificada e não estará mais disponível.

   Você pode selecionar o fuso horário a ser considerado para essa data e hora.

1. Defina um URL para redirecionar os visitantes quando eles tentarem acessar uma página de destino inativa.

   ![](assets/lp_settings_general.png)

>[!IMPORTANT]
>
>Você também pode definir uma data e hora de implantação. A página de destino será publicada automaticamente na data especificada.

## Publicação de uma landing page {#publishing-a-landing-page}

Ao publicar uma página de destino, ela fica ativa e pode ser acessada pelos visitantes.

Você pode desfazer a publicação ou atualizar e republicar a página de destino a qualquer momento usando o botão **[!UICONTROL Publish]**. No entanto, se a republicação falhar e você ainda não tiver desfeito a publicação da página de destino, a primeira versão permanecerá online.
