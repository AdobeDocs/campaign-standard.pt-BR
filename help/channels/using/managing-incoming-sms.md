---
title: Gerenciamento de SMS de entrada
description: Saiba como gerenciar SMS PARAR e armazenar SMS de entrada no Adobe Campaign.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: delivery,smsContent,back
feature: SMS
role: User
level: Intermediate
exl-id: 86cb6f4c-a5a7-4d9d-bbfd-4a70af38cf3a
source-git-commit: 30d0c2552bea3a7cbd8500be4e8c0c74e5a40a99
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# Gerenciamento de SMS de entrada{#managing-incoming-sms}

## Gerenciar SMS PARAR {#managing-stop-sms}

Quando um perfil responde a uma mensagem SMS enviada pelo Campaign, você pode configurar mensagens que são automaticamente enviadas de volta, bem como a ação a ser executada.

Essa configuração é definida na variável **[!UICONTROL Automatic reply sent to the MO]** seção do [Conta externa de Roteamento de SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO significa &quot;Originado por dispositivo móvel&quot;, o que significa que você pode configurar uma resposta automática para o dispositivo móvel que enviou o SMS.

Para fazer isso:

1. No menu avançado, no logotipo do Adobe Campaign, selecione **[!UICONTROL Administration > Application settings > External accounts]** em seguida, o **[!UICONTROL SMS routing via SMPP]** conta externa.
1. No **[!UICONTROL Automatic reply sent to the MO]** categoria, clique em **[!UICONTROL Create element]** para configurar sua resposta automática.

   ![](assets/sms_mo_1.png)

1. Escolha a palavra-chave que acionará essa resposta automática. As palavras-chave não diferenciam maiúsculas de minúsculas. Por exemplo, aqui, se os recipients enviarem a palavra-chave &quot;PARAR&quot;, eles receberão a resposta automática.

   Deixe esta coluna vazia se quiser enviar a mesma resposta independentemente da palavra-chave.

   >[!IMPORTANT]
   >
   >Somente caracteres alfanuméricos são autorizados.

   ![](assets/sms_mo_2.png)

1. No **[!UICONTROL Short code]** especifique um número que seja usado normalmente para enviar deliveries e servirá como nome de remetente. Você também pode decidir deixar o **[!UICONTROL Short code]** coluna vazia, para enviar a mesma resposta independentemente do código curto.

   ![](assets/sms_mo_4.png)

1. Digite a resposta que deseja enviar aos seus destinatários no campo **[!UICONTROL Reply]**.

   Para realizar uma ação sem enviar uma resposta, deixe o **[!UICONTROL Reply]** coluna vazia. Por exemplo, isso permite remover da quarentena o número de telefone de um usuário que responde com uma mensagem diferente de &quot;PARAR&quot;.

   ![](assets/sms_mo_3.png)

1. No **[!UICONTROL Additional action]** , vincule uma ação à sua resposta automática:

   * A variável **[!UICONTROL Send to quarantine]** A ação coloca o número de telefone do perfil em quarentena automaticamente.
   * A variável **[!UICONTROL Remove from quarantine]** a ação remove o número de telefone do perfil da quarentena.
   * A variável **[!UICONTROL None]** permite enviar a mensagem somente para seus recipients sem realizar uma ação.

   Por exemplo, na configuração abaixo, se os recipients enviarem a palavra-chave &quot;PARAR&quot;, eles receberão automaticamente uma confirmação de unsubscription e seu número de telefone será enviado para quarentena com o **[!UICONTROL On denylist]** status. Esse status se refere apenas ao número de telefone. O perfil é para que o usuário continue recebendo mensagens de email.

   ![](assets/sms_mo.png)

1. Clique em **[!UICONTROL Save]**.

1. No **[!UICONTROL Advanced parameters]** do delivery de SMS **[!UICONTROL Properties]**, é possível definir um **[!UICONTROL Short code]** para excluir automaticamente os recipients que recusaram. Para obter mais informações, consulte [nesta seção](../../administration/using/configuring-sms-channel.md#configuring-sms-properties).

Os recipients agora podem ter a assinatura cancelada automaticamente nas mensagens e ser enviados para quarentena com essa resposta automática. Os recipients em quarentena são listados na variável **[!UICONTROL Addresses]** tabela disponível por meio do **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** menu. Para obter mais informações sobre quarentenas, consulte este [seção](../../sending/using/understanding-quarantine-management.md).

Esse SMS de entrada pode ser armazenado, se necessário. Para obter mais informações, consulte esta [seção](#storing-incoming-sms).

## Armazenando SMS de entrada {#storing-incoming-sms}

No **[!UICONTROL SMS routing via SMPP]** conta externa, você pode optar por armazenar mensagens de entrada, por exemplo, quando um assinante responde &quot;PARAR&quot; a uma mensagem SMS para ser removido das listas de recipients.

![](assets/sms_config_mo_1.png)

Ao verificar **[!UICONTROL Store incoming MO in the database]** no **[!UICONTROL SMPP channel settings]** , todos os SMS serão armazenados na tabela inSMS e poderão ser recuperados por meio de uma atividade de query em um workflow.

Para fazer isso:

1. No **[!UICONTROL SMPP channel settings]** , marque **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. No **[!UICONTROL Marketing activities]** clique em **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Selecione o tipo de workflow.
1. Edite as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**. Para obter mais informações sobre a criação de workflows, consulte este [seção](../../automating/using/building-a-workflow.md).
1. Arraste e solte uma **[!UICONTROL Query]** e clique duas vezes na atividade.
1. No **[!UICONTROL Properties]** da consulta, escolha **[!UICONTROL Incoming SMS (inSMS)]** no **[!UICONTROL Resource]** campo.

   ![](assets/sms_config_mo_4.png)

1. Em seguida, no **[!UICONTROL Target]** , arraste e solte a **[!UICONTROL Incoming SMS attributes]** regra.

   ![](assets/sms_config_mo_5.png)

1. Aqui, queremos direcionar todas as mensagens recebidas do dia anterior. No **[!UICONTROL Field]** categoria, selecione **[!UICONTROL Creation date (created)]**.
1. Entrada **[!UICONTROL Filter type]**, selecione **[!UICONTROL Relative]** depois em **[!UICONTROL Level of precision]**, escolha **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. Em seguida, você pode optar por recuperar os dados de hoje, do dia anterior ou dos últimos dias. Clique em **[!UICONTROL Confirm]** quando o query é configurado.

Este query recuperará todas as mensagens STOP recebidas, dependendo do intervalo de tempo escolhido.

A atividade permite, por exemplo, criar uma população e personalizar melhor seus deliveries.
