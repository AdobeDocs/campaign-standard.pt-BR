---
title: Introdução ao modelo de dados do Campaign Standard
description: Enriqueça o modelo de dados do Campaign Standard com campos e recursos personalizados e estenda as APIs REST para expor campos estendidos.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Data Model
role: Developer
level: Intermediate
exl-id: a8d15053-c20f-4334-a732-3b36cb00794d
TQID: https://experienceleague.adobe.com/LHlfIZ24iApQfr6dL-x-nQViltSetibBgt1slLDsRi4
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 348
ht-degree: 24%

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

Os dados usados pelo Campaign são definidos com recursos diferentes definidos em um **modelo de dados predefinido**. O modelo de dados exibe uma estrutura SQL pronta para uso para um conjunto de recursos relacionados ao marketing: entrega, público-alvo, landing pages, perfil, etc. Cada recurso vem com filtros associados, que permitem navegar pelos recursos.

O menu **Diagnóstico** permite listar os objetos técnicos gerados pelo Campaign Standard: esquemas de dados, páginas da Web, filtros, etc., permitindo monitorar o modelo de dados e qualquer alteração feita nele.

Leia mais:

* [Conceitos do modelo de dados](../../developing/using/data-model-concepts.md)
* [Práticas recomendadas do modelo de dados](../../developing/using/data-model-best-practices.md)
* [Descrição do modelo de dados](../../developing/using/datamodel-introduction.md)
* [Monitoramento de alterações no modelo de dados](../../developing/using/monitoring-data-model-changes.md)

## Recursos personalizados {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

O Campaign Standard permite **Enriquecer o modelo de dados predefinido** para criar seus próprios recursos (por exemplo, adicionar tabelas de Produto ou Compra) ou estender recursos existentes com novos campos. Você também pode configurar as telas do Campaign para otimizar a navegação pelos novos recursos e campos criados.

Além disso, você pode **estender as APIs REST do Campaign Standard** para expor os campos estendidos das APIs para os Perfis de recursos personalizados. Isso permite, por exemplo, atualizar o perfil de um cliente com um código promocional gerado de um sistema de faturamento.

Leia mais:

* [Adicionar ou estender um recurso](../../developing/using/key-steps-to-add-a-resource.md)
* [Extensão da API](../../developing/using/about-extending-the-api.md)
* [Caso de uso: extensão do recurso de perfil com um novo campo](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [Caso de uso: extensão das assinaturas para um recurso de aplicativo](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## Trabalhar com APIs {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Com as APIs do Campaign Standard, crie integrações para o Adobe Campaign Standard e construa seu próprio ecossistema interagindo o Campaign com o painel de tecnologias que você usa. [Introdução às REST APIs do Campaign Standard](../../api/using/get-started-apis.md)

## Recursos adicionais

* [Exportação/importação de recursos personalizados](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
* [Exportar dados do Campaign para a Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
