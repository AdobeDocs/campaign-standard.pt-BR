---
title: Sobre a capacidade de entrega no Adobe Campaign Standard
description: Saiba mais sobre os conceitos e as práticas recomendadas relacionadas à entrega, bem como sobre as ferramentas oferecidas pelo Adobe Campaign Standard para otimizar o envio de entregas.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44049443f8028ed26089ee0d49944ebac6a62111

---


# Sobre a entrega{#about-deliverability}

Disponibilidade ou como medir o sucesso de suas campanhas atingindo a caixa de entrada dos destinatários sem saltar ou sendo marcado como spam.

O Adobe Campaign Deliverability é um serviço pago disponível em diferentes ofertas. Entre em contato com o material de entrega ou o serviço comercial.

A taxa de entrega depende de vários fatores, especialmente:

* Configuração correta das instâncias
* Sua reputação de endereço IP
* Qualidade dos endereços visados
* Baixas reclamações e taxas de rejeição
* Seu conteúdo de mensagem
* Autenticação de mensagem (SPF, DKIM, DMARC)
* reputação do remetente

## Pontos principais a serem verificados {#deliverability-key-points}

Para otimizar a entrega de emails do Adobe Campaign, recomendamos o uso das práticas recomendadas listadas abaixo. Os problemas de capacidade de entrega estão geralmente ligados às medidas de proteção contra spam implementadas pelos provedores de serviços de Internet e administradores de servidores de correio.

O recurso de entrega por email refere-se ao conjunto de características que determinam a capacidade de uma mensagem de chegar ao seu destino, por meio de um endereço de email pessoal, em pouco tempo e com a qualidade esperada em termos de conteúdo e formato. Estas características dividem-se em quatro categorias principais: qualidade, mensagem e conteúdo dos dados, infraestrutura de envio e reputação. Juntos, eles formam a base de um programa bem-sucedido de entrega de emails.

A taxa de entrega é o número de emails enviados que foram entregues com êxito aos destinatários.
Esta é uma lista dos pontos principais a serem verificados para garantir uma boa entrega.

## Ferramentas de entrega {#deliverability-tools}

Primeiro, comece consultando a documentação sobre as ferramentas de entrega fornecidas com o Campaign Standard:
* [Práticas recomendadas de entrega](https://helpx.adobe.com/campaign/kb/delivery-best-practices.html)
* [Personalização do nome do remetente](../../designing/using/personalization.md#personalizing-the-sender)
* [Teste da linha de assunto de um email](../../sending/using/testing-subject-line-email.md)
* [Otimização do tempo de envio](../../sending/using/optimizing-the-sending-time.md)
* [Visualizar mensagens](../../sending/using/previewing-messages.md)
* [Renderização de email](../../sending/using/email-rendering.md)
* [Monitoramento de uma entrega](../../sending/using/monitoring-a-delivery.md)
* [Receber alertas quando ocorrerem falhas](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Noções básicas sobre falhas de entrega](../../sending/using/understanding-delivery-failures.md)
* [Noções básicas sobre gestão de quarentena](../../sending/using/understanding-quarantine-management.md)
* [Quarentena vs lista negra](../../sending/using/understanding-quarantine-management.md#quarantine-vs-blacklisting)
* [Relatórios dinâmicos](../../reporting/using/about-dynamic-reports.md)

## Verificando a configuração da rede {#network-configuration}

Os spammers tentam ocultar a sua verdadeira identidade e, consequentemente, dificultam a identificação dos seus servidores. Uma configuração de rede legítima que não tente ocultar a identidade do servidor é essencial para enviar emails em grandes volumes.

## Enviando para endereços válidos {#valid-addresses}

Os spammers utilizam frequentemente geradores de endereços baseados em listas de nomes frequentes e nomes próprios; além disso, raramente processam notificações técnicas enviadas de volta pelos servidores de e-mail. Muitas vezes, uma alta taxa de endereços inválidos é interpretada como um sinal de spam. Os mecanismos de aceitação dupla e o tratamento eficaz das mensagens técnicas de rejeição permitem evitar esta situação.

## Redução da taxa de reclamação {#reduce-complaint-rate}

Geralmente, os provedores de internet têm um meio proeminente de reportar uma mensagem recebida como spam. Isso permite identificar fontes não confiáveis. Ao atender rapidamente às solicitações de não participação, fazer uso regular de uma determinada lista, verificar o consentimento por meio de um sistema de aceitação dupla e implementar loops de feedback, você pode reduzir as taxas de reclamação.

## Enviar para endereços em lojas {#honeypot-addresses}

Os provedores de acesso e outras organizações (consulte http://www.projecthoneypot.org/) usam caixas de correio que não correspondem às pessoas físicas, mas são criadas apenas para enganar spammers. Estes chamados endereços "mel pot" são publicados na Web para serem recolhidos por spambots e, por conseguinte, capturar remetentes ilegítimos. O uso de um mecanismo de aceitação dupla impede que esse tipo de endereço seja adicionado a uma lista. Ao usar uma lista de terceiros, é necessário ter certeza dos métodos empregados pelo seu responsável principal.

## Adaptação do conteúdo da mensagem {#adapt-message-content}

Em menor grau, o conteúdo de determinadas mensagens pode levar a que determinados filtros as detectem como spam. A utilização de determinadas palavras, a utilização de pontos de exclamação na linha de assunto e nas mensagens são interpretadas como sinais reveladores de spam. Os remetentes de spam também são conhecidos por substituir o texto por imagens para impedir que o texto ofensivo seja analisado automaticamente por filtros antisspam. Em resposta a isso, uma mensagem (em formato HTML) com uma alta proporção de imagens, ou imagens como anexos, pode acabar sendo bloqueada.

## Envio regular {#regular-deliveries}

Os spammers fazem entregas programadas para manter sua reputação ao longo do tempo. Por vezes, têm de adaptar o seu plano de marketing para cumprir as melhores práticas impostas pelos ISPs e, por isso, após um pico de reputação (aumento), configuram entregas regulares.
