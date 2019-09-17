---
title: Criação de um email
seo-title: Criação de um email
description: Criação de um email
seo-description: Siga estas etapas para criar um email de envio único no Adobe Campaign.
page-status-flag: nunca ativado
uuid: 74c7ef35-82c0-4bc4-b1f6-8e74fdcaea3c
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: canais
content-type: referência
topic-tags: mensagens de email
discoiquuid: b27e0170-e73f-4782-8568-02927fb374f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68d96b23f34f505c0a47a74a5e33bc3530fc4d72

---


# Criação de um email{#creating-an-email}

Você pode criar um email de uma [campanha](../../start/using/marketing-activities.md#creating-a-marketing-activity), da [página](../../start/using/interface-description.md#home-page)inicial do Adobe Campaign ou da lista [de atividades de](../../start/using/marketing-activities.md#about-marketing-activities)marketing. Também é possível criar emails recorrentes e de envio único a partir de um fluxo de trabalho.

1. Depois de começar a criar uma atividade de marketing por email, selecione o modelo que deseja usar.

   Por padrão, você pode escolher entre vários modelos para cada atividade de marketing. Isso permite pré-configurar certos parâmetros de acordo com suas necessidades e também atribuir uma marca à entrega. Para obter mais informações, consulte [Gerenciamento de modelos](../../start/using/about-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >Os modelos de teste A/B e de acompanhamento estão ocultos por padrão. Marque as caixas no lado esquerdo (painel **[!UICONTROL Filter]** lateral) se quiser exibi-las.

1. Insira as propriedades gerais do email. Você pode inserir um nome no campo **Rótulo** e editar a ID. O nome da atividade e sua ID são exibidos na interface, mas não são visíveis para os destinatários da mensagem.

   Você pode adicionar uma descrição que o usuário pode ver no conteúdo da campanha.

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >Você pode criar seu email em uma campanha principal a partir da página inicial ou da lista de atividades de marketing. Selecione-a nas campanhas que já foram criadas.

1. Defina a meta da sua mensagem com base em seus critérios comerciais. Consulte [Gerenciamento de perfis](../../audiences/using/about-profiles.md).

   Você também pode definir os perfis de teste que validarão a mensagem. Consulte [Gerenciamento de perfis](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles)de teste.

   ![](assets/email_creation_3.png)

1. Defina e personalize o conteúdo da mensagem, o nome do remetente e o assunto usando o [Email Designer](../../designing/using/overview.md). Para obter mais informações, consulte [Sobre design](../../designing/using/overview.md)de conteúdo de email.

   ![](assets/email_creation_4.png)

   Você pode projetar sua mensagem diretamente usando um modelo de conteúdo predefinido ou usando o Dreamweaver ou o Adobe Experience Manager. Se você não se sentir um designer, também poderá carregar um conteúdo que foi preparado para você ou importar um conteúdo existente de um URL. Consulte [Seleção de um conteúdo](../../designing/using/using-existing-content.md)existente.

1. Visualize sua mensagem. Consulte [Visualizar mensagens](../../sending/using/previewing-messages.md).
1. Confirme a criação do email.

   >[!NOTE]
   >
   >Para salvar seu email, é necessário primeiro fazer algumas edições no conteúdo. Se você clicar **[!UICONTROL Cancel]** nesse ponto, não concluirá o assistente e seu email não será criado.

   O painel de email é exibido. Permite que você verifique sua mensagem e [prepare o envio](../../sending/using/preparing-the-send.md).

   O **[!UICONTROL Edit properties]** botão no canto superior direito permite que você edite as propriedades do email. Por exemplo, é possível configurar o email para que seu rótulo seja calculado no momento da preparação da entrega.  Os parâmetros disponíveis estão listados [nesta seção](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. Agende o envio. Consulte [Agendamento de mensagens](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. Prepare sua mensagem para analisar sua meta. Consulte [Preparação do envio](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >Você pode definir regras de fadiga globais entre canais que excluirão automaticamente perfis supersolacionados de campanhas. Para obter mais informações, consulte Regras [de](../../administration/using/fatigue-rules.md)fadiga.

1. Envie provas para verificar e validar a mensagem e monitorar a renderização da caixa de entrada. Consulte [Enviar prova](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).

   ![](assets/bat_select.png)

1. Envie a mensagem e verifique sua entrega pelo painel de mensagens e registros. Consulte [Enviando mensagens](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. Meça o impacto de sua mensagem com os relatórios de entrega. Para obter mais informações sobre relatórios, consulte [esta seção](../../reporting/using/about-dynamic-reports.md).

**Tópicos** relacionados:

* [Criação de um vídeo de email](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-email-from-homepage-feature-video-use.html)
* [Criação de um guia passo a passo de email](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GettingStartedEmail.html) personalizado
* [Vídeo de integração](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html) do Adobe Campaign e do Dreamweaver
* [Integração com o Adobe Experience Manager](../../integrating/using/integrating-with-experience-manager.md)

