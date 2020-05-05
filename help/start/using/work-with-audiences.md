---
title: Personalização de listas
description: '"Saiba como personalizar a exibição e agir em telas de lista no Adobe Campaign Standard: classificar, filtrar, excluir ou duplicar elementos. As telas do Lista exibem elementos de um ou vários recursos especificados."'
page-status-flag: never-activated
uuid: 3350583c-91ca-4ea5-ac14-6b6f11c4a64a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 4ba4f766-fdee-4ff0-8fe4-0612ed2b69a4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 816d550d8bd0de085a47f97c1f6cc2fbb5e7acb9

---


# Trabalhar com perfis e audiências

<table>
<tr>
    <td valign="top">
        <a href="../../start/using/work-with-audiences.md"><img width="60px" alt="condições" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/creating-a-service.md"><img width="60px" alt="condições" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-custom-resources.md"><img width="60px" alt="condições" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-marketing-history.md"><img width="60px" alt="condições" src="assets/icon_profile.svg"/></a>
    </td>
</tr>
<tr>
<td>perfis do cliente</td>
<td>Enriquecendo seu banco de dados</td>
<td>Organizar suas audiências</td>
<td>Gerenciamento de privacidade</td>
</tr>
</table>

## perfis do cliente {#customer-profiles}

<img width="60px" alt="condições" src="assets/icon_profile.svg"/>

perfis Adobe Campaign representam todos os contatos armazenados no banco de dados. Cada perfil corresponde a uma entrada no banco de dados que contém as informações necessárias para que o perfil seja direcionado, qualificado e rastreado individualmente. Isso significa que um perfil pode ser: um cliente, um prospecto, um indivíduo inscrito em um boletim informativo, um recipient, um usuário ou qualquer outra denominação dependendo da organização.

**Leia mais**

* [Sobre perfis](../../audiences/using/about-profiles.md)
* [Acessar o número de Perfis ativos em sua organização](../../audiences/using/active-profiles.md)

## Enriquecendo seu banco de dados {#populating-database}

<img width="60px" alt="condições" src="assets/icon_populate.svg"/>

O Campaign Standard oferta várias ferramentas para ajudá-lo a expandir seu banco de dados de marketing. Esta seção detalha os diferentes métodos que podem ser usados para injetar dados na Campanha, com referências às documentações dedicadas.

### Importação de dados por meio de workflows {#importing-data-through-workflows}

Os Workflows permitem coletar dados e importá-los para o banco de dados de Campanha por meio do uso do [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) atividade. As informações genéricas e as práticas recomendadas ao importar dados por meio de workflows são apresentadas [nesta seção](../../automating/using/importing-data.md).

Além disso, você pode configurar modelos para importar dados. Usar templates de importação é uma prática recomendada se você precisar importar arquivos com a mesma estrutura regularmente. Você pode configurar dois tipos de modelos:

* **Modelos** de fluxo de trabalho: são workflows pré-configurados que podem ser configurados uma vez, de acordo com suas necessidades, e reutilizados sempre que você quiser importar dados e atualizar o banco de dados. Um exemplo de modelo de fluxo de trabalho para importar dados está detalhado [nesta seção](../../automating/using/importing-data.md#example--import-workflow-template).

* **Importar modelos** de dados: como os modelos de fluxo de trabalho, esses são modelos baseados em workflows, que estão configurados para carregar arquivos para atualizar o banco de dados. Depois de configurados, eles ficam disponíveis para usuários com uma visualização simplificada no menu **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** . Para obter mais informações sobre como importar modelos de dados, consulte a documentação [](../../automating/using/importing-data-with-import-templates.md)dedicada.

### Coleta de dados do landing page {#collecting-data-from-landing-pages}

Landing page são formulários da Web que podem ser usados para coletar dados e criar ou atualizar informações existentes no banco de dados. O princípio é o seguinte:

* Crie e crie sua landing page adicionando campos de entrada para coletar dados (nome, sobrenome, email etc.).
* Mapeie cada campo de entrada com o campo correspondente do banco de dados.
* Disponibilize a landing page on-line por um site ou por meio de um link direto em uma mensagem.

Para obter mais informações sobre o landing page, consulte a documentação [](../../channels/using/getting-started-with-landing-pages.md)dedicada.

**Leia mais**

* xxxx
* xxxx

### Sincronizando perfis do Microsoft Dynamics 365

A integração do Campaign Standard com o Microsoft Dynamics 365 permite transmitir dados de contato do Microsoft Dynamics 365 para o banco de dados de Campanhas.
Esses contatos ficam visíveis na lista de Perfis e podem ser direcionados para campanhas de marketing. For more on this integration, refer to the [dedicated documentation](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html).

>[!NOTE]
>
>Observe que o conector Campaign Standard-Microsoft Dynamics 365 está atualmente em Disponibilidade Limitada e está sujeito a várias limitações, detalhadas na documentação.

**Leia mais**

* xxxx
* xxxx

### Importação de dados por meio de chamadas de API

As APIs de Campaign Standard permitem que você execute operações para atualizar o banco de dados, como criação, atualização ou exclusão de perfis ou serviços. For more on how to use the APIs, refer to the [dedicated documentation](../../api/using/get-started-apis.md).

>[!CAUTION]
>
>Antes de executar a criação em massa de perfis ou a atualização por meio de chamadas de API, verifique as limitações de escala correspondentes ao seu contrato de licença. Para obter mais informações, consulte [esta página](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).

**Leia mais**

* xxxx
* xxxx

## Organizar suas audiências {#organizing-audiences}

<img width="60px" alt="condições" src="assets/icon_audience.svg"/>

Para permitir que você forneça mensagens relevantes e eficazes e envolva seus clientes com eficiência, o Adobe Campaign integra funcionalidades avançadas de análise e segmentação.

Graças aos workflows e ao editor de query, você pode criar audiências que serão direcionadas pelas suas diferentes campanhas, dependendo das informações que você tiver sobre elas, suas atividades, seus idiomas, suas preferências ou seus históricos de marketing. Isso permite que você filtre perfis inscritos, por exemplo, ou crie audiências de públicos alvos em um número ilimitado de critérios.

**Leia mais**

* [Sobre públicos-alvo](../../audiences/using/about-audiences.md)
* [Criação de públicos-alvo](../../audiences/using/creating-audiences.md)

## Gerenciamento de privacidade {#privacy-management}

<img width="60px" alt="condições" src="assets/icon_privacy.svg"/>

O GDPR é a nova lei de privacidade da União Europeia que concilia e moderniza os requisitos de proteção de dados. O GDPR aplica-se aos clientes do Adobe Campaign que coletam dados de residentes da UE. Além dos recursos de privacidade já disponíveis no Adobe Campaign (incluindo gerenciamento de consentimento, configurações de retenção de dados e funções de usuário), estamos aproveitando essa oportunidade em nossa função de Processador de dados para incluir recursos adicionais, para ajudar a facilitar sua preparação como Controlador de dados para determinadas solicitações do RGPD.

Consulte este [guia](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) para saber mais sobre as ferramentas e funcionalidades fornecidas pelo Adobe Campaign para ajudá-lo a se tornar compatível com o RGPD.

**Leia mais**

* xxxx
* xxxx