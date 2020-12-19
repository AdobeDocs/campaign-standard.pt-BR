---
solution: Campaign Standard
product: campaign
title: Gerenciamento de públicos da plataforma Adobe Experience
description: Saiba como gerenciar o Adobe Experience Platform no Campaign Standard.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 3%

---


# Gerenciamento de públicos da plataforma Adobe Experience {#about-audiences}

>[!IMPORTANT]
>
>O Serviço de Destinos de audiência está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar acessá-lo.

## Acesso ao Adobe Experience Platform audiência

Para acessar o construtor de segmentos da Adobe Experience Platform, navegue até a placa **[!UICONTROL Audiences]** no home page Campaign Standard (ou o link **[!UICONTROL Audiences]** no cabeçalho) e selecione o ambiente **[!UICONTROL Adobe Experience Platform]**.

![](assets/aep_audiences_access.png)

Primeiro, você será direcionado para a página lista de segmentos da Adobe Experience Platform, onde os segmentos da Adobe Experience Platform já existentes podem ser acessados para edição adicional.

Uma barra de pesquisa e um filtro estão disponíveis para ajudá-lo a encontrar o segmento do Adobe Experience Platform desejado.

![](assets/aep_audiences_list.png)

## Criando Adobe Experience Platform audiência

Para criar uma audiência Adobe Experience Platform diretamente no Campaign Standard, siga estas etapas:

1. Na página lista de segmentos do Adobe Experience Platform, clique no botão **[!UICONTROL New audience]** localizado no canto direito.

   ![](assets/aep_audiences_creation_create.png)

1. O Construtor de segmentos agora deve ser exibido em sua área de trabalho. Ele permite que você crie um segmento usando dados da Adobe Experience Platform que eventualmente serão usados para criar sua audiência.

1. Nomeie o segmento no painel direito e insira uma descrição (opcional).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Para criar com êxito um segmento, você deve selecionar uma **política de mesclagem** que corresponda à sua finalidade de marketing para esse segmento.

   No painel de configurações, uma política de mesclagem padrão da Plataforma é selecionada. Para obter mais informações sobre políticas de mesclagem, consulte a seção dedicada do [Guia do usuário do Construtor de segmentos](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html).

   ![](assets/aep_audiences_mergepolicy.png)

1. Defina as regras que identificarão os perfis a serem recuperados em sua audiência.

   Para fazer isso, arraste os atributos e/ou eventos desejados do painel esquerdo para o espaço de trabalho, defina as regras correspondentes e clique no botão **[!UICONTROL Create segment]** para salvar o segmento (consulte [Usando o Construtor de segmentos](../../audiences/using/aep-using-segment-builder.md)).

   ![](assets/aep_audiences_creation_query.png)

A audiência está pronta para ser ativada, você pode usá-la como um público alvo para suas campanhas (consulte [Direcionando o Adobe Experience Platform audiência](../../automating/using/aep-targeting-audiences.md)).

## Edição de públicos-alvo

Para editar uma audiência, abra-a e modifique as regras conforme necessário na interface do Construtor de segmentos (consulte [Usando o Construtor de segmentos](../../audiences/using/aep-using-segment-builder.md)).

Depois que as alterações forem concluídas, clique no botão **[!UICONTROL Save segment]** para atualizar sua audiência.

![](assets/aep_audiences_editing.png)
