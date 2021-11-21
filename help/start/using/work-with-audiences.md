---
title: Personalização de listas
description: '"Saiba como personalizar a exibição e atuar em telas de lista no Adobe Campaign Standard: classificação, filtragem, exclusão ou duplicação de elementos. Lista as telas que exibem elementos de um ou vários recursos especificados."'
audience: start
content-type: reference
topic-tags: discovering-the-interface
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 11%

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
<td>Perfis do cliente</td>
<td>Enriquecimento do banco de dados</td>
<td>Organize seus públicos-alvo</td>
<td>Gerenciamento de privacidade</td>
</tr>
</table>

## Perfis do cliente {#customer-profiles}

<img width="60px" alt="condições" src="assets/icon_profile.svg"/>

Os perfis do Adobe Campaign representam todos os contatos armazenados no banco de dados. Cada perfil corresponde a uma entrada no banco de dados que contém as informações necessárias para que esse perfil seja direcionado, qualificado e rastreado individualmente. Isso significa que um perfil pode ser: um cliente, um prospecto, um indivíduo que se inscreveu em um boletim informativo, um recipient, um usuário ou qualquer outra denominação dependendo da organização.

**Leia mais**

* [Sobre perfis](../../audiences/using/about-profiles.md)
* [Acessar o número de perfis ativos na organização](../../audiences/using/active-profiles.md)

## Enriquecimento do banco de dados {#populating-database}

<img width="60px" alt="condições" src="assets/icon_populate.svg"/>

O Campaign Standard oferece várias ferramentas para ajudá-lo a expandir seu banco de dados de marketing. Esta seção detalha os diferentes métodos que podem ser usados para inserir dados no Campaign, com referências às documentações dedicadas.

### Importação de dados por meio de workflows {#importing-data-through-workflows}

Os workflows permitem coletar dados e importá-los para o banco de dados do Campaign por meio do uso de [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) atividades. Informações genéricas e práticas recomendadas ao importar dados por meio de workflows são apresentadas em [esta seção](../../automating/using/about-data-import-and-export.md).

Além disso, é possível configurar modelos para importar dados. O uso de templates de importação é uma prática recomendada para importar arquivos com a mesma estrutura regularmente. Você pode configurar dois tipos de templates:

* **Templates de workflow**: esses são workflows pré-configurados que podem ser configurados uma vez de acordo com suas necessidades e reutilizados sempre que você quiser importar dados e atualizar o banco de dados. Um exemplo de template de workflow para importar dados é detalhado em [esta seção](../../automating/using/creating-import-workflow-templates.md).

* **Importar modelos de dados**: como modelos de workflow, esses são modelos baseados em workflows, que são configurados para carregar arquivos para atualizar o banco de dados. Depois de configurados, eles são disponibilizados para usuários com uma visualização simplificada na **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** menu. Para obter mais informações sobre importação de templates de dados, consulte [documentação dedicada](../../automating/using/importing-data-with-import-templates.md).

### Coleta de dados de landing pages {#collecting-data-from-landing-pages}

As landing pages são formulários web que podem ser usados para coletar dados e criar ou atualizar informações existentes no banco de dados. O princípio é o seguinte:

* Crie e projete sua landing page adicionando campos de entrada para coletar dados (nome, sobrenome, email, etc.).
* Mapeie cada campo de entrada com o campo correspondente do banco de dados.
* Disponibilizar a landing page online através de um site ou por meio de um link direto em uma mensagem.

Para obter mais informações sobre landing pages, consulte o [documentação dedicada](../../channels/using/getting-started-with-landing-pages.md).

**Leia mais**

* xxxx
* xxxx

### Sincronizar perfis do Microsoft Dynamics 365

A integração do Campaign Standard com o Microsoft Dynamics 365 permite transmitir dados de contato do Microsoft Dynamics 365 para o banco de dados do Campaign.
Esses contatos ficam visíveis na lista Perfis e podem ser direcionados para campanhas de marketing. Para obter mais informações sobre essa integração, consulte [documentação dedicada](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>Observe que o conector Campaign Standard-Microsoft Dynamics 365 está atualmente com Disponibilidade Limitada e está sujeito a várias limitações, detalhadas na documentação.

**Leia mais**

* xxxx
* xxxx

### Importação de dados por meio de chamadas de API

As APIs do Campaign Standard permitem executar operações para atualizar o banco de dados, como criação, atualização ou exclusão de perfis ou serviços. Para obter mais informações sobre como usar as APIs, consulte [documentação dedicada](../../api/using/get-started-apis.md).

>[!CAUTION]
>
>Antes de executar a criação em massa de perfis ou a atualização por meio de chamadas de API, verifique as limitações de escala correspondentes ao seu contrato de licença. Para obter mais informações, consulte [esta página](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).

**Leia mais**

* xxxx
* xxxx

## Organizar os públicos {#organizing-audiences}

<img width="60px" alt="condições" src="assets/icon_audience.svg"/>

Para permitir que você entregue mensagens relevantes e eficazes e envolva seus clientes com eficiência, o Adobe Campaign integra funcionalidades avançadas de análise e direcionamento.

Graças aos fluxos de trabalho e ao editor de consultas, você pode criar públicos-alvo que serão direcionados por suas diferentes campanhas, dependendo das informações que você tem sobre eles, suas atividades, idioma, preferências ou histórico de marketing. Isso permite filtrar os perfis subscritos, por exemplo, ou criar públicos-alvo em um número ilimitado de critérios.

**Leia mais**

* [Sobre públicos](../../audiences/using/about-audiences.md)
* [Criação de públicos](../../audiences/using/creating-audiences.md)

## Gerenciamento de privacidade {#privacy-management}

<img width="60px" alt="condições" src="assets/icon_privacy.svg"/>

O GDPR é a nova lei de privacidade da União Europeia que concilia e moderniza os requisitos de proteção de dados. O GDPR aplica-se aos clientes do Adobe Campaign que coletam dados de residentes da UE. Além dos recursos de privacidade já disponíveis no Adobe Campaign (incluindo o gerenciamento de consentimento, as configurações de retenção de dados e as funções de usuários), aproveitamos a oportunidade, em função de nosso papel como Processador de Dados, para incluir recursos adicionais que ajudam o Controlador de Dados a estar de acordo com determinadas solicitações do GDPR.

Consulte esta [guia](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=pt-BR) para saber mais sobre as ferramentas e as funcionalidades fornecidas pelo Adobe Campaign para ajudá-lo a se tornar compatível com o GDPR.

**Leia mais**

* xxxx
* xxxx