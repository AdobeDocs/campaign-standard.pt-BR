---
title: Chamada de um recurso usando uma chave de identificação composta
description: Saiba como chamar um recurso usando uma chave de identificação composta
translation-type: tm+mt
source-git-commit: 1e1e1f5f9dd239e45d83330aed74a951a7b332d4
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 6%

---


# Chamada de um recurso usando uma chave de identificação composta{#calling-a-resource-using-a-composite-identification-key}

Em alguns casos, pode ser necessário definir para um recurso uma chave de identificação composta por dois campos. Depois que a chave de identificação é configurada, é necessário configurar uma definição de filtro para poder chamar o recurso com essa chave de identificação, seja da interface do Campaign Standard ou das APIs.

Nesse caso de uso, o recurso de **Perfil** foi estendido com os campos personalizados **&quot;ID do CRM&quot;** e **&quot;categoria&quot;** . Criaremos uma chave de identificação para o recurso do Perfil, que será composta desses dois campos. Em seguida, configuraremos uma definição de filtro, para que possamos acessar o recurso de Perfil usando a chave de identificação.

As principais etapas para este caso de uso são:

1. Configure a chave de identificação do recurso do Perfil, com base nos dois campos.
1. Configure a definição do filtro para poder chamar o recurso do Perfil usando sua chave de identificação.
1. Chame o recurso de Perfil da interface ou do APis.

Tópicos relacionados:

* [Criação ou extensão do recurso](../../developing/using/creating-or-extending-the-resource.md)
* [Definindo chaves de identificação](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [APIs Campaign Standard REST](../../api/using/get-started-apis.md)

## Etapa 1: Configurar a chave de identificação{#step-1-configure-the-identification-key}

>[!NOTE]
> Os conceitos globais ao configurar as chaves de identificação são detalhados [nesta seção](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. Antes de configurar a chave de identificação, verifique se o recurso foi estendido com os campos desejados e se foi publicado. Para obter mais informações, consulte [esta seção](../../developing/using/creating-or-extending-the-resource.md).

1. Vá para o menu **[!UICONTROL Administration]** / **[!UICONTROL Developement]** / **[!UICONTROL Custom resources]** e abra o **[!UICONTROL Profile]** recurso.

   ![](assets/uc_idkey1.png)

1. Na **[!UICONTROL Identification keys]** seção, clique no **[!UICONTROL Create element]** botão.

   ![](assets/uc_idkey2.png)

1. Adicione os dois campos personalizados &quot;ID do CRM&quot; e &quot;Categoria&quot; e clique em **[!UICONTROL Confirm]**.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > Se quiser exibir os dois campos personalizados na interface do perfil, configure a **[!UICONTROL Screen definition]** guia. Para obter mais informações, consulte [esta seção](../../developing/using/configuring-the-screen-definition.md).

1. Agora você pode configurar a definição do filtro para poder chamar o recurso usando sua chave de identificação.

## Etapa 2: Configurar a definição do filtro{#step-2-configure-the-filter-definition}

>[!NOTE]
> Os conceitos globais ao configurar definições de filtro são detalhados na [presente seção](../../developing/using/configuring-filter-definition.md).

1. Na **[!UICONTROL Filter definition]** guia, clique em **[!UICONTROL Add an element]** e insira o rótulo e a ID da definição do filtro.

1. Edite as propriedades da definição de filtro para configurar suas regras.

   ![](assets/uc_idkey4.png)

1. Arraste e solte no espaço de trabalho a tabela que contém os campos usados na chave de identificação.

   ![](assets/uc_idkey5.png)

1. Selecione o primeiro campo usado na chave de identificação (&quot;ID do CRM&quot;) e ative a **[!UICONTROL Switch to parameters]** opção.

   ![](assets/uc_idkey6.png)

1. Na **[!UICONTROL Filter conditions]** seção, mantenha o **[!UICONTROL Equal]** operador, defina o nome do parâmetro e clique no sinal de mais para criá-lo.

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > Depois de clicar no botão mais, o nome do parâmetro é gerado automaticamente. Observe essas informações, pois será necessário usar o filtro das APIs.

1. Repita as etapas acima com todos os campos que compõem a chave de identificação (&quot;categoria&quot;) e salve as alterações.

   ![](assets/uc_idkey8.png)

1. A definição do filtro agora está configurada. Você pode publicar o recurso para que o filtro esteja disponível.

## Etapa 3: Chame o recurso com base em sua chave de identificação{#step-3-call-the-resource-based-on-its-identification-key}

Depois que a chave de identificação e sua definição de filtro estiverem configuradas, você poderá usá-las para chamar o recurso, seja da interface padrão da Campanha ou das APIs REST.

Para usar a definição de filtro da interface, use uma **[!UICONTROL Query]** atividade em um fluxo de trabalho (consulte [esta seção](../../automating/using/query.md)). O filtro fica disponível no painel esquerdo.

![](assets/uc_idkey9.png)

Para usar a definição de filtro das APIs Campaign Standard REST, use a sintaxe abaixo:

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>Para chamar um filtro personalizado, use o prefixo &quot;por&quot; seguido do nome do filtro definido ao configurar a definição do filtro na [etapa 2](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition).

Em nosso caso, a sintaxe para recuperar um perfil da categoria &quot;spring&quot; com a ID do CRM &quot;123456&quot; seria:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

Para obter mais detalhes, consulte a documentação [das APIs REST do](../../api/using/filtering.md)Campaign Standard.