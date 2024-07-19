---
title: Criação de uma dimensão de perfil personalizada
description: Saiba como criar uma dimensão de perfil personalizada com base nos dados de perfil personalizados.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 98516af1-d4dd-4c1f-b360-f19208c22f82
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 5%

---

# Criação de uma dimensão de perfil personalizada{#creating-a-custom-profile-dimension}

Os relatórios também podem ser criados e gerenciados com base nos dados de perfil personalizados criados durante a extensão de recurso personalizado do perfil.

Neste exemplo, queremos criar o campo de perfil personalizado **Programas de fidelidade**, que será dividido em três níveis: ouro, prata e bronze. Esse perfil personalizado será estendido para poder usá-lo como uma dimensão de perfil personalizada em relatórios dinâmicos.

* [Etapa 1: criar um novo campo de perfil](#step-1--create-a-new-profile-field)
* [Etapa 2: estender os logs de envio com o campo de perfil](#step-2--extend-the-sending-logs-with-the-profile-field)
* [Etapa 3: criar um delivery direcionado a recipients inscritos no programa de fidelidade](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [Etapa 4: criar um relatório dinâmico para filtrar recipients com a dimensão de perfil personalizada](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## Etapa 1: criar um novo campo de perfil {#step-1--create-a-new-profile-field}

Primeiro, precisamos criar o novo campo de perfil **Programa de fidelidade** que atribuirá o nível de fidelidade aos nossos recipients: ouro, prata ou bronze.

>[!NOTE]
>
>Os recursos personalizados só podem ser gerenciados por um administrador.

Para fazer isso:

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** e depois o recurso personalizado **[!UICONTROL Profile (profile)]**.

   ![](assets/custom_profile_1.png)

1. Na guia **[!UICONTROL Data structure]**, na categoria **[!UICONTROL Fields]**, clique no botão **[!UICONTROL Add field]**.

   ![](assets/custom_profile_2.png)

1. Insira o **[!UICONTROL Label]**, **[!UICONTROL ID]** e selecione o recurso personalizado **[!UICONTROL Type]**. Aqui, selecionamos **[!UICONTROL Text]**, já que os recipients terão a escolha entre ouro, prata e bronze.

   ![](assets/custom_profile_3.png)

1. Clique no ícone ![](assets/custom_profile_22.png) para definir seu campo.

   ![](assets/custom_profile_12.png)

1. Aqui, precisamos especificar os valores autorizados verificando **[!UICONTROL Specify a list of authorized valued]** e criar cada valor clicando em **[!UICONTROL Create element]**.

   ![](assets/custom_profile_13.png)

1. Insira o **[!UICONTROL Label]** e **[!UICONTROL Value]** e clique em **[!UICONTROL Add]**. Para este exemplo, precisamos criar o valor ouro, prata e bronze. Clique em **[!UICONTROL Confirm]** ao concluir.

   ![](assets/custom_profile_14.png)

1. Selecione a guia **[!UICONTROL Screen definition]**. No menu suspenso **[!UICONTROL Detail screen configuration]**, marque a seção **[!UICONTROL Add personalized fields]** para criar uma nova seção em nosso perfil.

   ![](assets/custom_profile_4.png)

1. Clique no botão **[!UICONTROL Add an element]** para criar sua nova seção. Selecione o **[!UICONTROL Type]**: **[!UICONTROL Input field]**, **[!UICONTROL Value]** ou **[!UICONTROL List]** e, em seguida, o campo a ser adicionado nesta nova seção.

   ![](assets/custom_profile_5.png)

1. Você também pode adicionar um título à sua seção no campo **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   Clique em **[!UICONTROL Save]** quando a configuração estiver concluída.

   ![](assets/custom_profile_6.png)

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** para começar a publicar seu recurso personalizado.
1. Clique em **[!UICONTROL Prepare publication]** e, quando a preparação estiver concluída, clique no botão **[!UICONTROL Publish]**.

   ![](assets/custom_profile_7.png)

O novo campo de perfil agora está pronto para ser usado e selecionado pelos recipients.

![](assets/custom_profile_8.png)

## Etapa 2: estender os logs de envio com o campo de perfil {#step-2--extend-the-sending-logs-with-the-profile-field}

Agora que o campo de perfil foi criado, precisamos estender os logs de envio com nosso campo de perfil para criar a dimensão de perfil personalizado associada em relatórios dinâmicos.

Antes de estender o log com nosso campo de perfil, verifique se a janela PII foi aceita para ter acesso à guia **[!UICONTROL Sending logs extension]**. Para obter mais informações, consulte esta [página](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

>[!NOTE]
>
>Os logs só podem ser estendidos com campos de perfil pelo administrador.

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** e depois o recurso personalizado **[!UICONTROL Profile (profile)]**.
1. Abra o menu suspenso **[!UICONTROL Sending logs extension]**.
1. Clique no botão **[!UICONTROL Create element]**.

   ![](assets/custom_profile_9.png)

1. Selecione o campo criado anteriormente e clique em **[!UICONTROL Confirm]**.
1. Marque **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** para criar sua dimensão de perfil personalizada.

   ![](assets/custom_profile_10.png)

   Essa opção só estará disponível se a janela PII tiver sido aceita. Para obter mais informações, consulte esta [página](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

1. Clique em **[!UICONTROL Add]** e salve o recurso personalizado.
1. Como o recurso personalizado foi modificado, precisamos publicá-lo para implementar as novas alterações.

   No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** para começar a publicar seu recurso personalizado.

1. Clique em **[!UICONTROL Prepare publication]** e, quando a preparação estiver concluída, clique no botão **[!UICONTROL Publish]**.

   ![](assets/custom_profile_7.png)

Seu perfil personalizado agora está disponível como uma dimensão de perfil personalizada em seus relatórios.

Agora que seu campo foi criado e que os logs de envio foram estendidos com esse campo de perfil, você pode começar a direcionar recipients nos deliveries.

## Etapa 3: criar um delivery direcionado a recipients inscritos no programa de fidelidade {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

Depois que o campo de perfil for publicado, você poderá iniciar o delivery. Neste exemplo, queremos direcionar todos os recipients inscritos no programa de fidelidade.

1. Na guia **[!UICONTROL Marketing activities]**, clique em **[!UICONTROL Create]** e selecione **[!UICONTROL Email]**.
1. Escolha um **[!UICONTROL Email type]** e insira as propriedades de seu email.
1. Para direcionar os destinatários inscritos no programa de fidelidade, arraste e solte a atividade **[!UICONTROL Profiles (attributes)]**.
1. Selecione o campo criado anteriormente no menu suspenso **[!UICONTROL Field]**.

   ![](assets/custom_profile_16.png)

1. Selecione seu **[!UICONTROL Filter conditions]**. Aqui, queremos direcionar os recipients que fazem parte de um dos três níveis do programa de fidelidade.

   ![](assets/custom_profile_17.png)

1. Clique em **[!UICONTROL Confirm]** e, quando terminar a filtragem, clique em **[!UICONTROL Next]**.
1. Defina e personalize o conteúdo da mensagem, o nome do remetente e o assunto. Para obter mais informações sobre a criação de emails, consulte esta [página](../../designing/using/designing-content-in-adobe-campaign.md).

   Em seguida, clique em **[!UICONTROL Create]**.

1. Quando estiver pronto, você poderá visualizar e enviar sua mensagem. Para obter mais informações sobre como preparar e enviar sua mensagem, consulte esta [página](../../sending/using/preparing-the-send.md).

Assim que o email for enviado corretamente aos recipients selecionados, você poderá começar a filtrar os dados e rastrear o sucesso do delivery com relatórios.

## Etapa 4: criar um relatório dinâmico para filtrar recipients com a dimensão de perfil personalizada {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

Após enviar a entrega, você pode detalhar os relatórios usando a dimensão de perfil personalizada na tabela **[!UICONTROL Profile]**.

1. Na guia **[!UICONTROL Reports]**, selecione um relatório pronto para uso ou clique no botão **[!UICONTROL Create]** para iniciar um do zero.

   ![](assets/custom_profile_18.png)

1. Na categoria **[!UICONTROL Dimensions]**, clique em **[!UICONTROL Profile]** e arraste e solte sua dimensão de perfil do **Programa de fidelidade** personalizado na tabela de forma livre.

   ![](assets/custom_profile_19.png)

1. Arraste e solte as métricas **[!UICONTROL Processed/Sent]** e **[!UICONTROL Open]** para começar a filtrar seus dados.

   ![](assets/custom_profile_20.png)

1. Arraste e solte uma visualização no seu espaço de trabalho se necessário.

   ![](assets/custom_profile_21.png)

**Tópicos relacionados:**

* [Usando dados de perfil personalizados para criar relatórios relevantes](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
