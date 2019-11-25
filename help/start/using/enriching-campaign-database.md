---
title: Enriquecimento da base de dados
description: Saiba mais sobre os vários métodos para enriquecer o banco de dados.
page-status-flag: never-activated
uuid: 71f53808-0309-49f6-a4ee-3446eac9758a
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b06edadfa963881403328c4ab37d25d701bc8237

---


# Enriquecimento da base de dados{#enriching-the-database}

O Campaign Standard oferece várias ferramentas para ajudá-lo a expandir seu banco de dados de marketing. Esta seção detalha os diferentes métodos que você pode usar para injetar dados no Campaign, com referências às documentações dedicadas.

## Importação de dados por meio de fluxos de trabalho {#importing-data-through-workflows}

Os fluxos de trabalho permitem coletar dados e importá-los para o banco de dados do Campaign por meio do uso de [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) atividades.

Informações genéricas e práticas recomendadas ao importar dados por meio de fluxos de trabalho são apresentadas [nesta seção](../../automating/using/importing-data.md).

Além disso, você pode configurar modelos para importar dados. Usar modelos de importação é uma prática recomendada se você precisar importar arquivos com a mesma estrutura regularmente.

Você pode configurar dois tipos de modelos:

* **Modelos** de fluxo de trabalho: esses são fluxos de trabalho pré-configurados que podem ser configurados uma vez, de acordo com suas necessidades, e reutilizados sempre que você quiser importar dados e atualizar o banco de dados.

   Um exemplo de modelo de fluxo de trabalho para importar dados está detalhado [nesta seção](../../automating/using/importing-data.md#example--import-workflow-template).

* **Importar modelos** de dados: como modelos de fluxo de trabalho, esses são modelos baseados em fluxos de trabalho, que são configurados para carregar arquivos para atualizar o banco de dados. Depois de configurados, eles ficam disponíveis para usuários com uma visualização simplificada no menu **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** .

   Para obter mais informações sobre como importar modelos de dados, consulte a documentação [](../../automating/using/importing-data-with-import-templates.md)dedicada.

## Coleta de dados de páginas iniciais {#collecting-data-from-landing-pages}

As páginas iniciais são formulários da Web que podem ser usados para coletar dados e criar ou atualizar informações existentes no banco de dados.

O princípio é o seguinte:

* Crie e crie sua página inicial adicionando campos de entrada para coletar dados (nome, sobrenome, email etc.).
* Mapeie cada campo de entrada com o campo correspondente do banco de dados.
* Disponibilize a página de aterrissagem on-line através de um site ou por meio de um link direto em uma mensagem.

Para obter mais informações sobre páginas iniciais, consulte a documentação [](../../channels/using/about-landing-pages.md)dedicada.

## Sincronizando perfis do Microsoft Dynamics 365

A integração do Campaign Standard com o Microsoft Dynamics 365 permite transmitir dados de contato do Microsoft Dynamics 365 para o banco de dados do Campaign.
Esses contatos ficam visíveis na lista Perfis e podem ser direcionados para campanhas de marketing.

For more on this integration, refer to the [dedicated documentation](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html).

>[!NOTE]
>
>Observe que o conector Campaign Standard-Microsoft Dynamics 365 está atualmente em Disponibilidade Limitada e está sujeito a várias limitações, detalhadas na documentação.

## Importação de dados por meio de chamadas de API

As APIs do Campaign Standard permitem que você execute operações para atualizar o banco de dados, como criação, atualização ou exclusão de perfis ou serviços.

For more on how to use the APIs, refer to the [dedicated documentation](../../api/using/about-campaign-standard-apis.md).

>[!CAUTION]
>
>Antes de executar a criação ou atualização em massa de perfis por meio de chamadas de API, verifique as limitações de escala correspondentes ao seu contrato de licença. Para obter mais informações, consulte [esta página](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).
