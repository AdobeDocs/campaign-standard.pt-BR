---
solution: Campaign Standard
product: campaign
title: Gerenciamento de participação e não participação no Campaign
description: Entenda como o opt-in e o opt-out são gerenciados no Adobe Campaign.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 8%

---


# Gerenciamento de participação e não participação no Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Gerenciamento de participação e não participação de um perfil {#managing-opt-in-and-opt-out-from-a-profile}

Os usuários podem ser aceitos ou rejeitados por um operador diretamente da guia **[!UICONTROL General]** do perfil.

Na seção **[!UICONTROL No longer contact (on denylist)]** , as caixas de seleção selecionadas correspondem aos canais dos quais o usuário optou por não participar. Selecione os canais de acordo com as necessidades do usuário.

![](assets/optin_landingpage_3.png)

## Configuração de landing pages de opt-in e opt-out {#setting-up-opt-in-and-opt-out-landing-pages}

Para dar aos usuários a capacidade de aceitar ou rejeitar, é necessário criar e publicar uma landing page **[!UICONTROL Profile acquisition]**. Eles poderão selecionar os canais de acordo com suas necessidades. Para fazer isso, siga as etapas abaixo.

Você também pode configurar uma página de aterrissagem **[!UICONTROL Denylist]** que permitirá que os usuários optem por não participar de todos os deliveries. Para obter mais informações, consulte [Configuração de uma landing page para recusar todos os deliveries](#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>As landing pages também podem ser usadas para ativar a assinatura de serviços. Para obter mais informações, consulte [esta página](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service).

1. Crie uma landing page **[!UICONTROL Profile acquisition]** (consulte [esta seção](../../channels/using/getting-started-with-landing-pages.md)).
1. Adicione uma caixa de seleção ao conteúdo da página de aterrissagem para cada canal desejado, em seguida, vincule-a ao campo correspondente do banco de dados do Campaign.

   ![](assets/optin_landingpage_1.png)

1. Salve a landing page e a publique.
1. Na landing page, as caixas de seleção já estão selecionadas de acordo com a guia **[!UICONTROL General]** do perfil. O usuário pode selecionar ou desmarcar os canais de acordo com suas necessidades e enviar o formulário.

   ![](assets/optin_landingpage_2.png)

1. Depois que o formulário é enviado, a guia **[!UICONTROL General]** do perfil é atualizada de acordo com a seleção do usuário.

   ![](assets/optin_landingpage_3.png)

### Configuração de uma landing page para recusar todos os deliveries {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

Para dar aos usuários a capacidade de optar por não participar de todos os deliveries, é necessário criar e publicar uma landing page **[!UICONTROL Denylist]**. Para obter mais informações sobre a criação de landing pages, consulte [esta página](../../channels/using/getting-started-with-landing-pages.md).

Depois que um usuário clica no link da landing page, a opção **[!UICONTROL No longer contact (by any channel)]** no perfil é selecionada automaticamente.

![](assets/blocklisting_allchannels.png)

