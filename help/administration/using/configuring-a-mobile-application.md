---
title: Configurar um aplicativo para dispositivos móveis
description: Saiba como configurar o Adobe Campaign para enviar notificações por push ou mensagens no aplicativo usando o Experience Platform SDK
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 5f9a8e84-a362-42b6-8bd2-e5d56214c1db
source-git-commit: c1914c855011868c76debebbea87d7416faaf0dc
workflow-type: tm+mt
source-wordcount: '1309'
ht-degree: 2%

---

# Configurar um aplicativo para dispositivos móveis{#configuring-a-mobile-application}

## Configurar um aplicativo para dispositivos móveis usando SDKs do Adobe Experience Platform {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
> O Adobe Experience Platform Launch foi reformulado como um conjunto de tecnologias de coleção de dados na Adobe Experience Platform. Como resultado, várias alterações de terminologia foram implementadas na documentação do produto. Consulte o [seguinte documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=pt-BR){target="_blank"} para obter uma referência consolidada das alterações de terminologia.

Observe que as implementações de notificação por push e no aplicativo devem ser executadas por usuários especialistas. Para obter assistência, entre em contato com o executivo da sua conta da Adobe ou com o parceiro de serviços Professional.

Para enviar notificações por push e mensagens no aplicativo com o aplicativo Experience Platform SDK, um aplicativo para dispositivos móveis deve ser configurado na interface da Coleção de dados e no Adobe Campaign.

Depois que um aplicativo móvel é configurado, você pode recuperar os dados de PII coletados para criar ou atualizar perfis do banco de dados. Para obter mais informações, consulte esta seção: [Criar e atualizar informações de perfil com base nos dados do aplicativo móvel](../../channels/using/updating-profile-with-mobile-app-data.md).

Para saber mais sobre os diferentes casos de uso de publicação de conteúdo para dispositivos móveis com suporte no Adobe Campaign Standard usando os SDKs da Adobe Experience Platform, consulte esta [página](../../administration/using/supported-mobile-use-cases.md).

Para concluir a configuração, conclua as seguintes etapas:

1. No Adobe Campaign, acesse o seguinte:
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   Caso contrário, entre em contato com a equipe de conta.

1. Verifique se o usuário tem as permissões necessárias no Adobe Campaign Standard e nas tags na Adobe Experience Platform.

   * No Adobe Campaign Standard, verifique se o usuário do IMS faz parte dos Perfis de usuário padrão e de produto de administrador. Essa etapa permite que o usuário faça logon no Adobe Campaign Standard, navegue até a página do aplicativo móvel Experience Platform SDK e visualize as propriedades do aplicativo móvel que você criou na interface da Coleção de dados.

   * Na interface da Coleção de dados, verifique se o usuário do IMS faz parte de um perfil de produto do Experience Platform Launch.
