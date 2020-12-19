---
solution: Campaign Standard
product: campaign
title: 'Criar um formulário do Campaign no Experience Manager '
description: Com a integração do Adobe Experience Manager, você pode criar formulários diretamente no AEM para criar e atualizar perfis ou gerenciar subscrição.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 12%

---


# Criar um formulário do Campaign no Experience Manager {#creating-a-campaign-form-in-experience-manager}

Você pode criar &quot;formulários&quot; em seus sites AEM e mapear os campos em um formulário para os campos no banco de dados Adobe Campaign. Isso permite criar e atualizar perfis ou gerenciar as subscrições em um serviço.

Para criar um formulário Adobe Campaign no site AEM:

1. No site AEM, crie uma nova página com base no modelo **Perfil Adobe Campaign**.

   ![](assets/aem_content_forms.png)

1. Nas propriedades da página, selecione **[!UICONTROL Cloud Service]** correspondente à sua instância do Adobe Campaign.

   ![](assets/aem_content_forms_2.png)

1. Selecione o tipo de formulário no componente **[!UICONTROL Form Start]**:

   * **Adobe Campaign: Salvar perfil**
   * **Adobe Campaign: Inscrever-se nos Serviços**
   * **Adobe Campaign: Cancelar assinatura dos serviços**

1. Edite o conteúdo do formulário adicionando campos e componentes diferentes que podem ser mapeados para os campos do banco de dados da Adobe Campaign.
1. Teste e publique o formulário para torná-lo acessível no site AEM.

Para obter mais informações, consulte a [documentação detalhada](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html).
