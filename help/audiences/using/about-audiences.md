---
title: Sobre públicos-alvo
description: Saiba como criar públicos-alvo a partir de uma consulta, uma lista ou um arquivo e como importá-los da Adobe Experience Cloud.
page-status-flag: nunca ativado
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: referência
topic-tags: gerenciar públicos-alvo
discoiquuid: 750ecd8d-67a5-4180-bemou-2a8e3098c812
context-tags: público-alvo,assistente;público-alvo,visão geral;entrega,público-alvo,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Sobre públicos-alvo{#about-audiences}

Um público-alvo é uma lista de perfis com base em regras e atributos.

O Adobe Campaign permite que você crie seus públicos-alvo manualmente usando consultas ou automaticamente usando fluxos de trabalho dedicados. Você também pode usar públicos compartilhados na Adobe Experience Cloud. Todos os públicos-alvo são agrupados em uma lista que pode ser acessada pelo **[!UICONTROL Audiences]** cartão na página inicial do Adobe Campaign ou pelo **[!UICONTROL Audiences]** link.

![](assets/audience_1.png)

Você pode manipular diferentes tipos de público-alvo no Adobe Campaign. O tipo de público-alvo corresponde à forma como foi criado:

* **[!UICONTROL Query]**: indica que o público-alvo foi criado a partir de uma [consulta](../../automating/using/editing-queries.md#about-query-editor) nos dados do banco de dados do Adobe Campaign a partir da lista de públicos-alvo. Os públicos-alvo definidos por uma consulta são recompostos a cada novo uso.
* **[!UICONTROL List]**: indica que o público-alvo é uma lista fixa de perfis. Essas listas são criadas em um [fluxo de trabalho](../../automating/using/discovering-workflows.md), onde a dimensão de dados é conhecida ao salvar o público-alvo. Por exemplo, após as atividades de definição de metas (especialmente **[!UICONTROL Query]** ) ou após a reconciliação dos dados importados de um arquivo.
* **[!UICONTROL File]**: indica que o público-alvo foi criado diretamente de um fluxo de trabalho de importação [de](../../automating/using/load-file.md) arquivo e que a dimensão de dados era desconhecida ao salvar o público-alvo.
* **[!UICONTROL Experience Cloud]**: indica que o público-alvo foi importado da Adobe Experience Cloud. Essa opção só estará disponível se a funcionalidade de compartilhamento de público-alvo tiver sido configurada. Para obter mais informações, consulte [Importar um público-alvo da Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience).

![](assets/audience_type_selection.png)

