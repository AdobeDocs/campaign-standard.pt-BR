---
title: Personalização de listas
description: Saiba como personalizar a exibição e atuar em telas de lista no Adobe Campaign Standard:classificando, filtrando, excluindo ou duplicando elementos. Lista os elementos de exibição das telas de um ou vários recursos fornecidos.
audience: start
content-type: reference
topic-tags: discovering-the-interface
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 6%

---


# Trabalhar com perfis e públicos

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
<td>Perfis de cliente</td>
<td>Enriquecimento do banco de dados</td>
<td>Organize seus públicos</td>
<td>Gerenciamento de privacidade</td>
</tr>
</table>

## Perfis de cliente {#customer-profiles}

<img width="60px" alt="condições" src="assets/icon_profile.svg"/>

Os perfis do Adobe Campaign representam todos os contatos armazenados no banco de dados. Cada perfil corresponde a uma entrada no banco de dados que contém as informações necessárias para que esse perfil seja direcionado, qualificado e rastreado individualmente. Isso significa que um perfil pode ser: um cliente, um prospecto, uma pessoa inscrita em um boletim informativo, um recipient, um usuário ou qualquer outra denominação dependendo da organização.

**Leia mais**

* [Sobre perfis](../../audiences/using/about-profiles.md)
* [Acessar o número de perfis ativos em sua organização](../../audiences/using/active-profiles.md)

## Enriquecimento do banco de dados {#populating-database}

<img width="60px" alt="condições" src="assets/icon_populate.svg"/>

O Campaign Standard oferece várias ferramentas para ajudar você a aumentar seu banco de dados de marketing. Esta seção detalha os diferentes métodos que podem ser usados para inserir dados no Campaign, com referências às documentações dedicadas.

### Importação de dados por meio de workflows {#importing-data-through-workflows}

Os fluxos de trabalho permitem coletar dados e importá-los para o banco de dados do Campaign por meio do uso de [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) atividades. Informações genéricas e práticas recomendadas ao importar dados por meio de fluxos de trabalho são apresentadas em [esta seção](../../automating/using/about-data-import-and-export.md).

Além disso, você pode configurar modelos para importar dados. O uso de modelos de importação é uma prática recomendada para importar arquivos com a mesma estrutura regularmente. Você pode configurar dois tipos de modelos:

* **Modelos de fluxo de trabalho**: são fluxos de trabalho pré-configurados que você pode configurar uma vez de acordo com suas necessidades e reutilizar sempre que desejar importar dados e atualizar o banco de dados. Um exemplo de modelo de fluxo de trabalho para importar dados está detalhado em [esta seção](../../automating/using/creating-import-workflow-templates.md).

* **Importar modelos de dados**: assim como modelos de fluxo de trabalho, esses são modelos baseados em fluxos de trabalho, que são configurados para carregar arquivos para atualizar o banco de dados. Após configurados, eles são disponibilizados para usuários com uma exibição simplificada no menu **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]**. Para saber mais sobre como importar modelos de dados, consulte a [documentação dedicada](../../automating/using/importing-data-with-import-templates.md).

### Coleta de dados de landing pages {#collecting-data-from-landing-pages}

Páginas de aterrissagem são formulários web que podem ser usados para coletar dados e criar ou atualizar informações existentes no banco de dados. O princípio é o seguinte:

* Crie e projete a landing page adicionando campos de entrada para coletar dados (nome, sobrenome, email etc.).
* Mapeie cada campo de entrada com o campo correspondente do banco de dados.
* Disponibilizar a landing page online em um site ou por meio de um link direto em uma mensagem.

Para obter mais informações sobre páginas de aterrissagem, consulte a [documentação dedicada](../../channels/using/getting-started-with-landing-pages.md).

**Leia mais**

* xxxx
* xxxx

### Sincronização de perfis do Microsoft Dynamics 365

A integração do Campaign Standard com o Microsoft Dynamics 365 permite transmitir dados de contato do Microsoft Dynamics 365 para o banco de dados do Campaign.
Esses contatos ficam visíveis na Lista de perfis e podem ser direcionados em campanhas de marketing. Para obter mais informações sobre essa integração, consulte a [documentação dedicada](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>Observe que o conector Campaign Standard-Microsoft Dynamics 365 está atualmente com a disponibilidade limitada e está sujeito a várias limitações, detalhadas na documentação.

**Leia mais**

* xxxx
* xxxx

### Importação de dados por meio de chamadas de API

As APIs do Campaign Standard permitem executar operações para atualizar o banco de dados, como criação, atualização ou exclusão de perfis ou serviços. Para obter mais informações sobre como usar as APIs, consulte a [documentação dedicada](../../api/using/get-started-apis.md).

>[!CAUTION]
>
>Antes de executar a criação em massa ou atualização de perfis por meio de chamadas de API, verifique as limitações de escala correspondentes ao seu contrato de licença. Para obter mais informações, consulte [esta página](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).

**Leia mais**

* xxxx
* xxxx

## Organizar seus públicos {#organizing-audiences}

<img width="60px" alt="condições" src="assets/icon_audience.svg"/>

Para permitir que você forneça mensagens relevantes e eficazes e envolva seus clientes de maneira eficaz, o Adobe Campaign integra funcionalidades avançadas de análise e direcionamento.

Graças aos workflows e ao editor de query, você pode construir públicos-alvo que serão direcionados por suas diferentes campanhas, dependendo das informações que você tem neles, suas atividades, seu idioma, suas preferências ou seu histórico de marketing. Isso permite filtrar perfis inscritos, por exemplo, ou criar públicos-alvo em um número ilimitado de critérios.

**Leia mais**

* [Sobre públicos](../../audiences/using/about-audiences.md)
* [Criação de públicos](../../audiences/using/creating-audiences.md)

## Gerenciamento de privacidade {#privacy-management}

<img width="60px" alt="condições" src="assets/icon_privacy.svg"/>

O GDPR é a nova lei de privacidade da União Europeia que adequa e moderniza os requisitos de proteção de dados. O GDPR se aplica aos clientes do Adobe Campaign que coletam dados de residentes da UE. Além dos recursos de privacidade já disponíveis no Adobe Campaign (incluindo gerenciamento de consentimento, configurações de retenção de dados e funções de usuário), aproveitamos a oportunidade, em função da nossa função de Processador de dados, para incluir recursos adicionais que ajudam o Controlador de dados a estar de acordo com determinadas solicitações do GDPR.

Consulte [esta seção](../../start/using/privacy.md) para saber mais sobre as ferramentas e funcionalidades que a Adobe Campaign fornece para ajudá-lo a se tornar compatível com o GDPR.

**Leia mais**

* xxxx
* xxxx