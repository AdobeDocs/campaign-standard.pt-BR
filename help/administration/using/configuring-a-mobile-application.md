---
title: Configurar um aplicativo móvel
description: Descubra como configurar o Adobe Campaign para enviar notificações por push ou mensagens no aplicativo usando SDK V4 ou Experience Platform SDK.
page-status-flag: never-activated
uuid: 63e1476a-7875-4f48-ba9e-97f1a0007e42
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 2a14500f-5ede-4131-8b1a-b7fd65b7e3aa
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f4f09556fed8c3cca44a72ac6dfeb280379d58c3
workflow-type: tm+mt
source-wordcount: '1344'
ht-degree: 2%

---


# Configurar um aplicativo móvel{#configuring-a-mobile-application}

## Configuração de um aplicativo móvel usando os SDKs da plataforma Adobe Experience {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>A notificação por push e as implementações no aplicativo devem ser executadas por usuários especialistas. Se precisar de auxílio, entre em contato com seu executivo de conta da Adobe ou com os parceiros de serviços Professional.

Para enviar notificações por push e mensagens no aplicativo com o aplicativo Experience Platform SDK, um aplicativo móvel deve ser configurado no Adobe Experience Platform Experience Platform Experience Platform Launch e configurado no Adobe Campaign.

Para obter mais informações sobre o recurso obsoleto SDKs da versão 4 do Mobile, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4-deprecated.html).

Depois que um aplicativo móvel é configurado, você pode recuperar os dados de PII coletados para criar ou atualizar perfis do banco de dados. Para obter mais informações, consulte esta seção: [Criação e atualização de informações do perfil com base em dados](../../channels/using/updating-profile-with-mobile-app-data.md)do aplicativo móvel.

Para saber mais sobre os diferentes casos de uso de dispositivos móveis compatíveis com o Adobe Campaign Standard usando os SDKs da plataforma Adobe Experience, consulte esta [página](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html).

Para concluir a configuração, conclua as seguintes etapas:

1. No Adobe Campaign, verifique se você pode acessar o seguinte:
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**
   Caso contrário, entre em contato com a equipe de sua conta.

1. Verifique se o usuário tem as permissões necessárias no Adobe Campaign Standard e no Experience Platform Launch.
   * No Adobe Campaign Standard, verifique se o usuário IMS faz parte dos Perfis de Produto de Usuário Padrão e Administrador. Essa etapa permite que o usuário faça logon no Adobe Campaign Standard, navegue até a página do aplicativo móvel Experience Platform SDK e visualização as propriedades do aplicativo móvel que você criou no Experience Platform Launch.

   * No Experience Platform Launch, verifique se o usuário do IMS faz parte de um perfil de produto Experience Platform Launch.
Essa etapa permite que o usuário faça logon no Experience Platform Launch para criar e visualização às propriedades. Para obter mais informações sobre perfis de produtos no Experience Platform Launch, consulte Criar seu perfil de produtos. No perfil do produto, não deve haver permissões definidas na empresa ou nas propriedades, mas o usuário ainda pode fazer logon.
   Para concluir tarefas adicionais como instalar uma extensão, publicar um aplicativo, configurar ambientes e assim por diante, é necessário definir permissões no perfil do produto.

1. No Experience Platform Launch, crie um **[!UICONTROL Mobile property]**. Para obter mais informações, consulte [Configurar uma propriedade](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)móvel.

1. No Experience Platform Launch, clique na **[!UICONTROL Extensions]** guia, vá até **[!UICONTROL Catalog]** e pesquise a **[!UICONTROL Adobe Campaign Standard]** extensão. Para obter mais informações, consulte [Adobe Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).

1. Para suportar casos de uso de localização no Campaign Standard, instale a **[!UICONTROL Places]** extensão e a **[!UICONTROL Places Monitor]** extensão.
   * Instale a **[!UICONTROL Places]** extensão no Experience Platform Launch. Consulte esta [página](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/places-extension.html).
   * Instale a **[!UICONTROL Places Monitor]** extensão no Experience Platform Launch. Consulte esta [página](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)

