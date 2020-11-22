---
solution: Campaign Standard
product: campaign
title: Criar uma dimensão de perfil personalizada
description: Saiba como criar uma dimensão de perfil personalizada com base em dados de perfil personalizados.
audience: reporting
content-type: reference
topic-tags: customizing-reports
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 5%

---


# Criar uma dimensão de perfil personalizada{#creating-a-custom-profile-dimension}

Os relatórios também podem ser criados e gerenciados com base nos dados de perfil personalizados criados durante a extensão de recurso personalizado do perfil.

Neste exemplo, queremos criar os programas **de** Fidelidade do campo de perfil personalizado que serão divididos em três níveis: ouro, prata e bronze. Esse perfil personalizado será estendido para poder usá-lo como uma dimensão de perfil personalizada em relatórios dinâmicos.

* [Etapa 1: Criar um novo campo de perfil](#step-1--create-a-new-profile-field)
* [Etapa 2: Estender os registros de envio com o campo perfil](#step-2--extend-the-sending-logs-with-the-profile-field)
* [Etapa 3: Criar recipient de direcionamento de delivery inscritos no programa de fidelidade](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [Etapa 4: Criar um relatório dinâmico para filtrar recipient com a dimensão de perfil personalizado](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## Etapa 1: Criar um novo campo de perfil {#step-1--create-a-new-profile-field}

Primeiro, precisamos criar o novo programa **de** Fidelidade de campo de perfil que atribuirá o nível de fidelidade aos nossos recipient: ouro, prata ou bronze.

>[!NOTE]
>
>Os recursos personalizados só podem ser gerenciados por um administrador.

Para fazer isso:

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** e depois o recurso **[!UICONTROL Profile (profile)]** personalizado.

   ![](assets/custom_profile_1.png)

1. Na **[!UICONTROL Data structure]** guia, na **[!UICONTROL Fields]** categoria, clique no **[!UICONTROL Add field]** botão.

   ![](assets/custom_profile_2.png)

1. Digite o **[!UICONTROL Label]** e **[!UICONTROL ID]** selecione o recurso personalizado **[!UICONTROL Type]**. Aqui, escolhemos **[!UICONTROL Text]** já que os recipient terão a escolha entre ouro, prata e bronze.

   ![](assets/custom_profile_3.png)

1. Clique no ![](assets/custom_profile_22.png) ícone para definir seu campo.

   ![](assets/custom_profile_12.png)

1. Aqui, precisamos especificar os valores autorizados verificando **[!UICONTROL Specify a list of authorized valued]** e criando cada valor clicando em **[!UICONTROL Create element]**.

   ![](assets/custom_profile_13.png)

1. Digite o **[!UICONTROL Label]** e **[!UICONTROL Value]** clique em **[!UICONTROL Add]**. Para este exemplo, precisamos de criar o valor ouro, prata e bronze. Click **[!UICONTROL Confirm]** when done.

   ![](assets/custom_profile_14.png)

1. Selecione a guia **[!UICONTROL Screen definition]**. Na **[!UICONTROL Detail screen configuration]** lista suspensa, marque a **[!UICONTROL Add personalized fields]** seção para criar uma nova seção em nosso perfil.

   ![](assets/custom_profile_4.png)

1. Click the **[!UICONTROL Add an element]** button to create your new section. Selecione o **[!UICONTROL Type]**: **[!UICONTROL Input field]**, **[!UICONTROL Value]** ou **[!UICONTROL List]**, o campo a ser adicionado nesta nova seção.

   ![](assets/custom_profile_5.png)

1. Também é possível adicionar um título à sua seção no campo **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   Clique **[!UICONTROL Save]** quando a configuração estiver concluída.

   ![](assets/custom_profile_6.png)

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** para start na publicação de seu recurso personalizado.
1. Clique em **[!UICONTROL Prepare publication]** e, quando a preparação estiver concluída, clique no **[!UICONTROL Publish]** botão.

   ![](assets/custom_profile_7.png)

Seu novo campo de perfil agora está pronto para ser usado e selecionado por seus recipient.

![](assets/custom_profile_8.png)

## Etapa 2: Estender os registros de envio com o campo perfil {#step-2--extend-the-sending-logs-with-the-profile-field}

Agora que seu campo de perfil foi criado, precisamos estender os logs de envio com nosso campo de perfil para criar a dimensão de perfil personalizado associada nos relatórios dinâmicos.

Antes de estender o log com nosso campo de perfil, verifique se a janela PII foi aceita para ter acesso à **[!UICONTROL Sending logs extension]** guia. Para obter mais informações, consulte esta [página](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

>[!NOTE]
>
>Os registros só podem ser estendidos com campos de perfil pelo administrador.

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** e depois o recurso **[!UICONTROL Profile (profile)]** personalizado.
1. Abra o **[!UICONTROL Sending logs extension]** menu suspenso.
1. Clique no botão **[!UICONTROL Create element]**.

   ![](assets/custom_profile_9.png)

1. Select your previously created field and click **[!UICONTROL Confirm]**.
1. Marque **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** para criar sua dimensão de perfil personalizada.

   ![](assets/custom_profile_10.png)

   Essa opção só estará disponível se a janela PII tiver sido aceita. Para obter mais informações, consulte esta [página](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

1. Clique em **[!UICONTROL Add]** e salve seu recurso personalizado.
1. Como o recurso personalizado foi modificado, precisamos publicá-lo para implementar as novas alterações.

   No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** para start na publicação de seu recurso personalizado.

1. Clique em **[!UICONTROL Prepare publication]** e, quando a preparação estiver concluída, clique no **[!UICONTROL Publish]** botão.

   ![](assets/custom_profile_7.png)

Seu perfil personalizado agora está disponível como uma dimensão de perfil personalizada em seus relatórios.

Agora que seu campo foi criado e que os logs de envio foram estendidos com esse campo de perfil, você pode direcionar recipient para start em delivery.

## Etapa 3: Criar recipient de direcionamento de delivery inscritos no programa de fidelidade {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

Assim que o campo perfil for publicado, você poderá start o delivery. Neste exemplo, queremos público alvo de todos os recipient inscritos no programa de fidelidade.

1. Na guia **[!UICONTROL Marketing activities]**, clique em **[!UICONTROL Create]** e selecione **[!UICONTROL Email]**.
1. Escolha um e **[!UICONTROL Email type]** insira as propriedades do seu email.
1. Para o recipient do público alvo inscrito no programa de fidelidade, arraste e solte a **[!UICONTROL Profiles (attributes)]** atividade.
1. Selecione o campo criado anteriormente no **[!UICONTROL Field]** menu suspenso.

   ![](assets/custom_profile_16.png)

1. Selecione seu **[!UICONTROL Filter conditions]**. Aqui, queremos público alvo de recipient que fazem parte de um dos três níveis de programa de fidelidade.

   ![](assets/custom_profile_17.png)

1. Clique em **[!UICONTROL Confirm]** e, quando terminar de filtrar, clique em **[!UICONTROL Next]**.
1. Defina e personalize o conteúdo da mensagem, o nome do remetente e o assunto. For more information on email creation refer to this [page](../../designing/using/designing-content-in-adobe-campaign.md).

   Em seguida, clique em **[!UICONTROL Create]**.

1. Quando estiver pronto, você pode pré-visualização e enviar sua mensagem. Para obter mais informações sobre como preparar e enviar sua mensagem, consulte esta [página](../../sending/using/preparing-the-send.md).

Assim que seu email for enviado corretamente para os recipient selecionados, você poderá filtrar seus dados por start e rastrear o sucesso do delivery com os relatórios.

## Etapa 4: Criar um relatório dinâmico para filtrar recipient com a dimensão de perfil personalizado {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

Depois de enviar seu delivery, você pode detalhar os relatórios usando sua dimensão de perfil personalizada da **[!UICONTROL Profile]** tabela.

1. Na **[!UICONTROL Reports]** guia, selecione um relatório predefinido ou clique no botão **[!UICONTROL Create]** para start um do zero.

   ![](assets/custom_profile_18.png)

1. Na **[!UICONTROL Dimensions]** categoria, clique em **[!UICONTROL Profile]** e arraste e solte sua dimensão de perfil **de Fidelidade personalizada do programa** na tabela de forma livre.

   ![](assets/custom_profile_19.png)

1. Arraste e solte as métricas **[!UICONTROL Processed/Sent]** e **[!UICONTROL Open]** para filtrar seus dados por start.

   ![](assets/custom_profile_20.png)

1. Arraste e solte uma visualização no seu espaço de trabalho, se necessário.

   ![](assets/custom_profile_21.png)

**Tópicos relacionados:**

* [Usar dados de perfil personalizados para criar relatórios detalhados](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
