---
title: Sobre integrações do Campaign
description: O Adobe Campaign permite que você use outras soluções da Adobe e combine seus diferentes recursos.
page-status-flag: never-activated
uuid: 59d7cd99-a6f7-47f1-9b5c-c50e27a2bef8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: about-campaign-integrations
discoiquuid: 9633e9ca-3323-499b-8259-45165d59a4d0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b06edadfa963881403328c4ab37d25d701bc8237

---


# Sobre integrações do Campaign{#about-campaign-integrations}

Esta seção detalha as integrações funcionais disponíveis entre a versão atual do Adobe Campaign e outras soluções e serviços.

As diferentes integrações apresentadas abaixo permitem combinar as funcionalidades de fornecimento e de gerenciamento de campanha avançado do Adobe Campaign com um conjunto de soluções criadas para ajudar a personalizar a experiência dos usuários.

>[!NOTE]
>
> Por padrão, o Adobe Campaign já está vinculado a uma conta da Adobe Experience Cloud.

Dependendo do seu ambiente, outras soluções também podem ser vinculadas à Adobe Experience Cloud. Eles são vinculados como organizações (também chamados de locatários).

Uma organização é a entidade que permite a um administrador configurar grupos e usuários e controlar o logon único na Experience Cloud. A organização funciona como uma empresa de login que abrange todos os produtos e soluções da Experience Cloud. Na maioria das vezes, uma organização é o nome da sua empresa. No entanto, uma empresa pode ter muitas organizações. O gerenciamento de usuários e organizações é detalhado no portal [de ajuda da](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)Adobe Experience Cloud.

Se você quiser integrar fluxos de dados de outros sistemas com o Adobe Campaign, consulte nossa documentação [da](../../api/using/about-campaign-standard-apis.md)API.

>[!NOTE]
>
>O Adobe Campaign Standard também pode se conectar ao Microsoft Dynamics 365: essa integração permite a sincronização de todos os dados de contato disponíveis no sistema CRM, disponibilizando todos os dados de contato relevantes para atividades de campanha. Para obter mais informações sobre essa integração, consulte [Trabalhar com o Campaign e o Dynamics 365](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html).


<table> 
 <thead> 
  <tr> 
   <th> Solução<br /> </th> 
   <th> Use Case<br /> </th> 
   <th> Consulte <br />. </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Experience Manager<br /> 6.1, 6.2, 6.3, 6.4<br /> </td> 
   <td> Permite criar conteúdo de email ou formulários mapeados para o banco de dados do Adobe Campaign diretamente no Adobe Experience Manager.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">Trabalhar com o Campaign e o Experience Manager</a><br/>, <a href="https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html">Integrar o Experience Manager e o Campaign Standard</a> <br/>, <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_AEM.html">Criar um email com o Experience Manager e o Campaign</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Target<br /> Classic, Standard<br /> </td> 
   <td> Allows you to insert images that are dynamically computed by Adobe Target when an email created and sent by Adobe Campaign is opened.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">Trabalhe com o Campaign e o Target</a> , <br/>integre o Campaign e o Target <a href="https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html">,</a><br/>Personalize imagens de email em vídeo em tempo <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html"></a> real (etapa 3)
    </td> 
  </tr> 
  <tr> 
   <td> Analytics<br /> Standard, Premium <br /> </td> 
   <td> Permite rastrear o sucesso de entregas de email diretamente no Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">Compartilhar dados do Campaign com o Analytics</a><br/>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Compartilhar KPIs para vídeo de relatórios</a> integrados do Campaign (etapa 1)
    </td> 
  </tr> 
  <tr> 
   <td> Serviço principal do Adobe Audience Manager e Pessoas (Perfis e públicos-alvo)<br /> </td> 
   <td> Permita que você troque públicos-alvo por diferentes aplicativos da Adobe Experience Cloud que você usa.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">Serviço principal de pessoas (Perfis e públicos-alvo)</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Serviço principal de ativos e ativos sob demanda<br /> </td> 
   <td> Permite inserir ativos da biblioteca da Adobe Experience Cloud em emails e landing pages criadas no Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Serviço</a> ou ativos principais sob demanda<br /> </td> 
  </tr> 
  <tr> 
   <td> Pontos de interesse (Analytics para dispositivos móveis)<br /> </td> 
   <td> Permite coletar dados de Pontos de interesse dos assinantes do aplicativo móvel para enviar mensagens de marketing personalizadas com o Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">Enviar mensagens de marketing baseadas em localização com dados</a> de Campanha e Pontos de interesse (Analytics for Mobile)<br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Cloud Triggers<br /> </td> 
   <td> Permite enviar emails personalizados para seus clientes no Adobe Campaign como uma reação a comportamentos específicos que são rastreados em seu site pelo Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">Usar Acionadores da Experience Cloud no Campaign Standard</a><br/>, Acionadores de <a href="../../integrating/using/abandonment-triggers-use-cases.md">abandono - Casos</a><br/>de uso da campanha, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Acionar mensagens de recomercialização com base no vídeo de Atividade</a> do site (etapa 2)
    </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver<br /> </td> 
   <td> Permite editar um conteúdo de email do Dreamweaver e sincronizá-lo com o Adobe Campaign.<br /> </td> 
   <td> 
    <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">Criar emails personalizados com vídeo do Dreamweaver</a> <br/>, <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Usar extensão da campanha para o Dreamweaver</a> 
  </td> 
  </tr> 
  <tr> 
   <td> SDK de criação<br /> </td> 
   <td> Permite editar imagens e usar um conjunto completo de recursos desenvolvidos pelo Adobe Creative SDK para aprimorar suas imagens diretamente no editor de conteúdo.<br /> </td> 
   <td> <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">Modificação de imagens com o Adobe Creative SDK</a><br /> </td> 
  </tr> 
  <tr> 
   <td> SDKs da plataforma Experience<br /> </td> 
   <td> Permite a automação do processo de ativação da propriedade do aplicativo móvel no Adobe Campaign usando os SDKs da plataforma de experiência.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">Configuração de um aplicativo móvel usando SDKs da plataforma Experience</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

