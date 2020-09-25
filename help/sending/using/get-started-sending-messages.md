---
title: Introdução a testes e envios
description: Saiba como preparar e testar suas mensagens, agendar, enviar e monitorar, compreender o gerenciamento de falhas e quarentenas e otimizar a entrega.
page-status-flag: never-activated
uuid: 58666444-6e7c-4049-b2d2-8b26eabf5a82
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
discoiquuid: ae2eba1c-24ad-4839-afa9-5a2975570d9b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e67a173c5409d7693a3d7dab8f8ca3b03aeb886f
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 12%

---


# Introdução a testes e envios {#about-sending-messages-with-campaign}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_prepare.svg" width="60px"><p><a href="#prepare-test-send">Preparar e testar</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#send-track-messages">Enviar, monitorar e rastrear</a></p></td>
<td><img src="assets/do-not-localize/icon_deliverability.svg" width="60px"><p><a href="#improve-deliverability">Diretrizes de entregabilidade</a></p></td></tr>
</table>

Depois de definir o público alvo e criar o conteúdo de uma mensagem, é necessário preparar e testar o conteúdo dos delivery, personalização, renderização e configuração. Isso permite que você se certifique de que tudo esteja correto antes de enviar a mensagem para o público alvo principal. Para fazer isso, várias funcionalidades estão disponíveis como pré-visualização, provas, teste de linha de assunto do email ou renderização de email.

Depois que as campanhas de marketing tiverem sido executadas e as diferentes mensagens tiverem sido enviadas, monitore-as usando registros para verificar o sucesso de sua campanha e recupere as informações de rastreamento nos recipient.

Por fim, aproveite as diretrizes e as ferramentas de entrega disponíveis no Campaign Standard para melhorar o número de mensagens entregues e garantir campanhas de marketing bem-sucedidas.

## Preparar e testar {#prepare-test-send}

<img src="assets/do-not-localize/icon_prepare.svg" width="60px">

A preparação **da** mensagem de Campaign Standard analisa o público alvo, a personalização e a validade da mensagem. Os erros detectados durante esta etapa devem ser corrigidos antes de poder continuar.

**Pré-visualização e teste** suas mensagens usando vários recursos: envie provas para testar perfis ou perfis com metas, teste a linha de assunto de seus emails e verifique a renderização de suas mensagens para garantir que elas sejam exibidas da melhor forma em diversos clientes da Web, emails e dispositivos.

Aproveite os recursos de agendamento de Campanha para definir quando suas mensagens serão enviadas. Por exemplo, você pode adaptar o envio no fuso horário do recipient, otimizar a hora de envio ou calcular a data de envio.

Use **tipologias** para verificar durante a preparação se a mensagem é válida e atende aos seus critérios de qualidade por meio de regras de fadiga, controle e definição de metas. Por exemplo, para verificar se seus emails sempre contêm uma linha de assunto ou para excluir os canceladores dos recipient de mensagem.

Leia mais:

* [Preparação do envio](../../sending/using/preparing-the-send.md)
* [Visualização de mensagens](../../sending/using/previewing-messages.md)
* [Envio de provas](../../sending/using/sending-proofs.md)
* [Renderização de email](../../sending/using/email-rendering.md)
* [Agendamento de mensagens](../../sending/using/about-scheduling-messages.md)
* [Sobre tipologias e regras de tipologia](../../sending/using/about-typology-rules.md)

## Enviar, monitorar e rastrear {#send-track-messages}

<img src="assets/do-not-localize/icon_send.svg"  width="60px">

Quando a mensagem estiver pronta, você poderá confirmar os registros e relatórios de envio e acesso para **monitorar o delivery** e medir o sucesso da campanha. A Adobe Campaign também fornece um sistema de alerta por email para rastrear sucessos ou falhas do delivery, bem como recursos de gerenciamento de quarentenas.

**Rastreie o comportamento** dos recipient de mensagens usando cookies permanentes e de sessão para recuperar informações de rastreamento (URLs clicados, mirrores page, mensagens abertas...).

Por fim, você pode configurar a Adobe Campaign para **manter uma cópia dos emails** enviados de sua plataforma por meio do Email BCC. Em particular, se sua organização precisar arquivar todas as mensagens de email de saída para fins de conformidade, você poderá habilitar esse recurso.

Leia mais:

* [Confirmação do envio](../../sending/using/confirming-the-send.md)
* [Rastreamento de mensagens](../../sending/using/tracking-messages.md)
* [Arquivamento com email Cco](../../sending/using/archiving.md)
* [Monitoramento de uma entrega](../../sending/using/monitoring-a-delivery.md)
* [Noções básicas sobre falhas de delivery](../../sending/using/understanding-delivery-failures.md)
* [Noções básicas sobre gestão de quarentena](../../sending/using/understanding-quarantine-management.md)

## Diretrizes de entregabilidade {#improve-deliverability}

<img src="assets/do-not-localize/icon_deliverability.svg"  width="60px">

A capacidade de entrega permite medir o sucesso de suas campanhas ao chegar à sua caixa de entrada de recipient sem saltar ou ser marcado como spam.

O Campaign Standard fornece várias ferramentas **de** entrega para ajudá-lo a melhorar o número de mensagens entregues com êxito: Relatórios de pensamento do delivery, otimização do tempo de envio, pré-visualização de mensagens, renderização de e-mail, gerenciamento de quarentenas etc.

Leia mais:

* [Sobre a entregabilidade](../../sending/using/about-deliverability.md)
* [Monitoramento da capacidade de entrega](../../sending/using/monitor-deliverability.md)
* [Aprimoramento da reputação](../../sending/using/improving-reputation.md)
* [Recomendações técnicas](../../sending/using/technical-recommendations.md)
* [Controlar a taxa de transferência do Delivery](../../reporting/using/delivery-throughput.md)

## Recursos adicionais

* [Criação de emails de teste A/B](../../channels/using/designing-an-a-b-test-email.md)
* [Envie um teste, prepare e envie um email (vídeo)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/sending-test-preparing-sending-email.html)
* [Analisar um delivery de email e relatórios (vídeo)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/reviewing-personalized-email-delivery-and-reports.html)
* [Introdução aos emails](https://helpx.adobe.com/br/campaign/kb/acs-get-started-with-emails.html)
* [Práticas recomendadas para delivery](../../sending/using/delivery-best-practices.md)
* [Adicionar um grupo de controle](../../sending/using/control-group.md)
