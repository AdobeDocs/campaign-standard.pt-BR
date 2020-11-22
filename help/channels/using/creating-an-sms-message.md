---
solution: Campaign Standard
product: campaign
title: Criar uma mensagem SMS
description: Siga estas etapas para criar uma mensagem SMS de envio único no Adobe Campaign.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 100%

---


# Criar uma mensagem SMS{#creating-an-sms-message}

A criação de um delivery de SMS é muito semelhante à criação de um email comum. As etapas a seguir descrevem a configuração específica para esse canal. Consulte [Criar um email](../../channels/using/creating-an-email.md) para obter mais informações sobre outras opções.

Parâmetros de SMS avançados são detalhados na seção [Configuração de SMS](../../administration/using/configuring-sms-channel.md).

Para criar e enviar mensagens SMS para um telefone celular, é necessário:

* Uma conta externa de **[!UICONTROL Routing]** configurada no canal **[!UICONTROL Mobile (SMS)]** com o modo **[!UICONTROL Bulk delivery]**. Para mais informações, consulte a seção [Roteamento](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).
* Um template do delivery vinculado corretamente a essa conta externa.

1. Crie um delivery de SMS. Você pode fazer isso na [página inicial](../../start/using/interface-description.md#home-page) do Adobe Campaign, em uma [campanha](../../start/using/marketing-activities.md#creating-a-marketing-activity) ou na [lista de atividade de marketing](../../start/using/programs-and-campaigns.md#creating-a-campaign).

   Você também pode adicionar uma atividade SMS em um fluxo de trabalho. Para mais informações, consulte o Guia [Fluxos de trabalho](../../automating/using/sms-delivery.md).

   Ao criar uma mensagem, um assistente é exibido para orientá-lo pelas etapas mais importantes. O que é definido pelo assistente ainda pode ser editado depois diretamente do painel de mensagens.

1. Selecione o modelo que deseja usar. Você pode escolher o modelo SMS pronto para uso ou um dos seus próprios modelos.

   ![](assets/sms_creation_1.png)

   Para enviar para um telefone celular, o template do delivery deve estar corretamente vinculado à conta externa do roteamento SMS.

1. Insira as propriedades gerais do SMS.

   ![](assets/sms_creation_2.png)

   O rótulo da atividade e sua ID aparecem na interface, mas não são visíveis para os recipients da mensagem.

1. Especifique o público que deseja segmentar. É possível selecionar um público existente ou segmentar diretamente uma população definindo e combinando regras.

   ![](assets/sms_creation_3.png)

1. Adicione conteúdo ao seu SMS. Você também pode definir o conteúdo clicando na seção **[!UICONTROL Content]** do painel do delivery depois que a criação do SMS for finalizada. Consulte [Sobre design de conteúdo de SMS](../../channels/using/about-sms-and-push-content-design.md).

   Se você tiver inserido campos de personalização ou texto condicional no conteúdo da mensagem SMS, o comprimento da mensagem pode variar de um recipient para outro. Na verdade, esses fatores podem introduzir caracteres que não são considerados pela codificação GSM. Por isso, a duração da mensagem deve ser avaliada depois de realizada a personalização. Consulte [Personalização de mensagens SMS](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_creation_4.png)

1. Confirme a criação da mensagem. O painel é exibido.
1. Programe o envio. O SMS pode ser enviado manualmente logo após a preparação da mensagem ou automaticamente em uma data programada. Consulte [Agendamento de mensagens](../../sending/using/about-scheduling-messages.md).
1. Prepare a mensagem para analisar a validade, a personalização e o público alvo.

   ![](assets/sms_creation_6.png)

   >[!NOTE]
   >
   >Você pode definir regras de fadiga globais entre canais que excluirão automaticamente das campanhas os perfis com excesso de pedidos. Consulte [Regras de fadiga](../../sending/using/fatigue-rules.md).

1. Envie provas para verificar e validar a mensagem e monitorar a renderização da caixa de entrada. Consulte a seção [Envio de prova](../../sending/using/sending-proofs.md).
1. Confirme o envio da mensagem. O envio iniciará de acordo com a programação definida.

   ![](assets/sms_creation_7.png)

A mensagem é enviada. Você pode verificar o delivery pelo painel de mensagens e registros.

Quando o envio estiver concluído, você pode iniciar a medição do impacto de sua mensagem com relatórios do delivery incorporados ou personalizados.

**Tópicos relacionados:**

* [Sobre SMS e edição de conteúdo de notificações por push](../../channels/using/about-sms-and-push-content-design.md)
* [Gerenciamento de modelos](../../start/using/marketing-activity-templates.md)
* Vídeo [Criação de um delivery de SMS](https://docs.adobe.com/content/help/pt-BR/campaign-standard-learn/tutorials/communication-channels/mobile/sms/sms-delivery.translate.html)
