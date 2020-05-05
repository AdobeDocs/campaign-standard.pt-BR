---
title: Sobre públicos-alvo
description: Saiba como criar audiências a partir de um query, uma lista ou um arquivo e como importá-las da Adobe Experience Cloud.
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
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Sobre públicos-alvo{#about-audiences}

Uma audiência é uma lista de perfis com base em regras e atributos.

O Adobe Campaign permite que você crie suas audiências manualmente usando query ou automaticamente usando workflows dedicados. Você também pode usar audiências compartilhadas na Adobe Experience Cloud. Todas as audiências são agrupadas em uma lista que pode ser acessada pela **[!UICONTROL Audiences]** placa no home page Adobe Campaign ou pelo **[!UICONTROL Audiences]** link.

![](assets/audience_1.png)

É possível manipular diferentes tipos de audiência no Adobe Campaign. O tipo de audiência corresponde à forma como foi criada:

* **[!UICONTROL Query]**: indica que a audiência foi criada a partir de um [query](../../automating/using/editing-queries.md#about-query-editor) nos dados do banco de dados do Adobe Campaign a partir da lista do audiência. Audiências definidas por um query são recompostas a cada nova utilização.
* **[!UICONTROL List]**: indica que a audiência é uma lista fixa de perfis. Essas listas são criadas em um [fluxo de trabalho](../../automating/using/get-started-workflows.md), onde a dimensão de dados é conhecida ao salvar a audiência. Por exemplo, depois de direcionar atividades (especialmente **[!UICONTROL Query]** ) ou após a reconciliação de dados importados de um arquivo.
* **[!UICONTROL File]**: indica que a audiência foi criada diretamente de um fluxo de trabalho de importação [de](../../automating/using/load-file.md) arquivo e que a dimensão de dados era desconhecida ao salvar a audiência.
* **[!UICONTROL Experience Cloud]**: indica que a audiência foi importada da Adobe Experience Cloud. Essa opção só estará disponível se a funcionalidade de compartilhamento de audiências tiver sido configurada. Para obter mais informações, consulte [Importação de uma audiência da Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience).

![](assets/audience_type_selection.png)
