---
solution: Campaign Standard
product: campaign
title: Sobre a capacidade de entrega no Adobe Campaign Standard
description: Saiba mais sobre os conceitos e as práticas recomendadas relacionadas à capacidade de entrega, bem como sobre as ferramentas oferecidas pelo Adobe Campaign Standard para otimizar o envio de seus deliveries.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 8%

---


# O que é a capacidade de entrega{#about-deliverability}

A capacidade de delivery permite medir o sucesso das campanhas em chegar à caixa de entrada dos recipients sem rejeição ou sem serem marcadas como spam. [Saiba por que a capacidade de entrega é importante](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html#why-deliverability-matters).

Mais precisamente, a capacidade de fornecimento de email refere-se ao conjunto de características que determinam a capacidade de uma mensagem de alcançar seu destino por meio de um endereço de email pessoal, dentro de um curto período e com a qualidade esperada em termos de conteúdo e formato. <!--These characteristics fall into four main categories: data quality, message and content, sending infrastructure, and reputation. Together, they form the foundation of a successful email deliverability program.-->

Para aprofundar o assunto e saber mais sobre os termos, conceitos e abordagens principais da capacidade de entrega, consulte o [Guia de práticas recomendadas de capacidade de entrega do Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html).

## Como melhorar a capacidade de entrega {#deliverability-key-points}

Os problemas de capacidade de entrega estão geralmente ligados às medidas de proteção contra spam implementadas pelos provedores de serviços de Internet e administradores de servidores de correio.

* Para obter recomendações gerais sobre como projetar campanhas de marketing por email bem-sucedidas, consulte [Estratégia e definição de capacidade de delivery](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html).

* Para obter recomendações mais específicas sobre como otimizar a capacidade de entrega dos emails do Adobe Campaign, recomendamos o uso das práticas recomendadas listadas nesta seção.

>[!NOTE]
>
>Como os ISPs são obrigados a desenvolver continuamente novas técnicas sofisticadas de filtragem para proteger seus clientes de remetentes de spam, a capacidade de fornecimento de email é caracterizada por critérios e regras em constante mudança. Certifique-se de consultar o [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html) que é atualizado regularmente.

### Taxa de entregabilidade

A taxa de deliverability é o número de mensagens que acessam as caixas de entrada dos recipients em comparação ao número de mensagens que foram entregues. Para melhorar o deliverability, você pode trabalhar para aumentar essa taxa.

Com o Adobe Campaign, a taxa de deliverability depende de vários fatores, especialmente:

* Configuração correta de suas instâncias: entre em contato com o representante do Adobe para obter assistência.
* Configuração de rede legítima: consulte [esta seção](../../sending/using/optimize-delivery.md#network-config) e [Configuração e estratégia do domínio](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#domain-setup-and-strategy).
* Sua reputação do endereço IP: consulte [Estratégia de IP](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#ip-strategy).
* Qualidade dos endereços direcionados: consulte [Gestão de Quarentena](../../sending/using/optimize-delivery.md#quarantine-management).
* Taxas de [reclamações](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html) e [rejeição permanente](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces) baixas.
* O conteúdo da mensagem: consulte [Controle de conteúdo de email](../../sending/using/control-email-content.md).
* Autenticação de mensagem (SPF, DKIM, DMARC): consulte [esta seção](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication).
* Reputação do remetente: para saber como os ISPs principais avaliam a reputação de um remetente, consulte [esta seção](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/internet-service-provider-specifics/overview.html).

## Ferramentas de capacidade de entrega da campanha {#deliverability-tools}

O Adobe Campaign fornece várias ferramentas para acompanhar e melhorar o desempenho de deliverability de sua plataforma. Esta página também destaca os principais princípios que você deve ter em mente para otimizar a capacidade de entrega ao usar o Campaign.

### Crie cuidadosamente a sua mensagem

Ao configurar, criar e testar sua mensagem, siga as práticas recomendadas mencionadas nas seções listadas abaixo. O aproveitamento de todos os recursos fornecidos pela Adobe Campaign ajudará você a melhorar a capacidade de entrega.

* [Práticas recomendadas para delivery](../../sending/using/delivery-best-practices.md)
* [Controle de conteúdo de e-mail](../../sending/using/control-email-content.md)
* [Visualização de mensagens](../../sending/using/previewing-messages.md)
* [Envio de provas](../../sending/using/sending-proofs.md)

### Verificar consentimento por meio da aceitação dupla {#double-opt-in}

Para evitar o envio de mensagens para endereços inválidos, limitar as comunicações inadequadas e melhorar a reputação do remetente, o Adobe recomenda a implementação de um mecanismo de aceitação dupla. Isso permite garantir que seus destinatários tenham assinado intencionalmente.

Para obter mais informações, consulte [Sobre participação e não participação no Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Para obter mais informações sobre as práticas recomendadas ao coletar dados de seus clientes, consulte o [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/first-impressions/address-collection-and-list-growth.html#data-quality-and-hygiene).

### Aproveite o gerenciamento de quarentena

O Adobe Campaign gerencia uma lista que reúne reclamações de spam, devoluções permanentes e devoluções temporárias que ocorrem de forma consistente.

Para proteger sua capacidade de delivery, os recipients cujos endereços estão nessa lista são excluídos por padrão de todos os deliveries futuros, porque o envio para esses contatos pode prejudicar sua reputação de envio.

Alguns provedores de acesso à Internet consideram automaticamente emails como spam se a taxa de endereços inválidos for muito alta. A quarentena, portanto, evita que você seja adicionado à lista de bloqueios por esses provedores.

Para obter mais informações, consulte as seguintes seções:

* [Noções básicas sobre falhas de delivery](../../sending/using/understanding-delivery-failures.md)
* [Noções básicas sobre gestão de quarentena](../../sending/using/understanding-quarantine-management.md)
* [Quarentena × lista de bloqueios](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

### Usar ferramentas de monitoramento e relatórios

Use os recursos oferecidos pelo Adobe Campaign para monitorar sua capacidade de entrega.

O Adobe Campaign permite verificar o desempenho dos deliveries por meio de um conjunto de indicadores integrados em tempo real. <!--For example, you can check the number of messages that are successfully executed, sent and delivered. You can also verify the number of messages that have been opened and the number of messages/links that have been clicked.-->Você também pode criar relatórios totalmente personalizáveis e em tempo real para obter insights aprimorados sobre seus deliveries.

Para obter mais informações, consulte as seguintes seções:

* [Monitoramento da capacidade de entrega](../../sending/using/monitor-deliverability.md)

   <!--[Monitoring a delivery](../../sending/using/monitoring-a-delivery.md)-->
* [Receber alertas quando ocorrerem falhas](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Relatórios dinâmicos](../../reporting/using/about-dynamic-reports.md)

<!--## General recommendations

NOT SURE TO KEEP

Here are a few additional recommendations when it comes to deliverability.

### Send to valid addresses {#valid-addresses}

Spammers often use address generators based on lists of frequent names and first names; in addition, they rarely process technical notifications sent back by mail servers. A high rate of invalid addresses is often interpreted as a sign of spam.

Double opt-in mechanisms and effective handling of technical bounce messages make it possible to avoid this.

### Reduce complaint rate {#reduce-complaint-rate}

ISPs usually have a prominent means of reporting a received message as spam. This makes it possible to identify unreliable sources. By rapidly honoring opt-out requests, making regular use of a given list, verifying consent through a double opt-in system, and implementing feedback loops, you can reduce complaint rates.

<!--Sending to honeypot addresses {#honeypot-addresses}
ISPs and other organizations (refer to https://www.projecthoneypot.org/) make use of mailboxes that do not correspond to physical persons but are created simply to trick spammers. These so-called "honey pot" addresses are published on the Web in order to be collected by spambots and thus catch illegitimate senders. The use of a double opt-in mechanism precludes this sort of address being added to a list. When using a third-party list, you must be sure of the methods employed by its maintainer.-->

<!--## Sending on a regular basis {#regular-deliveries}

Spammers make programmed deliveries to maintain their reputation over time. They sometimes need to adapt their marketing plan to meet the best practices imposed by the ISPs and so, after a peak in reputation (ramp-up), they configure regular deliveries.-->
