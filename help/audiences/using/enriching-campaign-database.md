---
solution: Campaign Standard
product: campaign
title: Enriquecimento da base de dados
description: Saiba mais sobre os vários métodos para enriquecer o banco de dados.
audience: start
content-type: reference
topic-tags: about-adobe-campaign
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 3%

---


# Enriquecendo o banco de dados{#enriching-the-database}

O Campaign Standard oferta várias ferramentas para ajudá-lo a expandir seu banco de dados de marketing. Esta seção detalha os diferentes métodos que podem ser usados para injetar dados na Campanha, com referências às documentações dedicadas.

## Importação de dados por meio de workflows {#importing-data-through-workflows}

Os workflows permitem coletar dados e importá-los para o banco de dados de Campanha por meio do uso do [[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md) atividade.

Informações genéricas e práticas recomendadas ao importar dados por meio de workflows são apresentadas em [esta seção](../../automating/using/about-data-import-and-export.md).

Além disso, você pode configurar modelos para importar dados. Usar templates de importação é uma prática recomendada se você precisar importar arquivos com a mesma estrutura regularmente.

Você pode configurar dois tipos de modelos:

* **Modelos** de fluxo de trabalho: são workflows pré-configurados que podem ser configurados uma vez, de acordo com suas necessidades, e reutilizados sempre que você quiser importar dados e atualizar o banco de dados.

   Um exemplo de modelo de fluxo de trabalho para importar dados está detalhado em [esta seção](../../automating/using/creating-import-workflow-templates.md).

* **Importar modelos** de dados: como os modelos de fluxo de trabalho, esses são modelos baseados em workflows, que estão configurados para carregar arquivos para atualizar o banco de dados. Depois de configurados, eles ficam disponíveis para usuários com uma visualização simplificada no menu **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]**.

   Para obter mais informações sobre como importar modelos de dados, consulte a [documentação dedicada](../../automating/using/importing-data-with-import-templates.md).

## Coleta de dados do landing page {#collecting-data-from-landing-pages}

Landing page são formulários da Web que podem ser usados para coletar dados e criar ou atualizar informações existentes no banco de dados.

O princípio é o seguinte:

* Crie e crie sua landing page adicionando campos de entrada para coletar dados (nome, sobrenome, email etc.).
* Mapeie cada campo de entrada com o campo correspondente do banco de dados.
* Disponibilize a landing page on-line por um site ou por meio de um link direto em uma mensagem.

Para obter mais informações sobre o landing page, consulte a [documentação dedicada](../../channels/using/getting-started-with-landing-pages.md).

## Sincronizando perfis do Microsoft Dynamics 365

A integração do Campaign Standard com o Microsoft Dynamics 365 permite transmitir dados de contato do Microsoft Dynamics 365 para o banco de dados de Campanhas.
Esses contatos ficam visíveis na lista de Perfis e podem ser direcionados para campanhas de marketing.

Para obter mais informações sobre essa integração, consulte a [documentação dedicada](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

>[!NOTE]
>
>Observe que o conector Campaign Standard-Microsoft Dynamics 365 está atualmente em Disponibilidade Limitada e está sujeito a várias limitações, detalhadas na documentação.

## Importação de dados por meio de chamadas de API

As APIs de Campaign Standard permitem que você execute operações para atualizar o banco de dados, como criação, atualização ou exclusão de perfis ou serviços.

Para obter mais informações sobre como usar as APIs, consulte a [documentação dedicada](../../api/using/get-started-apis.md).

>[!IMPORTANT]
>
>Antes de executar a criação em massa de perfis ou a atualização por meio de chamadas de API, verifique as limitações de escala correspondentes ao seu contrato de licença. Para obter mais informações, consulte [esta página](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).
