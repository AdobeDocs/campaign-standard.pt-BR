---
title: Sobre o envio de mensagens com o Campaign
description: Descubra as diferentes etapas para testar e enviar uma mensagem.
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
source-git-commit: e6c43770755e59bf2a2d49540a052ac0bd2a2438

---


# Sobre o envio de mensagens com o Campaign{#about-sending-messages-with-campaign}

Depois de definir o público alvo e criar o conteúdo de uma mensagem, é necessário testar e aprovar o conteúdo, a personalização, a renderização e a configuração, e verificar se tudo está correto antes de enviar a mensagem para o público alvo principal.

Para fazer isso, as práticas recomendadas são:

* Prepare o envio: esta etapa permite que você vá para a análise e preparação de mensagens a serem enviadas. A preparação da mensagem analisa o público alvo, a personalização e a validade da mensagem. Os erros detectados durante esta etapa devem ser corrigidos antes de poder continuar. Você pode iniciar a preparação da mensagem quantas vezes forem necessárias. For more on message preparation, refer to [this section](../../sending/using/preparing-the-send.md).

   >[!NOTE]
   >
   >Você pode definir regras de fadiga globais entre canais que excluirão automaticamente perfis supersolacionados do campanha. Consulte Regras de [fadiga](../../sending/using/fatigue-rules.md).

* Mensagens de Pré-visualização usando um perfil de teste. For more on previewing messages, refer to [this section](../../sending/using/previewing-messages.md).
* Envie provas para testar mensagens. For more on proofs, refer to [this  section](../../sending/using/sending-proofs.md).
* Verifique a renderização da mensagem: certifique-se de que sua mensagem será exibida da melhor forma em uma variedade de clientes da Web, emails da Web e dispositivos. Saiba mais sobre a renderização por email [nesta seção](../../sending/using/email-rendering.md).

Você pode então:

* Agendar o envio: você pode definir quando as mensagens serão enviadas. Por exemplo, você pode adaptar o envio no fuso horário do recipient, otimizar a hora de envio ou calcular a data de envio. Saiba mais [nesta seção](../../sending/using/about-scheduling-messages.md).
* Envie a mensagem: quando a mensagem estiver pronta, você poderá start o envio. Os registros e relatórios de acesso ficam disponíveis para monitorar o delivery da mensagem e medir o sucesso da campanha. O Adobe Campaign também fornece um sistema de alerta por email para acompanhar os sucessos ou falhas do delivery. Learn more in [this page](../../sending/using/confirming-the-send.md).

## Tópicos relacionados

| Páginas úteis | Recursos adicionais |
|---|---|
| [Otimização da entrega](../../sending/using/about-deliverability.md) | [Gerenciamento de fadiga](../../sending/using/fatigue-rules.md) |
| [Monitoramento de uma entrega](../../audiences/using/creating-profiles.md) | [Criação de emails de teste A/B](../../channels/using/designing-an-a-b-test-email.md) |
| [Recebendo uma notificação quando ocorre uma falha](../../sending/using/receiving-alerts-when-failures-happen.md) | [Monitoramento de uma entrega](../../sending/using/monitoring-a-delivery.md) |
| [Criação de um grupo de controle](../../automating/using/workflow-control-group.md) | [Recebendo uma notificação quando ocorre uma falha](../../sending/using/receiving-alerts-when-failures-happen.md) |
| [Controlar a taxa de transferência do Delivery](../../reporting/using/delivery-throughput.md) | [Monitoramento de uma entrega](../../sending/using/monitoring-a-delivery.md) |