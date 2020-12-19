---
solution: Campaign Standard
product: campaign
title: Configurar o Adobe IO para integração com o Microsoft Dynamics 365
description: Saiba como configurar o E/S do Adobe para integração com o Microsoft Dynamics 365.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 5%

---


# Configurar o Adobe IO para integração com o Microsoft Dynamics 365

Ative seus dados do CRM na comunicação entre canais: aprenda as etapas necessárias durante a configuração de pré-integração para criar um novo projeto de E/S de Adobe e configurá-lo para a integração do Microsoft Dynamics 365.

## Visão geral

Adobe Campaign Standard - a integração do Microsoft Dynamics 365 está descrita em [esta página](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

Antes de executar a configuração de pré-integração neste artigo, supõe-se que você já tenha sido provisionado e que tenha acesso de administrador à instância de Campaign Standard da sua organização.  Se isso não aconteceu, você precisará entrar em contato com o Atendimento ao cliente da Adobe para concluir o provisionamento da Campanha.

>[!CAUTION]
>
>As etapas descritas abaixo precisam ser executadas por um administrador.

## Configuração

Você precisará criar um novo projeto de E/S de Adobe e configurá-lo para a integração.

### Criar um novo projeto

Para isso, siga o procedimento abaixo:

1. Navegue até [Console de E/S de Adobe](https://console.adobe.io/home#) e selecione a ID de organização do Adobe IMS no menu suspenso na parte superior direita da tela.

1. Em seguida, clique em **[!UICONTROL Create new project]** em **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. Em **[!UICONTROL Get started with your new project]**, clique em **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. Selecione a API do Adobe Campaign (talvez seja necessário rolar até a parte inferior) e clique em **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. Na tela seguinte, você terá a opção de carregar sua própria chave pública ou permitir que o Adobe IO gere o par de chaves para você. Essas instruções seguirão a última opção. Se você decidir permitir que o Adobe IO gere o par de chaves, clique na opção 1; em seguida, clique no botão **[!UICONTROL Generate keypair]**.

   ![](assets/adobeIO4.png)

1. Na tela seguinte, você será solicitado a nomear e selecionar o local de download do arquivo zip de par de chaves.

Depois de baixado, você pode descompactar o arquivo para revelar as chaves públicas e privadas. O Adobe IO já aplicou a chave pública ao seu projeto Adobe IO. Você precisará manter sua chave privada para mais tarde; a chave privada será usada durante a configuração de pré-integração da ferramenta de integração.

1. Clique em **[!UICONTROL Next]** para continuar

   ![](assets/adobeIO5.png)

1. Na tela seguinte, você selecionará perfis de produtos para associar a este projeto. Selecione o perfil de produto que contém na solução: Campaign Standard
produto: campanha
título: A ID de locatário da instância de Campanha - [!UICONTROL Administrators]

   Exemplo: Campaign Standard - your-campanha-locatário-ID - Administradores

1. Clique em **[!UICONTROL Save configured API]**.

   ![](assets/adobeIO6.png)

1. Na tela seguinte, você verá os detalhes do seu novo projeto de E/S de Adobe. Clique em **[!UICONTROL Add to Project]** no canto superior esquerdo da tela e selecione **API** no menu suspenso.

   ![](assets/adobeIO7.png)

1. Na tela seguinte, você precisará selecionar a API de Eventos de E/S e clicar em **[!UICONTROL Next]**.

1. Na tela seguinte, clique em **[!UICONTROL Save the configured API]**.  Você será levado de volta à tela de detalhes do projeto.

1. Agora, clique em **[!UICONTROL Add to Project]** na parte superior esquerda da tela e selecione **API** na lista suspensa, como anteriormente.

1. Na tela seguinte, você precisará selecionar a API de gerenciamento de E/S e clicar em **[!UICONTROL Next]**.

1. Na tela seguinte, clique em **[!UICONTROL Save the configured API]**.

A configuração da pré-integração na Campanha agora está concluída.  Prossiga para concluir a configuração de [pré-integração para o Microsoft Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

**Tópicos relacionados**

* [Adobe IO - Integração da conta de serviço](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - Configuração de acesso à API](../../api/using/setting-up-api-access.md)
* [Campaign Standard - Integração com o Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)