---
solution: Campaign Standard
product: campaign
title: Gerenciar SMS de entrada
description: Saiba como gerenciar o STOP SMS e armazenar o SMS recebido no Adobe Campaign.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 8%

---


# Gerenciar SMS de entrada{#managing-incoming-sms}

## Gerenciando STOP SMS {#managing-stop-sms}

Quando um perfil responde a uma mensagem SMS enviada pelo Campaign, você pode configurar mensagens que serão automaticamente enviadas para ele, bem como a ação a ser executada.

Essa configuração é definida na seção **[!UICONTROL Automatic reply sent to the MO]** da conta externa [do Roteamento SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO significa &quot;Mobile Originated&quot;, o que significa que você pode configurar uma resposta automática para o celular que enviou o SMS.

Para fazer isso:

1. No menu avançado, por meio do logotipo Adobe Campaign, selecione **[!UICONTROL Administration > Application settings > External accounts]** e a conta externa **[!UICONTROL SMS routing via SMPP]**.
1. Na categoria **[!UICONTROL Automatic reply sent to the MO]**, clique em **[!UICONTROL Create element]** para start ao configurar sua resposta automática.

   ![](assets/sms_mo_1.png)

1. Escolha a palavra-chave que acionará essa resposta automática. As palavras-chave não diferenciam maiúsculas de minúsculas. Por exemplo, aqui, se os recipient enviarem a palavra-chave &quot;PARAR&quot;, eles receberão a resposta automática.

   Deixe essa coluna vazia se desejar enviar a mesma resposta, independentemente da palavra-chave.

   ![](assets/sms_mo_2.png)

1. No campo **[!UICONTROL Short code]**, especifique um número que geralmente é usado para enviar delivery e servirá como nome de remetente. Você também pode decidir deixar a coluna **[!UICONTROL Short code]** vazia, para enviar a mesma resposta, independentemente do código curto.

   ![](assets/sms_mo_4.png)

1. Digite a resposta que deseja enviar aos seus recipient no campo **[!UICONTROL Reply]**.

   Para executar uma ação sem enviar uma resposta, deixe a coluna **[!UICONTROL Reply]** vazia. Por exemplo, isso permite remover da quarentena o número de telefone de um usuário que responde com uma mensagem diferente de &quot;PARAR&quot;.

   ![](assets/sms_mo_3.png)

1. No campo **[!UICONTROL Additional action]**, vincule uma ação à sua resposta automática:

   * A ação **[!UICONTROL Send to quarantine]** quarentena automaticamente o número de telefone do perfil.
   * A ação **[!UICONTROL Remove from quarantine]** remove o número de telefone do perfil da quarentena.
   * A ação **[!UICONTROL None]** permite que você envie apenas a mensagem para seus recipient sem executar uma ação.

   Por exemplo, na configuração abaixo, se os recipient enviarem a palavra-chave &quot;PARAR&quot;, eles receberão automaticamente uma confirmação de unsubscription e seu número de telefone será enviado para a quarentena com o status **[!UICONTROL On denylist]**. Esse status se refere apenas ao número de telefone, o perfil é feito para que o usuário continue recebendo mensagens de email.

   ![](assets/sms_mo.png)

Seus recipient agora podem ser automaticamente cancelados de inscrição em suas mensagens e enviados para a quarentena com essa resposta automática. Os recipient em quarentena estão listados na tabela **[!UICONTROL Addresses]** disponível no menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]**. Para obter mais informações sobre o quarentena, consulte esta [seção](../../sending/using/understanding-quarantine-management.md).

Esses SMS recebidos podem ser armazenados, se necessário. Para obter mais informações sobre isso, consulte esta [seção](#storing-incoming-sms).

## Armazenamento de SMS recebidos {#storing-incoming-sms}

Na conta externa **[!UICONTROL SMS routing via SMPP]**, você pode optar por armazenar mensagens recebidas, por exemplo, quando um assinante responde &quot;STOP&quot; a uma mensagem SMS para ser removido das listas do recipient.

![](assets/sms_config_mo_1.png)

Ao verificar **[!UICONTROL Store incoming MO in the database]** na categoria **[!UICONTROL SMPP channel settings]**, todo o SMS será armazenado na tabela inSMS e poderá ser recuperado por meio de uma atividade de query em um fluxo de trabalho.

Para fazer isso:

1. No campo **[!UICONTROL SMPP channel settings]**, marque **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. Na guia **[!UICONTROL Marketing activities]**, clique em **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Selecione o tipo de fluxo de trabalho.
1. Edite as propriedades do seu fluxo de trabalho e clique em **[!UICONTROL Create]**. Para obter mais informações sobre a criação de workflows, consulte esta [seção](../../automating/using/building-a-workflow.md).
1. Arraste e solte uma atividade **[!UICONTROL Query]** e duplo-clique na atividade.
1. Na guia **[!UICONTROL Properties]** do query, escolha **[!UICONTROL Incoming SMS (inSMS)]** no campo **[!UICONTROL Resource]**.

   ![](assets/sms_config_mo_4.png)

1. Em seguida, na guia **[!UICONTROL Target]**, arraste e solte a regra **[!UICONTROL Incoming SMS attributes]**.

   ![](assets/sms_config_mo_5.png)

1. Aqui, queremos público alvo de cada mensagem recebida do dia anterior. Na categoria **[!UICONTROL Field]**, selecione **[!UICONTROL Creation date (created)]**.
1. Em **[!UICONTROL Filter type]**, selecione **[!UICONTROL Relative]** e, em **[!UICONTROL Level of precision]**, escolha **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. Você pode optar por recuperar dados de hoje, do dia anterior ou dos últimos dias. Clique em **[!UICONTROL Confirm]** quando seu query estiver configurado.

Esse query recuperará todas as mensagens STOP recebidas, dependendo do intervalo de tempo escolhido.

A atividade permite, por exemplo, criar uma população e personalizar melhor seus delivery.
