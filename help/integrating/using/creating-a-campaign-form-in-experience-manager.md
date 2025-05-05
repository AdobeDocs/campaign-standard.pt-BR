---
title: Criação de um formulário do Campaign no Experience Manager
description: Com a integração do Adobe Experience Manager, é possível criar formulários diretamente no AEM para criar e atualizar perfis ou gerenciar assinaturas.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 61683639-3f71-4652-a138-acfc0e91e868
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 12%

---

# Criação de um formulário do Campaign no Experience Manager {#creating-a-campaign-form-in-experience-manager}

Você pode criar &quot;formulários&quot; nos sites AEM e mapear os campos em um formulário para os campos no banco de dados do Adobe Campaign. Isso permite criar e atualizar perfis ou gerenciar as assinaturas de um serviço.

Para criar um formulário do Adobe Campaign em seu site AEM:

1. No seu site AEM, crie uma nova página com base no modelo **Perfil do Adobe Campaign**.

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
