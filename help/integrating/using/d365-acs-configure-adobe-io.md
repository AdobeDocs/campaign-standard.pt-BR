---
title: Configurar o Adobe IO para integração com o Microsoft Dynamics 365
description: Saiba como configurar o Adobe IO para integração com o Microsoft Dynamics 365.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Integração do Microsoft CRM
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 3%

---


# Configuração do Adobe Campaign Standard e Adobe I/O para a integração com o Microsoft Dynamics 365

Este artigo explicará como configurar o Adobe Campaign Standard e o Adobe I/O para dar ao aplicativo de integração acesso aos dados.

## Configurar o Adobe Campaign Standard {#campaign-standard}

### Extensões de perfil

Ative &quot;extensões de perfil&quot; no Adobe Campaign Standard.   Isso é necessário para que campos personalizados no recurso Perfil sejam sincronizados do Microsoft Dynamics 365.   As etapas para habilitá-los são:

1. Vá para Configurações -> Administração -> Desenvolvimento -> Publicação.
1. Clique em &quot;Prepare publication&quot; para preparar uma publicação.
1. Após a conclusão da preparação, marque &quot;Create the Profiles &amp; Services Ext API&quot; (Criar a API de saída dos perfis e serviços) e clique em &quot;Publish&quot; (Publicar).

## Configurar o Adobe I/O {#adobe-io}

O Adobe I/O permite habilitar o acesso da API ao Adobe Campaign Standard e a outros produtos do Adobe.   Este artigo detalhará como configurar o Adobe I/O para dar à integração do Adobe Campaign Standard com o Microsoft Dynamics 365 acesso para sincronizar os dados.

### Visão geral

Antes de executar a configuração de pré-integração neste artigo, presume-se que você já tenha sido provisionado e tenha acesso de administrador à instância do Campaign Standard de sua organização.  Se isso não tiver acontecido, será necessário entrar em contato com o Atendimento ao cliente do Adobe para concluir o provisionamento do Campaign.

>[!CAUTION]
>
>As etapas descritas abaixo precisam ser executadas por um administrador.

### Configuração

Será necessário criar um novo projeto do Adobe IO e configurá-lo para a integração.

#### Criar um novo projeto

Para isso, siga o procedimento abaixo:

1. Navegue até [Adobe IO Console](https://console.adobe.io/home#) e selecione seu Adobe IMS Organization ID no menu suspenso, na parte superior direita da tela.

1. Em seguida, clique em **[!UICONTROL Create new project]** em **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. Em **[!UICONTROL Get started with your new project]**, clique em **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. Selecione a API do Adobe Campaign (talvez seja necessário rolar para a parte inferior) e clique em **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. Na próxima tela, você terá a opção de carregar sua própria chave pública ou permitir que o Adobe IO gere o par de chaves para você. Essas instruções seguirão a última opção. Se você decidir permitir que o Adobe IO gere o par de chaves, clique na opção 1; em seguida, clique no botão **[!UICONTROL Generate keypair]**.

   ![](assets/adobeIO4.png)

1. Na próxima tela, você será solicitado a nomear e selecionar o local de download do arquivo zip do par de chaves.

Após o download, é possível descompactar o arquivo para revelar as chaves públicas e privadas. O Adobe IO já aplicou a chave pública ao seu projeto do Adobe IO. Você precisará manter sua chave privada para mais tarde; a chave privada será usada durante a configuração de pré-integração da ferramenta de integração.

1. Clique em **[!UICONTROL Next]** para continuar

   ![](assets/adobeIO5.png)

1. Na próxima tela, você selecionará perfis de produto para associar a este projeto. Selecione o perfil de produto que contém no título: A ID do locatário da instância do Campaign - [!UICONTROL Administrators]

   Exemplo: Campaign Standard - your-campaign-tenantID - Administradores

1. Clique em **[!UICONTROL Save configured API]**.

   ![](assets/adobeIO6.png)

1. Na próxima tela, você verá os detalhes do novo projeto de Adobe IO. Clique em **[!UICONTROL Add to Project]** no canto superior esquerdo da tela e selecione **API** no menu suspenso.

   ![](assets/adobeIO7.png)

1. Na próxima tela, você precisará selecionar a API de Eventos de E/S e clicar em **[!UICONTROL Next]**.

1. Na próxima tela, clique em **[!UICONTROL Save the configured API]**.  Você será retornado à tela de detalhes do projeto.

1. Agora clique em **[!UICONTROL Add to Project]** no canto superior esquerdo da tela e selecione **API** no menu suspenso, como você fez anteriormente.

1. Na próxima tela, você precisará selecionar a API de gerenciamento de E/S e clicar em **[!UICONTROL Next]**.

1. Na próxima tela, clique em **[!UICONTROL Save the configured API]**.

A configuração de pré-integração no Campaign está concluída.

**Tópicos relacionados**

* [Configurar o Adobe IO para ](../../integrating/using/d365-acs-configure-adobe-io.md) integração com o Microsoft Dynamics 365 é o próximo passo para configurar a integração
* [A ](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) Visão geral do aplicativo de autoatendimento da integração contém a lista completa de etapas para ativar e executar a integração.


* [Adobe IO - Integração da conta de serviço](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - Configuração de acesso à API](../../api/using/setting-up-api-access.md)
* [Campaign Standard - Integração com o Dynamics 365](../../integrating/using/d365-acs-configure-d365.md)
