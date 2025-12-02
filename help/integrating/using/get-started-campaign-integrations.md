---
title: Introdução às integrações do Campaign
description: Use outras soluções da Adobe e combine suas diferentes funcionalidades com o Campaign.
audience: integrating
content-type: reference
topic-tags: get-started-campaign-integrations
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ecf88c7d-6729-4b3a-85c4-60427bb57442
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 78%

---

# Sobre integrações do Campaign{#get-started-campaign-integrations}

Esta seção detalha as integrações funcionais disponíveis entre a versão atual do Adobe Campaign e outras soluções e serviços.

As diferentes integrações apresentadas abaixo permitem combinar a entrega e as funcionalidades avançadas do gerenciamento de campanha do Adobe Campaign com um conjunto de soluções criadas para ajudar a personalizar a experiência dos usuários.

>[!NOTE]
>
> Por padrão, o Adobe Campaign já está vinculado a uma conta da Adobe Experience Cloud.

Dependendo do ambiente, outras soluções podem ser vinculadas à Adobe Experience Cloud. Elas são vinculadas como organizações (também chamadas de locatários).

Uma organização é a entidade que permite a um administrador configurar grupos e usuários e controlar o logon único na Experience Cloud. A organização funciona como uma empresa de login que abrange todos os produtos e soluções da Experience Cloud. Na maioria das vezes, uma organização é o nome da sua empresa. No entanto, uma empresa pode ter muitas organizações. O gerenciamento de usuários e organizações é detalhado no [portal de ajuda da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=pt-BR).

Se você quiser integrar fluxos de dados de outros sistemas ao Adobe Campaign, consulte nossa [documentação de API](../../api/using/get-started-apis.md).

>[!NOTE]
>
>O Adobe Campaign Standard também pode se conectar ao Microsoft Dynamics 365: essa integração permite a sincronização de todos os dados de contato disponíveis no sistema CRM, disponibilizando todos os dados de contato relevantes para atividades de campanha. Para obter mais informações sobre essa integração, consulte [Trabalhar com o Campaign e o Dynamics 365](../../integrating/using/d365-acs-get-started.md).


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
   <td> Adobe Experience Manager<br /> </td> 
   <td> Permite criar conteúdo de email ou formulários mapeados para o banco de dados do Adobe Campaign diretamente no Adobe Experience Manager.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">Trabalhe com o Campaign e o Experience Manager</a>, <a href="https://helpx.adobe.com/br/experience-manager/6-4/sites/administering/using/campaignstandard.html">Integre o Experience Manager e o Campaign Standard</a>, <a href="https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html?lang=pt-BR">Crie um email com o Experience Manager e o Campaign</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Target<br /> </td> 
   <td> Permite inserir imagens que são dinamicamente calculadas pelo Adobe Target quando o email criado e enviado pelo Adobe Campaign é aberto.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">Trabalhar com o Campaign e o Target</a>, <a href="https://experienceleague.adobe.com/docs/target/using/integrate/campaign-and-target.html?lang=pt-BR">Integrar o Campaign e o Target</a>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Personalizar imagens de email em vídeos em tempo real</a> (etapa 3)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Analytics<br /> </td> 
   <td> Permite rastrear o sucesso de suas entregas de email diretamente no Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">Compartilhe dados do Campaign com o Analytics</a>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">compartilhe KPIs para vídeo integrado de relatórios  do Campaign</a> (etapa 1)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager e Serviço principal para pessoas (Perfis e públicos)<br /> </td> 
   <td> Permita a troca de públicos-alvos com os diferentes aplicativos da Adobe Experience Cloud que você usa.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">Serviço principal de pessoas (Perfis e públicos-alvos)</a><br /> </td> 
  </tr> 
   <tr> 
   <td> Plataforma de dados do cliente em tempo real (RTCDP) da Adobe <br /> </td> 
   <td> A integração entre o Adobe Campaign e a Adobe Real-time Customer Data Platform (RTCDP) permite compartilhar dados de segmentos e importar públicos para a Adobe Campaign.</td>
   <td><a href="../../integrating/using/get-started-sources-destinations.md">Introdução a origens e destinos</a></td>
  </tr> 
  <tr> 
   <td> Serviço principal de ativos da Adobe e Assets On Demand<br /> </td> 
   <td> Permite inserir ativos da biblioteca da Adobe Experience Cloud em emails e landing pages criadas no Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Serviço principal de ativos</a> ou ativos por demanda<br /> </td> 
  </tr> 
  <tr> 
   <td> Pontos de interesse (Analytics para dispositivos móveis)<br /> </td> 
   <td> Permite coletar dados de pontos de interesse dos assinantes do aplicativo móvel para enviar mensagens de marketing personalizadas com o Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">Enviar mensagens de marketing de acordo com a localização com dados do Campaign e Pontos de interesse</a> (Analytics para dispositivos móveis)<br /> </td> 
  </tr> 
  <tr> 
   <td> Acionadores da Adobe Experience Cloud<br /> </td> 
   <td> Permite enviar emails personalizados para seus clientes no Adobe Campaign como uma reação a comportamentos específicos que são rastreados em seu site pelo Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">Use os acionadores da Experience Cloud no Campaign Standard</a>, <a href="../../integrating/using/abandonment-triggers-use-cases.md">casos de uso de acionadores de abandono do Campaign</a>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">mensagens de remarketing com base no vídeo de atividade do site</a> (etapa 2)
    </td> 
  </tr> 
    <tr> 
   <td> Adobe Journey Orchestration<br /> </td> 
   <td> Permite enviar emails, notificações por push e SMS usando os recursos de Mensagens Transacionais do Adobe Campaign Standard no contexto do Adobe Journey Orchestration, por meio de uma ação pronta para uso.<br /> </td> 
   <td> <a href="https://experienceleague.adobe.com/docs/journeys/using/action-journeys/working-with-adobe-campaign.html?lang=pt-BR">Trabalhando com o Adobe Journey Orchestration e o Adobe Campaign Standard</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Dreamweaver<br /> </td> 
   <td> Permite editar um conteúdo de email do Dreamweaver e sincronizá-lo com o Adobe Campaign.<br /> </td> 
   <td> 
    <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=pt-BR">Criar emails personalizados com vídeo do Dreamweaver</a>, <a href="https://helpx.adobe.com/br/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Usar extensão do Campaign para o Dreamweaver</a> 
  </td> 
  </tr> 
  <tr> 
   <td> SDKs do Adobe Experience Platform<br /> </td> 
   <td> Permite a automação do processo de ativação de propriedades do aplicativo móvel no Adobe Campaign usando os SDKs da Experience Platform.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/br/campaign/kb/configuring-app-sdk.html">Configurar um aplicativo móvel usando SDKs da Experience Platform</a><br /> </td> 
  </tr> 
 </tbody> 
</table>
