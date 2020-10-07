---
title: Gerenciamento de públicos da plataforma Adobe Experience
description: Saiba como gerenciar o Adobe Experience Platform no Campaign Standard.
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 3%

---


# Gerenciamento de públicos da plataforma Adobe Experience {#about-audiences}

>[!IMPORTANT]
>
>O Serviço de Destinos de audiência está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar acessá-lo.

## Acesso ao Adobe Experience Platform audiência

Para acessar o construtor de segmentos Adobe Experience Platform, navegue até a **[!UICONTROL Audiences]** placa no home page do Campaign Standard (ou o **[!UICONTROL Audiences]** link no cabeçalho) e selecione o **[!UICONTROL Adobe Experience Platform]** ambiente.

![](assets/aep_audiences_access.png)

Primeiro, você será direcionado para a página lista de segmentos da Adobe Experience Platform, onde os segmentos da Adobe Experience Platform já existentes podem ser acessados para edição adicional.

Uma barra de pesquisa e um filtro estão disponíveis para ajudá-lo a encontrar o segmento do Adobe Experience Platform desejado.

![](assets/aep_audiences_list.png)

## Criando Adobe Experience Platform audiência

Para criar uma audiência Adobe Experience Platform diretamente no Campaign Standard, siga estas etapas:

1. Na página lista de segmentos do Adobe Experience Platform, clique no **[!UICONTROL New audience]** botão localizado no canto direito.

   ![](assets/aep_audiences_creation_create.png)

1. O Construtor de segmentos agora deve ser exibido em sua área de trabalho. Ele permite que você crie um segmento usando dados da Adobe Experience Platform que eventualmente serão usados para criar sua audiência.

1. Nomeie o segmento no painel direito e insira uma descrição (opcional).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Para criar com êxito um segmento, é necessário selecionar uma política **de** mesclagem que corresponda à sua finalidade de marketing para esse segmento.

   No painel de configurações, uma política de mesclagem padrão da Plataforma é selecionada. Para obter mais informações sobre políticas de mesclagem, consulte a seção dedicada no guia [do usuário do Construtor de](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)segmentos.

   ![](assets/aep_audiences_mergepolicy.png)

1. Defina as regras que identificarão os perfis a serem recuperados em sua audiência.

   Para fazer isso, arraste os atributos e/ou eventos desejados do painel esquerdo para a área de trabalho, defina as regras correspondentes e clique no **[!UICONTROL Create segment]** botão para salvar o segmento (consulte [Uso do Construtor](../../audiences/using/aep-using-segment-builder.md)de segmentos).

   ![](assets/aep_audiences_creation_query.png)

A audiência está pronta para ser ativada, você pode usá-la como público alvo para suas campanhas (consulte [Direcionando audiências](../../automating/using/aep-targeting-audiences.md)do Adobe Experience Platform).

## Edição de públicos-alvo

Para editar uma audiência, abra-a e modifique as regras conforme necessário na interface do Construtor de segmentos (consulte [Uso do Construtor](../../audiences/using/aep-using-segment-builder.md)de segmentos).

Depois que as alterações forem concluídas, clique no **[!UICONTROL Save segment]** botão para atualizar sua audiência.

![](assets/aep_audiences_editing.png)
