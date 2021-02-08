---
title: Privacidade e consentimento no Adobe Campaign Standard
description: Esta seção fornece uma visão geral da privacidade, dos dados pessoais e do gerenciamento de consentimento no Adobe Campaign Standard, bem como das ferramentas disponíveis para lidar com eles.
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
translation-type: ht
source-git-commit: 2879066634a8a123ef5d07d46aa96479f156a923
workflow-type: ht
source-wordcount: '1479'
ht-degree: 100%

---


# Privacidade e consentimento{#privacy-and-consent}

## Recomendações gerais {#general-recommendations}

O Adobe Campaign é uma ferramenta poderosa para coletar e processar quantidades extremamente grandes de dados, incluindo informações pessoais e dados confidenciais. É por isso que a privacidade precisa de ser gerenciada com cuidado.

* Utilize sempre as informações pessoais de modo responsável e ético.

* Evite enviar emails não solicitados, notificações por push e mensagens SMS (&quot;spam&quot;). A Adobe acredita fortemente nos princípios da permissão de marketing para promover o valor e a fidelidade do cliente e, portanto, é estritamente proibido o uso do Adobe Campaign para o envio de mensagens não solicitadas.

### Regras de privacidade {#privacy-regulations}

Para gerenciar corretamente a privacidade e os dados pessoais, trabalhe dentro das legislações aplicáveis às regiões onde você opera. Estas regras incluem:
* [GDPR](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en) (Regulamento geral europeu de proteção de dados)
* [APD](https://www.gov.uk/data-protection) (Aplicação do GDPR pelo Reino Unido)
* [Diretiva europeia relativa à privacidade e às comunicações eletrônicas](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM Act](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business) (Lei norte-americana que define as regras e os requisitos para o email comercial)
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=) (Ato de Privacidade do Consumidor da Califórnia)
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/) (Lei de Proteção de Dados Pessoais da Tailândia)

