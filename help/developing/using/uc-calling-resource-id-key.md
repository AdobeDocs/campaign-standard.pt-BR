---
title: Chamar um recurso usando uma chave de identificação composta de dois campos
seo-title: Chamar um recurso usando uma chave de identificação composta de dois campos
description: Chamar um recurso usando uma chave de identificação composta de dois campos
seo-description: Saiba como chamar um recurso usando uma chave de identificação composta de dois campos
translation-type: tm+mt
source-git-commit: b46579e3bf270b26986e107be9d8e07a39841b38

---


# Chamar um recurso usando uma chave de identificação composta de dois campos

Em alguns casos, pode ser necessário definir para um recurso uma chave de identificação composta de dois campos. Após configurar a chave de identificação, é necessário configurar uma definição de filtro para poder chamar o recurso com essa chave de identificação, seja da interface do Campaign Standard ou de apis.

In this use case, the **Profile** resource has been extended with custom **"CRM ID"** and **"category"** field. Nós criaremos uma chave de identificação para o recurso Perfil, que será composta desses dois campos. Em seguida, configaremos uma definição de filtro para que possamos acessar o recurso Perfil usando a chave de identificação.

Estas etapas principais para esse caso de uso são:

1. Configure a chave de identificação do recurso de Perfil, com base nos dois campos.
1. Configure a definição do filtro para poder chamar o recurso Perfil usando sua chave de identificação.
1. Chame o recurso Perfil da interface ou das apis.

Tópicos relacionados:

* [Como criar ou estender o recurso](help/developing/using/creating-or-extending-the-resource.md)
* [Definição de chaves de identificação](help/developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [Apis REST REST da campanha](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)

## Etapa 1: Configurar a chave de identificação

>[!NOTE]
> Global concepts when configuring identification keys are detailed in [this section](help/developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. Antes de configurar a chave de identificação, certifique-se de que o recurso foi estendido com os campos desejados e que tenha sido publicado. For more on this, refer to [this section](help/developing/using/creating-or-extending-the-resource.md).

1. Go to the **[!UICONTROL Administration]** / **[!UICONTROL Developement]** / **[!UICONTROL Custom resources]** menu, then open the **[!UICONTROL Profile]** resource.

   ![](assets/uc_idkey1.png)

1. In the **[UICONTROL Identification keys]** section, click the **[!UICONTROL Create element]** button.

   ![](assets/uc_idkey2.png)

1. Add the two custom "CRM ID" and "Category" fields, then click **[UICONTROL Confirm]**.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > If you want to display the two custom fields in the profile's interface, configure the **[UICONTROL Screen definition]** tab. For more on this, refer to [this section](help/developing/using/configuring-the-screen-definition.md).

1. Agora você pode configurar a definição do filtro para poder chamar o recurso usando sua chave de identificação.

## Etapa 2: Configurar a definição do filtro

>[!NOTE]
> Global concepts when configuring filter definitions are detailed in [this section](help/developing/using/configuring-filter-definition.md).

1. In the **[UICONTROL Filter definition]** tab, click **[UICONTROL Add an element]**, then enter the filter definition's label and ID.

1. Edite as propriedades da definição de filtro para configurar suas regras.

   ![](assets/uc_idkey4.png)

1. Arraste e solte na área de trabalho a tabela que contém os campos usados na chave de identificação.

   ![](assets/uc_idkey5.png)

1. Select the first field used in the identification key ("CRM ID"), then activate the **[UICONTROL Switch to parameters]** option.

   ![](assets/uc_idkey6.png)

1. In the **[UICONTROL Filter conditions]** section, keep the **[UICONTROL Equal]** operator, then define the parameter's name and click the plus sign to create it.

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > Após clicar no botão mais, o nome do parâmetro será gerado automaticamente. Observe essas informações, pois será necessário usar o filtro das apis.

1. Repita as etapas acima com todos os campos que compõem a chave de identificação ("categoria") e salve suas alterações.

   ![](assets/uc_idkey8.png)

1. A definição do filtro agora está configurada. Você pode publicar o recurso para que o filtro esteja disponível.

## Etapa 3: Chamar o recurso com base em sua chave de identificação

Depois que a chave de identificação e a definição de filtro forem configuradas, você poderá usá-las para chamar o recurso, seja da interface padrão da campanha ou das apis REST.

To use the filter definition from the interface, use a **[UICONTROL Query]** activity in a workflow (see [this section](help/automating/using/query.md)). O filtro fica disponível no painel esquerdo.

![](assets/uc_idkey9.png)

Para usar a definição de filtro das apis do Campaign Standard REST, use a sintaxe abaixo:

\ «GET /profileAndServicesExt/ &lt; resourcename &gt; &lt; filtername &gt;? &lt; param 1_ parameter &gt; = &lt; value &gt; &amp; &lt; param 2_ parameter &gt; = &lt; value &gt;\ "

Em nosso caso, a sintaxe para recuperar um perfil da categoria "primavera" e com a ID de CRM "123456" seria:

\ «GET https://mc.adobe.io/ &lt; ORGANIZATION &gt;/campaign/profileandservicesext/profile/identification_ key? category_ parameter = spring &amp; crm_ id_ parameter = 123456\ «

For more details, refer to [Campaign Standard REST APIs documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#filtering).