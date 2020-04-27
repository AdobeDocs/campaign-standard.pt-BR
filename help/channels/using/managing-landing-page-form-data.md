---
title: Gerenciamento de dados de formulário da página de aterrissagem
description: Saiba como gerenciar dados de formulário de landing page.
page-status-flag: never-activated
uuid: 5b222ea2-6628-457f-a618-bfc0e5eb93dd
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 899c7152-f415-4df9-b4b4-5ff3470a4e32
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8c24e048c698f7ad699e83a753c114fcfd25f6a0

---


# Gerenciamento de dados de formulário da página de aterrissagem{#managing-landing-page-form-data}

## Alteração de propriedades de dados de formulário de landing page{#changing-a-landing-page-form-data-properties}

Você pode vincular campos do banco de dados a blocos de zona de entrada, botão de opção ou tipo de caixa de seleção. Para fazer isso, selecione o bloco e insira-o **[!UICONTROL Form data]** na paleta.

![](assets/delivery_content_9.png)

* The **Field** input zone lets you select a database field to link with the form field.
* The **Mandatory** option lets you only authorize the page&#39;s submission if the user has filled in the field. Se um campo obrigatório não for preenchido, uma mensagem de erro será exibida.

## Mapeamento de campos de formulário {#mapping-form-fields}

Os campos de entrada são usados para armazenar ou atualizar dados no banco de dados de Campanhas. Para isso, é necessário vincular campos do banco de dados a blocos de zona de entrada, botão de opção ou tipo de caixa de seleção. Para fazer isso:

1. Selecione um bloco na landing page.
1. Complete a **[!UICONTROL Form data]** parte da paleta.

   ![](assets/editing_lp_content_4.png)

1. Escolha um campo de banco de dados para vincular ao campo de formulário na zona de **[!UICONTROL Field]** seleção. As Landings page só podem ser mapeadas com **Perfis**.

1. Marque a **[!UICONTROL Mandatory]** opção, se necessário. A página só pode ser enviada se o usuário tiver completado esse campo. Se um campo obrigatório não for concluído, uma mensagem de erro será exibida quando o usuário validar a página.

1. Defina o tipo de campo escolhendo, por exemplo **[!UICONTROL Text]**, **[!UICONTROL Number]** ou **[!UICONTROL Date]** na área de **[!UICONTROL HTML type of the field]** seleção.
Se você escolher um obrigatório **[!UICONTROL Checkbox]**, verifique se ele é do **[!UICONTROL Field]** tipo.

>[!NOTE]
>
>Os campos padrão das landings page incorporadas são pré-configurados. Você pode modificá-los conforme necessário.

## armazenamento de dados e reconciliação{#data-storage-and-reconciliation}

Os parâmetros de reconciliação de dados permitem que você defina como os dados inseridos na landing page serão gerenciados depois que forem submetidos por um usuário.

Para fazer isso:

1. Edite as propriedades de landing page acessadas pelo ![](assets/edit_darkgrey-24px.png) ícone no painel de landing page e exiba os **[!UICONTROL Job]** parâmetros.

   ![](assets/lp_parameters_4.png)

1. Selecione o **[!UICONTROL Reconciliation key]**: esses campos do banco de dados (por exemplo: email, nome e sobrenome) são usados para determinar se o visitante tem um perfil que já é conhecido no banco de dados do Adobe Campaign. Isso permite atualizar ou criar um perfil, de acordo com os parâmetros de estratégia de atualização definidos.
1. Defina o **[!UICONTROL Form parameter mapping]**: esta seção permite mapear os parâmetros do campo de landing page e os usados na chave de reconciliação.
1. Selecione o **[!UICONTROL Update strategy]**: se a chave de reconciliação recuperar um perfil de banco de dados existente, você poderá optar por atualizar esse perfil com os dados inseridos no formulário ou impedir essa atualização.
