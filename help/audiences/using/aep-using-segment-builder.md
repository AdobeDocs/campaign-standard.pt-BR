---
title: Uso do Construtor de segmentos
description: Saiba como usar o Construtor de segmentos para criar audiências.
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: be7ab90583e9c6472fd2c86082e832432d0a32b9
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 2%

---


# Using the Segment Builder {#using-the-segment-builder}

>[!IMPORTANT]
>
>O serviço Destinos de Audiência está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar acessar.

O Construtor de segmentos permite criar audiências definindo regras com base nos dados provenientes do Perfil [Cliente em tempo](https://docs.adobe.com/content/help/pt-BR/experience-platform/profile/home.html)real.

Esta seção apresenta conceitos globais ao criar um segmento. Para obter informações detalhadas sobre o Construtor de segmentos propriamente dito, consulte o guia [do usuário do Construtor de](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)segmentos.

A interface do Construtor de segmentos é composta da seguinte maneira:

* O painel esquerdo fornece todos os atributos, eventos e audiências disponíveis para criar o segmento arrastando e soltando os campos desejados na área de trabalho do construtor de segmentos.
* A área central fornece um espaço de trabalho para criar o segmento definindo e combinando regras dos campos disponíveis.
* O painel do cabeçalho e direito exibe as propriedades do segmento (ou seja, nome, descrição e perfis qualificados estimados para o segmento).

![](assets/aep_audiences_interface.png)

## Criação de um segmento

Para criar um segmento, siga estas etapas:

O Construtor de segmentos agora deve ser exibido em sua área de trabalho. Ele permite que você crie um segmento usando dados do Adobe Experience Platform que eventualmente serão usados para criar sua audiência.

1. Nomeie o segmento e insira uma descrição (opcional).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Certifique-se de que a política de mesclagem desejada esteja selecionada no painel de configurações.

   Para obter mais informações sobre políticas de mesclagem, consulte a seção dedicada no guia [do usuário do Construtor de](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)segmentos.

   ![](assets/aep_audiences_mergepolicy.png)

1. Procure os campos desejados no painel esquerdo e arraste-os para a área de trabalho central.

   ![](assets/aep_audiences_dragfield.png)

1. Configure as regras correspondentes aos campos arrastados.

   ![](assets/aep_audiences_configure_rules.png)

1. Clique no botão **[!UICONTROL Create segment]**.

## Encontrar os campos certos para um segmento

O painel esquerdo lista todos os atributos, eventos e audiências disponíveis para uso na construção de regras.

Os campos listados são atributos capturados pela sua empresa e disponibilizados pelo sistema [](https://docs.adobe.com/content/help/pt-BR/experience-platform/xdm/home.html)Experience Data Model (XDM).

Os campos são organizados em guias:

* **[!UICONTROL Attributes]**: Atributos de perfis existentes que podem se originar do banco de dados e/ou Adobe Experience Platform. Referem-se a informações estáticas anexadas a um perfil (por exemplo, endereço de email, país de residência, status do programa de fidelidade, etc.).

   ![](assets/aep_audiences_attributestab.png)

* **[!UICONTROL Events]**: Atividades que identificam os consumidores que tiveram alguma interação com seus pontos de contato com o empresa, como &quot;qualquer pessoa que solicitou duas vezes em duas semanas&quot;. Isso pode ser transmitido do Adobe Analytics ou ingerido diretamente no Adobe Experience Platform usando ferramentas ETL de terceiros.

   ![](assets/aep_audiences_eventstab.png)

>[!NOTE]
>
>**A segmentação** de várias entidades permite estender os dados do Perfil com dados adicionais baseados em produtos, lojas ou outras classes que não sejam de perfil. Depois de conectados, os dados de classes adicionais ficam disponíveis como se fossem nativos para o schema do Perfil.
>
>For more on this, refer to the [dedicated documentation](https://docs.adobe.com/content/help/en/experience-platform/segmentation/multi-entity-segmentation.html).

Por padrão, o Construtor de segmentos exibe campos nos quais os dados já estão presentes. Para exibir o schema completo, incluindo campos para os quais os dados não estão presentes, ative a opção **[!UICONTROL Show full XDM schema]** nas configurações.

![](assets/aep_audiences_populatedfields.png)

O símbolo no final de cada campo fornece informações adicionais sobre o atributo e como usá-lo.

![](assets/aep_audiences_isymbol.png)

## Definição de regras para um segmento

>[!NOTE]
>
>A seção abaixo fornece informações globais sobre a definição de regras. Para obter mais informações, consulte o guia [do usuário do Construtor de](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)segmentos.

Para criar uma regra, siga estas etapas:

1. Localize o campo no painel esquerdo que reflete os atributos ou eventos nos quais a regra será baseada.

1. Arraste o campo até a área de trabalho central e configure-o de acordo com a definição de segmento desejada. Para fazer isso, várias funções de string e data/hora estão disponíveis.

   No exemplo abaixo, a regra público alvo todos os perfis com gênero igual a &quot;Masculino&quot;.

   ![](assets/aep_audiences_malegender.png)

   A população estimada correspondente ao segmento é automaticamente recalculada na **[!UICONTROL Segment Properties]** seção.

1. O **[!UICONTROL View Profiles]** botão fornece uma pré-visualização dos primeiros 20 registros correspondentes à regra, permitindo que você valide o segmento rapidamente.

   ![](assets/aep_audiences_samplepreview.png)

   Você pode adicionar quantas regras adicionais desejar, a fim de público alvo dos perfis corretos.

   Ao adicionar uma regra a um container, ela será anexada a quaisquer regras existentes com o operador lógico E. Se necessário, clique no operador lógico para modificá-lo.

   ![](assets/aep_audiences_andoperator.png)

Uma vez vinculadas, as duas regras formam um container.

## Comparar campos

O Construtor de segmentos permite que você compare dois campos para definir uma regra. Por exemplo, mulheres cujo endereço residencial está em um CEP diferente do endereço profissional.

Para fazer isso, siga estas etapas:

1. Arraste o primeiro campo que deseja comparar (por exemplo, o código postal do endereço residencial) para a área de trabalho central.

   ![](assets/aep_audiences_comparing_1.png)

1. Selecione o segundo campo (por exemplo, o código postal do endereço de trabalho) que será comparado ao primeiro campo.

   Arraste-o para a área de trabalho central, no mesmo container do primeiro campo, na **[!UICONTROL Drop here to compare operands]** caixa.

   ![](assets/aep_audiences_comparing_2.png)

1. Configure o operador entre os dois campos conforme desejado. Neste exemplo, queremos que nosso segmento público alvo perfis com o endereço residencial diferente do endereço de trabalho.

   ![](assets/aep_audiences_comparing_3.png)

A regra agora está configurada e pronta para ser ativada como uma audiência.
