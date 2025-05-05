---
title: Gerenciamento de públicos da Adobe Experience Platform
description: Saiba como gerenciar o Adobe Experience Platform no Campaign Standard.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 2f6c5cc6-0634-4418-a2ee-e1c133d9cbd2
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 2%

---

# Gerenciamento de públicos da Adobe Experience Platform {#about-audiences}

>[!IMPORTANT]
>
>O Serviço Audience Destinations está atualmente em versão beta, que pode estar sujeita a atualizações frequentes sem aviso prévio. Os clientes precisam ser hospedados no Azure (atualmente na versão beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar obter acesso.

## Acesso aos públicos da Adobe Experience Platform

Para acessar o construtor de segmentos da Adobe Experience Platform, navegue até o cartão **[!UICONTROL Audiences]** na página inicial do Campaign Standard (ou até o link **[!UICONTROL Audiences]** no cabeçalho) e selecione o ambiente **[!UICONTROL Adobe Experience Platform]**.

![](assets/aep_audiences_access.png)

Primeiro, você será direcionado para a página Lista de segmentos do Adobe Experience Platform, na qual os segmentos do Adobe Experience Platform já existentes podem ser acessados para edição adicional.

Uma barra de pesquisa e um filtro estão disponíveis para ajudar você a encontrar o segmento do Adobe Experience Platform desejado.

![](assets/aep_audiences_list.png)

## Criação de públicos da Adobe Experience Platform

Para criar um público-alvo do Adobe Experience Platform diretamente no Campaign Standard, siga estas etapas:

1. Na página da lista de segmentos do Adobe Experience Platform, clique no botão **[!UICONTROL New audience]** localizado no canto direito.

   ![](assets/aep_audiences_creation_create.png)

1. O Construtor de segmentos agora deve ser exibido em seu espaço de trabalho. Ele permite criar um segmento usando dados do Adobe Experience Platform que serão usados para criar seu público-alvo.

1. Nomeie o segmento no painel direito e insira uma descrição (opcional).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Para criar um segmento com êxito, você deve selecionar uma **política de mesclagem** que corresponda à sua finalidade de marketing para esse segmento.

   No painel de configurações, uma política de mesclagem padrão da Platform é selecionada. Para obter mais informações sobre políticas de mesclagem, consulte a seção dedicada do [guia do usuário do Construtor de segmentos](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=pt-BR).

   ![](assets/aep_audiences_mergepolicy.png)

1. Defina as regras que identificarão os perfis que serão recuperados no público-alvo.

   Para fazer isso, arraste os atributos e/ou eventos desejados do painel esquerdo para o espaço de trabalho, defina as regras correspondentes e clique no botão **[!UICONTROL Create segment]** para salvar o segmento (consulte [Usando o Construtor de Segmentos](../../integrating/using/aep-using-segment-builder.md)).

   ![](assets/aep_audiences_creation_query.png)

O público-alvo agora está pronto para ser ativado; você pode usá-lo como um direcionamento para suas campanhas (consulte [Direcionamento de públicos-alvo da Adobe Experience Platform](../../integrating/using/aep-targeting-audiences.md)).

## Edição de públicos

Para editar um público, abra-o e modifique as regras conforme necessário na interface do Construtor de segmentos (consulte [Uso do Construtor de segmentos](../../integrating/using/aep-using-segment-builder.md)).

Após concluir as alterações, clique no botão **[!UICONTROL Save segment]** para atualizar o público-alvo.

![](assets/aep_audiences_editing.png)
