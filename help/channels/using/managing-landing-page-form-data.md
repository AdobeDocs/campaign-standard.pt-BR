---
solution: Campaign Standard
product: campaign
title: Gerenciamento de dados de formulário de landing page
description: Saiba como gerenciar dados de formulário de landing page.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
feature: Landing Pages
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 99%

---


# Gerenciamento de dados de formulário de landing page{#managing-landing-page-form-data}

## Alteração das propriedades dos dados de formulário de landing page{#changing-a-landing-page-form-data-properties}

Você pode vincular campos de banco de dados à zona de entrada, ao botão de opção ou aos blocos de tipo de caixa de seleção. Para isso, selecione o bloco e insira o **[!UICONTROL Form data]** na paleta.

![](assets/delivery_content_9.png)

* A zona de entrada **Field** permite selecionar um campo de banco de dados a ser vinculado ao campo de formulário.
* A opção **Mandatory** permite autorizar o envio da página somente se o usuário tiver preenchido o campo. Se um campo obrigatório não estiver preenchido, uma mensagem de erro será exibida.

## Mapeamento de campos de formulário {#mapping-form-fields}

Os campos de entrada são usados para armazenar ou atualizar dados no banco de dados do Campaign. Para isso, você precisa vincular campos de banco de dados à zona de entrada, ao botão de opção ou aos blocos de tipo de caixa de seleção. Para fazer isso:

1. Selecione um bloco na landing page.
1. Preencha a parte **[!UICONTROL Form data]** na paleta.

   ![](assets/editing_lp_content_4.png)

1. Escolha um campo de banco de dados a ser vinculado ao campo de formulário na zona de seleção **[!UICONTROL Field]**. As landing pages só podem ser mapeadas com **Perfis**.

1. Marque a opção **[!UICONTROL Mandatory]**, se necessário. A página só poderá ser enviada se o usuário tiver preenchido esse campo. Se um campo obrigatório não estiver preenchido, uma mensagem de erro será exibida quando o usuário validar a página.

1. Defina o tipo de campo escolhendo, por exemplo **[!UICONTROL Text]**, **[!UICONTROL Number]** ou **[!UICONTROL Date]** na área de seleção **[!UICONTROL HTML type of the field]**.
Se você escolher uma **[!UICONTROL Checkbox]** obrigatória, verifique se ela é do tipo **[!UICONTROL Field]**.

>[!NOTE]
>
>Os campos padrão das landing pages incorporadas são pré-configurados. Você pode modificá-los conforme necessário.

## Armazenamento e reconciliação de dados{#data-storage-and-reconciliation}

Os parâmetros de reconciliação de dados permitem definir como os dados inseridos na landing page serão gerenciados depois que forem enviados por um usuário.

Para fazer isso:

1. Edite as propriedades de landing page acessadas pelo ícone ![](assets/edit_darkgrey-24px.png) no painel da landing page e exiba os parâmetros **[!UICONTROL Job]**.

   ![](assets/lp_parameters_4.png)

1. Selecione a **[!UICONTROL Reconciliation key]**: esses campos de banco de dados (por exemplo: email, nome, sobrenome) são usados para determinar se o visitante tem um perfil já conhecido no banco de dados do Adobe Campaign. Isso permite atualizar ou criar um perfil, de acordo com os parâmetros de estratégia de atualização definidos.
1. Defina o **[!UICONTROL Form parameter mapping]**: esta seção permite mapear os parâmetros do campo de landing page e os usados na chave de reconciliação.
1. Selecione a **[!UICONTROL Update strategy]**: se a chave de reconciliação recuperar um perfil de banco de dados, você poderá optar por atualizar esse perfil com os dados inseridos no formulário ou impedir essa atualização.
