---
title: Migração do aplicativo para dispositivos móveis SDK v4 para o SDK do Adobe Experience Platform
description: Saiba como migrar seu aplicativo para dispositivos móveis do SDK v4 para o Adobe Experience Platform SDK
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: eb7a209e-069e-4068-966d-05344bd838c7
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '1193'
ht-degree: 1%

---

# Como migrar seu aplicativo para dispositivos móveis do SDK v4 para o SDK da Adobe Experience Platform {#sdkv4-migration}

>[!IMPORTANT]
>
> O processo de migração é irreversível.
>
> Leia o documento atentamente antes de iniciar a migração do aplicativo para dispositivos móveis do SDK V4 para o SDK do Adobe Experience Platform.

## Sobre a migração do SDK V4

A Adobe Campaign Standard processa aplicativos móveis usando o SDK V4 como aplicativos separados daqueles que usam o SDK da Adobe Experience Platform.
Depois de atualizar a versão do SDK do Adobe da v4 para o Adobe Experience Platform, os aplicativos móveis precisam continuar usando os dados e campanhas existentes do assinante de aplicativos: portanto, é necessária uma migração.

>[!NOTE]
>
> Esta página documenta a migração de um aplicativo para dispositivos móveis SDK v4 para um aplicativo SDK da Adobe Experience Platform recém-criado. Os aplicativos para dispositivos móveis do SDK v4 não serão mesclados com o aplicativo para dispositivos móveis do SDK da Adobe Experience Platform com um **[!UICONTROL Configured]** **[!UICONTROL Property status]**.

| O que não será alterado após a migração |
|:-:|
| Não haverá nenhum efeito nos deliveries e campanhas existentes usando o aplicativo SDK V4 migrado. |
| O nome do aplicativo móvel permanecerá o mesmo. |
| As credenciais da plataforma do iOS e do Android serão mantidas. |
| Todos os assinantes do aplicativo e seus dados serão retidos. |
| O aplicativo móvel SDK v4 existente continuará enviando dados (dados PII, informações de assinante e token) para a Adobe Campaign Standard. |
| A variável **[!UICONTROL Organizational unit]** do aplicativo móvel permanecerá o mesmo. |

| O que será alterado após a migração |
|:-:|
| O aplicativo para dispositivos móveis estará disponível em **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**. Antes da migração, ele estava disponível em **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**. |
| A variável **[!UICONTROL Collect PII Endpoint]** do aplicativo será alterado. O mais antigo **[!UICONTROL Collect PII Endpoint]** continuará a funcionar, os dados enviados não serão perdidos. |
| O aplicativo será vinculado a uma tag **[!UICONTROL Mobile Property]**. Ele será processado como um aplicativo móvel recém-criado. |
| O aplicativo Adobe Experience Platform SDK original usado na migração não existirá como um aplicativo separado. Somente o aplicativo SDK v4 migrado estará disponível. |

## Migrar seu aplicativo para dispositivos móveis do SDK v4 para o Adobe Experience Platform SDK {#how-to-migrate}

Antes de migrar, considere as seguintes recomendações:

* O processo de migração é irreversível.
* Não execute a migração de vários aplicativos ao mesmo tempo. Você também deve garantir que a migração de um mesmo aplicativo não seja acionada por várias janelas ao mesmo tempo.
* Antes da migração, verifique se você recebeu a **[!UICONTROL Organizational unit]** do aplicativo móvel que você deseja migrar e do aplicativo Adobe Experience Platform que você está usando para migração.
* Após a migração, o aplicativo se tornará um aplicativo do SDK da Adobe Experience Platform. Suas alterações serão vinculadas à tag correspondente **[!UICONTROL Mobile Property]**.

1. Criar um novo **[!UICONTROL Mobile property]** na interface da Coleção de dados. Para obter mais informações, consulte [documentação](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/).

1. No Adobe Campaign Standard, no menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]** e abra o **[!UICONTROL syncWithLaunch]** fluxo de trabalho. Verifique se o fluxo de trabalho terminou sem erros.

1. Após a conclusão do fluxo de trabalho, na **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]** verifique se o aplicativo para dispositivos móveis está disponível no Adobe Campaign Standard e em **[!UICONTROL Ready to Configure]** estado.

   ![](assets/aep_v4_2.png)

1. Entrada **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**, selecione o aplicativo SDK V4 que deseja migrar.

1. Selecione a guia **[!UICONTROL Mobile application migration to AEP SDK]**.

   ![](assets/aep_v4_3.png)

1. No **[!UICONTROL Select AEP SDK mobile application to merge current application with]** selecione o aplicativo para dispositivos móveis Adobe Experience Platform SDK criado anteriormente.

1. Clique em **[!UICONTROL Migrate]**.

   ![](assets/aep_v4_4.png)

1. Na janela **[!UICONTROL Migration application]**, clique em **[!UICONTROL Ok]**.

   ![](assets/aep_v4_5.png)

1. A janela de conclusão bem-sucedida é exibida, clique em **[!UICONTROL Go to Adobe Experience Platform SDK Channel list]**.

1. Na página da lista de canais do SDK da Adobe Experience Platform, verifique se o aplicativo móvel V4 anterior está definido como **[!UICONTROL Ready To Configure]**.

1. Selecione seu aplicativo para dispositivos móveis e clique em **[!UICONTROL Save]** para concluir a migração.

