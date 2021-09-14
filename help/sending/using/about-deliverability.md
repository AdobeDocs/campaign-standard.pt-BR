---
title: Sobre a capacidade de entrega no Adobe Campaign Standard
description: Saiba mais sobre os conceitos e as práticas recomendadas relacionadas à capacidade de entrega, bem como sobre as ferramentas oferecidas pelo Adobe Campaign Standard para otimizar o envio de seus deliveries.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 5e523519-7192-4031-9d96-559af23074d9
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 75%

---

# O que é capacidade de entrega{#about-deliverability}

A capacidade de delivery permite medir o sucesso das campanhas em chegar à caixa de entrada dos recipients sem rejeição ou sem serem marcadas como spam. [Saiba por que a capacidade de delivery é importante](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html?lang=pt-BR#why-deliverability-matters).

Mais precisamente, a capacidade de delivery refere-se ao conjunto de características que determinam o potencial de uma mensagem de alcançar seu destino por meio de um endereço de email pessoal, dentro de um curto período e com a qualidade esperada em termos de conteúdo e formato. <!--These characteristics fall into four main categories: data quality, message and content, sending infrastructure, and reputation. Together, they form the foundation of a successful email deliverability program.-->

Para aprofundar o assunto e saber mais sobre os termos, conceitos e abordagens principais da capacidade de delivery, consulte o [Manual de práticas recomendadas de capacidade de delivery da Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=pt-BR).

## Como melhorar a capacidade de entrega {#deliverability-key-points}

Os problemas de capacidade de delivery estão geralmente ligados às medidas de proteção contra spam implementadas pelos provedores de serviços de Internet e administradores de servidores de correio.

* Para obter recomendações gerais sobre como projetar campanhas de marketing por email bem-sucedidas, consulte [Estratégia e definição de capacidade de delivery](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html?lang=pt-BR).

* Para obter recomendações mais específicas sobre como otimizar a capacidade de entrega dos emails do Adobe Campaign, recomendamos o uso das práticas recomendadas listadas nesta seção.

>[!NOTE]
>
>Como os ISPs são obrigados a desenvolver continuamente novas técnicas sofisticadas de filtragem para proteger seus clientes contra remetentes de spam, a capacidade de delivery de email é caracterizada por critérios e regras em constante mudança. Consulte o [Manual de práticas recomendadas de capacidade de delivery da Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html), que é atualizado regularmente.

### Taxa da capacidade de delivery

A taxa da capacidade de delivery é o número de mensagens que chegam nas caixas de entrada dos recipients em comparação ao número de mensagens que foram entregues. Para melhorar a capacidade de delivery, você pode trabalhar para aumentar essa taxa.

Com o Adobe Campaign, a taxa da capacidade de delivery depende de vários fatores, principalmente:

* Configuração correta das instâncias: entre em contato com o representante da Adobe para obter assistência.
* Configuração de rede legítima: consulte [esta seção](../../sending/using/optimize-delivery.md#network-config) e [Configuração e estratégia do domínio](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=pt-BR#domain-setup-and-strategy).
* Reputação do endereço IP: consulte [Estratégia de IP](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=pt-BR#ip-strategy).
* Qualidade dos endereços direcionados: consulte [Gerenciamento de quarentena](../../sending/using/optimize-delivery.md#quarantine-management).
* Baixas taxas de [reclamação](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html?lang=pt-BR) e [rejeição permanente](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html?lang=pt-BR#hard-bounces).
* O conteúdo da mensagem: consulte [Controle de conteúdo de email](../../sending/using/control-email-content.md).
* Autenticação de mensagem (SPF, DKIM, DMARC): consulte [esta seção](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=pt-BR#authentication).
* Reputação do remetente: para saber como os principais ISPs avaliam a reputação de um remetente, consulte [esta seção](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/internet-service-provider-specifics/overview.html?lang=pt-BR).

## Ferramentas de capacidade de entrega do Campaign {#deliverability-tools}

O Adobe Campaign fornece várias ferramentas para acompanhar e melhorar o desempenho de deliverability de sua plataforma. Esta página também destaca os princípios mais importantes que você deve ter em mente para otimizar a capacidade de delivery ao usar o Campaign.

### Crie cuidadosamente a sua mensagem

Ao configurar, criar e testar sua mensagem, siga as práticas recomendadas mencionadas nas seções listadas abaixo. O aproveitamento de todos os recursos fornecidos pela Adobe Campaign ajudará você a melhorar a capacidade de entrega.

* [Práticas recomendadas de entrega](../../sending/using/delivery-best-practices.md)
* [Controle de conteúdo de email](../../sending/using/control-email-content.md)
* [Visualização de mensagens](../../sending/using/previewing-messages.md)
* [Envio de provas](../../sending/using/sending-proofs.md)

### Verificar consentimento por meio da aceitação dupla {#double-opt-in}

Para evitar o envio de mensagens a endereços inválidos, limitar as comunicações inadequadas e melhorar a reputação do remetente, a Adobe recomenda a implementação de um mecanismo de aceitação dupla. Isso permite garantir que seus destinatários tenham assinado intencionalmente.

Para obter mais informações, consulte [Sobre participação e não participação no Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Para obter mais informações sobre as práticas recomendadas ao coletar dados de clientes, consulte o [Manual de práticas recomendadas de capacidade de delivery da Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/first-impressions/address-collection-and-list-growth.html?lang=pt-BR#data-quality-and-hygiene).

### Aproveitar o gerenciamento de quarentena

O Adobe Campaign gerencia uma lista que reúne reclamações de spam, rejeições permanentes e rejeições temporárias que ocorrem de forma consistente.

Para proteger sua capacidade de delivery, os recipients cujos endereços estão nessa lista são excluídos por padrão de todos os deliveries futuros, porque o envio para esses contatos pode prejudicar sua reputação de envio.

Alguns provedores de acesso à Internet consideram automaticamente emails como spam se a taxa de endereços inválidos é muito alta. A quarentena, portanto, evita que você seja adicionado à lista de bloqueios por esses provedores.

Para obter mais informações, consulte estas seções:

* [Compreensão de falhas de entrega](../../sending/using/understanding-delivery-failures.md)
* [Compreensão do gerenciamento de quarentena](../../sending/using/understanding-quarantine-management.md)
* [Quarentena × lista de bloqueios](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

### Usar ferramentas de monitoramento e relatórios

Use os recursos oferecidos pelo Adobe Campaign para monitorar a capacidade de delivery da sua plataforma.

O Adobe Campaign permite verificar o desempenho dos deliveries por meio de um conjunto de indicadores integrados em tempo real. <!--For example, you can check the number of messages that are successfully executed, sent and delivered. You can also verify the number of messages that have been opened and the number of messages/links that have been clicked.-->Você também pode criar relatórios totalmente personalizáveis e em tempo real para obter insights aprimorados sobre seus deliveries.

Para obter mais informações, consulte estas seções:

* [Monitoramento da capacidade de entrega](../../sending/using/monitor-deliverability.md)

   <!--[Monitoring a delivery](../../sending/using/monitoring-a-delivery.md)-->
* [Recebimento de alertas quando ocorrerem falhas](../../sending/using/receiving-alerts-when-failures-happen.md)
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
