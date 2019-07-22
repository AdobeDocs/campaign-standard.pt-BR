---
title: Criação de um email
seo-title: Criação de um email
description: Criação de um email
seo-description: Siga estas etapas para criar um email de envio único no Adobe Campaign.
page-status-flag: nunca ativado
uuid: 74 c 7 ef 35-82 c 0-4 bc 4-b 1 f 6-8 e 74 fdcaea 3 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: por email
discoiquuid: b 27 e 0170-e 73 f -4782-8568-02927 fb 374 f 4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8f4c849adf1852d8a23c5ff5252da25c175faa84

---


# Creating an email{#creating-an-email}

You can create an email from a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity), from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page), or in the [marketing activity list](../../start/using/marketing-activities.md#about-marketing-activities). Também é possível criar emails de envio único e recorrentes a partir de um fluxo de trabalho.

1. Depois de começar a criar uma atividade de marketing por email, selecione o modelo que deseja usar.

   Por padrão, é possível escolher entre vários modelos para cada atividade de marketing. Isso permite pré-configurar determinados parâmetros de acordo com suas necessidades e também atribuir uma marca à sua entrega. For more on this, see [Managing templates](../../start/using/about-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >Os modelos de teste A/B/B estão ocultos por padrão. Check the boxes on the left side ( **[!UICONTROL Filter]** lateral panel) if you want to display them.

1. Insira as propriedades gerais do email. You can enter a name in the **Label** field and edit the ID. O nome da atividade e a ID aparecem na interface, mas não são visíveis para os destinatários da mensagem.

   Você pode adicionar uma descrição que o usuário pode visualizar no conteúdo da campanha.

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >Você pode criar seu e-mail em uma campanha principal na página inicial ou na lista de atividades de marketing. Selecione a partir das campanhas que já foram criadas.

1. Defina a meta da sua mensagem com base nos critérios do seu negócio. See [Managing profiles](../../audiences/using/about-profiles.md).

   Você também pode definir os perfis de teste que validarão a mensagem. See [Managing test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles).

   ![](assets/email_creation_3.png)

1. Define and personalize the message content, sender name and subject using the [Email Designer](../../designing/using/about-email-content-design.md#about-the-email-designer). For more on this, see [About email content design](../../designing/using/about-email-content-design.md).

   ![](assets/email_creation_4.png)

   Você pode criar sua mensagem diretamente usando um modelo de conteúdo predefinido ou usando o Dreamweaver ou o Adobe Experience Manager. Se não se sentir como um designer, você também pode carregar um conteúdo que foi preparado para você ou importar um conteúdo existente de um URL. See [Selecting an existing content](../../designing/using/selecting-an-existing-content.md).

1. Visualize sua mensagem. See [Previewing messages](../../sending/using/previewing-messages.md).
1. Confirme a criação do email.

   >[!NOTE]
   >
   >Para salvar seu email, primeiro faça algumas edições no conteúdo. If you click **[!UICONTROL Cancel]** at this point, you will not complete the wizard and your email will not be created.

   O painel de e-mail é exibido. It allows you to check your message and [prepare the send](../../sending/using/preparing-the-send.md).

   The **[!UICONTROL Edit properties]** button in the upper-right corner allows you to edit the properties of the email. Por exemplo, você pode configurar o email para que sua etiqueta seja calculada no tempo de preparação da entrega. Available parameters are listed in [this section](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. Programe o envio. See [Scheduling messages](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. Prepare sua mensagem para analisar sua meta. See [Preparing the send](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >Você pode definir regras globais de esgotamento entre canais que excluirão automaticamente os perfis substituídos das campanhas. For more on this, see [Fatigue rules](../../administration/using/fatigue-rules.md).

1. Envie testes para verificar e validar a mensagem e monitorar a renderização da caixa de entrada. See [Sending proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).

   ![](assets/bat_select.png)

1. Envie a mensagem e verifique sua entrega através do painel de mensagens e logs. See [Sending messages](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. Meça o impacto da sua mensagem com os relatórios de entrega. For more on reporting, see [this section](../../reporting/using/about-dynamic-reports.md).

**Tópicos relacionados**:

* [Criação de](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-email-from-homepage-feature-video-use.html) um vídeo por email
* [Criar um guia passo a passo personalizado e](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GettingStartedEmail.html) personalizado
* [Vídeo de integração](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html) do Adobe Campaign e Dreamweaver
* [Integração com o Adobe Experience Manager](../../integrating/using/integrating-with-experience-manager.md)

