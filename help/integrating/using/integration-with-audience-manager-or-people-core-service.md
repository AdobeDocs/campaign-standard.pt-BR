---
title: Provisionamento e configuração da integração com o Audience Manager ou o Serviço principal de pessoas
description: Saiba como configurar a integração do serviço principal Audience Manager / People para começar a compartilhar públicos ou segmentos com as diferentes soluções da Adobe Experience Cloud.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
exl-id: 04d0fe26-a8cc-49ae-aaa9-b470169068ee
source-git-commit: 26e37cea37b33924ac634c5e4ab7c60804a738f1
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 46%

---

# Provisionamento e configuração da integração com o Audience Manager ou o Serviço principal de pessoas{#integration-with-audience-manager-or-people-core-service}

O provisionamento e a configuração do núcleo de Audience Manager e Pessoas no Adobe Campaign executam duas etapas: [Enviando solicitação para o Adobe](#submitting-request-to-adobe) depois [Configuração da integração no Adobe Campaign](#configuring-the-integration-in-adobe-campaign).

## Envio de solicitação à Adobe {#submitting-request-to-adobe}

A integração do Audience Manager (AAM) ou do serviço principal Pessoas permite importar e exportar públicos ou segmentos no Adobe Campaign.

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
   <td> ID da sua organização. <br> Para encontrar o ID da organização, consulte <a href="https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=pt-BR">esta página</a></td> 
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

Após o envio dessa solicitação, o Adobe continuará a provisionar a integração e entrará em contato para fornecer detalhes e informações para você finalizar a configuração:

* [Etapa 1: configurar ou verificar as contas externas no Adobe Campaign](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [Etapa 2: configurar as Fontes de dados](#step-2--configure-the-data-sources)
* [Etapa 3: configurar o servidor de rastreamento do Campaign](#step-3--configure-campaign-tracking-server)
* [Etapa 4: configurar o Serviço de ID de visitante](#step-4--configure-the-visitor-id-service)

### Etapa 1: configurar ou verificar as contas externas no Adobe Campaign {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

Primeiro, precisamos configurar ou verificar as contas externas no Adobe Campaign. Essas contas devem ter sido configuradas pelo Adobe e as informações necessárias devem ter sido comunicadas a você.

Para fazer isso:

1. No menu avançado, selecione **Administração > Configurações de aplicativo > Contas externas**.

   Selecione uma das seguintes contas externas disponíveis para essa integração:

   ![](assets/integration_aam_1.png)

1. Enter **[!UICONTROL Receiver server]** no seguinte formato
1. Insira o **[!UICONTROL AWS Access Key ID]**, **[!UICONTROL Secret Access Key]** e **[!UICONTROL AWS Region]**.

Suas contas externas estão configuradas para essa integração.

### Etapa 2: configurar as Fontes de dados {#step-2--configure-the-data-sources}

As duas fontes de dados a seguir são criadas no Audience Manager: Adobe Campaign (MID) e Adobe Campaign (DecderedId). Ao mesmo tempo, essas duas fontes de dados estão disponíveis no Adobe Campaign:

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**: esta é uma fonte de dados pronta para uso configurada por padrão para a ID do visitante. Os segmentos criados a partir do Campaign farão parte dessa fonte de dados.
* **ID declarada** fonte de dados: essa fonte de dados precisa ser criada e mapeada com o **[!UICONTROL DeclaredId]** definição de fonte de dados do Audience Manager.

Observe que, no caso de vários sites com domínios diferentes, o Adobe Campaign não oferece suporte à reconciliação com base na ECID.

Para configurar a fonte de dados do **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**:

1. Entrada **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, selecione **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. Escolher **[!UICONTROL Adobe Campaign]** no **[!UICONTROL Data Source/ Alias]** menu suspenso.
1. Insira o **[!UICONTROL AAM Destination ID]** fornecido pela Adobe.

   ![](assets/integration_aam_3.png)

1. No **[!UICONTROL Reconciliation process]** categoria, recomendamos que você não altere os critérios de reconciliação e sempre use o **[!UICONTROL Visitor ID]**.
1. Clique em **[!UICONTROL Save]**.

Para criar o **[!UICONTROL Declared ID]** fonte de dados:

1. Entrada **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, clique no link **[!UICONTROL Create]** botão.
1. Edite o **[!UICONTROL Label]** da sua fonte de dados.
1. No **[!UICONTROL Data Source/ Alias]** selecione a Fonte de dados correspondente à variável **[!UICONTROL DeclaredID]** fonte de dados do Audience Manager.
1. Configure sua fonte de dados inserindo o **[!UICONTROL Data Source / Alias]** e **[!UICONTROL AAM Destination ID]** fornecido pela Adobe.
1. Defina o **[!UICONTROL Reconciliation process]** conforme necessário.
1. Clique em **[!UICONTROL Save]**.

>[!NOTE]
>
>A variável **[!UICONTROL AAM Destination ID]** não será necessário se você estiver configurando a fonte de dados compartilhada para o [Integração entre o Campaign e os acionadores](../../integrating/using/configuring-triggers-in-experience-cloud.md). **[!UICONTROL Priority]** O só é necessário ao configurar a integração Triggers - Campaign. A Prioridade decide qual Fonte de Dados será configurada primeiro. A prioridade pode ser qualquer número, como 1 ou 100. Quanto maior a prioridade, maior a preferência durante a reconciliação.

### Etapa 3: configurar o servidor de rastreamento do Campaign {#step-3--configure-campaign-tracking-server}

Para a configuração da integração com o Serviço principal de pessoas ou o Audience Manager, também é necessário configurar o servidor de rastreamento do Campaign.

Para permitir que os públicos-alvo compartilhados funcionem com a ID de visitante, o domínio do servidor de rastreamento precisa ser um subdomínio do URL clicado ou do site principal.

>[!IMPORTANT]
>
> Certifique-se de que o Servidor de Rastreamento do Campaign está registrado no domínio (CNAME). Você pode encontrar mais informações sobre a configuração do nome de domínio em [este artigo](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/product-specific-resources/campaign/ac-domain-name-setup.html?lang=pt-BR).

### Etapa 4: configurar o Serviço de ID de visitante {#step-4--configure-the-visitor-id-service}

Se o serviço de ID do visitante nunca tiver sido configurado em suas propriedades da web ou sites, consulte este [documento](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-aam-analytics.html?lang=pt-BR) para saber como configurar o serviço ou este [vídeo](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

Sincronize identificadores de clientes com a ID declarada, usando a função `setCustomerID` no serviço de ID da Experience Cloud com o código de integração: `AdobeCampaignID`. O `AdobeCampaignID` deve corresponder ao valor do conjunto de chaves de reconciliação na fonte de dados do destinatário configurada na [Etapa 2: configure as fontes de dados](#step-2--configure-the-data-sources).

Sua configuração e provisionamento estão finalizados, a integração agora pode ser usada para importar e exportar públicos-alvo ou segmentos.
