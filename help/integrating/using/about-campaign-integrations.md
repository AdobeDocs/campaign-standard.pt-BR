---
title: Sobre integrações de campanha
seo-title: Sobre integrações de campanha
description: Sobre integrações de campanha
seo-description: O Adobe Campaign permite que você use outras soluções da Adobe e combine seus diferentes recursos.
page-status-flag: nunca ativado
uuid: 59 d 7 cd 99-a 6 f 7-47 f 1-9 b 5 c-c 50 e 27 a 2 bef 8
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: about-campaign-integrations
discoiquuid: 9633 e 9 ca -3323-499 b -8259-45165 d 59 a 4 d 0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 337f2270f3f66d5172084a4e2a19d6185bf097ff

---


# About Campaign integrations{#about-campaign-integrations}

Esta seção detalha as integrações funcionais disponíveis entre a versão atual do Adobe Campaign e outras soluções e serviços.

As diferentes integrações apresentadas abaixo permitem combinar a entrega e as funcionalidades avançadas de gerenciamento de campanha do Adobe Campaign com um conjunto de soluções criadas para ajudar a personalizar a experiência dos usuários.

>[!NOTE]
>
> Por padrão, o Adobe Campaign já está vinculado a uma conta da Adobe Experience Cloud.

Dependendo do seu ambiente, outras soluções também podem ser vinculadas à Adobe Experience Cloud. Eles são vinculados como Organizações (também chamados de Inquilinos).

Uma organização é a entidade que permite ao administrador configurar grupos e usuários, além de controlar o logon único na Experience Cloud. A organização funciona como uma empresa de logon que abrange todos os produtos e soluções da Experience Cloud. Muitas vezes, uma organização é o nome da sua empresa. No entanto, uma empresa pode ter muitas organizações. User and organization management is detailed in the [Adobe Experience Cloud help portal](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html).

If you would like to integrate data flows from other systems with Adobe Campaign, have a look at our [API documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).

>[!NOTE]
>
>O Adobe Campaign Standard também pode se conectar ao Microsoft Dynamics 365: essa integração habilita a sincronização de todos os dados de Contato disponíveis no sistema de CRM, tornando todos os dados relevantes de Contato disponíveis para atividades de campanha. For more on this integration, refer to [Working with Campaign and Dynamics 365](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html).


<table> 
 <thead> 
  <tr> 
   <th> Solution<br /> </th> 
   <th> Use Case<br /> </th> 
   <th> Refer to<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Experience Manager<br /> 6.1, 6.2, 6.3, 6.4<br /> </td> 
   <td> Allows you to create email contents or forms mapped to the Adobe Campaign database directly in Adobe Experience Manager.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">Trabalhar com Campanha e Experience Manager</a><br/>, <a href="https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html">Integrar Experience Manager e Campaign Standard</a><br/>, <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_AEM.html">Criar um e-mail com o Experience Manager e Campaign</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Target<br /> Classic, Standard<br /> </td> 
   <td> Allows you to insert images that are dynamically computed by Adobe Target when an email created and sent by Adobe Campaign is opened.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">Trabalhar com Campanha e Destino</a><br/>, <a href="https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html">Integrar campanha e meta</a><br/>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Personalizar imagens de email em</a> vídeo em tempo real (etapa 3)
    </td> 
  </tr> 
  <tr> 
   <td> Analytics<br /> Standard, Premium <br /> </td> 
   <td> Allows you to track the success of your email deliveries directly in Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">Compartilhar dados de campanha com o Analytics</a><br/>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Compartilhar kpis para vídeo de relatório</a> integrado da campanha (etapa 1)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager and People core service (Profiles &amp; Audiences)<br /> </td> 
   <td> Allow you to exchange audiences with the different Adobe Experience Cloud applications that you use.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">Serviços essenciais para pessoas (perfis e públicos-alvo)</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Asset core service and Assets On Demand<br /> </td> 
   <td> Allows you to insert assets from your Adobe Experience Cloud library into emails and landing pages created in Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Serviços principais</a> ou ativos sob demanda<br /> </td> 
  </tr> 
  <tr> 
   <td> Points of Interest (Analytics for Mobile)<br /> </td> 
   <td> Allows you to collect Points of Interest data from your mobile application's subscribers to send personalized marketing messages with Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">Enviar mensagens de marketing baseadas em local com dados de Campanha e Pontos de interesse</a> (Analytics para dispositivos móveis)<br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Cloud Triggers<br /> </td> 
   <td> Allows you to send personalized emails to your customers in Adobe Campaign as a reaction to specific behaviors that are tracked on your website by Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">Usar Acionadores da Experience Cloud em casos de uso padrão da campanha</a><br/>, <a href="../../integrating/using/abandonment-triggers-use-cases.md">Acionadores de abandono-Campanha</a><br/>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Acionar mensagens de remarketing baseadas no vídeo Atividade</a> do site (etapa 2)
    </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver<br /> </td> 
   <td> Allows you to edit an email content from Dreamweaver and synchronize it with Adobe Campaign.<br /> </td> 
   <td> 
    <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">Criar emails personalizados com</a> o vídeo <br/>do Dreamweaver, <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">usar a extensão de campanha para Dreamweaver</a> 
  </td> 
  </tr> 
  <tr> 
   <td> Creative SDK<br /> </td> 
   <td> Allows you to edit images and use a complete set of features powered by the Adobe Creative SDK to enhance your images directly in the content editor.<br /> </td> 
   <td> <a href="../../designing/using/modifying-images-with-the-adobe-creative-sdk.md">Modificação de imagens com o Adobe Creative SDK</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Platform SDKs<br /> </td> 
   <td> Allows automation of the Mobile App Property activation process in Adobe Campaign using the Experience Platform SDKs.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">Configuração de um aplicativo móvel usando sdks da Experience Platform</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

