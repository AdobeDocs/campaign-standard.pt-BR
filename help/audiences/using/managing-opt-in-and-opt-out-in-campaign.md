---
title: Gerenciamento de participação e não participação no Campaign
seo-title: Gerenciamento de participação e não participação no Campaign
description: Gerenciamento de participação e não participação no Campaign
seo-description: Saiba como o opt-in e o opt-out são gerenciados no Adobe Campaign.
page-status-flag: nunca ativado
uuid: aa1801ec-562b-420e-8d79-c07d066b7b1a
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: referência
topic-tags: processos de aceitação-participação e opção-não-participação
discoiquuid: 6b5680f2-bba9-453e-a0d5-8ca69dd02001
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Gerenciamento de participação e não participação no Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Gerenciamento de participação e não participação de um perfil {#managing-opt-in-and-opt-out-from-a-profile}

Os usuários podem receber ou receber a opção de um operador diretamente da **[!UICONTROL General]** guia de perfil.

Na **[!UICONTROL No longer contact (blacklist)]** seção, as caixas de seleção selecionadas correspondem aos canais dos quais o usuário optou por recusar. Selecione os canais de acordo com as necessidades do usuário.

![](assets/optin_landingpage_3.png)

## Configuração de páginas iniciais de aceitação e recusa {#setting-up-opt-in-and-opt-out-landing-pages}

Para dar aos usuários a capacidade de aceitar ou recusar, é necessário criar e publicar uma página de **[!UICONTROL Profile acquisition]** aterrissagem. Poderão então selecionar os canais de acordo com as suas necessidades. Para fazer isso, siga as etapas abaixo.

Você também pode configurar uma página de **[!UICONTROL BlackList]** aterrissagem que permitirá que os usuários recusem todas as entregas. Para obter mais informações, consulte [Configuração de uma página de aterrissagem para recusar todas as entregas](#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>As páginas iniciais também podem ser usadas para ativar a assinatura de serviços. Para obter mais informações, consulte [esta página](../../channels/using/designing-a-landing-page.md#linking-a-form-to-a-service).

1. Crie uma página de **[!UICONTROL Profile acquisition]** aterrissagem (consulte [esta seção](../../channels/using/about-landing-pages.md)).
1. Adicione uma caixa de seleção no conteúdo da página inicial para cada canal desejado e, em seguida, vincule-a ao campo correspondente do banco de dados Campanha.

   ![](assets/optin_landingpage_1.png)

1. Salve a página de aterrissagem e publique-a.
1. Na página inicial, as caixas de seleção já estão selecionadas de acordo com a **[!UICONTROL General]** guia de perfil. O usuário pode selecionar ou desmarcar os canais de acordo com suas necessidades e enviar o formulário.

   ![](assets/optin_landingpage_2.png)

1. Depois que o formulário é enviado, a guia **[!UICONTROL General]** de perfil é atualizada de acordo com a seleção do usuário.

   ![](assets/optin_landingpage_3.png)

### Configurar uma página de aterrissagem para recusar todas as entregas {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

Para dar aos usuários a capacidade de recusar todas as entregas, é necessário criar e publicar uma página de **[!UICONTROL BlackList]** aterrissagem. For more on landing pages creation, refer to [this page](../../channels/using/about-landing-pages.md).

Quando um usuário clica no link da página inicial, a **[!UICONTROL No longer contact (by any channel)]** opção no perfil é selecionada automaticamente.

![](assets/blacklisting_allchannels.png)

