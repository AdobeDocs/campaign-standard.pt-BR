---
title: Criação de um formulário do Campaign no Experience Manager
description: Com a integração do Adobe Experience Manager, você pode criar formulários diretamente no AEM para criar e atualizar perfis ou gerenciar assinaturas.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 61683639-3f71-4652-a138-acfc0e91e868
TQID: 'https://experienceleague.adobe.com/5wklRtwZ6Wubvyo-yu2ogEHufoqYBh6cvaJEoBC-Lkk'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0
    internal-label: Triggers
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 11%
---
# Criação de um formulário do Campaign no Experience Manager {#creating-a-campaign-form-in-experience-manager}

Você pode criar &quot;formulários&quot; nos sites do AEM e mapear os campos em um formulário para os campos no banco de dados do Adobe Campaign. Isso permite criar e atualizar perfis ou gerenciar as assinaturas de um serviço.

Para criar um formulário do Adobe Campaign no seu site do AEM:

1. No site do AEM, crie uma nova página com base no modelo **Perfil do Adobe Campaign**.

   ![](assets/aem_content_forms.png)

1. Nas propriedades da página, selecione o **[!UICONTROL Cloud Service]** correspondente à sua instância do Adobe Campaign.

   ![](assets/aem_content_forms_2.png)

1. Selecione o tipo de formulário do componente **[!UICONTROL Form Start]**:

   * **Adobe Campaign: Salvar perfil**
   * **Adobe Campaign: Assinar Serviços**
   * **Adobe Campaign: cancelar assinatura dos serviços**

1. Edite o conteúdo do formulário adicionando diferentes campos e componentes que você pode mapear para os campos do banco de dados do Adobe Campaign.
1. Teste e publique o formulário para torná-lo acessível no site do AEM.

Para obter mais informações, consulte a [documentação detalhada](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html?lang=pt-BR).
