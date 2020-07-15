---
title: Provisionamento e configuração da integração com o Audience Manager ou o serviço principal do People
description: 'Saiba mais sobre como configurar a integração do serviço principal do Audience Manager / Pessoas para compartilhar audiências ou segmentos com as diferentes soluções da Adobe Experience Cloud. '
page-status-flag: never-activated
uuid: e7329644-0033-4729-b4a7-61bef137f4b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: eb24f4ea-325f-433a-91a0-c45906320bcb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bd74905985734412b4fb11ad11d70faf9fcc9ca6
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 39%

---


# Provisionamento e configuração da integração com o Audience Manager ou o serviço principal do People{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

O provisionamento e a configuração do núcleo de Audience Manager e Pessoas no Adobe Campaign executam duas etapas: [Envio da solicitação para a Adobe](#submitting-request-to-adobe) e, em seguida, [Configuração da integração no Adobe Campaign](#configuring-the-integration-in-adobe-campaign).

## Envio de solicitação à Adobe {#submitting-request-to-adobe}

A integração de Audience Manager (AAM) ou serviço principal de pessoas permite importar e exportar audiências ou segmentos no Adobe Campaign.

Essa integração deve ser configurada primeiro. Para solicitar o provisionamento dessa integração, escreva um e-mail para [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com) com as seguintes informações:

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Tipo de Solicitação:</strong><br /> </td> 
   <td> Configurar a integração do Campaign com o serviço principal de Pessoas/AAM </td> 
  </tr> 
  <tr> 
   <td> <strong>Nome da Organização:</strong><br /> </td> 
   <td> O nome da sua organização </td> 
  </tr> 
  <tr> 
   <td> <strong>ID da Org. de IMS</strong><br /> </td> 
   <td> Sua ID de empresa IMS. <br> Você pode encontrar a ID de organização do IMS no Experience Cloud, no menu Administração. Também é fornecido ao se conectar pela primeira vez à Adobe Experience Cloud. </td> 
  </tr> 
  <tr> 
   <td> <strong>Ambiente:</strong><br /> </td> 
   <td> Exemplo: Produção </td> 
  </tr> 
  <tr> 
   <td> <strong>Serviço de Pessoas ou AAM</strong><br /> </td> 
   <td> Exemplo: Adobe Audience Manager. Informe à equipe de provisionamento se você possui ou não uma licença do Audience Manager.</td> 
  </tr> 
  <tr> 
   <td> <strong>ID declarada ou ID do visitante</strong><br /> </td> 
   <td> Exemplo: ID declarada </td> 
  </tr> 
  <tr> 
   <td> <strong>Informações adicionais</strong><br /> </td> 
   <td> Qualquer informação ou comentário útil existente </td> 
  </tr> 
 </tbody> 
</table>

## Configuração da integração no Adobe Campaign {#configuring-the-integration-in-adobe-campaign}

Depois de enviar essa solicitação, a Adobe continuará com o provisionamento da integração para você e entrará em contato com você para fornecer detalhes e informações que você precisa para finalizar a configuração:

* [Etapa 1: configurar ou verificar as contas externas no Adobe Campaign](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [Etapa 2: Configurar as fontes de dados](#step-2--configure-the-data-sources)
* [Etapa 3: configurar o servidor de rastreamento do Campaign](#step-3--configure-campaign-tracking-server)
* [Etapa 4: configurar o Serviço de ID de visitante](#step-4--configure-the-visitor-id-service)

### Etapa 1: configurar ou verificar as contas externas no Adobe Campaign {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

Primeiro precisamos configurar ou verificar as contas externas no Adobe Campaign. Essas contas devem ter sido configuradas pela Adobe e as informações necessárias devem ter sido comunicadas a você.

Para fazer isso:

1. No menu avançado, selecione **Administração > Configurações do aplicativo > Conta externa**.

   Selecione uma das seguintes contas externas disponíveis para esta integração:

   ![](assets/integration_aam_1.png)

1. Digite **[!UICONTROL Receiver server]** o seguinte formato
1. Insira o **[!UICONTROL AWS Access Key ID]**, **[!UICONTROL Secret Access Key]** e **[!UICONTROL AWS Region]**.

Suas contas externas agora estão configuradas para essa integração.

### Step 2: Configure the Data Sources {#step-2--configure-the-data-sources}

As duas fontes de dados a seguir são criadas dentro do gerenciador de Audiências: Adobe Campaign (MID) e Adobe Campaign (DeclaratedId). Ao mesmo tempo, essas duas fontes de dados estão disponíveis no Adobe Campaign:

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**: Esta é uma fonte de dados pronta para uso configurada por padrão para a ID do Visitante. Os segmentos criados a partir do Campaign farão parte dessa fonte de dados.
* **Fonte de dados da ID** declarada: Essa fonte de dados precisa ser criada e mapeada com a definição da fonte de **[!UICONTROL DeclaredId]** dados do Audience Manager.

Observe que no caso de vários sites com domínios diferentes, o Adobe Campaign não oferece suporte à reconciliação com base no ECID.

To configure the **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** data source:

1. Em **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, selecione **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. Choose **[!UICONTROL Adobe Campaign]** in the **[!UICONTROL Data Source/ Alias]** drop-down.
1. Insira o **[!UICONTROL AAM Destination ID]** fornecido pela Adobe.

   ![](assets/integration_aam_3.png)

1. Na **[!UICONTROL Reconciliation process]** categoria, recomendamos que você não altere os critérios de reconciliação e sempre use o **[!UICONTROL Visitor ID]**.
1. Clique em **[!UICONTROL Save]**.

Para criar a fonte de **[!UICONTROL Declared ID]** dados:

1. Em **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, clique no **[!UICONTROL Create]** botão.
1. Edite o conteúdo **[!UICONTROL Label]** de sua fonte de dados.
1. Na **[!UICONTROL Data Source/ Alias]** lista suspensa, escolha a Fonte de dados correspondente à fonte de **[!UICONTROL DeclaredID]** dados do Audience Manager.
1. Configure sua fonte de dados inserindo o formulário **[!UICONTROL Data Source / Alias]** e **[!UICONTROL AAM Destination ID]** fornecido pela Adobe.
1. Defina o **[!UICONTROL Reconciliation process]** conforme necessário.
1. Clique em **[!UICONTROL Save]**.

>[!NOTE]
>
>O **[!UICONTROL AAM Destination ID]** campo não é necessário se você estiver configurando a fonte de dados compartilhada para a integração [](../../integrating/using/configuring-triggers-in-experience-cloud.md)Campanha-Acionadores. **[!UICONTROL Priority]** só é necessário ao configurar os Acionadores - integração Campanha. A prioridade decide qual fonte de dados será configurada primeiro. A prioridade pode ser qualquer número, como 1 ou 100. Quanto maior a prioridade, maior a preferência durante a reconciliação.

### Etapa 3: configurar o servidor de rastreamento do Campaign {#step-3--configure-campaign-tracking-server}

Para a configuração da integração com o Serviço Principal de Pessoas ou o Audience Manager, também é necessário configurar o servidor de rastreamento do Campaign.

Aqui, verifique se o Servidor de rastreamento de Campanha está registrado no domínio (CNAME). Você pode encontrar mais informações sobre delegação de nome de domínio [neste artigo](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/Technotes/AdobeCampaign_Deliverability_Sub_Domain_Delegation.pdf).

### Etapa 4: configurar o Serviço de ID de visitante {#step-4--configure-the-visitor-id-service}

Se o serviço de ID do visitante nunca foi configurado em suas propriedades da Web ou sites, consulte este [documento](https://docs.adobe.com/content/help/en/id-service/using/implementation/setup-aam-analytics.html) para saber como configurar o serviço ou este [vídeo](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

Sua configuração e provisionamento estão finalizados, a integração agora pode ser usada para importar e exportar públicos ou segmentos.
