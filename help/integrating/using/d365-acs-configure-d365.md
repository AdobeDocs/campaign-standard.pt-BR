---
title: Configurar o Microsoft Dynamics 365 para integração com o Campaign
description: Saiba como configurar o Microsoft Dynamics 365 para integração com o Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 57e85f8e-65b4-44ea-98e6-0c555acf6dee
source-git-commit: 6947d163119dd6fc5966fdc723530b02bdd4a469
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 1%

---

# Configurar o Microsoft Dynamics 365 para integração com o Adobe Campaign Standard

Saiba como configurar a integração com o Microsoft Dynamics 365 e ativar os dados do CRM na comunicação entre canais com o Adobe Campaign Standard.

## Visão geral

A descrição geral da integração do Adobe Campaign Standard com o Microsoft Dynamics 365 está descrita em [esta página](../../integrating/using/d365-acs-get-started.md).

Vários aplicativos precisarão ser configurados para habilitar a integração. No entanto, este artigo se concentrará nas etapas necessárias no Dynamics 365.

## Pré-requisitos

Antes de executar a configuração de pré-integração neste documento, presume-se que você já tenha provisionado e tido acesso de administrador à instância do Microsoft Dynamics 365 de sua organização.  Se isso não tiver acontecido, você precisará entrar em contato com o suporte ao cliente da Microsoft para concluir o provisionamento do Dynamics 365.

Se você estiver configurando a integração para ambientes de preparo e produção, será necessário executar as etapas abaixo para as instâncias de preparo e produção do Dynamics 365. Algumas instruções abaixo variam um pouco, dependendo se você está configurando um estágio ou uma instância de produção do Dynamics 365 (por exemplo, para a instância de produção, selecione &quot;prod&quot; para `<stage or prod>`)

## Configuração do aplicativo e das permissões

Um token de acesso OAuth permite que a ferramenta de integração seja autenticada em sua instância do Microsoft Dynamics 365 por meio de APIs da Web para publicar eventos de experiência de Campaign Standard na exibição da linha do tempo da interface do Microsoft Dynamics 365.

As etapas principais estão descritas no vídeo a seguir:

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Para gerar o token de acesso OAuth, siga as etapas descritas abaixo.

### Registrar um novo aplicativo {#register-a-new-app}

