---
title: Privacidade e consentimento no Adobe Campaign Standard
description: Esta seção fornece uma visão geral da privacidade, dados pessoais e gerenciamento de consentimento no Adobe Campaign Standard, bem como das ferramentas disponíveis para lidar com esses problemas.
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: faddcc870adcf9e71e50004a69a219b16ddc044f

---


# Privacy and Consent{#privacy-and-consent}

## Recomendações gerais {#general-recommendations}

O Adobe Campaign é uma ferramenta poderosa para coletar e processar quantidades extremamente grandes de dados, incluindo informações pessoais e dados confidenciais. É por isso que a privacidade precisa de ser gerida com cuidado.

* Fazer sempre uso responsável e ético de informações pessoais.

* Evite enviar emails não solicitados, notificações por push e mensagens SMS (&quot;spam&quot;). A Adobe acredita firmemente nos princípios da permissões de marketing na promoção do valor e da fidelidade da vida útil do cliente e, portanto, proíbe estritamente o uso do Adobe Campaign no envio de mensagens não solicitadas.

### Regras de privacidade {#privacy-regulations}

Para gerenciar corretamente a privacidade e os dados pessoais, trabalhe dentro das legislações aplicáveis às regiões onde você opera. Estes regulamentos incluem:
* [RGPD](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en) (Regulamento geral europeu de proteção de dados)
* [APD](https://www.gov.uk/data-protection) (aplicação do RPD pelo Reino Unido)
* [Diretiva europeia relativa à privacidade e às comunicações eletrônicas](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM Act](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business) (lei norte-americana que define as regras e os requisitos para o email comercial)
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=) (California Consumer Privacy Act)
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/) (Lei de Proteção de Dados Pessoais da Tailândia)

