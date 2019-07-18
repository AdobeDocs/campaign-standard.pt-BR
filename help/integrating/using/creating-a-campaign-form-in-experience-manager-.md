---
title: 'Criação de um formulário de campanha no Experience Manager '
seo-title: 'Criação de um formulário de campanha no Experience Manager '
description: 'Criação de um formulário de campanha no Experience Manager '
seo-description: Com a integração do Adobe Experience Manager, você pode criar formulários diretamente no AEM para criar e atualizar perfis ou gerenciar assinaturas.
page-status-flag: nunca ativado
uuid: 43057 f 81-d 47 d -4 b 96-b 150-217 c 289 cd 608
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 4 a 8 b 5807-87 dd -4 db 4-bd 67-890 f 0 adae 932
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Creating a Campaign form in Experience Manager {#creating-a-campaign-form-in-experience-manager}

É possível criar "formulários" em seus sites AEM e mapear os campos em um formulário para os campos no banco de dados do Adobe Campaign. Isso permite criar e atualizar perfis ou gerenciar assinaturas de um serviço.

Para criar um formulário do Adobe Campaign no site do AEM:

1. No site do AEM, crie uma nova página com base no modelo** Adobe Campaign Profile**.

   ![](assets/aem_content_forms.png)

1. In the page properties, select the **[!UICONTROL Cloud Service]** corresponding to your Adobe Campaign instance.

   ![](assets/aem_content_forms_2.png)

1. Select the form type from the **[!UICONTROL Form Start]** component:

   * **Adobe Campaign: Salvar perfil**
   * **Adobe Campaign: Assinar os serviços**
   * **Adobe Campaign: Cancelar inscrição nos serviços**

1. Edite o conteúdo do formulário adicionando campos e componentes diferentes que você pode mapear para os campos do banco de dados do Adobe Campaign.
1. Teste e publique o formulário para torná-lo acessível no site do AEM.

For more information, refer to the [detailed documentation](https://docs.adobe.com/docs/en/aem/6-2/author/personalization/adobe-campaign/adobe-campaign-forms.html).
