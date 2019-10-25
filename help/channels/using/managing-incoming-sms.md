---
title: Gerenciar SMS de entrada
seo-title: Gerenciar SMS de entrada
description: Gerenciar SMS de entrada
seo-description: Saiba como gerenciar STOP SMS e armazenar mensagens SMS recebidas no Adobe Campaign.
page-status-flag: nunca ativado
uuid: f063052b-96ef-41b6-bf1b-4006de73f0b9
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: canais
content-type: referência
topic-tags: sms-messages
discoiquuid: ee1970e6-1ced-46e0-94e6-8337768300ee
delivercontext-tags: entrega,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Gerenciar SMS de entrada{#managing-incoming-sms}

## Gerenciamento de SMS STOP {#managing-stop-sms}

Quando um perfil responde a uma mensagem SMS enviada via Campaign, você pode configurar mensagens que são automaticamente enviadas de volta a ele, bem como a ação a ser executada.

Essa configuração é definida na **[!UICONTROL Automatic reply sent to the MO]** seção da conta [externa do](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)SMS Routing. MO significa "Mobile Originated", o que significa que você pode configurar uma resposta automática para o celular que enviou o SMS.

Para fazer isso:

1. No menu avançado, por meio do logotipo do Adobe Campaign, selecione **[!UICONTROL Administration > Application settings > External accounts]** e depois a conta **[!UICONTROL SMS routing via SMPP]** externa.
1. Na **[!UICONTROL Automatic reply sent to the MO]** categoria, clique em **[!UICONTROL Create element]** para começar a configurar sua resposta automática.

   ![](assets/sms_mo_1.png)

1. Escolha a palavra-chave que acionará essa resposta automática. As palavras-chave não diferenciam maiúsculas de minúsculas. Por exemplo, aqui, se os destinatários enviarem a palavra-chave "PARAR", eles receberão a resposta automática.

   Deixe essa coluna vazia se desejar enviar a mesma resposta, independentemente da palavra-chave.

   ![](assets/sms_mo_2.png)

1. No **[!UICONTROL Short code]** campo, especifique um número normalmente usado para enviar entregas e que servirá como nome de remetente. Você também pode decidir deixar a **[!UICONTROL Short code]** coluna vazia, para enviar a mesma resposta, independentemente do código curto.

   ![](assets/sms_mo_4.png)

1. Digite a resposta que deseja enviar aos destinatários no campo **[!UICONTROL Reply]**.

   To carry out an action without sending a reply, leave the **[!UICONTROL Reply]** column empty. Por exemplo, isso permite remover da quarentena o número de telefone de um usuário que responde com uma mensagem diferente de "PARAR".

   ![](assets/sms_mo_3.png)

1. No **[!UICONTROL Additional action]** campo, vincule uma ação à sua resposta automática:

   * A **[!UICONTROL Send to quarantine]** ação coloca automaticamente em quarentena o número de telefone do perfil.
   * A **[!UICONTROL Remove from quarantine]** ação remove o número de telefone do perfil da quarentena.
   * A **[!UICONTROL None]** ação permite que você envie somente a mensagem para seus destinatários sem executar uma ação.
   Por exemplo, na configuração abaixo, se os destinatários enviarem a palavra-chave "PARAR", eles receberão automaticamente uma confirmação de cancelamento de assinatura e seu número de telefone será enviado para quarentena com o **[!UICONTROL Blacklisted]** status. Esse status se refere apenas ao número de telefone, o perfil não está na lista negra para que o usuário continue recebendo mensagens de email.

   ![](assets/sms_mo.png)

Seus destinatários agora podem ser cancelados automaticamente de sua inscrição em suas mensagens e enviados para quarentena com essa resposta automática. Os destinatários em quarentena são listados na tabela **[!UICONTROL Addresses]** disponível no menu **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Quarantines]** . For more information on quarantines, refer to this [section](../../sending/using/understanding-quarantine-management.md).

Esses SMS recebidos podem ser armazenados, se necessário. For more information on this, refer to this [section](#storing-incoming-sms).

## Armazenamento de SMS recebido {#storing-incoming-sms}

Na conta **[!UICONTROL SMS routing via SMPP]** externa, você pode optar por armazenar mensagens recebidas, por exemplo, quando um assinante responde "PARAR" em uma mensagem SMS para ser removido das listas de destinatários.

![](assets/sms_config_mo_1.png)

Ao verificar **[!UICONTROL Store incoming MO in the database]** a **[!UICONTROL SMPP channel settings]** categoria, todo o SMS será armazenado na tabela inSMS e poderá ser recuperado por meio de uma atividade de consulta em um fluxo de trabalho.

Para fazer isso:

1. No **[!UICONTROL SMPP channel settings]** campo, verifique **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. Na **[!UICONTROL Marketing activities]** guia, clique em **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Selecione o tipo de fluxo de trabalho.
1. Edite as propriedades do seu fluxo de trabalho e clique em **[!UICONTROL Create]**. For more on workflows creation, refer to this [section](../../automating/using/building-a-workflow.md).
1. Arraste e solte uma **[!UICONTROL Query]** atividade e clique duas vezes na atividade.
1. Na **[!UICONTROL Properties]** guia da consulta, escolha **[!UICONTROL Incoming SMS (inSMS)]** no **[!UICONTROL Resource]** campo.

   ![](assets/sms_config_mo_4.png)

1. Em seguida, na **[!UICONTROL Target]** guia, arraste e solte a **[!UICONTROL Incoming SMS attributes]** regra.

   ![](assets/sms_config_mo_5.png)

1. Aqui, queremos direcionar cada mensagem recebida do dia anterior. Na **[!UICONTROL Field]** categoria, selecione **[!UICONTROL Creation date (created)]**.
1. Em **[!UICONTROL Filter type]**, selecione **[!UICONTROL Relative]** e em **[!UICONTROL Level of precision]**, escolha **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. Você pode optar por recuperar dados de hoje, do dia anterior ou dos últimos dias. Clique **[!UICONTROL Confirm]** quando sua consulta estiver configurada.

Essa consulta recuperará cada mensagem STOP recebida, dependendo do intervalo de tempo escolhido.

A atividade permite, por exemplo, criar uma população e personalizar melhor suas entregas.
