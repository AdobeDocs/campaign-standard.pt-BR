---
solution: Campaign Standard
product: campaign
title: Introdução ao modelo de dados do Campaign Standard
description: Enriqueça o modelo de dados do Campaign Standard com campos e recursos personalizados e estenda as APIs REST para expor campos estendidos.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Data Model
role: Developer
level: Intermediate
exl-id: a8d15053-c20f-4334-a732-3b36cb00794d
translation-type: tm+mt
source-git-commit: c5a9c27a2ce459dfd0f04159095bfc8a2cf4c0f6
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 28%

---

# Introdução ao modelo de dados do Campaign Standard {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">Modelo de dados</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">Recursos personalizados</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">Trabalhar com APIs</a></p></td></tr>
</table>

Estenda o modelo de dados do Campaign Standard com seus próprios campos e recursos e monitore todas as alterações no modelo de dados em uma única visualização.

## Modelo de dados {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

Os dados usados pelo Campaign são definidos por meio de diferentes recursos definidos em um **modelo de dados predefinido**. O modelo de dados exibe uma estrutura SQL pronta para uso para um conjunto de recursos relacionados a marketing: entrega, público-alvo, páginas de aterrissagem, perfil, etc. Cada recurso vem com filtros associados, permitindo navegar pelos recursos.

O menu **Diagnosis** permite listar os objetos técnicos gerados pelo Campaign Standard: esquemas de dados, páginas da Web, filtros etc., que permitem monitorar o modelo de dados e qualquer alteração feita nele.

Leia mais:

* [Conceitos do modelo de dados](../../developing/using/data-model-concepts.md)
* [Práticas recomendadas do modelo de dados](../../developing/using/data-model-best-practices.md)
* [Descrição do modelo de dados](../../developing/using/datamodel-introduction.md)
* [Monitoramento de alterações no modelo de dados](../../developing/using/monitoring-data-model-changes.md)

## Recursos personalizados {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

O Campaign Standard permite **Enriquecer o modelo de dados predefinido** para criar seus próprios recursos (por exemplo, para adicionar tabelas de Compra ou Produto) ou estender os recursos existentes com novos campos. Você também pode configurar as telas do Campaign para otimizar a navegação por meio dos novos recursos e campos que foram criados.

Além disso, você pode **estender as APIs REST do Campaign Standard** para expor os campos estendidos das APIs para os perfis de recursos personalizados. Isso permite, por exemplo, atualizar o perfil de um cliente com um código promocional gerado de um sistema de cobrança.

Leia mais:

* [Adicionar ou estender um recurso](../../developing/using/key-steps-to-add-a-resource.md)
* [Extensão da API](../../developing/using/about-extending-the-api.md)
* [Caso de uso: Extensão do recurso de perfil com um novo campo](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [Caso de uso: Extensão das assinaturas para um recurso de aplicativo](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## Trabalhar com APIs {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Com as APIs do Campaign Standard, crie integrações para o Adobe Campaign Standard e crie seu próprio ecossistema, conectando o Campaign ao painel de tecnologias que você usa. [Introdução às REST APIs do Campaign Standard](../../api/using/get-started-apis.md)

## Recursos adicionais

* [Exportação/importação de recursos personalizados](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
* [Exportar dados do Campaign para o Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
