---
solution: Campaign Standard
product: campaign
title: Recomendações técnicas de capacidade de entrega para o Adobe Campaign Standard
description: Leia sobre algumas recomendações técnicas para melhorar a capacidade de entrega com o Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Avaliação do delivery
role: Profissional
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 43%

---


# Recomendações técnicas{#technical-recommendations}

Várias técnicas, configurações e ferramentas que podem ser usadas para melhorar a taxa de entrega estão listadas abaixo. Aqui estão algumas definições dos principais termos técnicos.

**Reverse DNS**: o Adobe Campaign verifica se um DNS reverso é fornecido para um endereço IP e se ele é apontado corretamente ao IP.

**As** regras MX são usadas para controlar a velocidade na qual o MTA da campanha (Agente de transferência de mensagens) envia emails para cada domínio de email individual ou ISP (por exemplo, hotmail.com, comcast.net). Normalmente, essas regras se baseiam nos limites publicados pelos ISPs (por exemplo, não incluir mais de 20 mensagens por cada conexão SMTP).

**TLS**  (Transport Layer Security) é um protocolo de criptografia que pode ser usado para proteger a conexão entre dois servidores de email e proteger o conteúdo de um email de ser lido por qualquer pessoa que não seja os recipients pretendidos.

**O SPF**  (Sender Policy Framework) é um padrão de autenticação de email que permite ao proprietário de um domínio especificar quais servidores de email têm permissão para enviar email em nome desse domínio. Este padrão usa o domínio no cabeçalho &quot;Return-Path&quot; do email (também conhecido como o endereço &quot;Envelope From&quot;).

**A autenticação DKIM**  (Domain Keys Identified Mail) é sucessora do SPF e usa criptografia de chave pública que permite ao servidor de email de recebimento verificar se uma mensagem foi enviada pela pessoa ou entidade pela qual alega ter sido enviada e se o conteúdo da mensagem foi alterado entre o momento em que foi originalmente enviada (e o DKIM &quot;assinado&quot;) e o momento em que foi recebida. Normalmente, esse padrão usa o domínio no cabeçalho &quot;From&quot; ou &quot;Sender&quot;.

**DMARC**  (Domain-based Message Authentication, Reporting and Conformance) é a forma mais recente de autenticação de email e depende da autenticação SPF e DKIM para determinar se um email foi aprovado ou reprovado. O DMARC é único e eficiente de duas maneiras muito importantes:
* Conformidade - permite que o remetente instrua os ISPs sobre o que fazer com qualquer mensagem que não seja autenticada (por exemplo, não aceitar).
* Relatório - fornece ao remetente um relatório detalhado mostrando todas as mensagens que falharam na autenticação DMARC, juntamente com o domínio &quot;From&quot; e o endereço IP usados para cada uma. Isso permite que uma empresa identifique emails legítimos que estejam falhando na autenticação e precise de algum tipo de &quot;correção&quot; (por exemplo, adicionar endereços IP ao registro SPF), bem como as fontes e a prevalência de tentativas de phishing em seus domínios de email.

O DMARC pode se beneficiar dos relatórios gerados por 250ok.

**SMTP**  (Simple mail transfer protocol) é um padrão de Internet para transmissão de e-mail.

**IPs** dedicados: O Adobe fornece uma estratégia de IP dedicada para cada cliente com um IP ampliado para criar uma reputação e otimizar o desempenho do delivery.
