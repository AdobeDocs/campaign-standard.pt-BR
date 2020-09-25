---
title: Introdução ao modelo de dados do Campaign Standard
description: Acesse a descrição integrada do modelo de dados, estenda o modelo de dados Campaign Standard com campos e recursos personalizados e monitore todas as alterações no modelo de dados em uma única visualização.
page-status-flag: never-activated
uuid: 7c1e8cea-90d0-491f-ab8f-6cd69f8a6c3b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 40503917-7a53-4d99-96a4-57aa9e98ec87
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e67a173c5409d7693a3d7dab8f8ca3b03aeb886f
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 15%

---


# Introdução ao modelo de dados do Campaign Standard {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">Modelo de dados</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">Recursos personalizados</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">Trabalhar com APIs</a></p></td></tr>
</table>

Estenda o modelo de dados Campaign Standard com seus próprios campos e recursos e monitore todas as alterações no modelo de dados em uma única visualização.

## Modelo de dados {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

Os dados usados pela Campanha são definidos por meio de diferentes recursos definidos em um modelo **de dados** predefinido. O modelo de dados exibe uma estrutura SQL predefinida para um conjunto de recursos relacionados a marketing: delivery, audiência, landings page, perfil etc. Cada recurso vem com filtros associados, permitindo que você navegue pelos recursos.

O menu **Diagnóstico** permite que você lista os objetos técnicos gerados pelo Campaign Standard: schemas de dados, páginas da Web, filtros etc., que permitem monitorar o modelo de dados e qualquer alteração feita nele.

Leia mais:

* [Conceitos do modelo de dados](../../developing/using/data-model-concepts.md)
* [Práticas recomendadas do modelo de dados](../../developing/using/data-model-best-practices.md)
* [Descrição do modelo de dados](../../developing/using/datamodel-introduction.md)
* [Monitoramento de alterações no modelo de dados](../../developing/using/monitoring-data-model-changes.md)

## Recursos personalizados {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

O Campaign Standard permite **Enriquecer o modelo** de dados predefinido para criar seus próprios recursos (por exemplo, para adicionar tabelas de Compra ou Produto) ou estender os recursos existentes com novos campos. Você também pode configurar telas de Campanha para otimizar a navegação pelos novos recursos e campos que foram criados.

Além disso, é possível **estender APIs** Campaign Standard REST para expor os campos estendidos das APIs aos Perfis de recursos personalizados. Isso permite, por exemplo, atualizar o perfil de um cliente com um código promocional gerado de um sistema de cobrança.

Leia mais:

* [Adicionar ou estender um recurso](../../developing/using/key-steps-to-add-a-resource.md)
* [Extensão da API](../../developing/using/about-extending-the-api.md)
* [Caso de uso: Extensão do recurso de perfil a um novo campo](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [Caso de uso: Extensão das subscrições a um recurso de aplicativo](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## Trabalhar com APIs {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Com as APIs de Campaign Standard, crie integrações para Adobe Campaign Standard e construa seu próprio ecossistema, interagindo a Campanha com o painel de tecnologias que você usa. [Introdução às APIs REST do Campaign Standard](../../api/using/get-started-apis.md)

## Recursos adicionais

* [Sobre o Conector de dados da Adobe Experience Platform](../../developing/using/aep-about-data-connector.md)
* [Criação de recursos personalizados (vídeo)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/developing/custom-resources-develop/creating-custom-resources.html)
* [Exportação/importação de recursos personalizados](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
