---
solution: Campaign Standard
product: campaign
title: Configurar o Microsoft Dynamics 365 para integração com o Campaign
description: Saiba como configurar o Microsoft Dynamics 365 para integração com o Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '917'
ht-degree: 1%

---


# Configurar o Microsoft Dynamics 365 para integração com o Adobe Campaign Standard

Saiba como configurar a integração com o Microsoft Dynamics 365 e ativar seus dados do CRM na comunicação entre canais com o Adobe Campaign Standard.

## Visão geral

A descrição geral da integração do Adobe Campaign Standard com o Microsoft Dynamics 365 é descrita em [this page](../../integrating/using/d365-acs-get-started.md).

Vários aplicativos precisarão ser configurados para habilitar a integração. No entanto, este artigo se concentrará nas etapas necessárias no Dynamics 365.

## Pré-requisitos

Antes de executar a configuração de pré-integração neste documento, presume-se que você já tenha provisionado e tenha acesso de administrador à instância do Microsoft Dynamics 365 de sua organização.  Se isso não tiver acontecido, será necessário entrar em contato com o suporte ao cliente da Microsoft para concluir o provisionamento do Dynamics 365.

Se estiver configurando a integração para ambientes de preparação e produção, será necessário executar as etapas abaixo para as instâncias de preparação e produção do Dynamics 365. Algumas instruções abaixo variam um pouco, dependendo se você estiver configurando uma instância do stage ou do Production Dynamics 365 (por exemplo, por exemplo, selecione &quot;prod&quot; para `<stage or prod>`)

## Configuração do aplicativo e permissões

Um token de acesso OAuth permite que a ferramenta de integração se autentique com sua instância do Microsoft Dynamics 365 por meio de APIs da Web para publicar eventos de experiência do Campaign Standard na exibição de linha do tempo da interface do Microsoft Dynamics 365.

As etapas principais são descritas no vídeo a seguir:

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Para gerar o token de acesso OAuth, siga as etapas descritas abaixo.

### Registrar um novo aplicativo {#register-a-new-app}

1. Sob o login do administrador, faça logon no portal.azure.com.

1. Clique em **[!UICONTROL Azure Active Directory]** no menu lateral esquerdo; em seguida, clique em **[!UICONTROL App registrations]** no submenu exibido.

1. Clique em **[!UICONTROL New registration]** na parte superior da tela.

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. Preencha a tela de registro do aplicativo:

   * Nome: adobe campaign `<stage or prod>`
   * Tipo de conta compatível: **[!UICONTROL Accounts in this organizational directory only]** (valor padrão)

Para obter mais informações sobre como criar um novo aplicativo, consulte [esta seção](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app).

>[!NOTE]
>
>O diretório do Microsoft Azure atribui uma ID de aplicativo exclusiva (cliente) ao seu aplicativo. Posteriormente, essa ID será necessária na configuração do Dynamics 365, bem como na execução da configuração da ferramenta de integração.

### Gerar segredo de cliente {#generate-a-client-secret}

1. Na tela de visão geral do aplicativo, no submenu à esquerda, clique em **[!UICONTROL Certificates and Secrets > New client secret]**

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. Insira uma descrição, defina a duração e clique em **[!UICONTROL OK]**.

O segredo do cliente foi criado. Mantenha o valor temporariamente para a conclusão da configuração de pré-integração da ferramenta de integração.

>[!CAUTION]
>
>Mantenha esse valor como precisará para concluir a configuração de pré-integração da ferramenta de integração. Ele não pode ser recuperado posteriormente.


### Permissões de configuração

1. Nesta tela ou na tela de visão geral do aplicativo, clique em **[!UICONTROL API permissions]** no submenu à esquerda.  Depois de clicar em **[!UICONTROL Add a permission]**, é necessário selecionar **[!UICONTROL Dynamics CRM]** no menu.

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. Em seguida, marque a caixa **[!UICONTROL user_impersonation]** e clique no botão **[!UICONTROL Add permissions]**.

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

Para obter mais informações sobre a configuração de permissão, consulte [esta seção](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis).

