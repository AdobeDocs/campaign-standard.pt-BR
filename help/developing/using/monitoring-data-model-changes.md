---
title: Monitoramento de alterações no modelo de dados
description: Saiba como diagnosticar o modelo de dados do Adobe Campaign.
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ced9a897-47e9-4128-84fb-35660c553cd4
TQID: 'https://experienceleague.adobe.com/XWMP0LlTRgqEJujGETPzVXOCUvkm-Q9OXC-RvaWd-58'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: a1681cd8-6b2e-4955-9113-33b5f7a22b8c
    internal-label: Data model architecture
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 8%
---
# Monitoramento de alterações no modelo de dados{#monitoring-data-model-changes}

No menu **[!UICONTROL Diagnosis]**, é possível exibir os objetos técnicos gerados pelo aplicativo para analisá-los.

>[!NOTE]
>
>As telas nesse menu são somente leitura.

![](assets/diagnostic.png)

Você pode exibir os seguintes tipos de objetos:

* Esquemas de dados
* Páginas da Web
* Filtros
* Navegação
* Componentes
* Processos em lote

É possível alterar a configuração da lista:

* Você pode adicionar e remover colunas.
* Você pode definir nomes de coluna.
* Você pode definir a ordem de exibição das colunas na lista.
* Você pode escolher a ordem de classificação dos valores na lista.

Você pode filtrar a lista:

* Você pode incluir ou excluir esquemas de dados nativos, páginas da Web, filtros e objetos de navegação.
* Você pode pesquisar objetos pelo nome deles.
* Você pode filtrar os trabalhos em lotes com base em seu status, data de início e data de término.

Você pode baixar a lista exibida em um arquivo no formato TXT com valores separados por vírgula.

Você pode exibir os detalhes do objeto selecionado.

Por exemplo, você pode usar esse recurso para exibir os critérios de filtragem de filtros prontos para uso. Este exemplo mostra o código exibido para os critérios de filtragem de um filtro pronto para uso:

```xml
<where displayFilter="Has clicked an offer">
  <condition boolOperator="AND" enabledIf="$(offer) != ''" expr="trackingLog" internalId="1" setOperator="EXISTS">
    <condition boolOperator="AND" expr="[url/offer] = $RestKey(offer)" internalId="2"/>
    <condition boolOperator="AND" expr="[@url-id] != 1" internalId="3"/>
  </condition>
</where>
```

![](assets/diagnosis_filter_criteria.png)