---
title: Configurar um aplicativo para dispositivos móveis
description: Saiba como configurar o Adobe Campaign para enviar notificações por push ou mensagens no aplicativo usando o Experience Platform SDK
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 5f9a8e84-a362-42b6-8bd2-e5d56214c1db
source-git-commit: 884cd5e9c09aa85e744ca06b202eb46f73a33a76
workflow-type: tm+mt
source-wordcount: '1260'
ht-degree: 4%

---

# Configurar um aplicativo para dispositivos móveis{#configuring-a-mobile-application}

## Configurar um aplicativo móvel usando SDKs do Adobe Experience Platform {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
> A Adobe Experience Platform Launch foi reformulada como um conjunto de tecnologias de coleta de dados no Adobe Experience Platform. Como resultado, várias alterações de terminologia foram implementadas na documentação do produto. Consulte a [documento a seguir](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html) para uma referência consolidada das alterações de terminologia.

Observe que a notificação por push e as implementações no aplicativo devem ser executadas por usuários especialistas. Para obter ajuda, entre em contato com o executivo da sua conta Adobe ou com o parceiro de serviços Professional.

Para enviar notificações por push e mensagens no aplicativo com o aplicativo SDK do Experience Platform, um aplicativo para dispositivos móveis deve ser configurado na interface do usuário da coleta de dados e configurado no Adobe Campaign.

Depois que um aplicativo móvel é configurado, você pode recuperar os dados PII coletados para criar ou atualizar perfis do banco de dados. Para obter mais informações, consulte esta seção: [Criação e atualização de informações de perfil com base em dados de aplicativo móvel](../../channels/using/updating-profile-with-mobile-app-data.md).

Para saber mais sobre os diferentes casos de uso de dispositivos móveis compatíveis com o Adobe Campaign Standard usando os SDKs do Adobe Experience Platform, consulte esta seção [página](../../administration/using/supported-mobile-use-cases.md).

Para concluir a configuração, conclua as seguintes etapas:

1. No Adobe Campaign, verifique se você pode acessar o seguinte:
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   Caso contrário, entre em contato com a equipe de conta.

1. Verifique se o usuário tem as permissões necessárias no Adobe Campaign Standard e as tags no Adobe Experience Platform.
   * No Adobe Campaign Standard, verifique se o usuário IMS faz parte dos Perfis de produto padrão do usuário e do administrador. Essa etapa permite que o usuário faça logon no Adobe Campaign Standard, navegue até a página do aplicativo móvel SDK do Experience Platform e exiba as propriedades do aplicativo móvel que você criou na interface do usuário da coleta de dados.

   * Na interface do usuário da coleta de dados, verifique se o usuário IMS faz parte de um perfil de produto do Experience Platform Launch.
