---
title: Gerenciamento de entrada SMS
seo-title: Gerenciamento de entrada SMS
description: Gerenciamento de entrada SMS
seo-description: Saiba como gerenciar o STOP SMS e armazenar o SMS de entrada no Adobe Campaign.
page-status-flag: nunca ativado
uuid: f 063052 b -96 ef -41 b 6-bf 1 b -4006 de 73 f 0 b 9
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: sms-messages
discoiquuid: ee 1970 e 6-1 ed -46 e 0-94 e 6-8337768300 ee
delivercontext-tags: entrega, smscontent, voltar
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Managing incoming SMS{#managing-incoming-sms}

## Managing STOP SMS {#managing-stop-sms}

Quando um perfil responde a uma mensagem SMS enviada por meio da Campanha, é possível configurar mensagens que são enviadas automaticamente para ele, bem como a ação a ser executada.

This configuration is defined in the **[!UICONTROL Automatic reply sent to the MO]** section of the [SMS Routing external account](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO corresponde a «Mobile Originated», o que significa que você pode configurar uma resposta automática para o dispositivo móvel que enviou o SMS.

Para fazer isso:

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]** then the **[!UICONTROL SMS routing via SMPP]** external account.
1. Under the **[!UICONTROL Automatic reply sent to the MO]** category, click **[!UICONTROL Create element]** to start configuring your automatic reply.

   ![](assets/sms_mo_1.png)

1. Escolha a palavra-chave que acionará essa resposta automática. As palavras-chave não fazem distinção entre maiúsculas e minúsculas. Por exemplo, aqui, se os destinatários enviarem a palavra-chave "STOP", receberão a resposta automática.

   Deixe essa coluna vazia se quiser enviar a mesma resposta, não importa qual é a palavra-chave.

   ![](assets/sms_mo_2.png)

1. In the **[!UICONTROL Short code]** field, specify a number that is usually used to send deliveries and will serve as a sender name. You can also decide to leave the **[!UICONTROL Short code]** column empty, to send the same reply no matter what the short code.

   ![](assets/sms_mo_4.png)

1. Type in the answer you want to send to your recipients in the field **[!UICONTROL Reply]**.

   To carry out an action without sending a reply, leave the **[!UICONTROL Reply]** column empty. Por exemplo, isso permite remover da quarentena o número de telefone de um usuário que responde com uma mensagem diferente de "STOP".

   ![](assets/sms_mo_3.png)

1. In the **[!UICONTROL Additional action]** field, link an action to your automatic reply:

   * **[!UICONTROL Send to quarantine]** A ação faz a quarentena automática do número de telefone do perfil.
   * **[!UICONTROL Remove from quarantine]** A ação remove o número do telefone de quarentena.
   * **[!UICONTROL None]** A ação permite que você envie a mensagem aos seus destinatários sem executar uma ação.
   For example, in the configuration below, if recipients send the keyword "STOP", they will automatically receive an unsubscription confirmation and their phone number will be sent to quarantine with the **[!UICONTROL Blacklisted]** status. Esse status se refere somente ao número de telefone, o perfil não é lista negra para que o usuário continue recebendo mensagens de email.

   ![](assets/sms_mo.png)

Os destinatários agora podem ser automaticamente cancelados de assinar suas mensagens e enviados para quarentena com essa resposta automática. The quarantined recipients are listed in the **[!UICONTROL Addresses]** table available through the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Quarantines]** menu. For more information on quarantines, refer to this [section](../../sending/using/understanding-quarantine-management.md).

Esses SMS de entrada podem ser armazenados se necessário. For more information on this, refer to this [section](../../channels/using/managing-incoming-sms.md#storing-incoming-sms).

## Storing incoming SMS {#storing-incoming-sms}

In the **[!UICONTROL SMS routing via SMPP]** external account, you can choose to store incoming messages for example when a subscriber replies "STOP" to an SMS message in order to be removed from your recipient lists.

![](assets/sms_config_mo_1.png)

By checking **[!UICONTROL Store incoming MO in the database]** in the **[!UICONTROL SMPP channel settings]** category, all SMS will be stored in the inSMS table and can be retrieved via a query activity in a workflow.

Para fazer isso:

1. In the **[!UICONTROL SMPP channel settings]** field, check **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. In the **[!UICONTROL Marketing activities]** tab, click **[!UICONTROL Create]** then select **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Selecione o tipo de fluxo de trabalho.
1. Edit the properties of your workflow, then click **[!UICONTROL Create]**. For more on workflows creation, refer to this [section](../../automating/using/building-a-workflow.md).
1. Drag and drop a **[!UICONTROL Query]** activity and double-click the activity.
1. In the **[!UICONTROL Properties]** tab of the query, choose **[!UICONTROL Incoming SMS (inSMS)]** in the **[!UICONTROL Resource]** field.

   ![](assets/sms_config_mo_4.png)

1. Then, in the **[!UICONTROL Target]** tab, drag and drop the **[!UICONTROL Incoming SMS attributes]** rule.

   ![](assets/sms_config_mo_5.png)

1. Aqui, queremos direcionar cada mensagem recebida a partir do dia antes. In the **[!UICONTROL Field]** category, select **[!UICONTROL Creation date (created)]**.
1. In **[!UICONTROL Filter type]**, select **[!UICONTROL Relative]** then in **[!UICONTROL Level of precision]**, choose **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. Você pode optar por recuperar dados a partir de hoje, o dia antes ou os últimos dias. Click **[!UICONTROL Confirm]** when your query is configured.

Esta consulta recuperará cada mensagem STOP recebida dependendo do intervalo de tempo escolhido.

A atividade permite, por exemplo, criar uma população e personalizar melhor suas entregas.
