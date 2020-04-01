---
title: Configurar o Microsoft Dynamics 365 para integração com Campanhas
description: Saiba como configurar o Microsoft Dynamics 365 para integração com a Campanha.
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---


# Configurar o Microsoft Dynamics 365 para integração com Campanhas

Saiba como configurar a integração do Microsoft Dynamics 365 e ativar seus dados do CRM na comunicação entre canal com o Adobe Campaign Standard.

## Visão geral

Adobe Campaign Standard - a integração com o Microsoft Dynamics 365 está descrita [nesta página](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

Três sistemas que precisam ser provisionados para essa integração:

1. Adobe Campaign Standard - [Saiba mais](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
1. Microsoft Dynamics 365 para Vendas - Descrito abaixo
1. Unifi - [Saiba mais](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md)

Depois de provisionados, esses sistemas precisam ser configurados por um administrador.

Este artigo destaca as etapas, no lado do Microsoft Dynamics 365, necessárias durante o pós-provisionamento para permitir que um cliente use a integração Adobe Campaign Standard - Microsoft Dynamics 365.

## Pré-requisitos

Antes de executar as etapas de pós-provisionamento neste documento, presume-se que você já tenha provisionado e tenha acesso de administrador à instância do Microsoft Dynamics 365 da sua organização.  Se isso não tiver acontecido, você precisará entrar em contato com o suporte ao cliente da Microsoft para concluir o provisionamento do Dynamics 365.

## Configuração de aplicativos e permissões

Um token de acesso OAuth permite que o Unifi se autentique com sua instância do Microsoft Dynamics 365 por meio de APIs da Web para postar eventos de experiência do Campaign Standard para a visualização da linha do tempo da interface do Microsoft Dynamics 365.

As etapas principais estão descritas no vídeo a seguir:

** VÍDEO**

Para gerar o token de acesso OAuth, siga as etapas descritas abaixo.

### Registrar um novo aplicativo

1. Em seu logon de administrador, faça logon no portal.azure.com.

1. Clique em **[!UICONTROL Azure Active Directory]** no menu esquerdo; em seguida, clique **[!UICONTROL App registrations]** no submenu exibido.

1. Clique **[!UICONTROL New registration]** na parte superior da tela.

![](assets/MSdynACSIntegration-7.png)

Preencha a tela de registro do aplicativo:

* Nome: adobe campanha
* Tipo de conta suportado: **[!UICONTROL Accounts in this organizational directory only]** (valor padrão)

For more information about creating a new application, refer to [this section](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app).

>[!NOTE]
>
>O Azure AD atribui uma ID exclusiva de aplicativo (cliente) ao seu aplicativo. Você precisará dessa ID mais tarde na configuração do Dynamics 365, bem como ao executar as etapas do Unifi Post Provisioning.

### Gerar segredo do cliente

1. Na tela de visão geral do aplicativo, no submenu à esquerda, clique em **[!UICONTROL Certificates and Secrets > New client secret]**

   ![](assets/MSdynACSIntegration-8.png)

1. Insira uma descrição, defina a duração e clique em **[!UICONTROL OK]**.

Seu segredo de cliente agora é criado.  Mantenha o valor para a conclusão das etapas de pós-provisionamento Unifi.

>[!CAUTION]
>
>Mantenha esse valor, pois ele será necessário para concluir a etapa de pós-provisionamento Unifi. Não pode ser recuperado depois.

Para obter mais informações sobre como gerar um segredo de cliente, consulte esta seção.

### Permissões de configuração

1. Nessa tela ou na tela de visão geral do aplicativo, clique em **[!UICONTROL API permissions]** no submenu à esquerda.  Depois de clicar **[!UICONTROL Add a permission]**, é necessário selecionar **[!UICONTROL Dynamics CRM]** no menu.

   ![](assets/MSdynACSIntegration-9.png)

1. Em seguida, marque a caixa para **[!UICONTROL user_impersonation]** e clique no **[!UICONTROL Add permissions]** botão.

   ![](assets/MSdynACSIntegration-10.png)

Para obter mais informações sobre a configuração de permissão, consulte [esta seção](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis).

### Criar o usuário do aplicativo

Este novo usuário é um usuário genérico. Será utilizado pelo aplicativo: qualquer alteração no Microsoft Dynamics 365 usando a API será feita por este usuário. Para criá-lo, siga as etapas abaixo:

1. Navegue até sua instância do Dynamics 365 e faça logon como Administrador.

1. Clique no ícone de engrenagem no canto superior direito e clique em **[!UICONTROL Advanced Setting]**s. No banner superior, clique na lista suspensa ao lado de **[!UICONTROL Settings]**, clique em **[!UICONTROL Security > Users]**.

1. Clique no menu suspenso para ir para **[!UICONTROL Application Users]**. Clique em **[!UICONTROL New]**.

1. Certifique-se de que a lista suspensa ao lado do ícone do usuário esteja exibida **[!UICONTROL USER:APPLICATION USER]**.

Preencha a tela do novo usuário.  Sugestões de parâmetros:

* **[!UICONTROL User Name]** (email): adobeapi@`<hostname>`, onde `<hostname>` é o nome do host da sua instância do Dynamics 365
* **[!UICONTROL Application ID]**: ID do aplicativo que você registrou no Azure AD (isso é obrigatório)
* Você pode deixar em branco **[!UICONTROL Application ID URI]** e **[!UICONTROL Azure AD Object ID]**
* **[!UICONTROL Full Name]**: Adobe API
* **[!UICONTROL Email]**: igual a **[!UICONTROL User Name]** (ou ao email do administrador, se desejar)

Para obter mais informações sobre a criação de usuários do aplicativo, consulte [esta seção](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

1. Clique no ícone do usuário e carregue um ícone de Adobe Campaign; este é o ícone que será exibido na visualização Linha do tempo quando novos eventos da Adobe forem exibidos no Dynamics 365.

***getfile***

1. Abra a lista de funções do usuário clicando **[!UICONTROL MANAGE ROLES]** na faixa superior.

1. Role para baixo e selecione **[!UICONTROL System administrator]** acesso para este usuário.

1. Clique em **[!UICONTROL OK]**.

### Obter a ID do locatário

Siga as instruções no link a seguir para localizar sua ID de locatário.  Você precisará dessa ID durante o pós-provisionamento no Unifi: [https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id).

## Instale o Campaign Standard para o Microsoft Dynamics 365

Para integrar o aplicativo Dynamics 365 ao seu ambiente Campaign Standard, siga as etapas abaixo:

1. Navegue até o seguinte link: [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) e procure _Adobe Campaign para Dynamics 365_ na barra de pesquisa.
Como alternativa, você pode navegar até esse [link](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&tab=Overview).
1. Siga as instruções para instalar o aplicativo para sua instância do Dynamics 365.
1. Depois de instalado, navegue até a instância do Dynamics 365 e faça logon como administrador.
1. Clique no ícone de engrenagem no canto superior direito e clique em **[!UICONTROL Advanced Settings]**. No banner superior, clique na lista suspensa ao lado de **[!UICONTROL Settings]**, clique em **[!UICONTROL Processes]** embaixo **[!UICONTROL Process Center]**.
1. Procure por **[!UICONTROL Adobe Campaign Email Bounce]** tarefa e clique nela.
1. Na **[!UICONTROL Administration]** guia, altere o proprietário para o usuário do aplicativo Adobe API criado anteriormente clicando **[!UICONTROL Actions]** na faixa superior e selecione **[!UICONTROL Assign to another User]** a opção, selecione **[!UICONTROL Adobe API application user]** na lista suspensa a ser atribuída.
1. Reative o processo.
1. Faça o mesmo pela **[!UICONTROL Adobe Campaign Email Click]** tarefa.

>[!NOTE]
>
>Se, a qualquer momento, você desejar desativar esses processos, poderá fazê-lo nesta **[!UICONTROL Processes]** tela.

Quando essa configuração estiver concluída, você poderá configurar a configuração Unifi. Para obter mais informações, consulte esta [página](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

**Tópicos relacionados**

* [Campaign Standard - Integração com o Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [Configurar o Adobe IO para integração do Microsoft Dynamics 365](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
* [Configurar Unifi para Campaign - Integração do Microsoft Dynamics 365](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md)
