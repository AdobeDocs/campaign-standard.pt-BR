---
title: Configurar o Microsoft Dynamics 365 para integração com o Campaign
description: Saiba como configurar o Microsoft Dynamics 365 para integração com a Campanha.
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a7e02fa4fdef05d67118baf0f49fda7886c6768f
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 2%

---


# Configurar o Microsoft Dynamics 365 para integração com o Campaign

Saiba como configurar a integração do Microsoft Dynamics 365 e ativar seus dados do CRM na comunicação entre canais com a Adobe Campaign Standard.

## Visão geral

Adobe Campaign Standard - A integração do Microsoft Dynamics 365 está descrita [nesta página](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

Três sistemas que precisam ser provisionados para essa integração:

1. Adobe Campaign Standard - [Saiba mais](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
1. Microsoft Dynamics 365 para Vendas - Descrito abaixo
1. Ferramenta de integração - propriedade da equipe de consultoria da Adobe

Depois de provisionados, esses sistemas precisam ser configurados por um administrador.

Este artigo destaca as etapas, no lado do Microsoft Dynamics 365, necessárias durante a configuração de pré-integração para permitir que um cliente use a integração Adobe Campaign Standard - Microsoft Dynamics 365.

>[!NOTE]
>
>Até que a interface do usuário para a ferramenta de autoatendimento esteja disponível no final deste ano, a equipe de onboard ajudará você a configurar a integração.

## Pré-requisitos

Antes de executar a configuração de pré-integração neste documento, presume-se que você já provisionou e tem acesso de administrador à instância do Microsoft Dynamics 365 da sua organização.  Se isso não tiver acontecido, você precisará entrar em contato com o suporte ao cliente da Microsoft para concluir o provisionamento do Dynamics 365.

Se você estiver configurando a integração para ambientes de armazenamento temporário e de produção, será necessário executar as etapas abaixo para as instâncias do Dynamics 365 de armazenamento temporário e produção. Algumas instruções a seguir variam um pouco, dependendo da configuração de uma instância do Stage ou do Production Dynamics 365 (por exemplo, por exemplo, selecione &quot;prod&quot; para `<stage or prod>`)

## Configuração de aplicativos e permissões

Um token de acesso OAuth permite que a ferramenta de integração se autentique com sua instância do Microsoft Dynamics 365 por meio de APIs da Web para postar eventos de experiência do Campaign Standard para a visualização da linha do tempo da interface do Microsoft Dynamics 365.

As etapas principais estão descritas no vídeo a seguir:

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Para gerar o token de acesso OAuth, siga as etapas descritas abaixo.

### Registrar um novo aplicativo

1. Em seu logon de administrador, faça logon no portal.azure.com.

1. Clique em **[!UICONTROL Azure Active Directory]** no menu esquerdo; em seguida, clique **[!UICONTROL App registrations]** no submenu exibido.

1. Clique **[!UICONTROL New registration]** na parte superior da tela.

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. Preencha a tela de registro do aplicativo:

   * Nome: adobe campanha `<stage or prod>`
   * Tipo de conta suportado: **[!UICONTROL Accounts in this organizational directory only]** (valor padrão)

For more information about creating a new application, refer to [this section](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app).

>[!NOTE]
>
>O Azure AD atribui uma ID de aplicativo exclusiva (cliente) ao seu aplicativo. Você precisará dessa ID posteriormente na configuração do Dynamics 365, bem como na execução da configuração de pré-integração para a ferramenta de integração.

### Gerar segredo do cliente

1. Na tela de visão geral do aplicativo, no submenu à esquerda, clique em **[!UICONTROL Certificates and Secrets > New client secret]**

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. Insira uma descrição, defina a duração e clique em **[!UICONTROL OK]**.

Seu segredo de cliente agora é criado. Mantenha o valor temporariamente para a conclusão da configuração de pré-integração da ferramenta de integração.

>[!CAUTION]
>
>Mantenha esse valor, pois ele será necessário para concluir a configuração de pré-integração da ferramenta de integração. Não pode ser recuperado depois.


### Permissões de configuração

1. Nessa tela ou na tela de visão geral do aplicativo, clique em **[!UICONTROL API permissions]** no submenu à esquerda.  Depois de clicar **[!UICONTROL Add a permission]**, é necessário selecionar **[!UICONTROL Dynamics CRM]** no menu.

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. Em seguida, marque a caixa para **[!UICONTROL user_impersonation]** e clique no **[!UICONTROL Add permissions]** botão.

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

Para obter mais informações sobre a configuração de permissão, consulte [esta seção](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis).

### Criar o usuário do aplicativo

Este novo usuário é um usuário genérico. Será utilizado pelo aplicativo: qualquer alteração no Microsoft Dynamics 365 usando a API será feita por este usuário. Para criá-lo, siga as etapas abaixo:

1. Navegue até sua instância do Dynamics 365 e faça logon como Administrador.

1. Clique no ícone de engrenagem no canto superior direito e clique em **[!UICONTROL Advanced Settings]**. No banner superior, clique na lista suspensa ao lado de **[!UICONTROL Settings]**, clique em **[!UICONTROL Security > Users]**.

1. Clique no menu suspenso para ir para **[!UICONTROL Application Users]**. Clique em **[!UICONTROL New]**.

1. Certifique-se de que a lista suspensa ao lado do ícone do usuário esteja exibida **[!UICONTROL USER:APPLICATION USER]**.

   Preencha a tela do novo usuário.  Sugestões de parâmetros:

   * **[!UICONTROL User Name]** (email): adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (por exemplo, adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**: ID do aplicativo que você registrou no Azure AD (isso é obrigatório)
   * Você pode deixar em branco **[!UICONTROL Application ID URI]** e **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**: API Adobe `<stage or prod>`
   * **[!UICONTROL Email]**: igual a **[!UICONTROL User Name]** (ou ao email do administrador, se desejar)

   Para obter mais informações sobre a criação de usuários do aplicativo, consulte [esta seção](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

1. Clique no ícone do usuário e carregue um ícone do Adobe Campaign; este é o ícone que será exibido na visualização Linha do tempo quando novos eventos de Adobe forem exibidos no Dynamics 365.

<!-- ***getfile*** adobe campaign logo-->

1. Abra a lista de funções do usuário clicando **[!UICONTROL MANAGE ROLES]** na faixa superior.

1. Role para baixo e selecione **[!UICONTROL System administrator]** acesso para este usuário.

1. Clique em **[!UICONTROL OK]**.

### Obter a ID do locatário

Siga as instruções [nesta página](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) para localizar sua ID de locatário.  Você precisará dessa ID durante a configuração da pré-integração na ferramenta de integração.

## Instale o Campaign Standard para o Microsoft Dynamics 365

Para integrar o aplicativo Dynamics 365 ao seu ambiente Campaign Standard, siga as etapas abaixo:

1. Navegue até o seguinte link: [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) e procure _Adobe Campaign para Dynamics 365_ na barra de pesquisa.
Como alternativa, você pode navegar até esse [link](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview).
1. Siga as instruções para instalar o aplicativo para sua instância do Dynamics 365.
1. Depois de instalado, navegue até a instância do Dynamics 365 e faça logon como administrador.
1. Clique no ícone de engrenagem no canto superior direito e clique em **[!UICONTROL Advanced Settings]**. No banner superior, clique na lista suspensa ao lado de **[!UICONTROL Settings]**, clique em **[!UICONTROL Processes]** embaixo **[!UICONTROL Process Center]**.
1. Procure por **[!UICONTROL Adobe Campaign Email Bounce]** tarefa e clique nela.
1. Na **[!UICONTROL Administration]** guia, altere o proprietário para o usuário do aplicativo da API de Adobe criado anteriormente clicando **[!UICONTROL Actions]** na faixa superior e selecione **[!UICONTROL Assign to another User]** a opção, selecione **[!UICONTROL Adobe API application user]** na lista suspensa a ser atribuída.
1. Reative o processo.
1. Faça o mesmo pela **[!UICONTROL Adobe Campaign Email Click]** tarefa.

>[!NOTE]
>
>Se, a qualquer momento, você desejar desativar esses processos, poderá fazê-lo nesta **[!UICONTROL Processes]** tela.

**Tópicos relacionados**

* [Campaign Standard - Integração com o Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [Configurar o Adobe IO para integração com o Microsoft Dynamics 365](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
