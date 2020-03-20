---
title: Uso do Construtor de segmentos unificados
description: Saiba como usar o Construtor de segmentos unificados para criar públicos-alvo.
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
source-git-commit: fcb6a145b19b68865babba659bf0bfb7623397c8

---


# Uso do Construtor de segmentos unificados {#using-the-unified-segment-builder}

>[!IMPORTANT]
>
>O serviço de Destinos de público-alvo está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar acessar.

O Construtor de segmentos unificados permite que você crie públicos definindo regras com base nos dados provenientes do Serviço [de perfis](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation.html)unificados.

Esta seção apresenta conceitos globais ao criar um segmento. Para obter informações detalhadas sobre o Construtor de segmentos unificado, consulte o guia [do usuário do Construtor de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)segmentos.

A interface do Construtor de segmentos unificados é composta da seguinte maneira:

* O painel esquerdo fornece todos os atributos, eventos e públicos disponíveis para criar o segmento arrastando e soltando os campos desejados na área de trabalho do construtor de segmentos.
* A área central fornece um espaço de trabalho para criar o segmento definindo e combinando regras dos campos disponíveis.
* O painel direito e cabeçalho exibe as propriedades do segmento (ou seja, nome, descrição e perfis qualificados estimados para o segmento).

![](assets/aep_audiences_interface.png)

## Criação de um segmento

Para criar um segmento, siga estas etapas:

O Construtor de segmentos unificado agora deve ser exibido em sua área de trabalho. Ele permite que você crie um segmento usando dados da Adobe Experience Platform que serão usados para criar seu público-alvo.

1. Nomeie o segmento e insira uma descrição (opcional).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Certifique-se de que a política de mesclagem desejada esteja selecionada no painel de configurações.

   Para obter mais informações sobre políticas de mesclagem, consulte a seção dedicada no guia [do usuário do Construtor de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)segmentos.

   ![](assets/aep_audiences_mergepolicy.png)

1. Procure os campos desejados no painel esquerdo e arraste-os para a área de trabalho central.

   ![](assets/aep_audiences_dragfield.png)

1. Configure as regras correspondentes aos campos arrastados.

   ![](assets/aep_audiences_configure_rules.png)

1. Clique no botão **[!UICONTROL Create segment]**.

## Encontrar os campos certos para um segmento

O painel esquerdo lista todos os atributos, eventos e públicos disponíveis para uso na construção de regras.

Os campos listados são atributos capturados pela sua empresa e disponibilizados pelo sistema [](https://www.adobe.io/apis/experienceplatform/home/xdm.html)Experience Data Model (XDM).

Os campos são organizados em guias:

* **[!UICONTROL Attributes]**: Atributos de perfis existentes que podem se originar do banco de dados do Adobe Campaign e/ou da plataforma Adobe Experience. Referem-se a informações estáticas anexadas a um perfil (por exemplo, endereço de email, país de residência, status do programa de fidelidade, etc.).

   ![](assets/aep_audiences_attributestab.png)

* **[!UICONTROL Events]**: Atividades que identificam os consumidores que tiveram alguma interação com os pontos de contato dos clientes da sua empresa, como &quot;qualquer pessoa que tenha feito pedidos duas vezes em duas semanas&quot;. Isso pode ser transmitido do Adobe Analytics ou assimilado diretamente na Adobe Experience Platform usando ferramentas ETL de terceiros.

   ![](assets/aep_audiences_eventstab.png)

>[!NOTE]
>
>**A segmentação** de várias entidades permite estender os dados de perfil com dados adicionais baseados em produtos, lojas ou outras classes que não sejam de perfil. Depois de conectados, os dados de classes adicionais ficam disponíveis como se fossem nativos no esquema de perfil.
>
>For more on this, refer to the [dedicated documentation](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/tutorials/segmentation/multi_entity_segmentation.md).

Por padrão, o Construtor de segmentos unificados exibe campos nos quais os dados já estão presentes. Para exibir o esquema completo, incluindo campos para os quais os dados não estão presentes, ative a **[!UICONTROL Show full XDM schema]** opção nas configurações.

![](assets/aep_audiences_populatedfields.png)

O símbolo no final de cada campo fornece informações adicionais sobre o atributo e como usá-lo.

![](assets/aep_audiences_isymbol.png)

## Definição de regras para um segmento

>[!NOTE]
>
>A seção abaixo fornece informações globais sobre a definição de regras. Para obter mais informações, consulte o guia [do usuário do Construtor de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)segmentos.

Para criar uma regra, siga estas etapas:

1. Localize o campo no painel esquerdo que reflete os atributos ou eventos nos quais a regra se baseará.

1. Arraste o campo até a área de trabalho central e configure-o de acordo com a definição de segmento desejada. Para fazer isso, várias funções de string e data/hora estão disponíveis.

   No exemplo abaixo, a regra direcionará todos os perfis com gênero igual a &quot;Masculino&quot;.

   ![](assets/aep_audiences_malegender.png)

   A população estimada correspondente ao segmento é automaticamente recalculada na **[!UICONTROL Segment Properties]** seção.

1. O **[!UICONTROL View Profiles]** botão fornece uma visualização dos primeiros 20 registros correspondentes à regra, permitindo que você valide o segmento rapidamente.

   ![](assets/aep_audiences_samplepreview.png)

   Você pode adicionar quantas regras adicionais desejar, a fim de direcionar os perfis corretos.

   Ao adicionar uma regra a um contêiner, ela será anexada a quaisquer regras existentes com o operador lógico E. Se necessário, clique no operador lógico para modificá-lo.

   ![](assets/aep_audiences_andoperator.png)

Depois de vinculadas, as duas regras formam um contêiner.

## Comparar campos

O Construtor de segmentos unificados permite comparar dois campos para definir uma regra. Por exemplo, mulheres cujo endereço residencial está em um CEP diferente do endereço profissional.

Para fazer isso, siga estas etapas:

1. Arraste o primeiro campo que deseja comparar (por exemplo, o código postal do endereço residencial) para a área de trabalho central.

   ![](assets/aep_audiences_comparing_1.png)

1. Selecione o segundo campo (por exemplo, o código postal do endereço de trabalho) que será comparado ao primeiro campo.

   Arraste-o para a área de trabalho central, no mesmo contêiner do primeiro campo, na **[!UICONTROL Drop here to compare operands]** caixa.

   ![](assets/aep_audiences_comparing_2.png)

1. Configure o operador entre os dois campos conforme desejado. Neste exemplo, queremos que nosso segmento direcione perfis com o endereço residencial diferente do endereço de trabalho.

   ![](assets/aep_audiences_comparing_3.png)

A regra agora está configurada e pronta para ser ativada como um público-alvo.
