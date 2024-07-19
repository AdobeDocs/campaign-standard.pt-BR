---
title: Definição de mapeamento
description: Saiba como mapear um campo Campaign Standard com um campo Experience Data Model (XDM).
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 6383ddbe-922a-4363-a1da-166cf717b0dd
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 0%

---

# Definição de mapeamento {#mapping-definition}

>[!IMPORTANT]
>
>O Conector de dados do Adobe Experience Platform está atualmente na versão beta, que pode estar sujeita a atualizações frequentes sem aviso prévio. Os clientes precisam ser hospedados no Azure (atualmente na versão beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar obter acesso.

Nesta seção, você descobrirá como mapear um campo Campaign Standard com um campo Experience Data Model (XDM).

Para executar essa tarefa, os pré-requisitos são:

* uma definição de Esquema XDM por meio da interface ou usando a API REST associada ao XDM
* Criação de um conjunto de dados com base na definição do esquema XDM

1. Vá para **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** e escolha a entrada **[!UICONTROL Data mappings]**.

1. Clique em **[!UICONTROL Create]** para iniciar um novo mapeamento XDM.

   ![](assets/aep_createmapping.png)

1. Preencha os campos obrigatórios e selecione:

   * uma **targeting dimension**: este é o esquema de Campaign Standard a ser mapeado
   * um **conjunto de dados**: este é o pacote de dados associado a um esquema XDM no Adobe Experience Platform.

>[!NOTE]
>
>Para que um lote seja assimilado no Perfil do cliente em tempo real ou no Serviço de identidade, o conjunto de dados deve ser [habilitado para o Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/intro/get-started.html).
>
>Se o conjunto de dados selecionado já estiver sendo usado em um mapeamento de dados existente, um aviso será exibido para informá-lo de que seus dados podem ser substituídos no Adobe Experience Platform. Isso pode acontecer quando há alguns recipients comuns em mapeamentos de dados usando um mesmo conjunto de dados.

A tela a seguir apresenta a seção **[!UICONTROL Field mappings]**, na qual você pode criar um novo mapeamento para cada campo no esquema Campaign Standard.

![](assets/aep_fieldmappings.png)

O botão **[!UICONTROL Create new field mapping]** permite selecionar o campo Campaign Standard e a expressão de caminho de campo correspondente no esquema XDM.

Se não conseguir localizar um campo do Adobe Campaign Standard, você poderá usar o campo de pesquisa para pesquisá-lo. Atualmente, a pesquisa funciona somente para campos abertos na hierarquia.

![](assets/aep_mapfield.png)

Os recursos estendidos definidos no Campaign Standard são mapeados como todos os campos nativos. Eles são definidos na extensão _customer/default no XDM.

![](assets/aep_fieldscusmapping.png)

É possível personalizar a extensão XDM por meio da API e definir sua própria extensão, permitindo um melhor controle sobre o mapeamento.

Consulte o [Tutorial da API do registro de esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html) para obter mais detalhes sobre a API XDM.

Para mapear um campo de enumeração, é necessário usar o editor de expressão para definir cada valor de enumeração correspondente ao valor XDM. Por exemplo, o postaladdressfield precisa ser definido como:

![](assets/aep_enummapping.png)

Se o valor XDM for definido como uma enumeração no Esquema XDM, você poderá usar a função EXDM nativa que substituirá automaticamente a sintaxe **lif**.

![](assets/aep_enummappingexdm.png)

Para editar um mapeamento XDM, abra-o, modifique as informações desejadas e salve-as.

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>Por enquanto, se você editar um valor na seção **[!UICONTROL Field mappings]** e clicar fora do campo, a alteração não será exibida na interface até que você clique no botão **[!UICONTROL Save]**. Esse comportamento ocorre apenas uma vez, quando a edição em **[!UICONTROL Field Mappings]** é a primeira edição na página.
