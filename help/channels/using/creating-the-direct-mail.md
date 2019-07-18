---
title: Criação do mala direta
seo-title: Criação do mala direta
description: Criação do mala direta
seo-description: Siga estas etapas para criar uma entrega de email direta no Adobe Campaign.
page-status-flag: nunca ativado
uuid: 3 b 1365 c 4-4 ea 1-4434-818 b -05 ff 0 c 9 b 42 c 1
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: direta
discoiquuid: 5 b 02227 f -9438-4001-bc 2 f -3 d 8661 d 173 b 3
context-tags: entrega, directmailcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Creating the direct mail{#creating-the-direct-mail}

A criação de uma entrega de email direta é muito semelhante à criação de um e-mail normal. As etapas a seguir descrevem a configuração que é específica para este canal. Refer to [Creating an email](../../channels/using/creating-an-email.md) for more information on other options.

1. Crie uma nova entrega de email direta. You can create one from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page), in a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity) or in a [marketing activity list](../../start/using/programs-and-campaigns.md#creating-a-campaign).

   >[!NOTE]
   >
   >Você também pode adicionar uma atividade de mala direta em um fluxo de trabalho. For more on this, refer to the [Workflows](../../automating/using/direct-mail-delivery.md) guide.

   ![](assets/direct_mail_1.png)

1. Choose either the out-of-the-box **[!UICONTROL Direct mail]** template or one of your own templates. For more information on templates, refer to the [Managing templates](../../start/using/about-templates.md) section.

   ![](assets/direct_mail_2.png)

1. Insira as propriedades gerais da entrega.

   ![](assets/direct_mail_3.png)

1. Defina o público-alvo que deseja incluir no arquivo de extração, bem como os perfis de teste e trapping. See [Defining the direct mail audience](../../channels/using/defining-the-direct-mail-audience.md).

   ![](assets/direct_mail_4.png)

   >[!NOTE]
   >
   >A definição do público é muito semelhante à definição de um público-alvo normal de email. See [Creating audiences](../../audiences/using/creating-audiences.md).

1. Edite o conteúdo do arquivo: para incluir para cada perfil, estrutura de arquivos, cabeçalho e rodapé. See [Defining the direct mail content](../../channels/using/defining-the-direct-mail-content.md).

   ![](assets/direct_mail_5.png)

1. Click on the **[!UICONTROL Schedule]** section of the delivery dashboard to define the contact date. Para a mala direta, a data do contato é obrigatória. For more information, refer to [Scheduling the send](../../sending/using/about-scheduling-messages.md).

   ![](assets/direct_mail_8.png)

1. If you added test profiles (refer to [Adding test and trap profiles](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)), you can test your delivery before preparing the final file. Ele permite criar um arquivo de amostra contendo apenas os perfis de teste selecionados.

   Click on **[!UICONTROL Test]** to generate the sample file. Click on **[!UICONTROL Summary]**, in the top left corner, then select **[!UICONTROL Proofs]**. On the left part of the screen, select the proof and click on **[!UICONTROL Download file]**.

   >[!NOTE]
   >
   >The **[!UICONTROL Export]** role is required to allow Adobe Campaign to export the file and make it available for download. Entre em contato com o administrador.

   ![](assets/direct_mail_19.png)

1. Once you have defined your delivery content, audience and contact date, click on the **[!UICONTROL Prepare]** button, on the delivery dashboard.

   ![](assets/direct_mail_16.png)

   As regras de tipologia são aplicadas. Por exemplo, todos os endereços postais não especificados são excluídos do destino. This is why you need to make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information (see [Recommendations](../../channels/using/about-direct-mail.md#recommendations)). If you have defined a **[!UICONTROL Maximum volume of message]** in the direct mail properties or at the template level, it will also be applied here.

   ![](assets/direct_mail_25.png)

   >[!NOTE]
   >
   >Você pode definir regras globais de esgotamento entre canais que excluirão automaticamente os perfis substituídos das campanhas. See [Fatigue rules](../../administration/using/fatigue-rules.md).

1. Click on **[!UICONTROL Explore file]** to preview the first 100 lines of the file.

   ![](assets/direct_mail_18.png)

   O arquivo completo é acessível para download local na parte esquerda da tela. Downloading the file generates a log entry in the **[!UICONTROL Export audits]** menu. For more information on export audits, refer to the [Auditing exports](../../administration/using/auditing-export-logs.md) section.

   >[!NOTE]
   >
   >The **[!UICONTROL Export]** role is required to allow Adobe Campaign to export the file and make it available for download. Entre em contato com o administrador.

   If you need to change the delivery content, you only have to click on the **[!UICONTROL Regenerate file]** button to take the change into account. Não é necessário passar pela preparação novamente.

   ![](assets/direct_mail_21.png)

1. To confirm that the file is final, click on **[!UICONTROL Confirm]** in the delivery dashboard.

   ![](assets/direct_mail_20.png)

Agora você está pronto para enviar o arquivo de extração para o seu provedor de mala direta. Para isso, você tem várias opções:

* Envie-o por email regular, com o arquivo anexado
* Send it via Campaign: perform your direct mail within a campaign [workflow](../../automating/using/direct-mail-delivery.md) and add a **[!UICONTROL Transfer file]** to send the file via FTP for example. See [Transfer file](../../automating/using/transfer-file.md).

O provedor recupera a lista de endereços errôneos e envia essas informações para o Adobe Campaign, que lista automaticamente os endereços errôneos. See [Return to sender](../../channels/using/return-to-sender.md).