1. Em seu login de administrador, faça login no [portal.azure.com](https://portal.azure.com){target="_blank"}.

1. Clique em **[!UICONTROL Azure Active Directory]** no menu do lado esquerdo; em seguida, clique em **[!UICONTROL App registrations]** no submenu que é exibido.

1. Clique em **[!UICONTROL New registration]** na parte superior da tela.

1. Preencha a tela de registro do aplicativo:

   * Nome: adobe campaign `<stage or prod>`
   * Tipo de conta compatível: **[!UICONTROL Accounts in this organizational directory only]** (valor padrão)

Para obter mais informações sobre como criar um novo aplicativo, consulte [nesta seção](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.

>[!NOTE]
>
>O Microsoft Azure Diretory atribui uma ID de aplicativo (cliente) exclusiva ao aplicativo. Você precisará dessa ID posteriormente na configuração do Dynamics 365, bem como ao executar a configuração da ferramenta de integração.

### Gerar segredo do cliente {#generate-a-client-secret}

1. Na tela de visão geral do aplicativo, no submenu à esquerda, clique em **[!UICONTROL Certificates and Secrets > New client secret]**

1. Insira uma descrição, defina a duração e clique em **[!UICONTROL OK]**.

O segredo do cliente foi criado. Retenha o valor temporariamente para a conclusão da configuração de pré-integração da ferramenta de integração.

>[!CAUTION]
>
>Mantenha esse valor como você precisará dele para concluir a configuração de pré-integração da ferramenta de integração. Ele não pode ser recuperado posteriormente.


### Configurar permissões

1. Nesta tela ou na tela de visão geral do aplicativo, clique em **[!UICONTROL API permissions]** no submenu à esquerda.  Depois de clicar em **[!UICONTROL Add a permission]**, é necessário selecionar **[!UICONTROL Dynamics CRM]** no menu.

1. Em seguida, marque a caixa para **[!UICONTROL user_impersonation]** e clique no botão **[!UICONTROL Add permissions]** botão.

Para obter mais informações sobre a configuração de permissões, consulte [nesta seção](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis){target="_blank"}.

### Criar o usuário do aplicativo

Este novo usuário é um usuário genérico. Ele será usado pelo aplicativo: qualquer alteração no Microsoft Dynamics 365 usando a API será feita por esse usuário. Para criá-lo, siga as etapas abaixo:

1. Navegue até a instância do Dynamics 365 e faça logon como Administrador.

1. Clique no ícone de engrenagem no canto superior direito e clique em **[!UICONTROL Advanced Settings]**. No banner superior, clique na lista suspensa ao lado de **[!UICONTROL Settings]**, clique em **[!UICONTROL Security > Users]**.

1. Clique no menu suspenso para acessar **[!UICONTROL Application Users]**. Clique em **[!UICONTROL New]**.

1. O menu suspenso Garantir ao lado do ícone do usuário diz **[!UICONTROL USER:APPLICATION USER]**.

   Preencha a tela para o novo usuário.  Sugestões de parâmetros:

   * **[!UICONTROL User Name]** (email): adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (por exemplo, adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**: ID do aplicativo que você registrou no Azure AD (isso é obrigatório)
   * Você pode deixar em branco **[!UICONTROL Application ID URI]** e **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**: API ADOBE `<stage or prod>`
   * **[!UICONTROL Email]**: igual a **[!UICONTROL User Name]** (ou email do administrador, se desejar)

   Para obter mais informações sobre a criação de usuários no aplicativo, consulte [nesta seção](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user){target="_blank"}.

1. Clique no ícone do usuário e carregue um ícone do Adobe Campaign; esse é o ícone que será exibido na exibição Linha do tempo quando novos eventos de Adobe aparecerem no Dynamics 365.

1. Abra a lista de funções de usuário clicando em **[!UICONTROL MANAGE ROLES]** na faixa superior.

1. Role para baixo e selecione **[!UICONTROL System administrator]** para este usuário.

1. Clique em **[!UICONTROL OK]**.

### Obter a ID do locatário {#get-the-tenant-id}

Siga as instruções [nesta página](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) para encontrar sua ID de locatário.  Você precisará dessa ID durante a configuração de pré-integração na ferramenta de integração.

## Campaign Standard de instalação do Microsoft Dynamics 365 {#install-appsource-app}

Para integrar o aplicativo Dynamics 365 ao seu ambiente de Campaign Standard, siga as etapas abaixo:

1. Navegue até [Aplicativos comerciais do Microsoft](https://appsource.microsoft.com/en-us/marketplace/apps)e procure por_Adobe Campaign Standard_ na barra de pesquisa.
Como alternativa, você pode navegar para essa [link](https://appsource.microsoft.com/en-us/product/dynamics-365/adobe.adobe_campaign_d365?tab=Overview){target="_blank"}.
1. Siga as instruções para instalar o aplicativo para sua instância do Dynamics 365.
1. Depois de instalado, navegue até a instância do Dynamics 365 e entre como administrador.
1. Clique no ícone de engrenagem no canto superior direito e clique em **[!UICONTROL Advanced Settings]**. No banner superior, clique na lista suspensa ao lado de **[!UICONTROL Settings]**, clique em **[!UICONTROL Processes]** em **[!UICONTROL Process Center]**.
1. Pesquisar por **[!UICONTROL Adobe Campaign Email Bounce]** e clique nela.
1. No **[!UICONTROL Administration]** altere o proprietário para o usuário do aplicativo da API Adobe criado anteriormente clicando em **[!UICONTROL Actions]** na faixa superior, selecione **[!UICONTROL Assign to another User]** selecione **[!UICONTROL Adobe API application user]** na lista suspensa para atribuir.
1. Reative o processo.
1. Faça o mesmo para o **[!UICONTROL Adobe Campaign Email Click]** tarefa.

>[!NOTE]
>
>Se, a qualquer momento, você desejar desativar esses processos, faça isso nesta **[!UICONTROL Processes]** tela.

**Tópicos relacionados**

* [Configurar o Adobe Developer para integração com o Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-adobe-io.md) é a próxima etapa na configuração da integração do
* [Introdução ao aplicativo de integração de autoatendimento](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) A contém a lista completa de etapas para ativar a integração.
