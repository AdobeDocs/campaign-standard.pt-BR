---
title: Criar uma mensagem SMS
description: Siga estas etapas para criar uma mensagem SMS de envio único no Adobe Campaign.
page-status-flag: never-activated
uuid: 591ae97e-2d19-4f93-be4b-d8d20f1d2d12
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: b27381a9-19e5-4b65-b194-c72f475ba54d
delivercontext-tags: deliveryCreation,wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# Criar uma mensagem SMS{#creating-an-sms-message}

A criação de uma entrega de SMS é muito semelhante à criação de um email comum. As etapas a seguir descrevem a configuração que é específica para esse canal. Consulte [Criação de um email](../../channels/using/creating-an-email.md) para obter mais informações sobre outras opções.

Parâmetros SMS avançados são detalhados na seção de configuração [](../../administration/using/configuring-sms-channel.md) SMS.

Para criar e enviar mensagens SMS para um telefone celular, é necessário:

* Uma conta **[!UICONTROL Routing]**externa configurada no**[!UICONTROL Mobile (SMS)]** canal com o **[!UICONTROL Bulk delivery]**modo. For more on this, refer to the[Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)section.
* Um modelo de entrega vinculado corretamente a esta conta externa.

1. Crie uma entrega de SMS. Você pode fazer isso na [página](../../start/using/interface-description.md#home-page)inicial do Adobe Campaign, em uma [campanha](../../start/using/marketing-activities.md#creating-a-marketing-activity) ou na lista [de atividades de](../../start/using/programs-and-campaigns.md#creating-a-campaign)marketing.

   Você também pode adicionar uma atividade SMS em um fluxo de trabalho. For more on this, refer to the [Workflows](../../automating/using/sms-delivery.md) guide.

   Ao criar uma mensagem, um assistente é exibido para orientá-lo pelas etapas mais importantes. O que é definido pelo assistente ainda pode ser editado depois do painel de mensagens.

1. Selecione o modelo que deseja usar. Você pode escolher o modelo de SMS predefinido ou um dos seus próprios modelos.

   ![](assets/sms_creation_1.png)

   Para entregar para um telefone celular, o modelo de entrega deve estar corretamente vinculado à conta externa de roteamento SMS.

1. Insira as propriedades gerais do SMS.

   ![](assets/sms_creation_2.png)

   O rótulo da atividade e sua ID são exibidos na interface, mas não são visíveis para os destinatários da mensagem.

1. Especifique o público-alvo que deseja direcionar. Você pode selecionar um público existente ou direcionar diretamente a um público definindo e combinando regras.

   ![](assets/sms_creation_3.png)

1. Adicione conteúdo ao seu SMS. Você também pode definir o conteúdo clicando na **[!UICONTROL Content]**seção do painel de entrega, depois que a criação do SMS for finalizada. Consulte[Sobre design](../../channels/using/about-sms-and-push-content-design.md)de conteúdo SMS.

   Se você tiver inserido campos de personalização ou texto condicional no conteúdo de sua mensagem SMS, a duração da mensagem pode variar de um destinatário para outro. na verdade, esses fatores podem introduzir caracteres que não são considerados pela codificação GSM. Por isso, a duração da mensagem deve ser avaliada uma vez realizada a personalização. See [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_creation_4.png)

1. Confirme a criação da mensagem. Seu painel é exibido.
1. Agende o envio. O SMS pode ser enviado manualmente logo após a preparação da mensagem ou automaticamente em uma data programada. Consulte [Agendamento de mensagens](../../sending/using/about-scheduling-messages.md).
1. Prepare a mensagem para analisar sua validade, personalização e destino.

   ![](assets/sms_creation_6.png)

   >[!NOTE]
   >
   >Você pode definir regras de fadiga globais entre canais que excluirão automaticamente perfis supersolacionados de campanhas. Consulte Regras de [fadiga](../../administration/using/fatigue-rules.md).

1. Envie provas para verificar e validar a mensagem e monitorar a renderização da caixa de entrada. Consulte a seção [Enviando prova](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) .
1. Confirme o envio da mensagem. O envio será iniciado de acordo com a programação definida.

   ![](assets/sms_creation_7.png)

A mensagem é enviada. Você pode verificar sua entrega no painel de mensagens e nos registros.

Quando o envio estiver concluído, você poderá começar a medir o impacto de sua mensagem com relatórios de entrega incorporados ou personalizados.

**Tópicos relacionados:**

* [Sobre SMS e edição de conteúdo de push](../../channels/using/about-sms-and-push-content-design.md)
* [Gerenciamento de modelos](../../start/using/marketing-activity-templates.md)
* [Criar um vídeo de entrega](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/sms/sms-delivery.html) SMS