>[!NOTE]
>
>Para obter mais informações sobre como o RGPD, CCPA e PDPA se aplicam ao Adobe Campaign, consulte [esta página](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#whatisgdpr).

### Adobe Experience Cloud privacy {#experience-cloud-privacy}

O Adobe Campaign faz parte das soluções da Adobe Experience Cloud. A maneira como a privacidade é tratada na Campanha obedece aos princípios gerais da Adobe Experience Cloud, como os seguintes:

* **Quais informações são coletadas ao usar a Adobe Experience Cloud**

   Como empresa usando as soluções da Adobe Experience Cloud, você escolhe quais informações coletar e enviar para sua conta da Adobe Experience Cloud. Exemplos dos tipos de informações que podem ser coletadas incluem atividade de navegação na Web, endereços IP, informações de localização de dispositivos móveis, taxas de sucesso de campanha, itens comprados ou colocados no carrinho de compras etc.

   >[!NOTE]
   >
   >Quanto a todos os produtos da Adobe, a Campanha coleta informações sobre os usuários do aplicativo e do site. Para obter mais informações, consulte a Política [de privacidade da](https://www.adobe.com/privacy/policy.html)Adobe.

* **Como a Adobe Experience Cloud é usada para coletar informações**

   * As soluções da Adobe Experience Cloud usam cookies e tecnologias semelhantes, como Web beacons (também conhecidos como tags ou pixels), para permitir que você colete informações. Para obter mais informações sobre cookies e recursos de rastreamento com o Adobe Campaign, consulte [esta seção](#tracking-capabilities).
   * Você também pode usar as tecnologias da Adobe Experience Cloud em seus aplicativos móveis. Para obter mais informações sobre como enviar delivery para dispositivos móveis com Campanha, consulte [esta página](https://helpx.adobe.com/br/campaign/kb/acs-mobile.html).

* **As opções de privacidade dos usuários sobre o uso da Adobe Experience Cloud**

   A Adobe solicita que você forneça aos seus clientes políticas de privacidade descrevendo:

   * Suas práticas de privacidade em conexão com a Adobe Experience Cloud
   * Como os usuários podem definir suas preferências para a coleção ou usar suas informações em conexão com a Adobe Experience Cloud
   >[!NOTE]
   >
   >Quanto a todos os produtos da Adobe, os usuários da Campanha podem optar por não compartilhar informações coletadas sobre eles por meio de aplicativos e sites. Para obter mais informações, consulte as Perguntas frequentes [sobre o uso da](https://www.adobe.com/privacy/experience-cloud-usage-info-faq.html)Adobe Experience Cloud.

Para obter mais detalhes sobre a privacidade da Adobe Experience Cloud, consulte [esta página](https://www.adobe.com/br/privacy/marketing-cloud.html).

## Dados pessoais e pessoas {#personal-data}

Ao gerenciar a privacidade, é importante definir quais dados devem ser tratados com cuidado e por quem.
* **Dados** pessoais são informações que podem identificar direta ou indiretamente um indivíduo vivo.
* **Dados** Pessoais Sensíveis são informações relacionadas com a raça, visualizações políticas, crenças religiosas, antecedentes criminais, informações genéticas, dados de saúde, preferência sexual, informações biométricas, bem como membros de uniões comerciais.

As [principais legislações](#privacy-regulations) referem-se às diferentes entidades que gerem os dados da seguinte forma:
* Um controlador **de** dados é a autoridade que determina os meios e a finalidade de coletar, usar e compartilhar dados pessoais.
* Um Processador **de** dados é qualquer indivíduo ou parte que coleta, usa ou compartilha dados pessoais, conforme determinado pelo Controlador de dados.
* Uma pessoa **com** dados é qualquer pessoa viva cujos dados pessoais estão a ser recolhidos, utilizados ou partilhados e que pode ser identificada, direta ou indiretamente, por referência a esses dados pessoais.

Portanto, como uma empresa que coleta e compartilha dados pessoais, você é o Controlador de dados, seus clientes são os Indivíduos de dados e o Adobe Campaign atua como um Processador de dados ao manipular seus dados pessoais, conforme indicado por você. Observe que é sua responsabilidade, como um Controlador de dados, lidar com a relação com os Indivíduos de dados, como ao gerenciar solicitações [de](#privacy-requests)privacidade.

Ao integrar a Campanha com outras soluções da Experience Cloud, onde as audiências podem ser transferidas de um sistema para outro, como o serviço [de Destinos da](../../audiences/using/aep-about-audience-destinations-service.md)Audiência, o [Adobe Analytics](../../integrating/using/about-campaign-analytics-integration.md), o [Audiência Manager ou o serviço](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)principal de Pessoas, ou com outras soluções, como o [Microsoft Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md), é necessário prestar mais atenção à proteção de dados pessoais.

## Aquisição de dados {#data-acquisition}

O Adobe Campaign permite que você colete dados, incluindo informações pessoais e confidenciais. Portanto, é essencial que você receba e monitore o consentimento de seus recipient.

* Sempre tenha recipient que concordem em receber comunicações. Para fazer isso, continue a atender às solicitações de não participação o mais rápido possível e verifique o consentimento por meio de um processo de não participação do duplo. Para obter mais informações, consulte [Gerenciamento de aceitação e recusa na Campanha](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md) e [Configuração de um processo](../../channels/using/setting-up-a-double-opt-in-process.md)de aceitação de duplo.
* Não importe listas fraudulentas e use armadilhas para verificar se o arquivo cliente não está sendo usado de forma fraudulenta. Para obter mais informações, consulte [Uso de armadilhas](../../sending/using/using-traps.md).
* Por meio do gerenciamento de consentimento e direitos, você pode rastrear as preferências dos recipient, bem como gerenciar quem em sua organização pode acessar quais dados. Para obter mais informações, consulte [esta seção](#consent).
* Facilite e gerencie solicitações de privacidade de seus recipient. Para obter mais informações, consulte [esta seção](#privacy-requests).

## Gerenciamento de privacidade {#privacy-management}

O gerenciamento de privacidade está relacionado a todos os processos e ferramentas que podem ajudá-lo a cumprir as regras de privacidade (RGPD, CCPA etc.). Obtenha uma visão geral do que é o gerenciamento de privacidade [nesta página](https://helpx.adobe.com/br/campaign/kb/campaign-privacy-overview.html).

O Adobe Campaign oferece vários conjuntos de recursos dedicados ao gerenciamento de privacidade:
* Gerenciamento de consentimento, retenção de dados e funções de usuário. Consulte [esta seção](#consent).
* Solicitações de privacidade (direito de acesso e direito de ser esquecido). Consulte [esta seção](#privacy-requests).
* Recusar a venda de informações pessoais (específicas para CCPA). Consulte [esta seção](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa).

Os principais recursos de privacidade na Campanha e um exemplo das pessoas envolvidas são apresentados na [seção](https://helpx.adobe.com/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow).


### Consentimento, retenção e funções {#consent}

Originalmente, o Adobe Campaign oferta  apresenta recursos importantes que são essenciais para a privacidade:

* **Gerenciamento** de consentimento: Por meio do processo de gerenciamento de subscrições, você pode gerenciar suas preferências de recipient e rastrear quais recipient aceitaram em qual tipo de subscrição. Para obter mais informações, consulte [Subscrição](../../audiences/using/about-subscriptions.md) e [Landing page](../../channels/using/getting-started-with-landing-pages.md).
* **Retenção** de dados: Todas as tabelas de log padrão incorporadas têm períodos de retenção predefinidos, geralmente limitando seu armazenamento de dados a 6 meses ou menos. Períodos de retenção adicionais podem ser configurados com workflows. Para obter mais informações, entre em contato com os consultores ou administradores técnicos da Adobe.
* **Gerenciamento** de direitos: O Adobe Campaign fornece a capacidade de gerenciar os direitos atribuídos aos vários operadores de Campanha por meio de diferentes funções pré-criadas ou personalizadas. Isso permite gerenciar quem em sua empresa pode acessar, modificar ou exportar diferentes tipos de dados. For more on this, see [About access management](../../administration/using/about-access-management.md).

Para obter mais informações sobre esses recursos e como gerenciá-los no Adobe Campaign, consulte [esta página](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#consent).

### Privacy requests {#privacy-requests}

O Adobe Campaign fornece recursos adicionais para ajudá-lo a facilitar sua prontidão como um Controlador de dados para determinadas solicitações de Privacidade:

* O **direito de acesso** é o direito da pessoa a obter do responsável pelo tratamento de dados a confirmação de que os dados pessoais que lhes dizem respeito estão ou não a ser tratados, onde e porquê.

* O **direito de ser esquecido** (solicitação de exclusão) autoriza a pessoa a apagar seus dados pessoais pelo controlador.

>[!NOTE]
>
>Este conjunto de ferramentas está aqui para ajudá-lo com sua conformidade com a privacidade para RGPD, CCPA e PDPA. Para obter mais informações sobre esses diferentes regulamentos, consulte [esta página](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#whatisgdpr).

<!--* **GDPR** (General Data Protection Regulation) is the European Union’s (EU) privacy law that harmonizes and modernizes data protection requirements. GDPR applies to Adobe Campaign customers who hold data for Data Subjects residing in the EU.

* **CCPA** (California Consumer Privacy Act) provides California residents new rights in regards to their personal information and imposes data protection responsibilities on certain entities whom conduct business in California.

* **Thailand's PDPA** (Personal Data Protection Act) is the new privacy law that harmonizes and modernizes data protection requirements for Thailand. This regulation applies to Adobe Campaign customers who hold data for Data Subjects residing in this country.-->

As solicitações **de Acesso** e **Excluir** são apresentadas [nesta página](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess). As etapas de implementação para criar essas solicitações estão detalhadas [nesta página](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests). Os tutoriais também estão disponíveis [aqui](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/privacy/privacy-overview.html).

## Recursos de rastreamento {#tracking-capabilities}

Graças às suas funcionalidades de rastreamento, o Adobe Campaign permite que você rastreie o comportamento dos recipient do delivery usando cookies de sessão e cookies permanentes. Para obter mais informações sobre o rastreamento, consulte [esta página](../../sending/using/tracking-messages.md).

>[!NOTE]
>
>Regulamentos como o Regulamento geral de proteção de dados (RGPD) afirmam que as empresas exigem o acordo dos usuários do site antes de instalar qualquer cookie. Você deve informar aos usuários que seus sites estão equipados com ferramentas de rastreamento da Web por meio de uma solicitação de autorização.

Você também pode adicionar links [](../../designing/using/links.md#about-tracked-urls) rastreados em suas mensagens para medir o impacto do comportamento do delivery e do recipient no relatório integrado dos indicadores [de](../../reporting/using/tracking-indicators.md) rastreamento ou criar seus próprios relatórios [](../../reporting/using/about-dynamic-reports.md)dedicados.
