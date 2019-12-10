---
title: Recomendações técnicas de entregabilidade para o Adobe Campaign Standard
description: Leia sobre algumas recomendações técnicas para melhorar a entrega com o Adobe Campaign Standard.
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


# Recomendações técnicas{#technical-recommendations}

Além disso, várias técnicas, configurações e ferramentas que podem ser usadas para melhorar a taxa de entrega estão listadas abaixo.

Veja algumas definições dos principais termos técnicos.

**Reverter DNS** O Adobe Campaign verifica se um DNS reverso é fornecido para um endereço IP e se isso aponta corretamente para o IP.

**As regras** MX são usadas para controlar a velocidade na qual o MTA da campanha (Agente de transferência de mensagens) envia emails para cada domínio de email individual ou ISP (por exemplo, hotmail.com, comcast.net). Normalmente, essas regras se baseiam nos limites publicados pelos ISPs (por exemplo, não inclui mais de 20 mensagens por cada conexão SMTP).

**TLS** TLS (Transport Layer Security) é um protocolo de criptografia que pode ser usado para proteger a conexão entre dois servidores de email e proteger o conteúdo de um email de ser lido por qualquer pessoa que não seja os destinatários pretendidos.

**SPF** SPF (Sender Policy Framework) é um padrão de autenticação de email que permite ao proprietário de um domínio especificar quais servidores de email podem enviar emails em nome desse domínio. Este padrão usa o domínio no cabeçalho "Caminho de retorno" do email (também conhecido como o endereço "Envelope de").

**A autenticação DKIM** DKIM (Domain Keys Identified Mail) é uma sucessora do SPF e usa criptografia de chave pública que permite ao servidor de email receptor verificar se uma mensagem foi enviada pela pessoa ou entidade pela qual ela alega ter sido enviada e se o conteúdo da mensagem foi alterado entre o momento em que foi originalmente enviada (e o DKIM "assinado") e o momento em que foi recebida. Normalmente, esse padrão usa o domínio no cabeçalho "De" ou "Remetente".

**DMARC** DMARC (Domain-based Message Authentication, Reporting and Conformance) é a forma mais recente de autenticação de email e depende da autenticação SPF e DKIM para determinar se um email é aprovado ou reprovado. O DMARC é único e poderoso de duas formas muito importantes:
* Conformidade - permite que o remetente instrua os ISPs sobre o que fazer com qualquer mensagem que não seja autenticada (por exemplo, não aceitar).
* Relatório - fornece ao remetente um relatório detalhado mostrando todas as mensagens que falharam na autenticação DMARC, juntamente com o domínio "De" e o endereço IP usados para cada uma. Isso permite que uma empresa identifique e-mails legítimos que estejam falhando na autenticação e precise de algum tipo de "correção" (por exemplo, adicionar endereços IP ao registro SPF), bem como as fontes e a prevalência de tentativas de phishing em seus domínios de e-mail.

O DMARC pode aproveitar os relatórios gerados por 250ok.

**SMTP** SMTP (Simple Mail Transfer Protocol) é um padrão da Internet para transmissão de email.

**IPs dedicados** A Adobe fornece uma estratégia de IP dedicada para cada cliente com um IP ampliado para criar uma reputação e otimizar o desempenho do fornecimento.
