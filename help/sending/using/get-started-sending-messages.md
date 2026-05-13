---
title: Introdução a testes e envios
description: Prepare, teste, agende, envie e monitore suas mensagens.
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
role: User
level: Intermediate
exl-id: bcb28ef5-5cad-43c1-b11b-080abc791a72
TQID: https://experienceleague.adobe.com/0dYFLX0zAqDIz27Y-ekkp9a9rHE9zdjOjioh5gBwaAA
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 595
ht-degree: 15%

---

# Introdução a testes e envios {#about-sending-messages-with-campaign}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_prepare.svg" width="60px"><p><a href="#prepare-test-send">Preparar e testar</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#send-track-messages">Enviar, monitorar e rastrear</a></p></td>
<td><img src="assets/do-not-localize/icon_deliverability.svg" width="60px"><p><a href="#improve-deliverability">Diretrizes de entrega</a></p></td></tr>
</table>

Depois de definir o target e criar o conteúdo de uma mensagem, é necessário preparar e testar o conteúdo, a personalização, a renderização e a configuração dos deliveries. Isso permite que você verifique se tudo está correto antes de enviar a mensagem para o público-alvo principal. Para fazer isso, várias funcionalidades estão disponíveis, como pré-visualização, provas, teste de assunto de email ou renderização de email.

Depois que as campanhas de marketing tiverem sido executadas e as diferentes mensagens tiverem sido enviadas, monitore-as usando logs para verificar o sucesso da campanha e recuperar as informações de rastreamento dos recipients.

Por fim, aproveite as diretrizes e ferramentas de capacidade de delivery disponíveis no Campaign Standard para melhorar o número de mensagens entregues e garantir campanhas de marketing bem-sucedidas.

![](assets/do-not-localize/how-to-video.png) [Descubra como enviar um email de teste, preparar e enviar uma entrega de email em vídeo](#video)

## Preparar e testar {#prepare-test-send}

<img src="assets/do-not-localize/icon_prepare.svg" width="60px">

A **preparação da mensagem** do Campaign Standard analisa o destino, a personalização e a validade da mensagem. Os erros detectados durante essa etapa devem ser corrigidos para que você possa continuar.

**Visualize e teste** suas mensagens usando vários recursos: envie provas para perfis de teste ou perfis segmentados, teste a linha de assunto de seus emails e verifique a renderização de suas mensagens para garantir que elas sejam exibidas de maneira ideal em uma variedade de clientes Web, emails da Web e dispositivos.

Aproveite os recursos de agendamento do Campaign para definir quando suas mensagens serão enviadas. Por exemplo, você pode adaptar o envio no fuso horário do recipient, otimizar o horário de envio ou calcular a data de envio.

Use **tipologias** para verificar, durante a preparação, se sua mensagem é válida e atende aos seus critérios de qualidade por meio de regras de fadiga, controle e direcionamento. Por exemplo, para verificar se seus emails sempre contêm uma linha de assunto ou para excluir cancelamentos de assinatura dos recipients da mensagem.

Leia mais:

* [Preparação do envio](../../sending/using/preparing-the-send.md)
* [Visualização de mensagens](../../sending/using/previewing-messages.md)
* [Envio de provas](../../sending/using/sending-proofs.md)
* [Renderização de email](../../sending/using/email-rendering.md)
* [Agendamento de mensagens](../../sending/using/about-scheduling-messages.md)
* [Sobre tipologias e regras de tipologia](../../sending/using/about-typology-rules.md)

## Enviar, monitorar e rastrear {#send-track-messages}

<img src="assets/do-not-localize/icon_send.svg"  width="60px">

Quando a mensagem estiver pronta, você poderá confirmar os logs e relatórios de envio e acesso para **monitorar a entrega** e medir o sucesso da campanha. O Adobe Campaign também fornece um sistema de alerta por email para rastrear os sucessos ou as falhas do delivery, bem como os recursos de gerenciamento de quarentenas.

**Rastreie o comportamento** dos destinatários da mensagem usando cookies de sessão e permanentes para recuperar informações de rastreamento (URLs clicadas, mirror pages, mensagens abertas...).

Por fim, você pode configurar o Adobe Campaign para **manter uma cópia dos emails** enviados de sua plataforma por meio do Email Cco. Especificamente, se sua organização precisar arquivar todas as mensagens de e-mail enviadas para fins de conformidade, você poderá ativar esse recurso.

Leia mais:

* [Confirmação do envio](../../sending/using/confirming-the-send.md)
* [Rastreamento de mensagens](../../sending/using/tracking-messages.md)
* [Arquivamento com email Cco](../../sending/using/archiving.md)
* [Monitoramento de uma entrega](../../sending/using/monitoring-a-delivery.md)
* [Compreensão de falhas de entrega](../../sending/using/understanding-delivery-failures.md)
* [Compreensão do gerenciamento de quarentena](../../sending/using/understanding-quarantine-management.md)

## Diretrizes de entrega {#improve-deliverability}

<img src="assets/do-not-localize/icon_deliverability.svg"  width="60px">

A capacidade de delivery permite medir o sucesso das campanhas em chegar à caixa de entrada dos recipients sem rejeição ou sem serem marcadas como spam.

O Campaign Standard fornece várias **ferramentas de entrega** para ajudar você a melhorar o número de mensagens entregues com êxito: relatórios de taxa de transferência de entrega, otimização de tempo de envio, pré-visualização de mensagens, renderização de email, gerenciamento de quarentena, etc.

Leia mais:

* [Sobre a capacidade de entrega](../../sending/using/about-deliverability.md)
* [Monitoramento da capacidade de entrega](../../sending/using/monitor-deliverability.md)
* [Guia de práticas recomendadas de capacidade de delivery do Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=pt-BR)
* [Controle da taxa de transferência de delivery](../../reporting/using/delivery-throughput.md)

## Recursos adicionais

* [Criação de emails de teste A/B](../../channels/using/designing-an-a-b-test-email.md)
* [Introdução a mensagens](../../channels/using/key-steps-to-send-a-message.md)
* [Práticas recomendadas de entrega](../../sending/using/delivery-best-practices.md)
* [Adição de um grupo de controle](../../sending/using/control-group.md)

## Tutorial em vídeo {#video}

Este vídeo mostra como enviar um email de teste, preparar e enviar um delivery de email no Campaign Standard.

>[!VIDEO](https://video.tv.adobe.com/v/24013/)

Vídeos extras explicativos do Campaign Standard estão disponíveis [aqui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=pt-BR).
