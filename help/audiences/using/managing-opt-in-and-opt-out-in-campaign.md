---
title: Gerenciamento de aceitação e recusa no Campaign
description: Entenda como a aceitação e a recusa são gerenciadas no Adobe Campaign.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Intermediate
exl-id: 4aeb90c5-f5b5-4cfe-93fb-2fd01fb8d70e
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 8%

---

# Gerenciamento de aceitação e recusa no Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Gerenciamento de aceitação e recusa em um perfil {#managing-opt-in-and-opt-out-from-a-profile}

Os usuários podem ser aceitos ou recusados por um operador diretamente na guia **[!UICONTROL General]** do perfil.

Na seção **[!UICONTROL No longer contact (on denylist)]**, as caixas de seleção selecionadas correspondem aos canais dos quais o usuário optou por recusar. Selecione os canais de acordo com as necessidades do usuário.

![](assets/optin_landingpage_3.png)

## Configuração de páginas de aterrissagem de aceitação e recusa {#setting-up-opt-in-and-opt-out-landing-pages}

Para conceder aos usuários a capacidade de aceitar ou recusar, você deve criar e publicar uma página de aterrissagem **[!UICONTROL Profile acquisition]**. Eles poderão selecionar os canais de acordo com suas necessidades. Para fazer isso, siga as etapas abaixo.

Você também pode configurar uma página de aterrissagem **[!UICONTROL Denylist]** que permitirá aos usuários recusar todas as entregas. Para obter mais informações, consulte [Configuração de uma página de aterrissagem para recusar todas as entregas](#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>As landing pages também podem ser usadas para habilitar a assinatura de serviços. Para obter mais informações, consulte [esta página](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service).

1. Criar uma página de aterrissagem **[!UICONTROL Profile acquisition]** (consulte [esta seção](../../channels/using/getting-started-with-landing-pages.md)).
1. Adicione uma caixa de seleção no conteúdo da landing page para cada canal desejado e vincule-o ao campo correspondente do banco de dados do Campaign.

   ![](assets/optin_landingpage_1.png)

1. Salve a landing page e publique-a.
1. Na página de aterrissagem, as caixas de seleção já estão selecionadas de acordo com a guia do perfil **[!UICONTROL General]**. O usuário pode selecionar ou desmarcar os canais de acordo com suas necessidades e enviar o formulário.

   ![](assets/optin_landingpage_2.png)

1. Depois que o formulário for enviado, a guia do perfil **[!UICONTROL General]** será atualizada de acordo com a seleção do usuário.

   ![](assets/optin_landingpage_3.png)

### Configuração de uma landing page para recusar todos os deliveries {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

Para permitir que os usuários recusem todas as entregas, é necessário criar e publicar uma página de aterrissagem **[!UICONTROL Denylist]**. Para saber mais sobre a criação de páginas de aterrissagem, consulte [esta página](../../channels/using/getting-started-with-landing-pages.md).

Quando um usuário clica no link da página de aterrissagem, a opção **[!UICONTROL No longer contact (by any channel)]** no perfil é selecionada automaticamente.

![](assets/blocklisting_allchannels.png)
