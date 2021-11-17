---
title: Gerenciamento de SMS de entrada
description: Saiba como gerenciar STOP SMS e armazenar SMS recebido no Adobe Campaign.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: delivery,smsContent,back
feature: SMS
role: User
level: Intermediate
exl-id: 86cb6f4c-a5a7-4d9d-bbfd-4a70af38cf3a
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 2%

---

# Gerenciamento de SMS de entrada{#managing-incoming-sms}

## Gerenciar SMS STOP {#managing-stop-sms}

Quando um perfil responde a uma mensagem SMS, enviada pelo Campaign, você pode configurar mensagens que são automaticamente enviadas de volta a elas, bem como a ação a ser executada.

Essa configuração é definida na variável **[!UICONTROL Automatic reply sent to the MO]** da seção [Conta externa de roteamento SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO significa &quot;Remoto originado&quot;, o que significa que você pode configurar uma resposta automática para o celular que enviou o SMS.

Para fazer isso:

1. No menu avançado, selecione pelo logotipo do Adobe Campaign **[!UICONTROL Administration > Application settings > External accounts]** em seguida, **[!UICONTROL SMS routing via SMPP]** conta externa.
1. Em **[!UICONTROL Automatic reply sent to the MO]** categoria , clique em **[!UICONTROL Create element]** para configurar sua resposta automática.

   ![](assets/sms_mo_1.png)

1. Escolha a palavra-chave que acionará essa resposta automática. As palavras-chave não diferenciam maiúsculas de minúsculas. Por exemplo, aqui, se os recipients enviarem a palavra-chave &quot;PARAR&quot;, eles receberão a resposta automática.

   Deixe essa coluna vazia se desejar enviar a mesma resposta independentemente da palavra-chave.

   ![](assets/sms_mo_2.png)

1. No **[!UICONTROL Short code]** , especifique um número que geralmente é usado para enviar deliveries e servirá como nome de remetente. Você também pode decidir deixar a variável **[!UICONTROL Short code]** coluna vazia, para enviar a mesma resposta independentemente do código curto.

   ![](assets/sms_mo_4.png)

1. Digite a resposta que deseja enviar aos recipients no campo **[!UICONTROL Reply]**.

   Para realizar uma ação sem enviar uma resposta, deixe a variável **[!UICONTROL Reply]** coluna vazia. Por exemplo, isso permite remover da quarentena o número de telefone de um usuário que responde com uma mensagem diferente de &quot;PARAR&quot;.

   ![](assets/sms_mo_3.png)

1. No **[!UICONTROL Additional action]** , vincule uma ação à sua resposta automática:

   * O **[!UICONTROL Send to quarantine]** ação coloca o número de telefone do perfil em quarentena automaticamente.
   * O **[!UICONTROL Remove from quarantine]** ação remove o número de telefone do perfil da quarentena.
   * O **[!UICONTROL None]** permite enviar a mensagem somente para os recipients sem ter que realizar uma ação.

   Por exemplo, na configuração abaixo, se os recipients enviarem a palavra-chave &quot;PARAR&quot;, eles receberão automaticamente uma confirmação de unsubscription e seu número de telefone será enviado para a quarentena com a variável **[!UICONTROL On denylist]** status. Esse status se refere apenas ao número de telefone. O perfil é para que o usuário continue recebendo mensagens de email.

   ![](assets/sms_mo.png)

1. Clique em **[!UICONTROL Save]**.

1. No **[!UICONTROL Advanced parameters]** do delivery de SMS **[!UICONTROL Properties]**, é possível definir um **[!UICONTROL Short code]** para excluir automaticamente os recipients que optaram por não participar. Para obter mais informações, consulte [esta seção](../../administration/using/configuring-sms-channel.md#configuring-sms-properties).

Seus recipients agora podem ser automaticamente cancelados na assinatura de suas mensagens e enviados para quarentena com essa resposta automática. Os recipients em quarentena são listados na variável **[!UICONTROL Addresses]** tabela disponível por meio da **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** menu. Para obter mais informações sobre quarentenas, consulte esta seção [seção](../../sending/using/understanding-quarantine-management.md).

O SMS de entrada pode ser armazenado se necessário. Para obter mais informações sobre isso, consulte esta seção [seção](#storing-incoming-sms).

## Armazenamento de SMS de entrada {#storing-incoming-sms}

No **[!UICONTROL SMS routing via SMPP]** na conta externa, você pode optar por armazenar mensagens recebidas, por exemplo, quando um assinante responde &quot;PARAR&quot; em uma mensagem SMS para ser removido das listas de recipients.

![](assets/sms_config_mo_1.png)

Verificando **[!UICONTROL Store incoming MO in the database]** no **[!UICONTROL SMPP channel settings]** , todo o SMS será armazenado na tabela inSMS e poderá ser recuperado por meio de uma atividade de query em um workflow.

Para fazer isso:

1. No **[!UICONTROL SMPP channel settings]** campo, verificar **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. No **[!UICONTROL Marketing activities]** clique em **[!UICONTROL Create]** em seguida, selecione **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Selecione o tipo de fluxo de trabalho.
1. Edite as propriedades do seu fluxo de trabalho e clique em **[!UICONTROL Create]**. Para obter mais informações sobre a criação de workflows, consulte esta seção [seção](../../automating/using/building-a-workflow.md).
1. Arraste e solte uma **[!UICONTROL Query]** e clique duas vezes na atividade .
1. No **[!UICONTROL Properties]** da consulta, escolha **[!UICONTROL Incoming SMS (inSMS)]** no **[!UICONTROL Resource]** campo.

   ![](assets/sms_config_mo_4.png)

1. Em seguida, no **[!UICONTROL Target]** arraste e solte a guia **[!UICONTROL Incoming SMS attributes]** regra.

   ![](assets/sms_config_mo_5.png)

1. Aqui, queremos direcionar cada mensagem recebida do dia anterior. No **[!UICONTROL Field]** categoria , selecione **[!UICONTROL Creation date (created)]**.
1. Em **[!UICONTROL Filter type]**, selecione **[!UICONTROL Relative]** em seguida **[!UICONTROL Level of precision]**, escolha **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. Em seguida, você pode optar por recuperar os dados de hoje, dia anterior ou dos últimos dias. Clique em **[!UICONTROL Confirm]** quando o query estiver configurado.

Este query recuperará cada mensagem STOP recebida dependendo do intervalo de tempo escolhido.

A atividade permite, por exemplo, criar uma população e personalizar melhor seus deliveries.
