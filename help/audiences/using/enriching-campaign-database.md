---
solution: Campaign Standard
product: campaign
title: Enriquecimento do banco de dados
description: Saiba mais sobre os vários métodos para enriquecer o banco de dados.
audience: start
content-type: reference
topic-tags: about-adobe-campaign
feature: Profiles
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 3%

---


# Enriquecimento do banco de dados{#enriching-the-database}

O Campaign Standard oferece várias ferramentas para ajudá-lo a expandir seu banco de dados de marketing. Esta seção detalha os diferentes métodos que podem ser usados para inserir dados no Campaign, com referências às documentações dedicadas.

## Importação de dados por meio de workflows {#importing-data-through-workflows}

Os workflows permitem coletar dados e importá-los para o banco de dados do Campaign usando atividades [[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md) .

As informações genéricas e as práticas recomendadas ao importar dados por meio de workflows são apresentadas em [this section](../../automating/using/about-data-import-and-export.md).

Além disso, é possível configurar modelos para importar dados. O uso de templates de importação é uma prática recomendada se você precisar importar arquivos com a mesma estrutura regularmente.

Você pode configurar dois tipos de templates:

* **Templates** de workflow: são workflows pré-configurados que podem ser configurados uma vez de acordo com suas necessidades e reutilizados sempre que quiser importar dados e atualizar o banco de dados.

   Um exemplo de template de workflow para importar dados é detalhado em [this section](../../automating/using/creating-import-workflow-templates.md).

* **Importar modelos** de dados: como modelos de workflow, esses são modelos baseados em workflows, que são configurados para carregar arquivos para atualizar o banco de dados. Depois de configurados, eles são disponibilizados para usuários com uma visualização simplificada no menu **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]**.

   Para obter mais informações sobre importar templates de dados, consulte a [documentação dedicada](../../automating/using/importing-data-with-import-templates.md).

## Coleta de dados de landing pages {#collecting-data-from-landing-pages}

As landing pages são formulários web que podem ser usados para coletar dados e criar ou atualizar informações existentes no banco de dados.

O princípio é o seguinte:

* Crie e projete sua landing page adicionando campos de entrada para coletar dados (nome, sobrenome, email, etc.).
* Mapeie cada campo de entrada com o campo correspondente do banco de dados.
* Disponibilizar a landing page online através de um site ou por meio de um link direto em uma mensagem.

Para obter mais informações sobre landing pages, consulte a [documentação dedicada](../../channels/using/getting-started-with-landing-pages.md).

## Sincronizar perfis do Microsoft Dynamics 365

A integração do Campaign Standard com o Microsoft Dynamics 365 permite transmitir dados de contato do Microsoft Dynamics 365 para o banco de dados do Campaign.
Esses contatos ficam visíveis na lista Perfis e podem ser direcionados para campanhas de marketing.

Para obter mais informações sobre essa integração, consulte a [documentação dedicada](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>Observe que o conector Campaign Standard-Microsoft Dynamics 365 está atualmente com Disponibilidade Limitada e está sujeito a várias limitações, detalhadas na documentação.

## Importação de dados por meio de chamadas de API

As APIs do Campaign Standard permitem executar operações para atualizar o banco de dados, como criação, atualização ou exclusão de perfis ou serviços.

Para obter mais informações sobre como usar as APIs, consulte a [documentação dedicada](../../api/using/get-started-apis.md).

>[!IMPORTANT]
>
>Antes de executar a criação em massa de perfis ou a atualização por meio de chamadas de API, verifique as limitações de escala correspondentes ao seu contrato de licença. Para obter mais informações, consulte [esta página](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).
