---
title: 'Criar um formulário do Campaign no Experience Manager '
description: Com a integração do Adobe Experience Manager, você pode criar formulários diretamente no AEM para criar e atualizar perfis ou gerenciar assinaturas.
page-status-flag: never-activated
uuid: 43057f81-d47d-4b96-b150-217c289cd608
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 4a8b5807-87dd-4db4-bd67-890f0adae932
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5c1a540475b7d93c18c957243ee2a403b8154aa3

---


# Criar um formulário do Campaign no Experience Manager {#creating-a-campaign-form-in-experience-manager}

Você pode criar &quot;formulários&quot; em seus sites do AEM e mapear os campos em um formulário para os campos no banco de dados do Adobe Campaign. Isso permite que você crie e atualize perfis ou gerencie as assinaturas de um serviço.

Para criar um formulário do Adobe Campaign no site do AEM:

1. No site do AEM, crie uma nova página com base no modelo do Perfil **do** Adobe Campaign.

   ![](assets/aem_content_forms.png)

1. Nas propriedades da página, selecione o **[!UICONTROL Cloud Service]**correspondente à sua instância do Adobe Campaign.

   ![](assets/aem_content_forms_2.png)

1. Selecione o tipo de formulário no **[!UICONTROL Form Start]**componente:

   * **Adobe Campaign: Salvar perfil**
   * **Adobe Campaign: Inscrever-se nos Serviços**
   * **Adobe Campaign: Cancelar assinatura dos serviços**

1. Edite o conteúdo do formulário adicionando campos e componentes diferentes que podem ser mapeados para os campos do banco de dados do Adobe Campaign.
1. Teste e publique o formulário para torná-lo acessível no site do AEM.

Para obter mais informações, consulte a [documentação detalhada](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html).
