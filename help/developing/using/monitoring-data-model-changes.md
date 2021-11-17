---
title: Monitoramento de alterações no modelo de dados
description: Saiba como diagnosticar o modelo de dados Adobe Campaign.
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ced9a897-47e9-4128-84fb-35660c553cd4
source-git-commit: 5fef74296a4790102c75e609c270e52d5ead1d58
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 5%

---

# Monitoramento de alterações no modelo de dados{#monitoring-data-model-changes}

No **[!UICONTROL Diagnosis]** é possível exibir os objetos técnicos gerados pelo aplicativo para analisá-los.

>[!NOTE]
>
>As telas neste menu são somente leitura.

![](assets/diagnostic.png)

É possível exibir os seguintes tipos de objetos:

* Esquemas de dados
* Páginas da Web
* Filtros
* Navegação
* Componentes
* Trabalhos em lote

Você pode alterar a configuração da lista:

* É possível adicionar e remover colunas.
* É possível definir nomes de colunas.
* É possível definir a ordem de exibição das colunas na lista.
* Você pode escolher a ordem de classificação dos valores na lista.

Você pode filtrar a lista:

* Você pode incluir ou excluir esquemas de dados nativos, páginas da Web, filtros e objetos de navegação.
* Você pode pesquisar objetos pelo nome.
* Você pode filtrar trabalhos em lote em seu status, data de início e data de término.

Você pode baixar a lista exibida em um arquivo no formato TXT com valores separados por vírgula.

Você pode exibir os detalhes do objeto selecionado.

Por exemplo, você pode usar esse recurso para exibir os critérios de filtragem dos filtros prontos para uso. Este exemplo mostra o código exibido para os critérios de filtragem de um filtro pronto para uso:

```xml
<where displayFilter="Has clicked an offer">
  <condition boolOperator="AND" enabledIf="$(offer) != ''" expr="trackingLog" internalId="1" setOperator="EXISTS">
    <condition boolOperator="AND" expr="[url/offer] = $RestKey(offer)" internalId="2"/>
    <condition boolOperator="AND" expr="[@url-id] != 1" internalId="3"/>
  </condition>
</where>
```

![](assets/diagnosis_filter_criteria.png)