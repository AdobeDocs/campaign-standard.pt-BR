---
title: Introdução às integrações do Campaign
description: Use outras soluções de Adobe e combine suas diferentes capacidades com Campanhas.
page-status-flag: never-activated
uuid: 59d7cd99-a6f7-47f1-9b5c-c50e27a2bef8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: get-started-campaign-integrations
discoiquuid: 9633e9ca-3323-499b-8259-45165d59a4d0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d425e4b96604133fbdfc66fde38e4ca5c84baccd
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 90%

---


# Sobre integrações do Campaign{#get-started-campaign-integrations}

Esta seção detalha as integrações funcionais disponíveis entre a versão atual do Adobe Campaign e outras soluções e serviços.

As diferentes integrações apresentadas abaixo permitem combinar o delivery e as funcionalidades avançadas do gerenciamento de campanha do Adobe Campaign com um conjunto de soluções criadas para ajudar a personalizar a experiência dos usuários.

>[!NOTE]
>
> Por padrão, o Adobe Campaign já está vinculado a uma conta da Adobe Experience Cloud.

Dependendo do ambiente, outras soluções podem ser vinculadas à Adobe Experience Cloud. Elas são vinculadas como organizações (também chamadas de locatários).

Uma organização é a entidade que permite a um administrador configurar grupos e usuários e controlar o logon único na Experience Cloud. A organização funciona como uma empresa de login que abrange todos os produtos e soluções da Experience Cloud. Na maioria das vezes, uma organização é o nome da sua empresa. No entanto, uma empresa pode ter muitas organizações. O gerenciamento de usuários e organizações é detalhado no [portal de ajuda da Adobe Experience Cloud](https://docs.adobe.com/content/help/pt-BR/core-services/interface/manage-users-and-products/organizations.html).

Se você quiser integrar fluxos de dados de outros sistemas ao Adobe Campaign, consulte nossa [documentação de API](../../api/using/get-started-apis.md).

>[!NOTE]
>
>O Adobe Campaign Standard também pode se conectar ao Microsoft Dynamics 365: essa integração permite a sincronização de todos os dados de contato disponíveis no sistema CRM, disponibilizando todos os dados de contato relevantes para atividades de campanha. Para obter mais informações sobre essa integração, consulte [Trabalhar com o Campaign e o Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).


<table> 
 <thead> 
  <tr> 
   <th> Solução<br /> </th> 
   <th> Caso de uso<br /> </th> 
   <th> Consulte<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Experience Manager<br /> 6.1, 6.2, 6.3, 6.4, 6.5<br /> </td> 
   <td> Permite criar conteúdo de email ou formulários mapeados para o banco de dados do Adobe Campaign diretamente no Adobe Experience Manager.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">Trabalhe com Campanha e Experience Manager</a>, <a href="https://helpx.adobe.com/br/experience-manager/6-4/sites/administering/using/campaignstandard.html">integre Experience Manager e Campaign Standard</a>, <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_AEM.html">crie um email com Experience Manager e Campanha</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Target<br /> Classic, Standard<br /> </td> 
   <td> Permite inserir imagens que são dinamicamente calculadas pelo Adobe Target quando o email criado e enviado pelo Adobe Campaign é aberto.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">Trabalhe com Campanha e Público alvo</a>, <a href="https://docs.adobe.com/content/help/pt-BR/target/using/integrate/campaign-and-target.html">integre Campanha e Público alvo</a>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Personalize imagens de e-mail em vídeo em tempo</a> real (etapa 3)
    </td> 
  </tr> 
  <tr> 
   <td> Analytics<br /> Standard, Premium <br /> </td> 
   <td> Permite rastrear o sucesso de seus deliveries de email diretamente no Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">Compartilhe dados do Campaign com o Analytics</a>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">compartilhe KPIs para vídeo integrado de relatórios  do Campaign</a> (etapa 1)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager e Serviço principal para pessoas (Perfis e públicos)<br /> </td> 
   <td> Permita a troca de públicos com os diferentes aplicativos da Adobe Experience Cloud que você usa.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">Serviço principal de pessoas (Perfis e públicos)</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Serviço principal de ativos e ativos por demanda<br /> </td> 
   <td> Permite inserir ativos da biblioteca da Adobe Experience Cloud em emails e landing pages criadas no Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Serviço principal de ativos</a> ou ativos por demanda<br /> </td> 
  </tr> 
  <tr> 
   <td> Pontos de interesse (Analytics para dispositivos móveis)<br /> </td> 
   <td> Permite coletar dados de pontos de interesse dos assinantes do aplicativo móvel para enviar mensagens de marketing personalizadas com o Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">Enviar mensagens de marketing de acordo com a localização com dados do Campaign e Pontos de interesse</a> (Analytics para dispositivos móveis)<br /> </td> 
  </tr> 
  <tr> 
   <td> Acionadores da Experience Cloud<br /> </td> 
   <td> Permite enviar emails personalizados para seus clientes no Adobe Campaign como uma reação a comportamentos específicos que são rastreados em seu site pelo Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">Use os acionadores da Experience Cloud no Campaign Standard</a>, <a href="../../integrating/using/abandonment-triggers-use-cases.md">casos de uso de acionadores de abandono do Campaign</a>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">mensagens de remarketing com base no vídeo de atividade do site</a> (etapa 2)
    </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver<br /> </td> 
   <td> Permite editar um conteúdo de email do Dreamweaver e sincronizá-lo com o Adobe Campaign.<br /> </td> 
   <td> 
    <a href="https://docs.adobe.com/content/help/pt-BR/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.translate.html">Criar emails personalizados com vídeo Dreamweaver</a> , <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Usar extensão de Campanha para Dreamweaver</a> 
  </td> 
  </tr> 
  <tr> 
   <td> SDKs da Experience Platform<br /> </td> 
   <td> Permite a automação do processo de ativação de propriedades do aplicativo móvel no Adobe Campaign usando os SDKs da Experience Platform.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/br/campaign/kb/configuring-app-sdk.html">Configurar um aplicativo móvel usando SDKs da Experience Platform</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

