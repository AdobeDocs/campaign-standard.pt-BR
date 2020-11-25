---
solution: Campaign Standard
product: campaign
title: Gerenciamento de privacidade no Adobe Campaign Standard
description: Saiba mais sobre os recursos da Adobe Campaign Standard para gerenciar a privacidade.
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: tm+mt
source-git-commit: a9afa91302684ddd37a94a9999d90bf8c8e7abee
workflow-type: tm+mt
source-wordcount: '964'
ht-degree: 44%

---


# Gerenciamento de privacidade {#privacy-management}

Adobe Campaign offers a set of tools to help you comply with [Privacy regulations](#privacy-management-regulations) (including GDPR, CCPA, PDPA, LGPD).

Estes são os cinco principais recursos oferecidos pela Adobe Campaign para garantir o RGPD e outras regulamentações de privacidade prontas:

![](assets/privacy-gdpr-use-cases.png)

* **Direito de acesso**

* **Direito de excluir**

Para obter mais informações, consulte [Direito de acesso e direito de ser esquecido](#right-access-forgotten).

* **Gerenciamento de consentimento**

* **Retenção de dados**

* **Gerenciamento de direitos**

Para obter mais informações, consulte [Consentimento, Retenção e Funções](#consent-retention-roles).

<!--This section presents general information on what Privacy management is and the features provided by Adobe Campaign to manage the [Right to Access and Right to be Forgotten](#right-access-forgotten).

It also contains information on important features to manage Privacy ([consent, data retention and user roles](#consent-retention-roles)), as well as best practices to help you with your Privacy compliance when using Adobe Campaign.-->

## Regulamentos relativos à gestão da privacidade {#privacy-management-regulations}

Os recursos da Adobe Campaign ajudam você a cumprir as seguintes normas:

* **O GDPR** ([Regulamento Geral sobre a Proteção de Dados](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en)) é a lei de privacidade da União Europeia (UE) que adequa e moderniza os requisitos de proteção de dados para os países membros da UE. Siga os links abaixo para encontrar informações gerais sobre o RGPD:

   * https://www.adobe.com/br/privacy/general-data-protection-regulation.html
   * https://www.adobe.com/br/marketing-cloud/campaign/general-data-protection-regulation.html

* **O CCPA** ([Ato de privacidade do consumidor da Califórnia](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=)) fornece aos residentes da Califórnia novos direitos no que diz respeito a suas informações pessoais e impõe responsabilidades de proteção de dados a determinadas entidades com negócios na Califórnia.
* **O PDPA** ([Personal Data Protection Act](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/)) é a nova lei de privacidade que harmoniza e moderniza os requisitos de proteção de dados para a Tailândia.
* **A LGPD** ([Lei Geral de Proteção de Dados](https://iapp.org/media/pdf/resource_center/Brazilian_General_Data_Protection_Law.pdf)) entrará em vigor no início de 2021 para todas as empresas que coletam ou processam dados pessoais no Brasil.

Todos esses regulamentos se aplicam a clientes do Adobe Campaign que detêm dados para residentes nas respectivas regiões ou países mencionados acima (UE, Califórnia, Tailândia e Brasil).

>[!NOTE]
>
>Para obter mais informações sobre dados pessoais e as diferentes entidades que gerenciam os dados (Controlador de dados, Operador de dados e Titular de dados), consulte [Dados pessoais e Personalidades](../../start/using/privacy.md#personal-data).

## Right to Access and Right to be Forgotten {#right-access-forgotten}

In order to help you facilitate your Privacy readiness, Adobe Campaign allows you to handle **Access** and **Delete** requests.

* The **Right to Access** is the right for the Data Subject to obtain from the Data Controller confirmation as to whether or not personal data concerning them is being processed, where and for what purpose. O Controlador de dados deve fornecer uma cópia gratuita dos dados pessoais em formato eletrônico.

* Also known as Data Erasure, the **Right to be Forgotten** (delete request) entitles the Data Subject to have the Data Controller erase his/her personal data, cease further dissemination of the data, and potentially have third parties halt processing of the data.

To learn how you can create **Access** and **Delete** requests and how Adobe Campaign processes them, refer to the [implementation steps](../../start/using/privacy-requests.md#about-privacy-requests).

Tutorials on Privacy management in Campaign Standard are also available [here](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html?lang=en#privacy).

>[!NOTE]
>
>Para obter mais informações sobre dados pessoais e as diferentes entidades que gerenciam os dados (Controlador de dados, Operador de dados e Titular de dados), consulte [Dados pessoais e Personalidades](../../start/using/privacy.md#personal-data).

## Consentimento, retenção e funções {#consent-retention-roles}

Além dos recursos mais recentes **Direito de acesso** e **Direito de ser esquecido** , a Adobe Campaign oferta outros recursos importantes essenciais para a privacidade:

* [Gerenciamento](#consent-management)de consentimento: Funcionalidade de subscrição para gerenciamento de preferências
* [Retenção](#data-retention)de dados: períodos de retenção de dados em todas as tabelas de log padrão, períodos de retenção adicionais podem ser configurados com workflows
* [Gerenciamento de direitos](#rights-management): acesso a dados gerenciados por direito nomeado     

### Gerenciamento de consentimento {#consent-management}

Consentimento significa acordo da pessoa em causa para o tratamento de dados pessoais relativos a uma pessoa em causa. A obtenção de qualquer consentimento necessário para esse processamento é de responsabilidade do Controlador de Dados. Embora o Adobe Campaign forneça alguns recursos para ajudar o cliente a gerenciar o consentimento relacionado ao serviço, o Adobe não é responsável pelo consentimento. Os clientes devem trabalhar com os seus próprios serviços jurídicos para determinarem os seus próprios processos e práticas para qualquer consentimento necessário.

Os recursos para ajudar a gerenciar alguns aspectos do consentimento são fundamentais para a Adobe Campaign desde o início. Por meio do processo de gerenciamento de subscrições, os clientes podem rastrear quais recipient aceitaram em qual tipo de subscrição quer sejam boletins informativos, promoções diárias ou semanais ou qualquer outro tipo de programa de marketing.

![](assets/privacy-consent-management.png)

Para obter mais informações sobre o Gerenciamento de conteúdo, consulte [Sobre o subscrição](../../audiences/using/about-subscriptions.md) e [Introdução ao landing page](../../channels/using/getting-started-with-landing-pages.md).

Além das ferramentas de Gerenciamento de Consentimento fornecidas pela Adobe Campaign, você tem a possibilidade de rastrear se um consumidor optou pela venda de Informações Pessoais. Consulte [esta seção](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).

### Retenção de dados {#data-retention}

Em relação à retenção, as tabelas de log incorporadas na Campanha têm períodos de retenção predefinidos, geralmente limitando o armazenamento de dados a seis meses ou menos.

A seguir estão os valores de retenção padrão para tabelas integradas. Esteja ciente de que a configuração de retenção é definida pelos administradores técnicos da Adobe durante a implementação e os valores podem variar com base nos requisitos do cliente.

* **Rastreamento consolidado**: 6 meses
* **Registros de entrega**: 6 meses
* **Registros de monitoramento**: 6 meses
* **Eventos**: 1 mês
* **Estatísticas de processamento de evento**: 6 meses
* **Eventos arquivados**: 6 meses
* **Entidades** temporárias: 7 dias
* **Eventos de pipeline ignorados**: 1 mês
* **Alertas de entrega**: 1 mês
* **Auditoria de exportação**: 6 meses

E, assim como excluir, usando a funcionalidade padrão do fluxo de trabalho, é possível configurar períodos de retenção para qualquer tabela personalizada.

Entre em contato com os consultores Adobe ou administradores técnicos para saber mais sobre retenção ou se é necessário definir retenção para tabelas personalizadas.

### Gerenciamento de direitos {#rights-management}

O Adobe Campaign oferece a capacidade de gerenciar os direitos atribuídos aos vários operadores do Campaign por meio de diferentes funções pré-concebidas ou personalizadas.

Um dos benefícios é o de permitir a gestão da decisão sobre quem poderá acessar os diferentes tipos de dados na empresa. Por exemplo, é possível ter diferentes profissionais de marketing que cubram diversas regiões e cada um deles só poderá acessar os dados da sua região geográfica.

Da mesma forma, essa funcionalidade também permite a configuração de diferentes recursos para cada usuário, como limitar quem pode enviar as entregas, ou algo mais relevante para o Gerenciamento de privacidade, como quem pode alterar ou exportar dados.

![](assets/privacy-user-management.png)

For more on access management, see [this section](../../administration/using/about-access-management.md).