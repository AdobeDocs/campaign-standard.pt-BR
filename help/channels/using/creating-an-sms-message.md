---
title: Criação de uma mensagem SMS
seo-title: Criação de uma mensagem SMS
description: Criação de uma mensagem SMS
seo-description: Siga estas etapas para criar uma mensagem SMS de envio único no Adobe Campaign.
page-status-flag: nunca ativado
uuid: 591 ae 97 e -2 d 19-4 f 93-be 4 b-d 8 d 20 f 1 d 2 d 12
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: sms-messages
discoiquuid: b 27381 a 9-19 e 5-4 b 65-b 194-c 72 f 475 ba 54 d
delivercontext-tags: Deliverycreation, assistente
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d50d486ed77cb7989df47133bb49fde3227ae3a5

---


# Creating an SMS message{#creating-an-sms-message}

Criar uma entrega SMS é muito semelhante à criação de um e-mail normal. As etapas a seguir descrevem a configuração que é específica para este canal. Refer to [Creating an email](../../channels/using/creating-an-email.md) for more information on other options.

Advanced SMS parameters are detailed in the [SMS configuration](../../administration/using/configuring-sms-channel.md) section.

Para criar e enviar mensagens SMS a um telefone celular, você precisa:

* A **[!UICONTROL Routing]** external account configured on the **[!UICONTROL Mobile (SMS)]** channel with the **[!UICONTROL Bulk delivery]** mode. For more on this, refer to the [Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.
* Um modelo de entrega que está corretamente vinculado a esta conta externa.

1. Crie uma entrega SMS. You can do it from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page), in a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity) or in the [marketing activity list](../../start/using/programs-and-campaigns.md#creating-a-campaign).

   Também é possível adicionar uma atividade SMS em um fluxo de trabalho. For more on this, refer to the [Workflows](../../automating/using/sms-delivery.md) guide.

   Ao criar uma mensagem, um assistente é exibido para orientar você pelas etapas mais importantes. O que é definido por meio do assistente ainda pode ser editado depois do painel de mensagens.

1. Selecione o modelo que deseja usar. Você pode escolher o modelo de SMS out-of-the-box ou um de seus próprios modelos.

   ![](assets/sms_creation_1.png)

   Para fornecer a um telefone celular, o modelo de entrega deve estar vinculado corretamente à conta externo de roteamento de SMS.

1. Insira as propriedades gerais do SMS.

   ![](assets/sms_creation_2.png)

   O rótulo da atividade e a ID aparecem na interface, mas não são visíveis para os destinatários da mensagem.

1. Especifique o público-alvo que deseja direcionar. Você pode selecionar um público-alvo existente ou direcionar diretamente uma população ao definir e combinar regras.

   ![](assets/sms_creation_3.png)

1. Adicionar conteúdo ao SMS. You can also define the content by clicking the **[!UICONTROL Content]** section of the delivery dashboard, once the SMS creation is finalized. See [About SMS content design](../../designing/using/about-sms-and-push-content-design.md).

   Se você inseriu campos de personalização ou texto condicional no conteúdo de sua mensagem SMS, o comprimento da mensagem pode variar de um destinatário para outro. na verdade, esses fatores podem inserir caracteres que não são considerados pela codificação GSM. É por isso que o comprimento da mensagem deve ser avaliado após a realização da personalização. See [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_creation_4.png)

1. Confirme a criação da mensagem. O painel é exibido.
1. Programe o envio. O SMS pode ser enviado manualmente após a preparação da mensagem ou automaticamente em uma data programada. See [Scheduling messages](../../sending/using/about-scheduling-messages.md).
1. Prepare a mensagem para analisar sua validade, personalização e meta.

   ![](assets/sms_creation_6.png)

   >[!NOTE]
   >
   >Você pode definir regras globais de esgotamento entre canais que excluirão automaticamente os perfis substituídos das campanhas. See [Fatigue rules](../../administration/using/fatigue-rules.md).

1. Envie testes para verificar e validar a mensagem e monitorar a renderização da caixa de entrada. See the [Sending proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) section.
1. Confirme o envio da mensagem. O envio começará de acordo com a programação definida.

   ![](assets/sms_creation_7.png)

A mensagem é enviada. Você pode verificar sua entrega pelo painel de mensagens e logs.

Após concluir o envio, você pode começar a medir o impacto da sua mensagem com relatórios de entrega incorporados ou personalizados.

**Tópicos relacionados:**

* [Sobre a edição de conteúdo SMS e push](../../designing/using/about-sms-and-push-content-design.md)
* [Gerenciamento de modelos](../../start/using/about-templates.md)
* [Criar um vídeo de entrega](https://helpx.adobe.com/campaign/kt/acs/using/acs-creating-a-sms-delivery-feature-video-use.html) de SMS

