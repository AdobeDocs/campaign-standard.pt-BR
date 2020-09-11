---
title: Configurar o Adobe IO para integração com o Microsoft Dynamics 365
description: Saiba como configurar o E/S de Adobe para integração com o Microsoft Dynamics 365.
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
source-git-commit: 801741bd605d11d1c9f88995286ef206dd46470f
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 3%

---


# Configurar o Adobe IO para integração com o Microsoft Dynamics 365

Ative seus dados do CRM na comunicação entre canais: aprenda as etapas necessárias durante a configuração de pré-integração para criar um novo projeto de E/S de Adobe e configurá-lo para a integração do Microsoft Dynamics 365.

## Visão geral

Adobe Campaign Standard - A integração do Microsoft Dynamics 365 está descrita [nesta página](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

Antes de executar a configuração de pré-integração neste artigo, supõe-se que você já tenha sido provisionado e que tenha acesso de administrador à instância de Campaign Standard da sua organização.  Se isso não aconteceu, você precisará entrar em contato com o Atendimento ao cliente da Adobe para concluir o provisionamento da Campanha.

>[!CAUTION]
>
>As etapas descritas abaixo precisam ser executadas por um administrador.

## Configuração

Você precisará criar um novo projeto de E/S de Adobe e configurá-lo para a integração.

### Criar um novo projeto

Para isso, siga o procedimento abaixo:

1. Navegue até o Console [de E/S do](https://console.adobe.io/home#) Adobe e selecione a ID de organização do Adobe IMS no menu suspenso na parte superior direita da tela.

1. Em seguida, clique em **[!UICONTROL Create new project]** embaixo **[!UICONTROL Quick Start]**.

![](assets/adobeIO1.png)

1. Em **[!UICONTROL Get started with your new project]**, clique em **[!UICONTROL Add API]**.

![](assets/adobeIO2.png)

1. Selecione a API do Adobe Campaign (talvez seja necessário rolar até a parte inferior) e clique em &quot;Avançar&quot;.

![](assets/adobeIO3.png)

1. Na tela seguinte, você terá a opção de carregar sua própria chave pública ou permitir que o Adobe IO gere o par de chaves para você. Essas instruções seguirão a última opção. Se você decidir permitir que o Adobe IO gere o par de chaves, clique na opção 1; em seguida, clique no botão &quot;Gerar par de teclas&quot;.

![](assets/adobeIO4.png)

1. Na tela seguinte, você será solicitado a nomear e selecionar o local de download do arquivo zip de par de chaves.

Depois de baixado, você pode descompactar o arquivo para revelar as chaves públicas e privadas. O Adobe IO já aplicou a chave pública ao seu projeto Adobe IO. Você precisará manter sua chave privada para mais tarde; a chave privada será usada durante a configuração de pré-integração da ferramenta de integração.

1. Clique em &quot;Avançar&quot; para continuar

![](assets/adobeIO5.png)

1. Na tela seguinte, você selecionará perfis de produtos para associar a este projeto.

1. Selecione o perfil de produto que contém o título: A ID de locatário da sua instância de Campanha - [!UICONTROL Administrators] - Exemplo: Campaign Standard - your-campanha-locatário-ID - Administradores

1. Clique em [!UICONTROL Save configured API].

![](assets/adobeIO6.png)

1. Na tela seguinte, você verá os detalhes do seu novo projeto de E/S de Adobe.

1. Clique em &quot;Adicionar ao projeto&quot; na parte superior esquerda da tela e selecione &quot;API&quot; na lista suspensa.

![](assets/adobeIO7.png)

1. Na tela seguinte, você precisará selecionar a API de Eventos de E/S e clicar em &quot;Avançar&quot;.

1. Na tela seguinte, clique em &quot;Salvar API configurada&quot;.  Você será levado de volta à tela de detalhes do projeto.

1. Agora, clique em &quot;Adicionar ao projeto&quot; na parte superior esquerda da tela e selecione &quot;API&quot; na lista suspensa, como você fez anteriormente.

1. Na tela seguinte, você precisará selecionar a API de gerenciamento de E/S e clicar em &quot;Avançar&quot;.

1. Na tela seguinte, clique em &quot;Salvar API configurada&quot;.

A configuração da pré-integração na Campanha agora está concluída.  Prossiga para concluir a configuração de [pré-integração do Microsoft Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

**Tópicos relacionados**

* [Adobe IO - Integração da conta de serviço](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - Configuração de acesso à API](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#setting-up-api-access)
* [Campaign Standard - Integração com o Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)