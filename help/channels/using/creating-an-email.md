---
solution: Campaign Standard
product: campaign
title: Criar email
description: Siga estas etapas para criar um email de envio único no Adobe Campaign.
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: Profissional
level: Iniciante
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 20%

---


# Criar email{#creating-an-email}

Você pode criar um email a partir de uma [campanha](../../start/using/marketing-activities.md#creating-a-marketing-activity), a partir da [página inicial](../../start/using/interface-description.md#home-page) do Adobe Campaign ou na [lista de atividades de marketing](../../start/using/marketing-activities.md#about-marketing-activities). Também é possível criar emails recorrentes e de envio único a partir de um fluxo de trabalho.

![](assets/do-not-localize/how-to-video.png) [Descubra este recurso no vídeo](#video)

1. Depois de começar a criar uma atividade de marketing por email, selecione o template que deseja usar.

   Por padrão, você pode escolher entre vários templates para cada atividade de marketing. Isso permite pré-configurar determinados parâmetros de acordo com suas necessidades e também atribuir uma marca ao delivery. Para obter mais informações, consulte [Gerenciamento de modelos](../../start/using/marketing-activity-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >Os modelos de teste A/B e de acompanhamento estão ocultos por padrão. Marque as caixas no lado esquerdo ( **[!UICONTROL Filter]** painel lateral) se desejar exibi-las.

1. Insira as propriedades gerais do email. Você pode inserir um nome no campo **Label** e editar a ID. O nome da atividade e sua ID são exibidos na interface, mas não são visíveis para os recipients da mensagem.

   É possível adicionar uma descrição que o usuário pode ver no conteúdo da campanha.

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >Você pode criar seu email em uma campanha principal a partir da página inicial ou da lista de atividades de marketing. Selecione-a nas campanhas que já foram criadas.

1. Defina o público-alvo da mensagem com base nos critérios da empresa. Consulte [Sobre perfis](../../audiences/using/about-profiles.md).

   Você também pode definir os perfis de teste que validarão a mensagem. Consulte [Gerenciamento de perfis de teste](../../audiences/using/managing-test-profiles.md).

   ![](assets/email_creation_3.png)

1. Defina e personalize o conteúdo da mensagem, o nome do remetente e o assunto usando o [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md). Para obter mais informações, consulte [Sobre design de conteúdo de email](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/email_creation_4.png)

   Você pode criar sua mensagem diretamente usando um modelo de conteúdo predefinido ou usando o Dreamweaver ou Adobe Experience Manager. Se você não se sentir um designer, também poderá carregar um conteúdo que foi preparado para você ou importar um conteúdo existente de um URL. Consulte [Seleção de conteúdo existente](../../designing/using/using-existing-content.md).

1. Visualizar sua mensagem. Consulte [Pré-visualização de mensagens](../../sending/using/previewing-messages.md).
1. Confirme a criação do email.

   >[!NOTE]
   >
   >Para salvar seu email, primeiro é necessário fazer algumas edições no conteúdo. Se você clicar em **[!UICONTROL Cancel]** nesse ponto, não concluirá o assistente e seu email não será criado.

   O painel de email é exibido. Ela permite verificar sua mensagem e [preparar o envio](../../sending/using/preparing-the-send.md).

   O botão **[!UICONTROL Edit properties]** no canto superior direito permite editar as propriedades do email. Você pode, por exemplo, configurar o email para que seu rótulo seja computado no momento da preparação do delivery.  Os parâmetros disponíveis são listados em [this section](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. Programe o envio. Consulte [Agendamento de mensagens](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. Prepare sua mensagem para analisar seu público-alvo. Consulte [Preparando o envio](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >Você pode definir regras de fadiga globais entre canais que excluirão automaticamente das campanhas os perfis com excesso de pedidos. Para obter mais informações, consulte [Regras de fadiga](../../sending/using/fatigue-rules.md).

1. Envie provas para verificar e validar a mensagem e monitorar a renderização da caixa de entrada. Consulte [Envio de prova](../../sending/using/sending-proofs.md).

   ![](assets/bat_select.png)

1. Envie a mensagem e verifique seu delivery pelo painel de mensagens e logs. Consulte [Envio de mensagens](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. Meça o impacto da mensagem com relatórios do delivery. Para obter mais informações sobre relatórios, consulte [esta seção](../../reporting/using/about-dynamic-reports.md).

**Tópicos relacionados**:

* [Criação de um guia passo a passo ](https://helpx.adobe.com/br/campaign/kb/acs-get-started-with-emails.html) de email personalizado
* [Integração entre Adobe Campaign e Dreamweaver](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)
* [Integração com o Adobe Experience Manager](../../integrating/using/integrating-with-experience-manager.md)

## Vídeo tutorial {#video}

Este vídeo mostra como criar um email.

>[!VIDEO](https://video.tv.adobe.com/v/23721?quality=12)

Os vídeos de instruções adicionais do Campaign Standard estão disponíveis [aqui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=pt-BR).
