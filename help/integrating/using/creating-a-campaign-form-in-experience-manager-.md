---
solution: Campaign Standard
product: campaign
title: 'Criar um formulário do Campaign no Experience Manager '
description: Com a integração do Adobe Experience Manager, você pode criar formulários diretamente no AEM para criar e atualizar perfis ou gerenciar assinaturas.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 12%

---


# Criar um formulário do Campaign no Experience Manager {#creating-a-campaign-form-in-experience-manager}

Você pode criar &quot;formulários&quot; nos sites de AEM e mapear os campos em um formulário para os campos no banco de dados do Adobe Campaign. Isso permite criar e atualizar perfis ou gerenciar as assinaturas de um serviço.

Para criar um formulário Adobe Campaign no site AEM:

1. No seu site de AEM, crie uma nova página com base no modelo **Adobe Campaign Profile**.

   ![](assets/aem_content_forms.png)

1. Nas propriedades da página, selecione o **[!UICONTROL Cloud Service]** correspondente à instância do Adobe Campaign.

   ![](assets/aem_content_forms_2.png)

1. Selecione o tipo de formulário no componente **[!UICONTROL Form Start]**:

   * **Adobe Campaign: Salvar perfil**
   * **Adobe Campaign: Inscrever-se nos Serviços**
   * **Adobe Campaign: Cancelar assinatura dos serviços**

1. Edite o conteúdo do formulário adicionando diferentes campos e componentes que podem ser mapeados para os campos do banco de dados do Adobe Campaign.
1. Teste e publique o formulário para torná-lo acessível no site AEM.

Para obter mais informações, consulte a [documentação detalhada](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html).
