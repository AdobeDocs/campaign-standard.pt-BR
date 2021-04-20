---
solution: Campaign Standard
product: campaign
title: Gerenciamento de privacidade no Adobe Campaign Standard
description: Saiba mais sobre os recursos do Adobe Campaign Standard para gerenciar a privacidade.
audience: start
content-type: reference
topic-tags: discovering-the-interface
feature: Privacy
role: Business Practitioner
level: Intermediate
exl-id: 84cf8f6e-9ba0-4cd5-80e2-a61cefa31e0a
translation-type: ht
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: ht
source-wordcount: '965'
ht-degree: 100%

---

# Gerenciamento de privacidade {#privacy-management}

O Adobe Campaign oferece um conjunto de ferramentas para ajudar você a cumprir as [regras de privacidade](#privacy-management-regulations) (incluindo GDPR, CCPA, PDPA, LGPD).

Estes são os cinco principais recursos oferecidos pelo Adobe Campaign para garantir a conformidade com o GDPR e outras regras de privacidade:

![](assets/privacy-gdpr-use-cases.png)

* **Direito de acesso**

* **Direito de exclusão**

Para obter mais informações, consulte [Direito de acesso e direito ao esquecimento](#right-access-forgotten).

* **Gerenciamento de consentimento**

* **Retenção de dados**

* **Gerenciamento de direitos**

Para obter mais informações, consulte [Consentimento, Retenção e Funções](#consent-retention-roles).

<!--This section presents general information on what Privacy management is and the features provided by Adobe Campaign to manage the [Right to Access and Right to be Forgotten](#right-access-forgotten).

It also contains information on important features to manage Privacy ([consent, data retention and user roles](#consent-retention-roles)), as well as best practices to help you with your Privacy compliance when using Adobe Campaign.-->

## Regras sobre a gestão da privacidade {#privacy-management-regulations}

Os recursos do Adobe Campaign ajudam você a cumprir os seguintes requisitos:

* **O GDPR** ([Regulamento Geral sobre a Proteção de Dados](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en)) é a lei de privacidade da União Europeia (UE) que adequa e moderniza os requisitos de proteção de dados nos países membros da UE. Siga os links abaixo para encontrar informações gerais sobre o GDPR:

   * https://www.adobe.com/br/privacy/general-data-protection-regulation.html
   * https://www.adobe.com/marketing-cloud/campaign/general-data-protection-regulation.html

* **O CCPA** ([Ato de privacidade do consumidor da Califórnia](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=)) fornece aos residentes da Califórnia novos direitos no que diz respeito a suas informações pessoais e impõe responsabilidades de proteção de dados a determinadas entidades com negócios na Califórnia.
* O **PDPA** ([Ato de proteção de dados pessoais)](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/) é a nova lei de privacidade que adequa e moderniza os requisitos de proteção de dados na Tailândia.
* **A LGPD** ([Lei Geral de Proteção de Dados](https://iapp.org/media/pdf/resource_center/Brazilian_General_Data_Protection_Law.pdf)) entrará em vigor no início de 2021 para todas as empresas que coletam ou processam dados pessoais no Brasil.

Todos esses regulamentos se aplicam a clientes do Adobe Campaign que detêm dados para residentes nas respectivas regiões ou países mencionados acima (UE, Califórnia, Tailândia e Brasil).

>[!NOTE]
>
>Para obter mais informações sobre dados pessoais e as diferentes entidades que gerenciam os dados (Controlador de dados, Operador de dados e Titular de dados), consulte [Dados pessoais e Personalidades](../../start/using/privacy.md#personal-data).

## Direito de acesso e Direito ao esquecimento {#right-access-forgotten}

Para facilitar a conformidade com a privacidade, o Adobe Campaign permite manipular solicitações de **Acesso** e **Exclusão**.

* O **Direito de acesso** é o direito do Titular de dados de obter a confirmação do Controlador de dados, caso os dados relativos a ele estiverem sendo processados, onde e com qual finalidade. O Controlador de dados deve fornecer uma cópia gratuita dos dados pessoais em formato eletrônico.

* Também conhecido como Eliminação de dados, o **Direito ao esquecimento** (solicitação de exclusão) autoriza o Titular de dados a fazer com que o Controlador de dados apague seus dados pessoais, interrompa a divulgação dos dados e possivelmente o processamento dos dados por parte de terceiros.

Para saber como criar solicitações de **Acesso** e **Exclusão** e como o Adobe Campaign as processa, consulte os [passos de implementação](../../start/using/privacy-requests.md#about-privacy-requests).

Os tutoriais sobre o Gerenciamento de privacidade no Campaign Standard também estão disponíveis [aqui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html?lang=pt-BR#privacy).

>[!NOTE]
>
>Para obter mais informações sobre dados pessoais e as diferentes entidades que gerenciam os dados (Controlador de dados, Operador de dados e Titular de dados), consulte [Dados pessoais e Personalidades](../../start/using/privacy.md#personal-data).

## Consentimento, retenção e funções {#consent-retention-roles}

Além dos recursos mais recentes de **Direito de acesso** e **Direito ao esquecimento**, o Adobe Campaign oferece outros recursos importantes, essenciais para a privacidade:

* [Gerenciamento do consentimento](#consent-management): funcionalidade de assinatura para gerenciamento de preferências
* [Retenção de dados](#data-retention): períodos de retenção de dados em todas as tabelas de log padrão; períodos de retenção adicionais podem ser configurados com workflows
* [Gerenciamento de direitos](#rights-management): acesso a dados gerenciados por direito nomeado     

### Gerenciamento de consentimento {#consent-management}

Consentimento significa a aprovação do Titular dos dados para o tratamento de dados pessoais relativos à pessoa em questão. A obtenção de qualquer consentimento necessário para esse processamento é de responsabilidade do Controlador de Dados. Embora o Adobe Campaign forneça alguns recursos para ajudar o cliente a gerenciar o consentimento relacionado ao serviço, o Adobe não é responsável pelo consentimento. Os clientes devem trabalhar com os próprios serviços jurídicos para determinar seus próprios processos e práticas para qualquer consentimento necessário.

Os recursos para ajudar a gerenciar alguns aspectos do consentimento são fundamentais para o Adobe Campaign desde o início. Por meio do nosso processo de gerenciamento de assinatura, os clientes podem acompanhar quais recipients participaram de quais tipos de assinatura, sejam boletins informativos, promoções diárias ou semanais ou qualquer outro tipo de programa de marketing.

![](assets/privacy-consent-management.png)

Para obter mais informações sobre o Gerenciamento de consentimento , consulte [Sobre assinaturas](../../audiences/using/about-subscriptions.md) e [Introdução a landing pages](../../channels/using/getting-started-with-landing-pages.md).

Além das ferramentas de Gerenciamento de consentimento oferecidas pelo Adobe Campaign, existe a possibilidade de monitorar se o cliente optou pela não participação na venda de Informações pessoais. Consulte [esta seção](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).

### Retenção de dados {#data-retention}

Quanto à retenção, as tabelas de log integradas no Campaign têm períodos de retenção predefinidos, geralmente limitando o armazenamento dos dados a seis meses ou menos.

A seguir estão os valores de retenção padrão para tabelas integradas. Esteja ciente de que a configuração de retenção é definida pelos administradores técnicos da Adobe durante a implementação e os valores podem variar com base nos requisitos do cliente.

* **Rastreamento consolidado**: 6 meses
* **Registros de entrega**: 6 meses
* **Registros de monitoramento**: 6 meses
* **Eventos**: 1 mês
* **Estatísticas de processamento de evento**: 6 meses
* **Eventos arquivados**: 6 meses
* **Entidades temporárias**: 7 dias
* **Eventos de pipeline ignorados**: 1 mês
* **Alertas de entrega**: 1 mês
* **Auditoria de exportação**: 6 meses

De modo semelhante à exclusão, a funcionalidade padrão do workflow possibilita configurar períodos de retenção para qualquer tabela personalizada.

Entre em contato com os consultores da Adobe ou administradores técnicos para saber mais sobre retenção ou se é necessário definir a retenção para tabelas personalizadas.

### Gerenciamento de direitos {#rights-management}

O Adobe Campaign oferece a capacidade de gerenciar os direitos atribuídos aos vários operadores do Campaign por meio de diferentes funções pré-concebidas ou personalizadas.

Um dos benefícios é permitir a gestão da decisão sobre quem poderá acessar os diferentes tipos de dados na empresa. Por exemplo, é possível ter diferentes profissionais de marketing que cubram diversas regiões e cada um deles só poderá acessar os dados da sua região geográfica.

Da mesma forma, essa funcionalidade também permite a configuração de diferentes recursos para cada usuário, como limitar quem pode enviar os deliveries, ou algo mais relevante para o Gerenciamento de privacidade, como quem pode alterar ou exportar dados.

![](assets/privacy-user-management.png)

Para obter mais informações sobre gerenciamento de acesso, consulte [esta seção](../../administration/using/about-access-management.md).
