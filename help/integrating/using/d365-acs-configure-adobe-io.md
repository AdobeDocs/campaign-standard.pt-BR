---
title: Configurar o Adobe Developer para integração com o Microsoft Dynamics 365
description: Saiba como configurar o Adobe Developer para integração com o Microsoft Dynamics 365
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ab21b694-d05c-4ba4-b828-936803651b82
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 0%

---

# Configuração do Adobe Campaign Standard e do Adobe Developer para a integração com o Microsoft Dynamics 365

Este artigo explicará como configurar o Adobe Campaign Standard e o Adobe I/O para conceder ao aplicativo de integração acesso aos dados.

## Configurar Adobe Campaign Standard {#campaign-standard}

### Extensões de perfil

Ative as &quot;extensões de perfil&quot; no Adobe Campaign Standard.   Isso é necessário para que campos personalizados no recurso de Perfil sejam sincronizados do Microsoft Dynamics 365.   As etapas para ativá-los são:

1. Acesse Configurações -> Administração -> Desenvolvimento -> Publicação.
1. Clique em &quot;Preparar publicação&quot; para preparar uma publicação.
1. Após a conclusão da preparação, marque a opção &quot;Criar a API de extensão de Perfis e serviços&quot; e clique em &quot;Publicar&quot;.

## Configurar Adobe I/O {#adobe-io}

O Adobe I/O permite habilitar o acesso da API ao Adobe Campaign Standard, bem como a outros produtos da Adobe.   Este artigo detalha como configurar o Adobe I/O para conceder à integração do Adobe Campaign Standard com o Microsoft Dynamics 365 acesso para sincronizar os dados.

### Visão geral

Antes de executar a configuração de pré-integração neste artigo, presume-se que você já tenha sido provisionado e tenha acesso de administrador à instância do Campaign Standard de sua organização.  Se isso não acontecer, será necessário entrar em contato com o Atendimento ao cliente da Adobe para concluir o provisionamento do Campaign.

>[!CAUTION]
>
>As etapas descritas abaixo precisam ser executadas por um administrador.

### Configuração

Será necessário criar um novo projeto do Adobe Developer e configurá-lo para a integração.

#### Criar um novo projeto

Para isso, siga o procedimento abaixo:

1. Navegue até [Adobe Developer Console](https://console.adobe.io/home#) e selecione sua Adobe Organization ID no menu suspenso na parte superior direita da tela.

1. Em seguida, clique em **[!UICONTROL Create new project]** em **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. Em **[!UICONTROL Get started with your new project]**, clique em **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. Selecione a Adobe Campaign e clique em **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. Na próxima tela, você terá a opção de escolher o tipo de autenticação. Você pode escolher Servidor para servidor OAuth ou Conta de serviço (JWT). Observe que as credenciais da Conta de serviço (JWT) não são mais recomendadas para novos projetos e foram substituídas em favor das credenciais de servidor para servidor do OAuth mais recentes. As instruções fornecidas neste guia serão aplicadas apenas à autenticação de servidor para servidor do OAuth.

   ![](assets/adobeIO4.png)

1. Na próxima tela, você selecionará perfis de produto para associar a este projeto. Selecione o perfil de produto que contém no título: A ID do locatário da instância do Campaign - [!UICONTROL Administrators]

   Exemplo: Campaign Standard - your-campaign-tenantID - Administradores

1. Clique em **[!UICONTROL Save configured API]**.

   ![](assets/adobeIO5.png)

1. Na próxima tela, você verá os detalhes do novo projeto do Adobe Developer. Clique em **[!UICONTROL Add to Project]** no canto superior esquerdo da tela e selecione **API** no menu suspenso.

   ![](assets/adobeIO6.png)

1. Na próxima tela, você precisará selecionar a API de Eventos de E/S e clicar em **[!UICONTROL Next]**.

1. Na próxima tela, clique em **[!UICONTROL Save the configured API]**.  Você será redirecionado à tela de detalhes do projeto.

1. Agora clique em **[!UICONTROL Add to Project]** no canto superior esquerdo da tela e selecione **API** no menu suspenso, como você fez anteriormente.

1. Na próxima tela, você precisará selecionar a API de Gerenciamento de E/S e clicar em **[!UICONTROL Next]**.

1. Na próxima tela, clique em **[!UICONTROL Save the configured API]**.

A configuração da pré-integração no Campaign está concluída.

**Tópicos relacionados**

* [Configurar o Adobe Developer para integração com o Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-adobe-io.md) é a próxima etapa na configuração da integração
* [Visão Geral do Aplicativo de Autoatendimento de Integração](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) contém a lista completa de etapas para ativar a integração.
* [Adobe Developer - Integração de Conta de Serviço](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - Configuração de acesso à API](../../api/using/setting-up-api-access.md)
* [Campaign Standard - Integração com o Dynamics 365](../../integrating/using/d365-acs-configure-d365.md)
* [Migrar credenciais do JWT para o servidor do OAuth](../../integrating/using/d365-acs-self-service-app-migrate-credentials.md) contém as etapas para migrar credenciais do JWT para o servidor do OAuth.
