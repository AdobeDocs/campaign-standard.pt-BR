---
solution: Campaign Standard
product: campaign
title: Gerenciamento de públicos da plataforma Adobe Experience
description: Saiba como gerenciar a Adobe Experience Platform no Campaign Standard.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
translation-type: tm+mt
source-git-commit: 1c54f17980cf566f23dde1810a85b924c7f40c2c
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 3%

---


# Gerenciamento de públicos da plataforma Adobe Experience {#about-audiences}

>[!IMPORTANT]
>
>O Audience Destinations Service está atualmente em beta, que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam ser hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar acesso.

## Acesso a públicos da Adobe Experience Platform

Para acessar o construtor de segmentos da Adobe Experience Platform, navegue até o cartão **[!UICONTROL Audiences]** na página inicial do Campaign Standard (ou o link **[!UICONTROL Audiences]** no cabeçalho) e selecione o ambiente **[!UICONTROL Adobe Experience Platform]**.

![](assets/aep_audiences_access.png)

Primeiro, você será direcionado para a página de lista de segmentos da Adobe Experience Platform, onde os segmentos já existentes da Adobe Experience Platform podem ser acessados para edição adicional.

Uma barra de pesquisa e um filtro estão disponíveis para ajudar a encontrar o segmento desejado da Adobe Experience Platform.

![](assets/aep_audiences_list.png)

## Criação de públicos da Adobe Experience Platform

Para criar um público-alvo da Adobe Experience Platform diretamente no Campaign Standard, siga estas etapas:

1. Na página da lista de segmentos da Adobe Experience Platform, clique no botão **[!UICONTROL New audience]** localizado no canto direito.

   ![](assets/aep_audiences_creation_create.png)

1. O Construtor de segmentos agora deve ser exibido em seu espaço de trabalho. Ela permite criar um segmento usando dados da Adobe Experience Platform que serão usados eventualmente para criar seu público-alvo.

1. Nomeie o segmento no painel direito e insira uma descrição (opcional).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Para criar um segmento com êxito, você deve selecionar uma **política de mesclagem** que corresponda à sua finalidade de marketing para este segmento.

   No painel de configurações, uma política de mesclagem padrão da Plataforma é selecionada. Para obter mais informações sobre políticas de mesclagem, consulte a seção dedicada do [Guia do usuário do Construtor de segmento](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html).

   ![](assets/aep_audiences_mergepolicy.png)

1. Defina as regras que identificarão os perfis a serem recuperados no público-alvo.

   Para fazer isso, arraste os atributos e/ou eventos desejados do painel esquerdo para o espaço de trabalho, defina as regras correspondentes e clique no botão **[!UICONTROL Create segment]** para salvar o segmento (consulte [Uso do Construtor de segmentos](../../integrating/using/aep-using-segment-builder.md)).

   ![](assets/aep_audiences_creation_query.png)

O público-alvo agora está pronto para ser ativado, você pode usá-lo como um público-alvo para suas campanhas (consulte [Direcionamento de públicos da Adobe Experience Platform](../../integrating/using/aep-targeting-audiences.md)).

## Edição de públicos-alvo

Para editar um público-alvo, abra-o e modifique as regras conforme necessário na interface do Construtor de segmentos (consulte [Usar o Construtor de segmentos](../../integrating/using/aep-using-segment-builder.md)).

Depois que as alterações forem concluídas, clique no botão **[!UICONTROL Save segment]** para atualizar seu público-alvo.

![](assets/aep_audiences_editing.png)
