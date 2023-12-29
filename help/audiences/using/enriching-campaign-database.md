---
title: Enriquecimento do banco de dados
description: Saiba mais sobre os vários métodos para enriquecer o banco de dados.
audience: start
content-type: reference
topic-tags: about-adobe-campaign
feature: Profiles
role: User
level: Intermediate
exl-id: 9c55a8b3-034e-4319-8a88-7b59e83fa458
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 2%

---

# Enriquecimento do banco de dados{#enriching-the-database}

O Campaign Standard oferece várias ferramentas para ajudar você a aumentar seu banco de dados de marketing. Esta seção detalha os diferentes métodos que podem ser usados para inserir dados no Campaign, com referências às documentações dedicadas.

## Importação de dados por meio de workflows {#importing-data-through-workflows}

Os workflows permitem coletar dados e importá-los para o banco de dados do Campaign por meio do uso de [[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md) atividades.

As informações genéricas e as práticas recomendadas ao importar dados por meio de workflows são apresentadas em [nesta seção](../../automating/using/about-data-import-and-export.md).

Além disso, você pode configurar modelos para importar dados. Usar modelos de importação é uma prática recomendada se você precisar importar arquivos com a mesma estrutura regularmente.

Você pode configurar dois tipos de modelos:

* **Modelos de fluxo de trabalho**: são workflows pré-configurados que podem ser configurados uma vez de acordo com suas necessidades e reutilizados sempre que você quiser importar dados e atualizar o banco de dados.

  Um exemplo de template de workflow para importar dados é detalhado em [nesta seção](../../automating/using/creating-import-workflow-templates.md).

* **Importar modelos de dados**: assim como templates de workflow, esses são templates baseados em workflows, que são configurados para carregar arquivos para atualizar o banco de dados. Depois de configurados, eles são disponibilizados para usuários com uma visualização simplificada na **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** menu.

  Para obter mais informações sobre importação de modelos de dados, consulte a [documentação dedicada](../../automating/using/importing-data-with-import-templates.md).

## Coleta de dados de landing pages {#collecting-data-from-landing-pages}

Páginas de aterrissagem são formulários web que podem ser usados para coletar dados e criar ou atualizar informações existentes no banco de dados.

O princípio é o seguinte:

* Crie e projete a landing page adicionando campos de entrada para coletar dados (nome, sobrenome, email etc.).
* Mapeie cada campo de entrada com o campo correspondente do banco de dados.
* Disponibilizar a landing page online em um site ou por meio de um link direto em uma mensagem.

Para obter mais informações sobre landing pages, consulte [documentação dedicada](../../channels/using/getting-started-with-landing-pages.md).

## Sincronização de perfis do Microsoft Dynamics 365

A integração do Campaign Standard com o Microsoft Dynamics 365 permite transmitir dados de contato do Microsoft Dynamics 365 para o banco de dados do Campaign.
Esses contatos ficam visíveis na Lista de perfis e podem ser direcionados em campanhas de marketing.

Para obter mais informações sobre essa integração, consulte o [documentação dedicada](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>Observe que o conector do Campaign Standard-Microsoft Dynamics 365 está atualmente com a Disponibilidade limitada e está sujeito a várias limitações, detalhadas na documentação.

## Importação de dados por meio de chamadas de API

As APIs do Campaign Standard permitem executar operações para atualizar o banco de dados, como criação, atualização ou exclusão de perfis ou serviços.

Para obter mais informações sobre como usar as APIs, consulte [documentação dedicada](../../api/using/get-started-apis.md).

>[!IMPORTANT]
>
>Antes de executar a criação em massa ou atualização de perfis por meio de chamadas de API, verifique as limitações de escala correspondentes ao seu contrato de licença. Para obter mais informações, consulte [esta página](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).