Após essa migração, os assinantes coletados pela versão V4 do aplicativo móvel e os novos assinantes coletados pela versão AEP do aplicativo móvel estarão disponíveis no aplicativo migrado.

Para distinguir os dois tipos diferentes de assinantes, você pode adicionar um novo campo personalizado de **[!UICONTROL Text]** tipo ao estender o recurso personalizado **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** as `sdkversion` ou `appVersion` por exemplo. Para obter mais informações sobre como estender um recurso personalizado, consulte esta [página](../../developing/using/creating-or-extending-the-resource.md).
Em seguida, será necessário configurar a tag associada **[!UICONTROL Mobile property]** para enviar esse valor de campo personalizado na chamada Collect PII e alterar a configuração do aplicativo móvel de acordo.

## Perguntas frequentes {#faq}

### P: No aplicativo móvel SDK v4, a guia Mobile application migration to Adobe Experience Platform SDK não está visível. {#tab-not-visible}

A: No menu avançado **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**, verifique o valor do **[!UICONTROL Enable migration of mobile app from SDK v4 to Adobe Experience Platform SDK option]** opção. Ela deve ser definida como 1 e ativada por padrão. O administrador pode tê-la desabilitado manualmente.

![](assets/aep_v4_1.png)

### P: Na guia Mobile application migration para o Adobe Experience Platform SDK, a mensagem No data é exibida. {#no-data}

R: Somente a aplicação qualificada do seu **[!UICONTROL Organizational unit]** é exibido na lista. Verifique se você tem o aplicativo Adobe Experience Platform correto para a migração. A variável **[!UICONTROL Property Status]** do aplicativo Adobe Experience Platform deve ser definido como **[!UICONTROL Ready to Configure]**  e a variável **[!UICONTROL Mobile app migration status]** definir como **[!UICONTROL Not Migrated]**.

![](assets/aep_v4_6.png)

### P: Por que o aplicativo do SDK do Adobe Experience Platform com o Status de propriedade configurado não pode ser usado para migração? {#property-status}

R: O processo de migração retém os assinantes e atributos do SDK v4. Ele só mantém informações relacionadas à tag do aplicativo SDK da Adobe Experience Platform. Os assinantes e outros dados do aplicativo SDK da Adobe Experience Platform serão perdidos. Para evitar perda de dados, somente aplicativos SDK da Adobe Experience Platform com o **[!UICONTROL Ready to Configure]** **[!UICONTROL Property Status]** são elegíveis para migração.

### P: Após a migração, onde posso encontrar meu aplicativo para dispositivos móveis SDK v4 anterior? {#v4-app-not-visible}

R: O aplicativo móvel após a migração ficará visível no menu avançado **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**.

### P: Após a migração, onde posso encontrar meu aplicativo SDK do Adobe Experience Platform recém-criado? {#aep-not-visible}

R: O aplicativo Adobe Experience Platform SDK recém-criado usado para a migração não existirá como um aplicativo separado. Somente o aplicativo SDK v4 migrado estará disponível.

### P: Se a unidade organizacional do aplicativo móvel SDK v4 estiver definida como A (uma unidade secundária da unidade organizacional ALL) e o SDK do Adobe Experience Platform estiver definido como ALL. Como posso migrar meu aplicativo para dispositivos móveis? {#v4-org-unit}

A: Administradores do **[!UICONTROL Organizational unit]** TODOS terão os direitos de gerenciar ambos os aplicativos móveis e serão responsáveis pela migração.

### P: Se a unidade organizacional do aplicativo móvel SDK v4 estiver definida como A e o aplicativo SDK do Adobe Experience Platform estiver definido como B (um irmão da unidade organizacional A). Como posso migrar meu aplicativo para dispositivos móveis? {#aep-org-unit}

R: Aplicativo do SDK do Adobe Experience Platform sendo o ativo de um irmão **[!UICONTROL Organizational unit]**, o aplicativo móvel não estará visível para os usuários do **[!UICONTROL Organizational unit]** A. O aplicativo móvel estará disponível para os administradores do **[!UICONTROL Organizational unit]** TODOS, mas não recomendamos que esses administradores migrem o aplicativo para dispositivos móveis.
Nesse caso, você deve mover seus aplicativos móveis na mesma **[!UICONTROL Organizational unit]** ou em um **[!UICONTROL Organizational unit]** com um link principal.
Para obter mais informações sobre **[!UICONTROL Organizational unit]**, consulte esta página [seção](../../administration/using/organizational-units.md).

### P: Na página do aplicativo móvel do SDK do Adobe Experience Platform (migrado do aplicativo móvel v4), no menu suspenso Configurações do canal de push, nenhuma informação como data/nome carregado é exibida para a chave do Android ou o certificado do iOS {#no-information-v5}

R: O sistema não armazena essas informações quando o aplicativo para dispositivos móveis SDK V4 é criado. Ao migrar seu aplicativo para dispositivos móveis SDK V4 para um aplicativo para dispositivos móveis SDK da Adobe Experience Platform, seu aplicativo para dispositivos móveis migrado também não terá esse tipo de informação. Assim que um usuário fizer upload de um novo certificado da iOS ou chave do Android, os diferentes detalhes da chave ou do certificado serão armazenados e exibidos corretamente na **[!UICONTROL Push channel settings]** menu suspenso.
