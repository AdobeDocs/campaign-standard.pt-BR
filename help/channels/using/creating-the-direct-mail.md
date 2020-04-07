---
title: Criação do correio direto
description: Siga estas etapas para criar um delivery de mala direta no Adobe Campaign.
page-status-flag: never-activated
uuid: 3b1365c4-4ea1-4434-818b-05ff0c9b42c1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 5b02227f-9438-4001-bc2f-3d8661d173b3
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 155ed7e50e207e4c4dc0569e5e96b24e712e4be8

---


# Criação do correio direto{#creating-the-direct-mail}

A criação de um delivery de mala direta é muito semelhante à criação de um email comum. As etapas a seguir descrevem a configuração que é específica para esse canal. Consulte [Criação de um email](../../channels/using/creating-an-email.md) para obter mais informações sobre outras opções.

1. Crie um novo delivery de mala direta. Você pode criar um a partir do [home page](../../start/using/interface-description.md#home-page)Adobe Campaign, em uma [campanha](../../start/using/marketing-activities.md#creating-a-marketing-activity) ou em uma lista [de](../../start/using/programs-and-campaigns.md#creating-a-campaign)atividade de marketing.

   >[!NOTE]
   >
   >Você também pode adicionar uma atividade de mala direta em um fluxo de trabalho. For more on this, refer to the [Workflows](../../automating/using/direct-mail-delivery.md) guide.

   ![](assets/direct_mail_1.png)

1. Escolha o modelo pronto para uso **[!UICONTROL Direct mail]** ou um de seus próprios modelos. Para obter mais informações sobre modelos, consulte a seção [Gerenciamento de modelos](../../start/using/marketing-activity-templates.md) .

   ![](assets/direct_mail_2.png)

1. Insira as propriedades gerais do delivery.

   ![](assets/direct_mail_3.png)

1. Defina a audiência que deseja incluir no arquivo de extração, bem como os perfis de teste e captura. See [Defining the direct mail audience](../../channels/using/defining-the-direct-mail-audience.md).

   ![](assets/direct_mail_4.png)

   >[!NOTE]
   >
   >A definição da audiência é muito semelhante à definição de uma audiência de email comum. Consulte [Criação de audiências](../../audiences/using/creating-audiences.md).

1. Edite o conteúdo do arquivo: colunas a serem incluídas para cada perfil, estrutura de arquivos, cabeçalho e rodapé. See [Defining the direct mail content](../../channels/using/defining-the-direct-mail-content.md).

   ![](assets/direct_mail_5.png)

1. Clique na **[!UICONTROL Schedule]** seção do painel do delivery para definir a data de contato. Para a publicidade endereçada, a data de contato é obrigatória. Para obter mais informações, consulte [Agendamento do envio](../../sending/using/about-scheduling-messages.md).

   ![](assets/direct_mail_8.png)

1. Se você tiver adicionado perfis de teste (consulte [Adicionar perfis](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)de teste e armadilha), poderá testar o delivery antes de preparar o arquivo final. Ele permite que você crie um arquivo de amostra contendo apenas os perfis de teste selecionados.

   Clique em **[!UICONTROL Test]** para gerar o arquivo de amostra. Clique em **[!UICONTROL Summary]**, no canto superior esquerdo e selecione **[!UICONTROL Proofs]**. Na parte esquerda da tela, selecione a prova e clique em **[!UICONTROL Download file]**.

   >[!NOTE]
   >
   >A **[!UICONTROL Export]** função é necessária para permitir que o Adobe Campaign exporte o arquivo e disponibilize-o para download. Entre em contato com o administrador.

   ![](assets/direct_mail_19.png)

1. Depois de definir o conteúdo do delivery, a data de audiência e de contato, clique no **[!UICONTROL Prepare]** botão, no painel do delivery.

   ![](assets/direct_mail_16.png)

   Regras de tipologia são aplicadas. Por exemplo, todos os endereços postais não especificados são excluídos do público alvo. É por isso que você precisa verificar se marcou a **[!UICONTROL Address specified]** caixa nas informações dos perfis (consulte [Recomendações](../../channels/using/about-direct-mail.md#recommendations)). Se você tiver definido uma regra **[!UICONTROL Maximum volume of message]** nas propriedades de mala direta ou no nível do modelo, ela também será aplicada aqui.

   ![](assets/direct_mail_25.png)

   >[!NOTE]
   >
   >Você pode definir regras de fadiga globais entre canais que excluirão automaticamente perfis supersolacionados do campanha. Consulte Regras de [fadiga](../../sending/using/fatigue-rules.md).

1. Clique em **[!UICONTROL Explore file]** para pré-visualização nas primeiras 100 linhas do arquivo.

   ![](assets/direct_mail_18.png)

   O arquivo completo pode ser baixado localmente na parte esquerda da tela. Baixar o arquivo gera uma entrada de registro no **[!UICONTROL Export audits]** menu. Para obter mais informações sobre auditorias de exportação, consulte a seção [Auditando exportações](../../administration/using/auditing-export-logs.md) .

   >[!NOTE]
   >
   >A **[!UICONTROL Export]** função é necessária para permitir que o Adobe Campaign exporte o arquivo e disponibilize-o para download. Entre em contato com o administrador.

   Se precisar alterar o conteúdo do delivery, basta clicar no **[!UICONTROL Regenerate file]** botão para levar a alteração em consideração. Não precisa passar pela preparação de novo.

   ![](assets/direct_mail_21.png)

1. Para confirmar que o arquivo é final, clique em **[!UICONTROL Confirm]** no painel do delivery.

   ![](assets/direct_mail_20.png)

Agora você está pronto para enviar o arquivo de extração para seu provedor de mala direta. Para isso, você tem várias opções:

* Envie-o por email normal, com o arquivo anexado
* Envie-o por Campanha: execute seu email direto dentro de um [fluxo de trabalho](../../automating/using/direct-mail-delivery.md) de campanha e adicione um **[!UICONTROL Transfer file]** para enviar o arquivo via FTP, por exemplo. Consulte [Transferir arquivo](../../automating/using/transfer-file.md).

O provedor recupera a lista de endereços incorretos e envia essas informações para o Adobe Campaign que automaticamente faz a lista negra dos endereços incorretos. See [Return to sender](../../channels/using/return-to-sender.md).
