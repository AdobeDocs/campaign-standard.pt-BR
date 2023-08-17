---
title: Usar o Criador de segmentos
description: Saiba como usar o Construtor de segmentos para criar públicos.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 9a6c542e-10ed-4e77-abb3-36324e1cb38f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 3%

---

# Usar o Criador de segmentos {#using-the-segment-builder}

>[!IMPORTANT]
>
>O serviço Audience Destinations está atualmente em versão beta, que pode estar sujeita a atualizações frequentes sem aviso prévio. Os clientes precisam ser hospedados no Azure (atualmente na versão beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar obter acesso.

O Construtor de segmentos permite que você crie públicos-alvo definindo regras com base nos dados provenientes da [Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html).

Esta seção apresenta conceitos globais ao criar um segmento. Para obter informações detalhadas sobre o próprio Construtor de segmentos, consulte [Guia do usuário do Construtor de segmentos](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html).

A interface do Construtor de segmentos é composta da seguinte maneira:

* O painel esquerdo fornece todos os atributos, eventos e públicos-alvo disponíveis para criar o segmento ao arrastar e soltar os campos desejados no espaço de trabalho do construtor de segmentos.
* A área central fornece um espaço de trabalho para criar o segmento, definindo e combinando regras a partir dos campos disponíveis.
* O cabeçalho e o painel direito exibem as propriedades do segmento (ou seja, nome, descrição e perfis qualificados estimados para o segmento).

![](assets/aep_audiences_interface.png)

## Criação de um segmento

Para criar um segmento, siga estas etapas:

O Construtor de segmentos agora deve ser exibido em seu espaço de trabalho. Ele permite criar um segmento usando dados do Adobe Experience Platform que serão usados para criar seu público-alvo.

1. Nomeie o segmento e insira uma descrição (opcional).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Verifique se a política de mesclagem desejada está selecionada no painel de configurações.

   Para obter mais informações sobre políticas de mesclagem, consulte a seção dedicada do [Guia do usuário do Construtor de segmentos](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html).

   ![](assets/aep_audiences_mergepolicy.png)

1. Procure os campos desejados no painel esquerdo e arraste-os para o espaço de trabalho central.

   ![](assets/aep_audiences_dragfield.png)

1. Configure as regras correspondentes aos campos arrastados.

   ![](assets/aep_audiences_configure_rules.png)

1. Clique no botão **[!UICONTROL Create segment]**.

## Encontrar os campos certos para um segmento

O painel esquerdo lista todos os atributos, eventos e públicos-alvo que estão disponíveis para uso na criação de regras.

Os campos listados são atributos capturados pela sua empresa e foram disponibilizados por meio da [Sistema do Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html).

Os campos são organizados em guias:

* **[!UICONTROL Attributes]**: atributos de perfis existentes que podem se originar do banco de dados do Adobe Campaign e/ou do Adobe Experience Platform. Elas se referem às informações estáticas anexadas a um perfil (por exemplo, endereço de email, país de residência, status do programa de fidelidade etc.).

  ![](assets/aep_audiences_attributestab.png)

* **[!UICONTROL Events]**: atividades que identificam consumidores que tiveram alguma interação com os pontos de contato de clientes da sua empresa, como &quot;qualquer pessoa que fez um pedido duas vezes em duas semanas&quot;. Isso pode ser transmitido da Adobe Analytics ou assimilado diretamente na Adobe Experience Platform usando ferramentas de ETL de terceiros.

  ![](assets/aep_audiences_eventstab.png)

>[!NOTE]
>
>**Segmentação de várias entidades** O permite estender os dados do Perfil com dados adicionais com base em produtos, lojas ou outras classes que não sejam de perfil. Depois de conectados, os dados de classes adicionais ficam disponíveis como se fossem nativos do esquema de Perfil.
>
>Para obter mais informações, consulte a [documentação dedicada](https://experienceleague.adobe.com/docs/experience-platform/segmentation/multi-entity-segmentation.html).

Por padrão, o Construtor de segmentos exibe campos nos quais os dados já estão presentes. Para exibir o esquema completo, incluindo campos para os quais não há dados presentes, ative a opção **[!UICONTROL Show full XDM schema]** nas configurações.

![](assets/aep_audiences_populatedfields.png)

O símbolo no final de cada campo fornece informações adicionais sobre o atributo e como usá-lo.

![](assets/aep_audiences_isymbol.png)

## Definição de regras para um segmento

>[!NOTE]
>
>A seção abaixo fornece informações globais sobre a definição de regras. Para obter mais informações, consulte [Guia do usuário do Construtor de segmentos](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html).

Para criar uma regra, siga estas etapas:

1. Localize o campo no painel esquerdo que reflete os atributos ou eventos nos quais a regra será baseada.

1. Arraste o campo até o espaço de trabalho central e configure-o de acordo com a definição de segmento desejada. Para fazer isso, várias funções de string e data/hora estão disponíveis.

   No exemplo abaixo, a regra segmentará todos os perfis com gênero igual a &quot;Masculino&quot;.

   ![](assets/aep_audiences_malegender.png)

   A população estimada correspondente ao segmento é recalculada automaticamente na variável **[!UICONTROL Segment Properties]** seção.

1. A variável **[!UICONTROL View Profiles]** O botão fornece uma visualização dos primeiros 20 registros correspondentes à regra, permitindo validar rapidamente o segmento.

   ![](assets/aep_audiences_samplepreview.png)

   Você pode adicionar quantas regras desejar para direcionar os perfis corretos.

   Ao adicionar uma regra a um contêiner, ela será anexada a todas as regras existentes com o operador lógico AND. Se necessário, clique no operador lógico para modificá-lo.

   ![](assets/aep_audiences_andoperator.png)

Uma vez vinculadas, as duas regras formam um container.

## Comparação de campos

O Construtor de segmentos permite que você compare dois campos para definir uma regra. Por exemplo, mulheres cujo endereço residencial está em um CEP diferente de seu endereço comercial.

Para fazer isso, siga estes passos:

1. Arraste o primeiro campo que deseja comparar (por exemplo, o CEP do endereço residencial) para o espaço de trabalho central.

   ![](assets/aep_audiences_comparing_1.png)

1. Selecione o segundo campo (por exemplo, o CEP do endereço comercial) que será comparado com o primeiro campo.

   Arraste-o para o espaço de trabalho central, no mesmo container do primeiro campo, na **[!UICONTROL Drop here to compare operands]** caixa.

   ![](assets/aep_audiences_comparing_2.png)

1. Configure o operador entre os dois campos conforme desejado. Neste exemplo, queremos que nosso segmento direcione perfis com o endereço residencial diferente do endereço comercial.

   ![](assets/aep_audiences_comparing_3.png)

Agora a regra está configurada e pronta para ser ativada como um público-alvo.
