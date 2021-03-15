---
solution: Campaign Standard
product: campaign
title: Provisionamento e configuração da integração com o Audience Manager ou o serviço principal do People
description: 'Saiba como configurar a integração do serviço principal de Pessoas/Audience Manager para começar a compartilhar públicos ou segmentos com as diferentes soluções da Adobe Experience Cloud. '
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Integração do Serviço principal de pessoas
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 42%

---


# Provisionamento e configuração da integração com o Audience Manager ou o serviço principal do People{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

O provisionamento e a configuração do Audience Manager e do núcleo de Pessoas no Adobe Campaign seguem duas etapas: [Envio de solicitação para Adobe](#submitting-request-to-adobe) e então [Configuração da integração no Adobe Campaign](#configuring-the-integration-in-adobe-campaign).

## Envio de solicitação à Adobe {#submitting-request-to-adobe}

A integração do Audience Manager (AAM) ou do serviço principal People permite importar e exportar públicos ou segmentos no Adobe Campaign.

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
   <td> Sua IMS Organization ID. <br> Você pode encontrar sua IMS Organization ID na Experience Cloud, no menu Administração. Também é fornecido ao se conectar pela primeira vez à Adobe Experience Cloud. </td> 
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

Após enviar essa solicitação, o Adobe continuará a provisionar a integração e entrará em contato para fornecer detalhes e informações para você finalizar a configuração:

* [Etapa 1: configurar ou verificar as contas externas no Adobe Campaign](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [Etapa 2: Configurar as fontes de dados](#step-2--configure-the-data-sources)
* [Etapa 3: configurar o servidor de rastreamento do Campaign](#step-3--configure-campaign-tracking-server)
* [Etapa 4: configurar o Serviço de ID de visitante](#step-4--configure-the-visitor-id-service)

### Etapa 1: configurar ou verificar as contas externas no Adobe Campaign {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

Primeiro, precisamos configurar ou verificar as contas externas no Adobe Campaign. Essas contas devem ter sido configuradas pelo Adobe e as informações necessárias devem ter sido comunicadas a você.

Para fazer isso:

1. No menu avançado, selecione **Administration > Application settings > External accounts**.

   Selecione uma das seguintes contas externas disponíveis para essa integração:

   ![](assets/integration_aam_1.png)

1. Insira **[!UICONTROL Receiver server]** no seguinte formato
1. Insira o **[!UICONTROL AWS Access Key ID]**, **[!UICONTROL Secret Access Key]** e **[!UICONTROL AWS Region]**.

Suas contas externas estão configuradas para essa integração.

### Etapa 2: Configurar as Fontes de Dados {#step-2--configure-the-data-sources}

As duas fontes de dados a seguir são criadas dentro do Audience Manager: Adobe Campaign (MID) e Adobe Campaign (DeclarredId). Ao mesmo tempo, essas duas fontes de dados estão disponíveis no Adobe Campaign:

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**: Esta é uma fonte de dados pronta para uso configurada por padrão para a ID do Visitante. Os segmentos criados a partir do Campaign farão parte dessa fonte de dados.
* **Fonte** de dados da ID declarada: Essa fonte de dados precisa ser criada e mapeada com a definição da fonte de  **[!UICONTROL DeclaredId]** dados do Audience Manager.

Observe que, no caso de vários sites com domínios diferentes, o Adobe Campaign não oferece suporte à reconciliação com base na ECID.

Para configurar a fonte de dados do **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**:

1. Em **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, selecione **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. Escolha **[!UICONTROL Adobe Campaign]** no menu suspenso **[!UICONTROL Data Source/ Alias]**.
1. Insira o **[!UICONTROL AAM Destination ID]** fornecido pelo Adobe.

   ![](assets/integration_aam_3.png)

1. Na categoria **[!UICONTROL Reconciliation process]**, recomendamos que você não altere os critérios de reconciliação e sempre use o **[!UICONTROL Visitor ID]**.
1. Clique em **[!UICONTROL Save]**.

Para criar a fonte de dados **[!UICONTROL Declared ID]**:

1. Em **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, clique no botão **[!UICONTROL Create]**.
1. Edite o **[!UICONTROL Label]** de sua fonte de dados.
1. Na lista suspensa **[!UICONTROL Data Source/ Alias]** , escolha a Fonte de Dados correspondente à fonte de dados **[!UICONTROL DeclaredID]** no Audience Manager.
1. Configure sua fonte de dados inserindo os **[!UICONTROL Data Source / Alias]** e **[!UICONTROL AAM Destination ID]** fornecidos pelo Adobe.
1. Defina o **[!UICONTROL Reconciliation process]** conforme necessário.
1. Clique em **[!UICONTROL Save]**.

>[!NOTE]
>
>O campo **[!UICONTROL AAM Destination ID]** não é necessário se você estiver configurando a fonte de dados compartilhada para a [integração Campaign-Triggers](../../integrating/using/configuring-triggers-in-experience-cloud.md). **[!UICONTROL Priority]** só é necessário ao configurar os Acionadores - integração do Campaign. A prioridade decide qual fonte de dados será configurada primeiro. A prioridade pode ser qualquer número, como 1 ou 100. Quanto maior a prioridade, maior a preferência durante a reconciliação.

### Etapa 3: configurar o servidor de rastreamento do Campaign {#step-3--configure-campaign-tracking-server}

Para a configuração da integração com o Serviço Principal de Pessoas ou o Audience Manager, também é necessário configurar o servidor de rastreamento do Campaign.

Aqui, você precisa verificar se o Servidor de rastreamento de campanha está registrado no domínio (CNAME). Você pode encontrar mais informações sobre a configuração do nome de domínio em [este artigo](https://helpx.adobe.com/br/campaign/kb/domain-name-delegation.html).

### Etapa 4: configurar o Serviço de ID de visitante {#step-4--configure-the-visitor-id-service}

Se o serviço de ID do visitante nunca foi configurado em suas propriedades da Web ou sites, consulte este [documento](https://docs.adobe.com/content/help/pt-BR/id-service/using/implementation/setup-aam-analytics.html) para saber como configurar o serviço ou este [vídeo](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

Sua configuração e provisionamento estão finalizados, a integração agora pode ser usada para importar e exportar públicos ou segmentos.
