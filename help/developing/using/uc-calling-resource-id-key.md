---
title: Chamar um recurso usando uma chave de identificação composta
seo-title: Chamar um recurso usando uma chave de identificação composta
description: Chamar um recurso usando uma chave de identificação composta
seo-description: Saiba como chamar um recurso usando uma chave de identificação composta
translation-type: tm+mt
source-git-commit: ff9861a2b8a59843cc668cec9f89b9ea76822d66

---


# Chamar um recurso usando uma chave de identificação composta

Em alguns casos, pode ser necessário definir para um recurso uma chave de identificação composta de dois campos. Após configurar a chave de identificação, é necessário configurar uma definição de filtro para poder chamar o recurso com essa chave de identificação, seja da interface do Campaign Standard ou de apis.

Nesse caso de uso, o **recurso Perfil** foi estendido com o campo " **CRM ID"** personalizado e **"categoria"** . Nós criaremos uma chave de identificação para o recurso Perfil, que será composta desses dois campos. Em seguida, configaremos uma definição de filtro para que possamos acessar o recurso Perfil usando a chave de identificação.

As etapas principais para esse caso de uso são:

1. Configure a chave de identificação do recurso de Perfil, com base nos dois campos.
1. Configure a definição do filtro para poder chamar o recurso Perfil usando sua chave de identificação.
1. Chame o recurso Perfil da interface ou das apis.

Tópicos relacionados:

* [Como criar ou estender o recurso](../../developing/using/creating-or-extending-the-resource.md)
* [Definição de chaves de identificação](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [Apis REST REST da campanha](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)

## Etapa 1: Configurar a chave de identificação

>[!NOTE]
> Os conceitos globais ao configurar chaves de identificação são detalhados nesta [seção](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. Antes de configurar a chave de identificação, certifique-se de que o recurso foi estendido com os campos desejados e que tenha sido publicado. For more on this, refer to [this section](../../developing/using/creating-or-extending-the-resource.md).

1. Acesse o **[!UICONTROL Administration]** / **[!UICONTROL Developement]****[!UICONTROL Custom resources]** /menu e abra o **[!UICONTROL Profile]** recurso.

   ![](assets/uc_idkey1.png)

1. Na **[!UICONTROL Identification keys]** seção, clique no **[!UICONTROL Create element]** botão.

   ![](assets/uc_idkey2.png)

1. Adicione os dois campos personalizados "ID de CRM" e "Categoria" e clique **[!UICONTROL Confirm]** em.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > Se você quiser exibir os dois campos personalizados na interface do perfil, configure a **[!UICONTROL Screen definition]** guia. For more on this, refer to [this section](../../developing/using/configuring-the-screen-definition.md).

1. Agora você pode configurar a definição do filtro para poder chamar o recurso usando sua chave de identificação.

## Etapa 2: Configurar a definição do filtro

>[!NOTE]
> Os conceitos globais ao configurar definições de filtro são detalhados nesta [seção](../../developing/using/configuring-filter-definition.md).

1. Na **[!UICONTROL Filter definition]** guia, clique em **[!UICONTROL Add an element]**, em seguida, insira o rótulo e a ID da definição de filtro.

1. Edite as propriedades da definição de filtro para configurar suas regras.

   ![](assets/uc_idkey4.png)

1. Arraste e solte na área de trabalho a tabela que contém os campos usados na chave de identificação.

   ![](assets/uc_idkey5.png)

1. Selecione o primeiro campo usado na chave de identificação ("ID do CRM") e, em seguida, ative a **[!UICONTROL Switch to parameters]** opção.

   ![](assets/uc_idkey6.png)

1. Na **[!UICONTROL Filter conditions]** seção, mantenha o **[!UICONTROL Equal]** operador, defina o nome do parâmetro e clique no sinal de mais para criá-lo.

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > Após clicar no botão mais, o nome do parâmetro será gerado automaticamente. Observe essas informações, pois será necessário usar o filtro das apis.

1. Repita as etapas acima com todos os campos que compõem a chave de identificação ("categoria") e salve suas alterações.

   ![](assets/uc_idkey8.png)

1. A definição do filtro agora está configurada. Você pode publicar o recurso para que o filtro esteja disponível.

## Etapa 3: Chamar o recurso com base em sua chave de identificação

Depois que a chave de identificação e a definição de filtro forem configuradas, você poderá usá-las para chamar o recurso, seja da interface padrão da campanha ou das apis REST.

Para usar a definição de filtro da interface, use uma **[!UICONTROL Query]** atividade em um fluxo de trabalho (consulte [esta seção](../../automating/using/query.md)). O filtro fica disponível no painel esquerdo.

![](assets/uc_idkey9.png)

Para usar a definição de filtro das apis do Campaign Standard REST, use a sintaxe abaixo:

```
GET /profileAndServicesExt/<resourceName><filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

Em nosso caso, a sintaxe para recuperar um perfil da categoria "primavera" e com a ID de CRM "123456" seria:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/identification_key?category_parameter=spring&crm_id_parameter=123456
```

Para obter mais detalhes, consulte a documentação apis do [Campaign Standard REST](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#filtering).