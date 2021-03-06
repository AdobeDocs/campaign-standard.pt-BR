---
title: Chamada de um recurso usando uma chave de identificação composta
description: Saiba como chamar um recurso usando uma chave de identificação composta
feature: Data Model
role: Developer
level: Experienced
exl-id: c7aca0c3-525d-4195-8c04-2fad32ca43b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 7%

---

# Chamada de um recurso usando uma chave de identificação composta{#calling-a-resource-using-a-composite-identification-key}

Em alguns casos, pode ser necessário definir para um recurso uma chave de identificação que seja composta de dois campos. Depois que a chave de identificação estiver configurada, é necessário configurar uma definição de filtro para poder chamar o recurso com essa chave de identificação, da interface do Campaign Standard ou das APIs.

Nesse caso de uso, a variável **Perfil** recurso foi estendido com personalizado **&quot;CRM ID&quot;** e **&quot;category&quot;** campos. Criaremos uma chave de identificação para o recurso Perfil, que será composto desses dois campos. Em seguida, configuraremos uma definição de filtro, para que possamos acessar o recurso de Perfil usando a chave de identificação.

As principais etapas para este caso de uso são:

1. Configure a chave de identificação do recurso Perfil, com base nos dois campos.
1. Configure a definição de filtro, para poder chamar o recurso Perfil usando sua chave de identificação.
1. Chame o recurso Perfil da interface ou da APIs.

Tópicos relacionados:

* [Criação ou extensão do recurso](../../developing/using/creating-or-extending-the-resource.md)
* [Definição de chaves de identificação](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [APIs REST do Campaign Standard](../../api/using/get-started-apis.md)

## Etapa 1: Configurar a chave de identificação{#step-1-configure-the-identification-key}

>[!NOTE]
> Os conceitos globais ao configurar as chaves de identificação são detalhados em [esta seção](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. Antes de configurar a chave de identificação, verifique se o recurso foi estendido com os campos desejados e se foi publicado. Para obter mais informações, consulte [esta seção](../../developing/using/creating-or-extending-the-resource.md).

1. Vá para o **[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Custom resources]** , em seguida, abra o **[!UICONTROL Profile]** recurso.

   ![](assets/uc_idkey1.png)

1. No **[!UICONTROL Identification keys]** clique no botão **[!UICONTROL Create element]** botão.

   ![](assets/uc_idkey2.png)

1. Adicione os dois campos personalizados &quot;ID do CRM&quot; e &quot;Categoria&quot; e, em seguida, clique em **[!UICONTROL Confirm]**.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > Se quiser exibir os dois campos personalizados na interface do perfil, configure a variável **[!UICONTROL Screen definition]** guia . Para obter mais informações, consulte [esta seção](../../developing/using/configuring-the-screen-definition.md).

1. Agora você pode configurar a definição de filtro para poder chamar o recurso usando sua chave de identificação.

## Etapa 2: Configurar a definição de filtro{#step-2-configure-the-filter-definition}

>[!NOTE]
> Os conceitos globais ao configurar definições de filtro são detalhados em [esta seção](../../developing/using/configuring-filter-definition.md).

1. No **[!UICONTROL Filter definition]** clique em **[!UICONTROL Add an element]**, em seguida, insira o rótulo e a ID da definição de filtro.

1. Edite as propriedades da definição de filtro para configurar suas regras.

   ![](assets/uc_idkey4.png)

1. Arraste e solte no espaço de trabalho a tabela que contém os campos usados na chave de identificação.

   ![](assets/uc_idkey5.png)

1. Selecione o primeiro campo usado na chave de identificação (&quot;ID do CRM&quot;) e ative o **[!UICONTROL Switch to parameters]** opção.

   ![](assets/uc_idkey6.png)

1. No **[!UICONTROL Filter conditions]** mantenha **[!UICONTROL Equal]** , defina o nome do parâmetro e clique no sinal de mais para criá-lo.

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > Depois de clicar no botão **+** , o nome do parâmetro é gerado automaticamente. Observe essas informações, pois será necessário usar o filtro das APIs.

1. Repita as etapas acima com todos os campos que compõem a chave de identificação (&quot;categoria&quot;) e salve as alterações.

   ![](assets/uc_idkey8.png)

1. A definição do filtro está configurada. Você pode publicar o recurso para que o filtro esteja disponível.

## Etapa 3: Chamar o recurso com base em sua chave de identificação{#step-3-call-the-resource-based-on-its-identification-key}

Depois que a chave de identificação e sua definição de filtro forem configuradas, você poderá usá-las para chamar o recurso, na interface padrão do Campaign ou em APIs REST.

Para usar a definição de filtro da interface, use um **[!UICONTROL Query]** em um fluxo de trabalho (consulte [esta seção](../../automating/using/query.md)). O filtro estará disponível no painel esquerdo.

![](assets/uc_idkey9.png)

Para usar a definição de filtro das APIs REST do Campaign Standard, use a sintaxe abaixo:

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>Para chamar um filtro personalizado, use o prefixo &quot;by&quot; seguido do nome do filtro definido ao configurar a definição do filtro em [etapa 2](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition).

No nosso caso, a sintaxe para recuperar um perfil da categoria &quot;Spring&quot; com a ID do CRM &quot;123456&quot; seria:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

Para obter mais detalhes, consulte [Documentação das APIs REST do Campaign Standard](../../api/using/filtering.md).