Essa etapa permite que o usuário faça logon na interface do usuário da coleta de dados para criar e exibir as propriedades. Para obter mais informações sobre perfis de produtos na interface do usuário da Coleta de dados, consulte [Criar o perfil de produto](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/manage-permissions.html?lang=en#gain-admin-rights-for-a-tags-product-profile). No perfil do produto, não deve haver permissões definidas na empresa ou nas propriedades, mas o usuário ainda deve conseguir fazer logon.

   Para concluir tarefas adicionais como instalar uma extensão, publicar um aplicativo, configurar ambientes e assim por diante, você precisa definir permissões no perfil do produto.

1. Na interface do usuário da coleta de dados, crie um **[!UICONTROL Mobile property]**. Para saber mais, consulte [Configurar uma propriedade móvel](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).

1. Na interface do usuário da coleta de dados, clique no botão **[!UICONTROL Extensions]** guia , vá para **[!UICONTROL Catalog]** e pesquise por **[!UICONTROL Adobe Campaign Standard]** extensão. Para obter mais informações, consulte [Adobe Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).

1. Para suportar casos de uso de localização no Campaign Standard, instale o **[!UICONTROL Places]** na interface do usuário da Coleta de dados. Consulte esta [página](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html).

1. No Adobe Campaign Standard, configure a propriedade móvel que você criou na interface do usuário da coleta de dados. Consulte [Configuração do aplicativo Adobe Experience Platform Launch no Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Adicione a configuração específica do canal à configuração do aplicativo móvel.
Para saber mais, consulte [Configuração do aplicativo específico do canal no Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Se necessário, é possível excluir a propriedade da tag.
Para obter mais informações, consulte [Excluindo seu aplicativo](../../administration/using/configuring-a-mobile-application.md#delete-app).

## Sincronizar o AEPSDK do aplicativo móvel do fluxo de trabalho técnico do Launch {#aepsdk-workflow}

Depois de criar e configurar sua propriedade móvel na interface do usuário da Coleta de dados, a variável **[!UICONTROL Sync Mobile app AEPSDK from Launch]** o fluxo de trabalho técnico agora sincronizará as propriedades da tag mobile importadas no Adobe Campaign Standard.

Por padrão, o workflow técnico é iniciado a cada 15 minutos. Se necessário, ele pode ser reiniciado manualmente:

1. No Adobe Campaign Standard, no menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.
1. Abra o **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]** fluxo de trabalho.

   ![](assets/launch_10.png)

1. Clique no botão **[!UICONTROL Scheduler]** atividade .

1. Selecione **[!UICONTROL Immediate execution]**.

   ![](assets/launch_11.png)

Seu fluxo de trabalho agora será reiniciado e sincronizado com as propriedades da tag mobile importadas no Adobe Campaign Standard.

## Configuração do aplicativo no Adobe Campaign {#set-up-campaign}

Para usar uma propriedade de tag mobile no Campaign, você também deve configurar essa propriedade no Adobe Campaign. No Adobe Campaign, verifique se o usuário IMS faz parte dos Perfis de produto padrão do usuário e do administrador.

Aguarde a execução do fluxo de trabalho técnico e sincronize a propriedade móvel da tag com o Adobe Campaign. Em seguida, você pode configurá-lo no Adobe Campaign.

Para obter mais informações sobre Sincronizar AEPSDK do aplicativo móvel do fluxo de trabalho técnico do Launch, consulte esta seção [seção](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow).

>[!NOTE]
>
>Por padrão, os administradores com a unidade organizacional definida como TODOS podem editar o aplicativo móvel.

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/launch.png)

1. Selecione o aplicativo móvel que você criou na interface do usuário da Coleta de dados.
It **[!UICONTROL Property Status]** deve ser **[!UICONTROL Ready to configure]**.

   >[!NOTE]
   >
   >Por padrão, para recuperar a lista de aplicativos móveis criados na interface do usuário da Coleta de dados, o Campaign Standard usa o valor definido na opção NmsServer_URL para procurar propriedades correspondentes.
   >
   >Em alguns casos, o endpoint da Campanha para um aplicativo móvel pode ser diferente daquele definido em NmsServer_URL. Nesse caso, defina o terminal na variável `Launch_URL_Campaign` opção. O Campaign usará o valor dessa opção para procurar propriedades correspondentes na interface do usuário da coleta de dados.

   ![](assets/launch_4.png)

1. Você pode alterar a unidade organizacional do seu aplicativo móvel sob a variável **[!UICONTROL Access Authorization]** para limitar o acesso a esse aplicativo móvel a unidades específicas da organização. Para obter mais informações, consulte esta página.

   Aqui, o administrador pode atribuir unidades suborganizacionais selecionando-as na lista suspensa.

   ![](assets/launch_12.png)

1. Para fazer a conexão entre o Campaign e as tags no Adobe Experience Platform, clique em **[!UICONTROL Save]**.

1. Verifique se o status do aplicativo móvel foi alterado de **[!UICONTROL Ready to Configure]** para **[!UICONTROL Configured]**.

   Quando a extensão do Campaign mostrar que a chave foi configurada com sucesso, você também pode verificar se a propriedade foi configurada com êxito no Campaign.

   ![](assets/launch_5.png)

1. Para que essa configuração entre em vigor, as alterações precisam ser publicadas na interface do usuário da coleta de dados.

   Para obter mais informações, consulte [Publicar configuração](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration).

## Configuração do aplicativo específico para canal no Adobe Campaign {#channel-specific-config}

Seu aplicativo móvel agora está pronto para ser usado no Campaign para notificação por push ou deliveries no aplicativo. Agora você pode configurá-lo ainda mais, se necessário, para criar eventos que acionarão suas mensagens no aplicativo e/ou farão upload de certificados por push.

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

1. Selecione o aplicativo móvel que você criou e configurou na interface do usuário para coleta de dados.

1. No **[!UICONTROL Mobile application properties]** , você pode começar a adicionar eventos que estão disponíveis no aplicativo móvel para suas mensagens no aplicativo.

1. Para configurar os eventos, clique em **[!UICONTROL Create Element]**.

   ![](assets/launch_6.png)

1. Digite um nome e uma descrição.

   ![](assets/launch_7.png)

1. Clique em **[!UICONTROL Add]**.

   Seu evento agora está disponível na guia Acionadores ao criar uma mensagem no aplicativo. Para obter mais informações, consulte [Preparação e envio de uma mensagem no aplicativo](../../channels/using/preparing-and-sending-an-in-app-message.md).

1. No **[!UICONTROL Device-specific settings]** seção de um painel de aplicativo móvel, para cada dispositivo, forneça os detalhes do aplicativo, incluindo o certificado para iOS e a chave do servidor para Android.

   Após o upload do certificado, uma mensagem notifica você que o upload foi bem-sucedido e exibe a data de expiração do certificado.

   >[!NOTE]
   >
   >Depois de adicionar o certificado com êxito no Adobe Campaign Standard, você não poderá mais alterar as configurações novamente, pois apenas uma plataforma APNS (produção ou sandbox) pode ser adicionada ao aplicativo MCPNS.

   ![](assets/launch_8.png)

1. Clique no botão **[!UICONTROL Mobile application subscribers]** para ver uma lista de assinantes e outras informações sobre esses assinantes, por exemplo, se eles recusaram suas notificações.

## Excluindo seu aplicativo {#delete-app}

>[!CAUTION]
>
>A exclusão do aplicativo não pode ser revertida.

Para excluir seu aplicativo, conclua as etapas em [Exclusão de propriedades móveis](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch).

Depois que seu aplicativo for excluído, no Adobe Campaign, verifique se o status da propriedade do aplicativo foi atualizado corretamente para Excluído no Launch.

Ao clicar no aplicativo no Adobe Campaign, você pode remover completamente esse aplicativo do Adobe Campaign clicando em Excluir do Campaign.

![](assets/launch_9.png)