>[!NOTE]
>
>Para obter mais informações sobre como o GDPR, o CCPA e o PDPA se aplicam ao Adobe Campaign, consulte [esta página](https://helpx.adobe.com/br/campaign/kb/campaign-privacy-overview.html#whatisgdpr).

### Privacidade da Adobe Experience Cloud {#experience-cloud-privacy}

O Adobe Campaign faz parte das soluções da Adobe Experience Cloud. A maneira como a privacidade é tratada no Campaign obedece aos princípios gerais da Adobe Experience Cloud, como os seguintes:

* **Quais informações são coletadas ao usar a Adobe Experience Cloud**

   Como empresa usando as soluções da Adobe Experience Cloud, você escolhe quais informações coletar e enviar para sua conta da Adobe Experience Cloud. Exemplos dos tipos de informações que podem ser coletadas incluem atividade de navegação na web, endereços IP, informações de localização de dispositivos móveis, taxas de sucesso de campanha, itens comprados ou colocados no carrinho de compras, etc.

   >[!NOTE]
   >
   >Quanto a todos os produtos da Adobe, o Campaign coleta informações sobre os usuários do aplicativo e do site. Para obter mais informações, consulte a [Política de privacidade da Adobe](https://www.adobe.com/privacy/policy.html).

* **Como a Adobe Experience Cloud é usada para coletar informações**

   * As soluções da Adobe Experience Cloud usam cookies e tecnologias semelhantes, como web beacons (também conhecidos como tags ou pixels), para permitir que você colete informações. Para obter mais informações sobre cookies e recursos de rastreamento com o Adobe Campaign, consulte [esta seção](#tracking-capabilities).
   * Você também pode usar as tecnologias da Adobe Experience Cloud em seus aplicativos móveis. Para obter mais informações sobre como enviar deliveries para dispositivos móveis com o Campaign, consulte [esta página](https://helpx.adobe.com/campaign/kb/acs-mobile.html).

* **As opções de privacidade dos usuários sobre o uso da Adobe Experience Cloud**

   A Adobe solicita que você forneça aos seus clientes políticas de privacidade descrevendo:

   * Suas práticas de privacidade em conexão com a Adobe Experience Cloud
   * Como os usuários podem definir suas preferências para a coleção ou usar suas informações em conexão com a Adobe Experience Cloud

   >[!NOTE]
   >
   >Quanto a todos os produtos da Adobe, os usuários do Campaign podem recusar o compartilhamento das informações coletadas sobre eles por meio de aplicativos e sites. Para obter mais informações, consulte as [Perguntas frequentes sobre o uso de informações com a Adobe Experience Cloud](https://www.adobe.com/privacy/experience-cloud-usage-info-faq.html).

Para obter mais detalhes sobre a privacidade da Adobe Experience Cloud, consulte [esta página](https://www.adobe.com/br/privacy/marketing-cloud.html).

## Dados pessoais e Personalidades {#personal-data}

Ao gerenciar a privacidade, é importante definir quais dados devem ser tratados com cuidado e por quem.
* **Dados pessoais** são informações que podem identificar direta ou indiretamente um indivíduo vivo.
* **Dados confidenciais pessoais** são informações relacionadas a raça, visão política, crenças religiosas, antecedentes criminais, informações genéticas, dados de saúde, preferência sexual, informações biométricas, bem como participação em uniões comerciais.

As [principais legislações](#privacy-regulations) referem-se às diferentes entidades que gerem os dados da seguinte forma:
* Um **Controlador de dados** é a autoridade que determina os meios e a finalidade de coleta, utilização e compartilhamento de dados pessoais.
* Um **Processador de dados** é qualquer pessoa física ou parte que coleta, utiliza ou compartilha dados pessoais, conforme determinado pelo Controlador de dados.
* Um **Titular de dados** é qualquer pessoa viva cujos dados pessoais estejam sendo coletados, utilizados ou compartilhados, e que possa ser identificada, direta ou indiretamente, por referência a esses dados pessoais.

Portanto, como uma empresa que coleta e compartilha dados pessoais, você é o Controlador de dados, seus clientes são os Titulares dos dados e o Adobe Campaign atua como um Processador de dados ao tratar os dados pessoais indicados por você. Observe que é sua responsabilidade como Controlador de dados, tratar a relação com os Titulares dos dados, como ao gerenciar [solicitações de privacidade](#privacy-requests).

Ao integrar o Campaign a outras soluções da Experience Cloud, onde os públicos-alvo podem ser transferidos de um sistema para outro, como o serviço do [Audience Destinations](../../audiences/using/aep-about-audience-destinations-service.md), [Adobe Analytics](../../integrating/using/about-campaign-analytics-integration.md), [Audience Manager ou o serviço principal People](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md), ou outras soluções como o [Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md), é necessário ter cuidado extra com a proteção de dados pessoais.

## Aquisição de dados {#data-acquisition}

O Adobe Campaign permite coletar dados, inclusive informações pessoais e confidenciais. Portanto, é essencial que você receba e monitore o consentimento de seus recipients.

* Tenha sempre o consentimento do recipient para o recebimento de comunicações. Para fazer isso, continue atendendo às solicitações de recusa o mais rápido possível e verifique o consentimento por meio de um duplo processo de aceitação. Para obter mais informações, consulte [Gerenciamento de aceitação e recusa no Campaign](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md) e [Configuração de um processo duplo de aceitação](../../channels/using/setting-up-a-double-opt-in-process.md).
* Não importe listas fraudulentas e use armadilhas para verificar se o arquivo do seu cliente não está sendo usado de forma fraudulenta. Para obter mais informações, consulte [Uso de armadilhas](../../sending/using/using-traps.md).
* Por meio do gerenciamento de consentimento e direitos, você pode rastrear as preferências dos recipients, bem como gerenciar quem em sua organização pode acessar quais dados. Para obter mais informações, consulte [esta seção](#consent).
* Facilite e gerencie solicitações de privacidade de seus recipients. Para obter mais informações, consulte [esta seção](#privacy-requests).

## Gerenciamento de privacidade {#privacy-management}

O gerenciamento de privacidade está relacionado a todos os processos e ferramentas que podem ajudar você a cumprir as regras de privacidade (RGPD, CCPA, etc.). Obtenha uma visão geral do que é o gerenciamento de privacidade [nesta página](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html).

O Adobe Campaign oferece vários conjuntos de recursos dedicados ao gerenciamento de privacidade:
* Gerenciamento de consentimento, retenção de dados e funções de usuário. Consulte [esta seção](#consent).
* Solicitações de privacidade (Direito de acesso e Direito de ser esquecido). Consulte [esta seção](#privacy-requests).
* Recusar a venda de informações pessoais (específico para CCPA). Consulte [esta seção](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa).

Os principais recursos de privacidade do Campaign e um exemplo das personalidades envolvidas são apresentados nesta [seção](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-faq.html?lang=pt-BR#getting-started).


### Consentimento, retenção e funções {#consent}

Originalmente, o Adobe Campaign oferece recursos importantes que são essenciais à privacidade:

* **Gerenciamento de consentimento**: por meio do processo de gerenciamento de assinaturas, você pode gerenciar suas preferências de recipient e rastrear quais recipients aceitaram e que tipo de assinatura. Para obter mais informações, consulte [Assinaturas](../../audiences/using/about-subscriptions.md) e [Landing pages](../../channels/using/getting-started-with-landing-pages.md).
* **Retenção de dados**: todas as tabelas de registro padrão incorporadas têm períodos de retenção predefinidos, geralmente limitando seu armazenamento de dados a 6 meses ou menos. Períodos de retenção adicionais podem ser configurados com workflows. Para obter mais informações, entre em contato com os consultores ou administradores técnicos da Adobe.
* **Gerenciamento de direitos**: o Adobe Campaign oferece a capacidade de gerenciar os direitos atribuídos aos vários operadores do Campaign por meio de diferentes funções pré-concebidas ou personalizadas. Isso permite gerenciar quem em sua empresa pode acessar, modificar ou exportar diferentes tipos de dados. Para obter mais informações, consulte [Sobre o gerenciamento de acesso](../../administration/using/about-access-management.md).

Para obter mais informações sobre esses recursos e como gerenciá-los no Adobe Campaign, consulte [esta página](https://helpx.adobe.com/br/campaign/kb/campaign-privacy-overview.html#consent).

### Solicitações de privacidade {#privacy-requests}

O Adobe Campaign fornece recursos adicionais para ajudar você se tornar um Controlador de dados para determinadas Solicitações de privacidade:

* O **Direito de acesso** é o Direito do titular de dados de obter a confirmação do Controlador de dados, caso os dados relativos a ele estejam sendo processados, onde e com que finalidade.

* O **Direito de ser esquecido** (solicitação de exclusão) autoriza o Titular dos dados a ter seus dados pessoais cancelados pelo Controlador de dados.

>[!NOTE]
>
>Este conjunto de ferramentas ajuda com a conformidade de privacidade para o GDPR, CCPA e PDPA. Para obter mais informações sobre esses diferentes regulamentos, consulte [esta página](https://helpx.adobe.com/br/campaign/kb/campaign-privacy-overview.html#whatisgdpr).

<!--* **GDPR** (General Data Protection Regulation) is the European Union’s (EU) privacy law that harmonizes and modernizes data protection requirements. GDPR applies to Adobe Campaign customers who hold data for Data Subjects residing in the EU.

* **CCPA** (California Consumer Privacy Act) provides California residents new rights in regards to their personal information and imposes data protection responsibilities on certain entities whom conduct business in California.

* **Thailand's PDPA** (Personal Data Protection Act) is the new privacy law that harmonizes and modernizes data protection requirements for Thailand. This regulation applies to Adobe Campaign customers who hold data for Data Subjects residing in this country.-->

As solicitações de **Acesso** e **Exclusão** são apresentadas [nesta página](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=pt-BR#getting-started). As etapas de implementação para criar essas solicitações estão detalhadas [nesta página](https://helpx.adobe.com/br/campaign/kb/acs-privacy.html#ManagingPrivacyRequests). Os tutoriais também estão disponíveis [aqui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html?lang=pt-BR#privacy).

## Recursos de rastreamento {#tracking-capabilities}

Graças às suas funcionalidades de rastreamento, o Adobe Campaign permite rastrear a comportamento dos seus recipients de delivery utilizando cookies de seção e cookies permanentes. Para obter mais informações sobre rastreamento, consulte [esta página](../../sending/using/tracking-messages.md).

>[!NOTE]
>
>Regulamentos como o Regulamento Geral sobre a Proteção de Dados (GDPR) afirmam que as empresas exigem o consentimento dos usuários do site antes da instalação de qualquer cookie. Você deve informar aos usuários que seus sites estão equipados com ferramentas de rastreamento da web por meio de uma solicitação de autorização.

Você também pode adicionar [links rastreados](../../designing/using/links.md#about-tracked-urls) em suas mensagens para medir o impacto do comportamento do delivery e do recipient no relatório integrado dos [indicadores de rastreamento](../../reporting/using/tracking-indicators.md) ou criar seus próprios [relatórios exclusivos](../../reporting/using/about-dynamic-reports.md).
