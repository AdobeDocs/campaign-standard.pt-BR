---
solution: Campaign Standard
product: campaign
title: Definição de mapeamento
description: Saiba como mapear um campo Campaign Standard com um campo do Modelo de dados de experiência (XDM).
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 2729852365a2e74d2a603d95f75285fe54313e71
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 2%

---


# Definição de mapeamento {#mapping-definition}

>[!IMPORTANT]
>
>O Adobe Experience Platform Data Connector está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar acessá-lo.

Nesta seção, você descobrirá como mapear um campo Campaign Standard com um campo do Modelo de dados de experiência (XDM).

Para executar essa tarefa, os pré-requisitos são:

* uma definição de Schema XDM via interface ou usando a REST API associada ao XDM
* uma criação de conjunto de dados com base na definição do schema XDM

1. Vá para **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** e escolha a entrada **[!UICONTROL Data mappings]**.

1. Clique em **[!UICONTROL Create]** para start de um novo mapeamento XDM.

   ![](assets/aep_createmapping.png)

1. Preencha os campos obrigatórios e selecione:

   * a **targeting dimension**: este é o schema Campaign Standard para mapear
   * a **conjunto de dados**: este é o pacote de dados associado a um schema XDM no Adobe Experience Platform.

>[!NOTE]
>
>Para que um lote seja ingerido no Perfil do cliente em tempo real ou no Serviço de identidade, o conjunto de dados deve estar [ativado para o Perfil do cliente em tempo real](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/intro/get-started.html).
>
>Se o conjunto de dados selecionado já estiver sendo usado em um mapeamento de dados existente, um aviso será exibido para informá-lo de que seus dados podem ser substituídos no Adobe Experience Platform. Isso pode acontecer quando há alguns recipient comuns em datamappings usando um mesmo conjunto de dados.

A tela a seguir apresenta a seção **[!UICONTROL Field mappings]**, na qual você pode criar um novo mapeamento para cada campo no schema Campaign Standard.

![](assets/aep_fieldmappings.png)

O botão **[!UICONTROL Create new field mapping]** permite selecionar o campo Campaign Standard e a expressão do caminho do campo correspondente no schema XDM.

Se você não conseguir localizar um campo do Adobe Campaign Standard, poderá usar o campo de pesquisa para pesquisar pelo campo. Atualmente, a pesquisa só funciona para campos que estão abertos na hierarquia.

![](assets/aep_mapfield.png)

Os recursos estendidos definidos no Campaign Standard são mapeados como todos os campos nativos. Eles são definidos na extensão _customer/default no XDM.

![](assets/aep_fieldscusmapping.png)

Você pode personalizar a extensão XDM por meio da API e definir sua própria extensão, permitindo um melhor controle do mapeamento.

Consulte [tutorial da API do Registro do Schema](https://docs.adobe.com/content/help/pt-BR/experience-platform/xdm/api/getting-started.html) para obter mais detalhes sobre a API XDM.

Para mapear um campo de lista discriminada, é necessário usar o editor de expressão para definir cada valor de lista discriminada correspondente ao valor XDM. Por exemplo, o postalAdressfield precisa ser definido como:

![](assets/aep_enummapping.png)

Se o valor XDM for definido como uma lista discriminada no Schema XDM, você poderá usar a função EXDM nativa que substituirá automaticamente a sintaxe **lif**.

![](assets/aep_enummappingexdm.png)

Para editar um mapeamento XDM, abra-o, modifique as informações desejadas e salve-as.

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>Por enquanto, se você editar um valor na seção **[!UICONTROL Field mappings]** e clicar fora do campo, sua alteração não será exibida na interface até que você clique no botão **[!UICONTROL Save]**. Esse comportamento ocorre apenas uma vez, quando a edição em **[!UICONTROL Field Mappings]** é a primeira edição na página.
