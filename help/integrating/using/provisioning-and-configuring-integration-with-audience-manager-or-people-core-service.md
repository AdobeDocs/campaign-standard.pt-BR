---
title: Provisionamento e configuração da integração com o Audience Manager ou o serviço principal de Pessoas
seo-title: Provisionamento e configuração da integração com o Audience Manager ou o serviço principal de Pessoas
description: Provisionamento e configuração da integração com o Audience Manager ou o serviço principal de Pessoas
seo-description: 'Saiba como configurar a integração de serviço principal do Audience Manager/Pessoas para iniciar o compartilhamento de públicos-alvo ou segmentos com as diferentes soluções da Adobe Experience Cloud. '
page-status-flag: nunca ativado
uuid: e 7329644-0033-4729-b 4 a 7-61 bef 137 f 4 b 5
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: eb 24 f 4 ea -325 f -433 a -91 a 0-c 45906320 bcb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Provisioning and configuring integration with Audience Manager or People core service{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

The provisioning and configuring of Audience Manager and People core in Adobe Campaign take two steps: [Submitting request to Adobe](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#submitting-request-to-adobe) then [Configuring the integration in Adobe Campaign](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#configuring-the-integration-in-adobe-campaign).

## Submitting request to Adobe {#submitting-request-to-adobe}

A integração do Audience Manager (AAM) ou de pessoas principais permite importar e exportar públicos-alvo ou segmentos no Adobe Campaign.

Essa integração deve ser configurada primeiro. To request provisioning of this integration, write an email to [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com) with the following information:

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Tipo de solicitação:</strong><br /> </td> 
   <td> Configurar o AAM/People Core Service-Campaign Integration </td> 
  </tr> 
  <tr> 
   <td> <strong>Nome da organização:</strong><br /> </td> 
   <td> Nome da organização </td> 
  </tr> 
  <tr> 
   <td> <strong>ID Org IMS</strong><br /> </td> 
   <td> Sua ID de organização IMS * </td> 
  </tr> 
  <tr> 
   <td> <strong>Ambiente:</strong><br /> </td> 
   <td> Exemplo: Produção </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM ou Serviço de pessoas</strong><br /> </td> 
   <td> Exemplo: Adobe Audience Manager </td> 
  </tr> 
  <tr> 
   <td> <strong>ID declarada ou ID do visitante</strong><br /> </td> 
   <td> Exemplo: ID declarada </td> 
  </tr> 
  <tr> 
   <td> <strong>Informações adicionais</strong><br /> </td> 
   <td> Qualquer informação ou comentário útil que você pode ter </td> 
  </tr> 
 </tbody> 
</table>

* You can find your IMS Org ID on the Experience Cloud, in the **Administration** menu. Ela também é fornecida quando você se conecta pela primeira vez à Adobe Experience Cloud.

## Configuring the integration in Adobe Campaign {#configuring-the-integration-in-adobe-campaign}

Após enviar esta solicitação, a Adobe continuará para o provisionamento da integração para você e entrará em contato com você para fornecer detalhes e informações que você precisa finalizar a configuração:

* [Etapa 1: Configurar ou verificar as contas externas no Adobe Campaign](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [Etapa 2: Configurar as fontes de dados](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources)
* [Etapa 3: Configurar o servidor de rastreamento de campanha](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-3--configure-campaign-tracking-server)
* [Etapa 4: Configurar o serviço de ID do visitante](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-4--configure-the-visitor-id-service)

### Step 1: Configure or check the external accounts in Adobe Campaign {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

Primeiro, precisamos configurar ou verificar as contas externas no Adobe Campaign. Essas contas devem ter sido configuradas pela Adobe e as informações necessárias deveriam ter sido enviadas a você.

Para fazer isso:

1. From the advanced menu, select **Administration &gt; Application settings &gt; External accounts**.

   Selecione uma das seguintes contas externas disponíveis para esta integração:

   ![](assets/integration_aam_1.png)

1. Enter **[!UICONTROL Receiver server]** in following format
1. Enter the **[!UICONTROL AWS Access Key ID]**, **[!UICONTROL Secret Access Key]** and **[!UICONTROL AWS Region]**.

Suas contas externas estão configuradas para essa integração.

### Step 2: Configure the Data Sources {#step-2--configure-the-data-sources}

As duas fontes de dados seguintes são criadas dentro do Audience Manager: Adobe Campaign (MID) e Adobe Campaign (declaredid). Ao mesmo tempo, essas duas fontes de dados estão disponíveis no Adobe Campaign:

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**: Essa é uma fonte de dados predefinida configurada por padrão para a ID do visitante. Os segmentos criados a partir da Campanha serão parte dessa fonte de dados.
* **Fonte de dados da ID** declarada: Essa fonte de dados precisa ser criada e mapeada com a definição da fonte **[!UICONTROL DeclaredId]** de dados do Audience Manager.

Observe que, no caso de vários sites com domínios diferentes, o Adobe Campaign não oferece suporte à reconciliação com base no ECID.

To configure the **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** data source:

1. In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, select **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. Choose **[!UICONTROL Adobe Campaign]** in the **[!UICONTROL Data Source/ Alias]** drop-down.
1. Enter the **[!UICONTROL AAM Destination ID]** provided by Adobe.

   ![](assets/integration_aam_3.png)

1. In the **[!UICONTROL Reconciliation process]** category, we advise you not to change the reconciliation criteria and always use the **[!UICONTROL Visitor ID]**.
1. Click **[!UICONTROL Save]**.

To create the **[!UICONTROL Declared ID]** data source:

1. In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, click the **[!UICONTROL Create]** button.
1. Edit the **[!UICONTROL Label]** of your data source.
1. In the **[!UICONTROL Data Source/ Alias]** drop-down, choose the Data Source corresponding to the **[!UICONTROL DeclaredID]** data source from Audience Manager.
1. Configure your data source by entering the **[!UICONTROL Data Source / Alias]** and **[!UICONTROL AAM Destination ID]** provided by Adobe.
1. Set the **[!UICONTROL Reconciliation process]** as needed.
1. Click **[!UICONTROL Save]**.

>[!NOTE]
>
>**[!UICONTROL AAM Destination ID]** O campo não é necessário se você estiver configurando a fonte de dados compartilhados para a integração [com o Campaign-Aciongers](../../integrating/using/configuring-triggers-in-experience-cloud.md). **[!UICONTROL Priority]** só é necessário ao configurar a integração Acionadores - Campanha. Prioridade determina qual Fonte de Dados será configurada primeiro. A prioridade pode ser qualquer número como 1 ou 100. Quanto maior for a prioridade, maior será a preferência durante a reconciliação.

### Step 3: Configure Campaign Tracking server {#step-3--configure-campaign-tracking-server}

Para a configuração da integração com o serviço Pessoas principais ou o Manager Manager, também é necessário configurar o servidor de rastreamento de campanha.

Aqui, você precisa verificar se o Servidor de rastreamento de campanha está registrado no domínio (CNAME). You can find more information about domain name delegation in [this article](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/Technotes/AdobeCampaign_Deliverability_Sub_Domain_Delegation.pdf).

### Step 4: Configure the Visitor ID Service {#step-4--configure-the-visitor-id-service}

In the case that your Visitor ID service has never been configured on your web properties or websites, refer to the following [document](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-aam-analytics.html) to learn how to configure your service or the following [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

Sua configuração e provisionamento foram finalizados, a integração agora pode ser usada para importar e exportar públicos ou segmentos.
