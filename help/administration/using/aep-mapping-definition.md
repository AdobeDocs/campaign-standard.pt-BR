---
title: Definição de mapeamento
description: Saiba como mapear um campo Campaign Standard com um campo do Modelo de dados de experiência (XDM).
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 327d0e4f862b39c60fb3943d1128f4f42828bc0d

---


# Definição de mapeamento {#mapping-definition}

>[!IMPORTANT]
>
>O serviço Campaign Standard Data está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar acessar.

Nesta seção, você descobrirá como mapear um campo Campaign Standard com um campo do Modelo de dados de experiência (XDM).

Para executar essa tarefa, os pré-requisitos são:

* uma definição de Schema XDM via interface ou usando a REST API associada ao XDM
* uma criação de conjunto de dados com base na definição do schema XDM

1. Vá até **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** e escolha a **[!UICONTROL Data mappings]** entrada.

1. Clique em **[!UICONTROL Create]** para start de um novo mapeamento XDM.

   ![](assets/aep_createmapping.png)

1. Preencha os campos obrigatórios e selecione:

   * um **targeting dimension**: este é o schema Campaign Standard para mapear
   * um **conjunto de dados**: este é o pacote de dados associado a um schema XDM na Adobe Experience Platform.

>[!NOTE]
>
>Para que um lote seja ingerido no Perfil do cliente em tempo real ou no Serviço de identidade, o conjunto de dados deve ser [ativado para o Perfil](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/intro/get-started.html)do cliente em tempo real.
>
>Se o conjunto de dados selecionado já estiver sendo usado em um mapeamento de dados existente, um aviso será exibido para informá-lo de que seus dados podem ser substituídos na Adobe Experience Platform. Isso pode acontecer quando há alguns recipient comuns em datamappings usando um mesmo conjunto de dados.

A tela a seguir apresenta a **[!UICONTROL Field mappings]** seção na qual você pode criar um novo mapeamento para cada campo no schema Campaign Standard.

![](assets/aep_fieldmappings.png)

O **[!UICONTROL Create new field mapping]** botão permite selecionar o campo Campaign Standard e a expressão do caminho do campo correspondente no schema XDM.

Se você não conseguir localizar um campo Campaign Standard, poderá usar o campo de pesquisa para procurar o campo. Atualmente, a pesquisa só funciona para campos que estão abertos na hierarquia.

![](assets/aep_mapfield.png)

Os recursos estendidos definidos no Campaign Standard são mapeados como todos os campos nativos. Eles são definidos na extensão _customer/default no XDM.

![](assets/aep_fieldscusmapping.png)

Você pode personalizar a extensão XDM por meio da API e definir sua própria extensão, permitindo um melhor controle do mapeamento.

Consulte o tutorial [da API do Registro de](https://docs.adobe.com/content/help/en/experience-platform/xdm/api/getting-started.html) Schemas para obter mais detalhes sobre a API XDM.

Para mapear um campo de lista discriminada, é necessário usar o editor de expressão para definir cada valor de lista discriminada correspondente ao valor XDM. Por exemplo, o postalAdressfield precisa ser definido como:

![](assets/aep_enummapping.png)

Se o valor XDM for definido como uma lista discriminada no Schema XDM, você poderá usar a função EXDM nativa que substituirá automaticamente a sintaxe **lif** .

![](assets/aep_enummappingexdm.png)

Para editar um mapeamento XDM, abra-o, modifique as informações desejadas e salve-as.

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>Por enquanto, se você editar um valor na seção e, em seguida, clicar fora do campo, sua alteração não será exibida na interface até que você clique no **[!UICONTROL Field mappings]** **[!UICONTROL Save]** botão. Esse comportamento ocorre apenas uma vez, quando a edição em **[!UICONTROL Field Mappings]** é a primeira edição na página.
