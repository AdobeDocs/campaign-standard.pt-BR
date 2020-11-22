---
solution: Campaign Standard
product: campaign
title: Sobre a capacidade de entrega no Adobe Campaign Standard
description: Saiba mais sobre os conceitos e as práticas recomendadas relacionadas à capacidade de entrega, bem como sobre as ferramentas oferecidas pela Adobe Campaign Standard para otimizar o envio dos delivery.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 82%

---


# Sobre a entregabilidade{#about-deliverability}

A capacidade de entrega permite medir o sucesso de suas campanhas ao chegar à sua caixa de entrada de recipient sem saltar ou ser marcado como spam.

A taxa de delivery depende de vários fatores, especialmente:

* A configuração correta das instâncias
* A reputação do endereço IP
* A qualidade dos endereços de destino
* Baixas taxas de reclamação e rejeição
* O conteúdo da mensagem
* Autenticação da mensagem (SPF, DKIM, DMARC)
* Reputação do remetente

## Pontos principais a serem verificados {#deliverability-key-points}

Para otimizar a capacidade de delivery de emails do Adobe Campaign, recomendamos o uso das práticas recomendadas listadas abaixo. Os problemas de capacidade de entrega estão geralmente ligados a medidas de proteção contra spam implementadas por provedores de serviço da Internet e administradores de servidores de e-mail.

A capacidade de fornecimento de email refere-se ao conjunto de características que determinam a capacidade de uma mensagem de alcançar seu destino por meio de um endereço de email pessoal, dentro de um curto período e com a qualidade esperada em termos de conteúdo e formato. Essas características estão em quatro categorias principais: qualidade de dados, mensagem e conteúdo, infraestrutura de envio e reputação. Juntos, elas formam a base de um programa bem-sucedido de capacidade de fornecimento de email.

A taxa de delivery é o número de emails enviados que foram entregues com êxito aos recipients.
Esta é uma lista dos pontos principais a serem verificados para garantir um bom delivery.

## Ferramentas de entrega {#deliverability-tools}

Em primeiro lugar, consulte a documentação sobre as ferramentas de entrega fornecidas com o Campaign Standard:
* [Práticas recomendadas para delivery](../../sending/using/delivery-best-practices.md)
* [Personalização do nome do remetente](../../designing/using/personalization.md#personalizing-the-sender)
* [Teste da linha de assunto de um email](../../sending/using/testing-subject-line-email.md)
* [Otimização do tempo de envio](../../sending/using/optimizing-the-sending-time.md)
* [Visualização de mensagens](../../sending/using/previewing-messages.md)
* [Renderização de email](../../sending/using/email-rendering.md)
* [Monitorar um delivery](../../sending/using/monitoring-a-delivery.md)
* [Receber alertas quando ocorrerem falhas](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Noções básicas sobre falhas de delivery](../../sending/using/understanding-delivery-failures.md)
* [Noções básicas sobre gestão de quarentena](../../sending/using/understanding-quarantine-management.md)
* [Quarentena × lista de bloqueios](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)
* [Relatórios dinâmicos](../../reporting/using/about-dynamic-reports.md)

## Verificar a configuração da rede {#network-configuration}

Os remetentes de spam tentam ocultar a verdadeira identidade e, assim, dificultam a identificação dos servidores. Uma configuração de rede legítima que não tente ocultar a identidade do servidor é essencial para enviar emails em grandes volumes.

## Sending to valid addresses {#valid-addresses}

Os remetentes de spam utilizam frequentemente geradores de endereços baseados em listas de nomes frequentes e nomes próprios; além disso, raramente processam notificações técnicas enviadas de volta pelos servidores de email. Muitas vezes, uma alta taxa de endereços inválidos é interpretada como um sinal de spam. Os mecanismos de aceitação dupla e o tratamento eficaz das mensagens técnicas de rejeição permitem evitar esta situação.

## Redução da taxa de reclamação {#reduce-complaint-rate}

Geralmente, os provedores de internet têm um meio proeminente de reportar uma mensagem recebida como spam. Isso permite identificar fontes não confiáveis. Ao atender rapidamente às solicitações de recusa, fazer uso regular de uma determinada lista, verificar o consentimento por meio de um sistema de aceitação dupla e implementar loops de feedback, você pode reduzir as taxas de reclamação.

## Sending to honeypot addresses {#honeypot-addresses}

Os provedores de acesso e outras organizações (consulte http://www.projecthoneypot.org/) usam caixas de correio que não correspondem às pessoas físicas, mas são criadas apenas para enganar spammers. Esses endereços, chamados de &quot;honey pot&quot;, são publicados na Web para serem recolhidos por spambots e, assim, capturar remetentes ilegítimos. O uso de um mecanismo de aceitação dupla impede que esse tipo de endereço seja adicionado a uma lista. Ao usar uma lista de terceiros, é necessário ter certeza dos métodos empregados pelo responsável principal.

## Adaptação do conteúdo da mensagem {#adapt-message-content}

Em menor grau, o conteúdo de determinadas mensagens pode levar a que determinados filtros as detectem como spam. A utilização de determinadas palavras e o uso de pontos de exclamação na linha de assunto e nas mensagens são interpretados como sinais reveladores de spam. Os remetentes de spam também são conhecidos por substituir o texto por imagens para impedir que o texto ofensivo seja analisado automaticamente por filtros anti-spam. Em resposta a isso, uma mensagem (em formato HTML) com uma alta proporção de imagens, ou imagens como anexos, pode acabar sendo bloqueada.

## Envio regular {#regular-deliveries}

Os remetentes de spam fazem deliveries programados para manter a reputação ao longo do tempo. Por vezes, eles precisam adaptar o plano de marketing para cumprir as melhores práticas impostas pelos ISPs e, por isso, após um pico de reputação (aumento), configuram deliveries regulares.
