---
title: Sobre públicos-alvo
description: Saiba como criar públicos-alvo a partir de uma consulta, uma lista ou um arquivo e como importá-los da Adobe Experience Cloud.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Audiences
role: User
level: Beginner
exl-id: f99987d8-b1bf-4ec7-885c-fb511f4168ac
TQID: 'https://experienceleague.adobe.com/NPcDi1kh8Ye1Y14CAwVxBLW-0qwHnpFRUQ2WYj7BJbI'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 85%
---
# Sobre públicos-alvos{#about-audiences}

Um público-alvo é uma lista de perfis com base em regras e atributos.

O Adobe Campaign permite criar públicos-alvo manualmente usando consultas ou automaticamente com fluxos de trabalho dedicados. Você também pode usar públicos-alvo compartilhados da Adobe Experience Cloud. Todos os públicos-alvo são agrupados em uma lista que pode ser acessada pelo cartão **[!UICONTROL Audiences]** na home page do Adobe Campaign ou pelo link **[!UICONTROL Audiences]**.

![](assets/audience_1.png)

É possível manipular diferentes tipos de público-alvo no Adobe Campaign. O tipo de público-alvo corresponde ao modo como ele foi criado:

* **[!UICONTROL Query]**: indica que o público-alvo foi criado usando uma [consulta](../../automating/using/editing-queries.md#about-query-editor) nos dados do banco de dados do Adobe Campaign através da lista de públicos-alvo. Os públicos-alvo definidos por uma consulta são recalculados a cada novo uso.
* **[!UICONTROL List]**: indica que o público-alvo é uma lista fixa de perfis. Essas listas são criadas em um [fluxo de trabalho](../../automating/using/get-started-workflows.md), no qual a dimensão de dados é conhecida quando o público-alvo é salvo. Por exemplo, após o direcionamento de atividades (especialmente **[!UICONTROL Query]**) ou a reconciliação dos dados importados de um arquivo.
* **[!UICONTROL File]**: indica que o público-alvo foi criado diretamente de um fluxo de trabalho de [importação de arquivo](../../automating/using/load-file.md) e que a dimensão de dados era desconhecida quando o público-alvo foi salvo.
* **[!UICONTROL Experience Cloud]**: indica que o público-alvo foi importado da Adobe Experience Cloud. Essa opção só estará disponível se a funcionalidade de compartilhamento de públicos-alvo tiver sido configurada. Para saber mais, consulte [Importação de um público-alvo da Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience).

![](assets/audience_type_selection.png)
