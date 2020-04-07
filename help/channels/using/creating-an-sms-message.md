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
source-git-commit: 155ed7e50e207e4c4dc0569e5e96b24e712e4be8

---


# Criar uma mensagem SMS{#creating-an-sms-message}

A criação de um delivery SMS é muito semelhante à criação de um email comum. As etapas a seguir descrevem a configuração que é específica para esse canal. Consulte [Criação de um email](../../channels/using/creating-an-email.md) para obter mais informações sobre outras opções.

Parâmetros SMS avançados são detalhados na seção de configuração [](../../administration/using/configuring-sms-channel.md) SMS.

Para criar e enviar mensagens SMS para um telefone celular, é necessário:

* Uma **[!UICONTROL Routing]** conta externa configurada no **[!UICONTROL Mobile (SMS)]** canal com o **[!UICONTROL Bulk delivery]** modo. For more on this, refer to the [Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.
* Um template do delivery vinculado corretamente a essa conta externa.

1. Crie um delivery SMS. Você pode fazer isso a partir do [home page](../../start/using/interface-description.md#home-page)Adobe Campaign, em uma [campanha](../../start/using/marketing-activities.md#creating-a-marketing-activity) ou na lista [da atividade](../../start/using/programs-and-campaigns.md#creating-a-campaign)de marketing.

   Você também pode adicionar uma atividade SMS em um fluxo de trabalho. For more on this, refer to the [Workflows](../../automating/using/sms-delivery.md) guide.

   Ao criar uma mensagem, um assistente é exibido para orientá-lo pelas etapas mais importantes. O que é definido pelo assistente ainda pode ser editado depois do painel de mensagem.

1. Selecione o modelo que deseja usar. Você pode escolher o modelo de SMS predefinido ou um dos seus próprios modelos.

   ![](assets/sms_creation_1.png)

   Para enviar para um telefone celular, o template do delivery deve estar corretamente ligado à conta externa do roteamento SMS.

1. Insira as propriedades gerais do SMS.

   ![](assets/sms_creation_2.png)

   A etiqueta de atividade e sua ID são exibidas na interface, mas não são visíveis para os recipient de mensagem.

1. Especifique a audiência que deseja público alvo. É possível selecionar uma audiência existente ou público alvo direto de uma população definindo e combinando regras.

   ![](assets/sms_creation_3.png)

1. Adicione conteúdo ao seu SMS. Você também pode definir o conteúdo clicando na **[!UICONTROL Content]** seção do painel do delivery, depois que a criação do SMS for finalizada. Consulte [Sobre design](../../channels/using/about-sms-and-push-content-design.md)de conteúdo SMS.

   Se você tiver inserido campos de personalização ou texto condicional no conteúdo de sua mensagem SMS, o comprimento da mensagem pode variar de um recipient para outro. na verdade, esses fatores podem introduzir caracteres que não são considerados pela codificação GSM. Por isso, a duração da mensagem deve ser avaliada uma vez realizada a personalização. See [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_creation_4.png)

1. Confirme a criação da mensagem. Seu painel é exibido.
1. Agende o envio. O SMS pode ser enviado manualmente logo após a preparação da mensagem ou automaticamente em uma data programada. Consulte [Agendamento de mensagens](../../sending/using/about-scheduling-messages.md).
1. Prepare a mensagem para analisar sua validade, personalização e público alvo.

   ![](assets/sms_creation_6.png)

   >[!NOTE]
   >
   >Você pode definir regras de fadiga globais entre canais que excluirão automaticamente perfis supersolacionados do campanha. Consulte Regras de [fadiga](../../sending/using/fatigue-rules.md).

1. Envie provas para verificar e validar a mensagem e monitorar a renderização da caixa de entrada. Consulte a seção [Enviando prova](../../sending/using/sending-proofs.md) .
1. Confirme o envio da mensagem. O envio será start de acordo com a programação definida.

   ![](assets/sms_creation_7.png)

A mensagem é enviada. Você pode verificar seu delivery pelo painel de mensagens e registros.

Quando o envio estiver concluído, você poderá start a medição do impacto de sua mensagem com relatórios do delivery incorporados ou personalizados.

**Tópicos relacionados:**

* [Sobre SMS e edição de conteúdo de push](../../channels/using/about-sms-and-push-content-design.md)
* [Gerenciamento de modelos](../../start/using/marketing-activity-templates.md)
* [Criar um vídeo de delivery](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/sms/sms-delivery.html) SMS