1. No Adobe Campaign Standard, configure a propriedade móvel que você criou no Experience Platform Launch. Consulte [Configuração do aplicativo Adobe Experience Platform Launch no Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Adicione a configuração específica do canal à configuração do aplicativo móvel.
Para obter mais informações, consulte Configuração do aplicativo específico para o [Canal](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Se necessário, você pode excluir sua propriedade Experience Platform Launch.
Para obter mais informações, consulte [Excluindo seu aplicativo](../../administration/using/configuring-a-mobile-application.md#delete-app)Experience Platform Launch.

## Sincronizar o aplicativo móvel AEPSDK do fluxo de trabalho técnico do Launch {#aepsdk-workflow}

>[!IMPORTANT]
>
>Este recurso é um recurso beta no Adobe Campaign a partir da versão 20.3. Você precisará enviar um ticket para o Atendimento ao cliente da Adobe (diretamente ou por meio de seu contato com a Adobe) para que o fluxo de trabalho **[!UICONTROL sync Mobile app AEPSDK from Launch]** técnico seja ativado na instância do Adobe Campaign.

Depois de criar e configurar sua propriedade móvel no Experience Platform Launch, o fluxo de trabalho **[!UICONTROL Sync Mobile app AEPSDK from Launch]** técnico sincronizará as propriedades móveis do Adobe Launch importadas no Adobe Campaign Standard.

Por padrão, o fluxo de trabalho técnico start a cada 15 minutos. Se necessário, pode ser reiniciado manualmente:

1. No Adobe Campaign Standard, no menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.
1. Abra o **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]** fluxo de trabalho.

   ![](assets/launch_10.png)

1. Clique na **[!UICONTROL Scheduler]** atividade.

1. Selecione **[!UICONTROL Immediate execution]**.

   ![](assets/launch_11.png)

Seu fluxo de trabalho agora reiniciará e sincronizará as propriedades móveis do Adobe Launch importadas no Adobe Campaign Standard.

## Configuração do aplicativo Adobe Experience Platform Launch no Adobe Campaign {#set-up-campaign}

Para usar uma propriedade móvel do Experience Platform Launch no Campaign, também é necessário configurar essa propriedade no Adobe Campaign. No Adobe Campaign, verifique se o usuário IMS faz parte dos Perfis de Produto Padrão de Usuário e Administrador.

Para os usuários com o sinalizador de recurso de fluxo de trabalho técnico do aplicativo Sincronizar AEPSDK do aplicativo móvel do Launch ativado, você precisará aguardar a execução do fluxo de trabalho técnico e sincronizar a propriedade Launch mobile com o Adobe Campaign. Em seguida, você pode configurá-lo no Adobe Campaign.

Para obter mais informações sobre Sincronizar o aplicativo móvel AEPSDK do sinalizador de recurso de fluxo de trabalho técnico do Launch, consulte esta [seção](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow).

>[!NOTE]
>
>Por padrão, os administradores com a unidade organizacional definida como TODOS podem editar o aplicativo móvel.

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/launch.png)

1. Selecione o aplicativo móvel que você criou no Experience Platform Launch.
Deve **[!UICONTROL Property Status]** ser **[!UICONTROL Ready to configure]**.

   >[!NOTE]
   >
   >Por padrão, para recuperar a lista de aplicativos móveis criados no Adobe Launch, o Campaign Standard usa o valor definido na opção NmsServer_URL para procurar propriedades correspondentes.
Em alguns casos, o ponto de extremidade de Campanha para um aplicativo móvel pode ser diferente daquele definido em NmsServer_URL. Nesse caso, defina o terminal na opção Launch_URL_Campanha. A Campanha usará o valor dessa opção para procurar as propriedades correspondentes no Adobe Launch.

   ![](assets/launch_4.png)

1. Você pode alterar a unidade organizacional do aplicativo móvel na **[!UICONTROL Access Authorization]** seção para limitar o acesso a esse aplicativo móvel a unidades específicas da organização. Para obter mais informações, consulte esta página.

   Aqui, o administrador pode atribuir unidades suborganizacionais selecionando-as no menu suspenso.

   ![](assets/launch_12.png)

1. Para fazer a conexão entre a Campaign e o Experience Platform Launch, clique em **[!UICONTROL Save]**.

1. Verifique se o status do aplicativo móvel foi alterado de **[!UICONTROL Ready to Configure]** para **[!UICONTROL Configured]**.

   Quando a extensão da Campanha Experience Platform Launch mostra que a chave foi configurada com êxito, você também pode verificar se a propriedade foi configurada com êxito na Campanha.

   ![](assets/launch_5.png)

1. Para que essa configuração tenha efeito, as alterações precisam ser publicadas no Experience Platform Launch.

   Para obter mais informações, consulte [Publicar configuração](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration).

## Configuração do aplicativo específico do Canal no Adobe Campaign {#channel-specific-config}

Seu aplicativo móvel agora está pronto para ser usado na Campanha para notificações por push ou delivery no aplicativo. Agora você pode configurá-lo ainda mais se necessário para criar eventos que acionarão suas mensagens no aplicativo e/ou fazer upload de certificados de push.

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

1. Selecione o aplicativo móvel que você criou e configurou no Experience Platform Launch.

1. Na **[!UICONTROL Mobile application properties]** guia, é possível adicionar eventos que estão disponíveis no aplicativo móvel para as mensagens no aplicativo.

1. Para configurar seus eventos, clique em **[!UICONTROL Create Element]**.

   ![](assets/launch_6.png)

1. Digite um nome e uma descrição.

   ![](assets/launch_7.png)

1. Clique em **[!UICONTROL Add]**.

   Seu evento agora está disponível na guia Acionadores quando você cria uma mensagem no aplicativo. Para obter mais informações, consulte [Preparação e envio de uma mensagem](../../channels/using/preparing-and-sending-an-in-app-message.md)no aplicativo.

1. Na **[!UICONTROL Device-specific settings]** seção de um painel de aplicativo móvel, para cada dispositivo, forneça os detalhes do aplicativo, incluindo o certificado para iOS e a chave do servidor para Android.

   Após o upload do certificado, uma mensagem notifica que o upload foi bem-sucedido e exibe a data de expiração do certificado.

   >[!NOTE]
   >
   >Depois de adicionar o certificado com êxito no Adobe Campaign Standard, não será mais possível alterar as configurações novamente, pois apenas uma plataforma APNS (produção ou caixa de proteção) pode ser adicionada ao aplicativo MCPNS.

   ![](assets/launch_8.png)

1. Clique na **[!UICONTROL Mobile application subscribers]** guia para ver uma lista de assinantes e outras informações sobre esses assinantes, por exemplo, se eles opt out de suas notificações.

## Excluindo seu aplicativo Adobe Experience Platform Launch {#delete-app}

A exclusão do aplicativo Experience Platform Launch não pode ser revertida.

>[!CAUTION]
>
>A exclusão do aplicativo Experience Platform Launch não pode ser revertida.

Para excluir o aplicativo Experience Platform Launch, conclua as etapas em [Excluir propriedades](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch)móveis.

Depois que seu aplicativo for excluído, no Adobe Campaign, verifique se o status da Propriedade do aplicativo foi atualizado corretamente para Excluído no Launch.

Ao clicar em seu aplicativo no Adobe Campaign, você pode optar por remover completamente esse aplicativo do Adobe Campaign, clicando em Excluir da Campanha.

    ![](assets/launch_9.png)