### Criar o usuário do aplicativo

Este novo usuário é um usuário genérico. Ele será usado pelo aplicativo: qualquer alteração no Microsoft Dynamics 365 usando a API será feita por este usuário. Para criá-lo, siga as etapas abaixo:

1. Navegue até a instância do Dynamics 365 e faça logon como Administrador.

1. Clique no ícone de engrenagem no canto superior direito e clique em **[!UICONTROL Advanced Settings]**. No banner superior, clique no menu suspenso ao lado de **[!UICONTROL Settings]**, clique em **[!UICONTROL Security > Users]**.

1. Clique no menu suspenso para **[!UICONTROL Application Users]**. Clique em **[!UICONTROL New]**.

1. Certifique-se de que o menu suspenso ao lado do ícone do usuário diz **[!UICONTROL USER:APPLICATION USER]**.

   Preencha a tela do novo usuário.  Sugestões de parâmetros:

   * **[!UICONTROL User Name]** (email): adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (por exemplo, adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**: ID do aplicativo que você registrou no Azure AD (isso é obrigatório)
   * Você pode deixar em branco **[!UICONTROL Application ID URI]** e **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**: API Adobe  `<stage or prod>`
   * **[!UICONTROL Email]**: igual a  **[!UICONTROL User Name]** (ou ao email do administrador, se desejar)

   Para obter mais informações sobre a criação de usuários do aplicativo, consulte [esta seção](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

1. Clique no ícone do usuário e faça upload de um ícone do Adobe Campaign; este é o ícone que será exibido na exibição Linha do tempo quando os novos Adobe forem exibidos no Dynamics 365.

1. Abra a lista de funções de usuário clicando em **[!UICONTROL MANAGE ROLES]** na faixa superior.

1. Role para baixo e selecione **[!UICONTROL System administrator]** acesso para este usuário.

1. Clique em **[!UICONTROL OK]**.

### Obter a ID do locatário {#get-the-tenant-id}

Siga as instruções [nesta página](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) para localizar sua ID de locatário.  Você precisará dessa ID durante a configuração de pré-integração na ferramenta de integração.

## Instale o Campaign Standard para Microsoft Dynamics 365 {#install-appsource-app}

Para integrar o aplicativo Dynamics 365 ao seu ambiente Campaign Standard, siga as etapas abaixo:

1. Navegue até o link a seguir: [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) e procure _Adobe Campaign para Dynamics 365_ na barra de pesquisa.
Como alternativa, você pode navegar até este [link](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview).
1. Siga as instruções para instalar o aplicativo para sua instância do Dynamics 365.
1. Depois de instalado, navegue até a instância do Dynamics 365 e faça logon como administrador.
1. Clique no ícone de engrenagem no canto superior direito e clique em **[!UICONTROL Advanced Settings]**. No banner superior, clique no menu suspenso ao lado de **[!UICONTROL Settings]**, clique em **[!UICONTROL Processes]** em **[!UICONTROL Process Center]**.
1. Procure por **[!UICONTROL Adobe Campaign Email Bounce]** tarefa e clique nela.
1. Na guia **[!UICONTROL Administration]** , altere o proprietário para o usuário do aplicativo Adobe API criado anteriormente clicando em **[!UICONTROL Actions]** na faixa superior e selecione **[!UICONTROL Assign to another User]** opção, selecione **[!UICONTROL Adobe API application user]** na lista suspensa para atribuir.
1. Reative o processo.
1. Faça o mesmo para a tarefa **[!UICONTROL Adobe Campaign Email Click]**.

>[!NOTE]
>
>Se desejar desativar esses processos a qualquer momento, faça isso na tela **[!UICONTROL Processes]**.

**Tópicos relacionados**

* [Configurar o Adobe IO para ](../../integrating/using/d365-acs-configure-adobe-io.md) integração com o Microsoft Dynamics 365 é o próximo passo para configurar a integração
* [Introdução ao ](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) aplicativo de integração de autoatendimento contém a lista completa de etapas para ativar e executar a integração.