Esta etapa permite que o usuário faça logon na interface da Coleção de dados para criar e exibir as propriedades. Para obter mais informações sobre perfis de produtos na Interface da Coleção de Dados, consulte [Criar perfil de produto](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/manage-permissions.html?lang=pt-BR#gain-admin-rights-for-a-tags-product-profile). No perfil do produto, não deve haver permissões definidas na empresa ou nas propriedades, mas o usuário ainda deve conseguir fazer logon.

   Para concluir tarefas adicionais, como instalar uma extensão, publicar um aplicativo, configurar ambientes e assim por diante, é necessário definir permissões no perfil do produto.

1. Na interface da Coleção de Dados, crie um **[!UICONTROL Mobile property]**. Para saber mais, consulte [Configurar uma propriedade móvel](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property).

1. Na interface da Coleção de Dados, clique na guia **[!UICONTROL Extensions]**, vá para **[!UICONTROL Catalog]** e procure a extensão **[!UICONTROL Adobe Campaign Standard]**. Para obter mais informações, consulte [Adobe Campaign Standard](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard).

1. Para oferecer suporte a casos de uso de localização no Campaign Standard, instale a extensão **[!UICONTROL Places]** na interface da Coleção de Dados. Consulte esta [página](https://developer.adobe.com/client-sdks/solution/places).

1. No Adobe Campaign Standard, configure a propriedade móvel que você criou na interface da coleção de dados. Consulte [Configurando seu aplicativo do Adobe Experience Platform Launch no Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Adicione a configuração específica do canal à configuração do aplicativo móvel.
Para saber mais, consulte [Configuração do aplicativo específico do canal no Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Se necessário, você pode excluir a propriedade da tag.
Para obter mais informações, consulte [Excluindo seu aplicativo](../../administration/using/configuring-a-mobile-application.md#delete-app).

## Sincronizar AEPSDK do aplicativo móvel a partir do fluxo de trabalho técnico do Launch {#aepsdk-workflow}

Depois de criar e configurar sua propriedade móvel na interface da Coleção de dados, o fluxo de trabalho técnico do **[!UICONTROL Sync Mobile app AEPSDK from Launch]** sincronizará as propriedades móveis de tag importadas no Adobe Campaign Standard.

Por padrão, o fluxo de trabalho técnico é iniciado a cada 15 minutos. Se necessário, ele poderá ser reiniciado manualmente:

1. No Adobe Campaign Standard, no menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.
1. Abra o fluxo de trabalho **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]**.

   ![](assets/launch_10.png)

1. Clique na atividade **[!UICONTROL Scheduler]**.

1. Selecione **[!UICONTROL Immediate execution]**.

   ![](assets/launch_11.png)

Seu fluxo de trabalho agora reiniciará e sincronizará as propriedades de dispositivos móveis de tag importadas no Adobe Campaign Standard.

## Configuração do aplicativo no Adobe Campaign {#set-up-campaign}

Para usar uma propriedade de tag móvel no Campaign, você também deve configurar essa propriedade no Adobe Campaign. No Adobe Campaign, verifique se o usuário do IMS faz parte dos Perfis de usuário padrão e de produto de administrador.

Aguarde até que o fluxo de trabalho técnico seja executado e sincronize a propriedade móvel da tag com a Adobe Campaign. Em seguida, você pode configurá-lo no Adobe Campaign.

Para obter mais informações sobre o aplicativo móvel de sincronização AEPSDK do fluxo de trabalho técnico do Launch, consulte esta [seção](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow).

>[!NOTE]
>
>Por padrão, os administradores com a unidade organizacional definida como ALL podem editar o aplicativo móvel.

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/launch.png)

1. Selecione o aplicativo móvel criado na interface da coleção de dados.
Seu **[!UICONTROL Property Status]** deve ser **[!UICONTROL Ready to configure]**.

   >[!NOTE]
   >
   >Por padrão, para recuperar a lista de aplicativos móveis criados na interface da Coleção de dados, o Campaign Standard usa o valor definido na opção NmsServer_URL para procurar propriedades correspondentes.
   >
   >Em alguns casos, o endpoint do Campaign para um aplicativo móvel pode ser diferente daquele definido em NmsServer_URL. Nesse caso, defina o ponto de extremidade na opção `Launch_URL_Campaign`. O Campaign usará o valor dessa opção para procurar propriedades correspondentes na interface da Coleção de dados.

   ![](assets/launch_4.png)

1. Você pode alterar a unidade organizacional do aplicativo móvel na seção **[!UICONTROL Access Authorization]** para limitar o acesso a esse aplicativo móvel a unidades organizacionais específicas. Para obter mais informações, consulte esta página.

   Aqui, o administrador pode atribuir unidades sub-organizacionais selecionando-as na lista suspensa.

   ![](assets/launch_12.png)

1. Para fazer a conexão entre o Campaign e as tags na Adobe Experience Platform, clique em **[!UICONTROL Save]**.

1. Verifique se o status do aplicativo móvel mudou de **[!UICONTROL Ready to Configure]** para **[!UICONTROL Configured]**.

   Quando a extensão do Campaign mostrar que a pkey foi configurada com êxito, você também poderá verificar se a propriedade foi configurada com êxito no Campaign.

   ![](assets/launch_5.png)

1. Para que essa configuração tenha efeito, as alterações precisam ser publicadas na interface da Coleção de dados.

   Para obter mais informações, consulte [Configuração de publicação](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration)

## Configuração do aplicativo específico do canal no Adobe Campaign {#channel-specific-config}

Seu aplicativo móvel agora está pronto para ser usado na notificação por push ou nos deliveries no aplicativo do Campaign. Agora você pode configurá-lo ainda mais, se necessário, para criar eventos que acionarão suas mensagens no aplicativo e/ou carregarão certificados Push.

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

1. Selecione o aplicativo para dispositivos móveis criado e configurado na interface da Coleção de dados.

1. Na guia **[!UICONTROL Mobile application properties]**, você pode começar a adicionar eventos que estão disponíveis no aplicativo móvel para suas mensagens no aplicativo.

1. Para configurar seus eventos, clique em **[!UICONTROL Create Element]**.

   ![](assets/launch_6.png)

1. Digite um nome e uma descrição.

   ![](assets/launch_7.png)

1. Clique em **[!UICONTROL Add]**.

   Seu evento agora está disponível na guia Acionadores ao criar uma mensagem no aplicativo. Para obter mais informações, consulte [Preparando e enviando uma mensagem no aplicativo](../../channels/using/preparing-and-sending-an-in-app-message.md).

1. Na seção **[!UICONTROL Device-specific settings]** de um painel de aplicativo móvel, para cada dispositivo, forneça os detalhes do aplicativo.

   +++ Para iOS

   Informe os seguintes detalhes do aplicativo:

   * **ID do Aplicativo (ID do Pacote iOS)**: consulte a [documentação do Apple](https://developer.apple.com/documentation/appstoreconnectapi/bundle_ids){target="_blank"} para obter mais informações sobre a ID do Pacote.
   * **Arquivo de Certificado (P8) do iOS**: arraste e solte sua chave de autenticação .p8. Para obter instruções sobre como gerar o arquivo de autenticação .p8, consulte sua [conta de desenvolvedor do Apple](https://developer.apple.com/account/ios/authkey/create){target="_blank"}.
   * **ID da Chave**: consulte a [documentação da Apple](https://developer.apple.com/help/account/manage-keys/get-a-key-identifier/){target="_blank"} para obter mais informações sobre a ID da Chave.
   * **iOS Team ID**: consulte a [documentação do Apple](https://developer.apple.com/help/account/manage-your-team/locate-your-team-id/){target="_blank"} para obter mais informações sobre a iOS Team ID.

         ![](assets/mobile_app_ios_config.png)
     +++

   +++ Para Android

   Informe os seguintes detalhes do aplicativo:

   * **ID do Aplicativo (Nome do Pacote Android)**: consulte a [documentação do Android](https://support.google.com/admob/answer/9972781?hl=en#:~:text=The%20package%20name%20of%20an,supported%20third%2Dparty%20Android%20stores){target="_blank"} para obter mais informações sobre o nome do Pacote.
   * **Arquivo de chave privada (Json) do Android**: arraste e solte seu arquivo de chave privada .json. Para obter instruções sobre como gerar o arquivo de chave privada .json, consulte a [Documentação do desenvolvedor para Firebase](https://firebase.google.com/docs/admin/setup#initialize_the_sdk_in_non-google_environments){target="_blank"}.

     ![](assets/mobile_app_android_config.png)
   +++

1. Depois que o certificado for carregado, uma mensagem notificará que o upload foi bem-sucedido e exibirá a data de expiração do certificado.

1. Clique na guia **[!UICONTROL Mobile application subscribers]** para ver uma lista de assinantes e outras informações sobre esses assinantes, por exemplo, se eles optaram por não receber suas notificações.

## Excluindo seu aplicativo {#delete-app}

>[!CAUTION]
>
>A exclusão do aplicativo não pode ser revertida.

Para excluir seu aplicativo, conclua as etapas em [Excluindo propriedades móveis](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#deleting-mobile-properties-in-the-data-collection-ui).

Depois que o aplicativo for excluído, no Adobe Campaign, verifique se o status da Propriedade do aplicativo foi atualizado corretamente para Excluído no Launch.

Ao clicar no aplicativo no Adobe Campaign, é possível optar por remover completamente esse aplicativo do Adobe Campaign clicando em Excluir do Campaign.

![](assets/launch_9.png)
