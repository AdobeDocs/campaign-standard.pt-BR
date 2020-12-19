---
solution: Campaign Standard
product: campaign
title: Gerenciamento de participação e não participação no Campaign
description: Saiba como o opt-in e o opt-out são gerenciados no Adobe Campaign.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 8%

---


# Gerenciamento de participação e não participação no Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Gerenciando aceitação e exclusão de um perfil {#managing-opt-in-and-opt-out-from-a-profile}

Os usuários podem ser opt in ou removidos por um operador diretamente da guia perfil **[!UICONTROL General]**.

Na seção **[!UICONTROL No longer contact (on denylist)]**, as caixas de seleção selecionadas correspondem aos canais dos quais o usuário optou por opt out. Selecione os canais de acordo com as necessidades do usuário.

![](assets/optin_landingpage_3.png)

## Configurando landings page de aceitação e recusa {#setting-up-opt-in-and-opt-out-landing-pages}

Para dar aos usuários a capacidade de opt in ou opt out, é necessário criar e publicar uma landing page **[!UICONTROL Profile acquisition]**. Eles poderão então selecionar os canais de acordo com suas necessidades. Para fazer isso, siga as etapas abaixo.

Você também pode configurar uma landing page **[!UICONTROL Denylist]** que permitirá que os usuários opt out de todos os delivery. Para obter mais informações, consulte [Configurar uma landing page para opt out de todos os delivery](#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>As landings page também podem ser usadas para ativar a subscrição de serviços. Para obter mais informações, consulte [esta página](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service).

1. Crie uma landing page **[!UICONTROL Profile acquisition]** (consulte [esta seção](../../channels/using/getting-started-with-landing-pages.md)).
1. Adicione uma caixa de seleção no conteúdo da landing page para cada canal desejado e, em seguida, vincule-a ao campo correspondente do banco de dados da Campanha.

   ![](assets/optin_landingpage_1.png)

1. Salve a landing page e publique-a.
1. Na landing page, as caixas de seleção já estão selecionadas de acordo com a guia perfil **[!UICONTROL General]**. O usuário pode selecionar ou desmarcar os canais de acordo com suas necessidades e enviar o formulário.

   ![](assets/optin_landingpage_2.png)

1. Depois que o formulário é enviado, a guia perfil **[!UICONTROL General]** é atualizada de acordo com a seleção do usuário.

   ![](assets/optin_landingpage_3.png)

### Configuração de uma landing page para opt out de todos os delivery {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

Para dar aos usuários a capacidade de opt out de todos os delivery, é necessário criar e publicar uma landing page **[!UICONTROL Denylist]**. Para obter mais informações sobre a criação do landing page, consulte [esta página](../../channels/using/getting-started-with-landing-pages.md).

Quando um usuário clica no link de landing page, a opção **[!UICONTROL No longer contact (by any channel)]** no perfil é automaticamente selecionada.

![](assets/blocklisting_allchannels.png)

