---
title: Criação de uma dimensão de perfil personalizada
description: Saiba como criar uma dimensão de perfil personalizada com base em dados de perfil personalizados.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 98516af1-d4dd-4c1f-b360-f19208c22f82
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 5%

---

# Criação de uma dimensão de perfil personalizada{#creating-a-custom-profile-dimension}

Os relatórios também podem ser criados e gerenciados com base em dados de perfil personalizados criados durante a extensão de recurso personalizado do perfil.

Neste exemplo, queremos criar o campo de perfil personalizado **Programas de fidelidade** que serão divididos em três níveis: ouro, prata e bronze. Esse perfil personalizado será estendido para poder usá-lo como uma dimensão de perfil personalizada em relatórios dinâmicos.

* [Etapa 1: Criar um novo campo de perfil](#step-1--create-a-new-profile-field)
* [Etapa 2: Estender os logs de envio com o campo de perfil](#step-2--extend-the-sending-logs-with-the-profile-field)
* [Etapa 3: Criar um delivery direcionado a recipients inscritos no programa de fidelidade](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [Etapa 4: Criar um relatório dinâmico para filtrar recipients com a dimensão de perfil personalizada](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## Etapa 1: Criar um novo campo de perfil {#step-1--create-a-new-profile-field}

Primeiro, precisamos criar o novo campo de perfil **Programa de fidelidade** que atribuirá o nível de fidelidade aos nossos recipients: ouro, prata ou bronze.

>[!NOTE]
>
>Os recursos personalizados só podem ser gerenciados por um administrador.

Para fazer isso:

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** em seguida, **[!UICONTROL Profile (profile)]** recurso personalizado.

   ![](assets/custom_profile_1.png)

1. No **[!UICONTROL Data structure]** na guia , no **[!UICONTROL Fields]** , clique no botão **[!UICONTROL Add field]** botão.

   ![](assets/custom_profile_2.png)

1. Insira o **[!UICONTROL Label]**, **[!UICONTROL ID]** e selecione o recurso personalizado **[!UICONTROL Type]**. Aqui, selecionamos **[!UICONTROL Text]** já que os recipients terão a escolha entre ouro, prata e bronze.

   ![](assets/custom_profile_3.png)

1. Clique no botão ![](assets/custom_profile_22.png) ícone para definir o campo.

   ![](assets/custom_profile_12.png)

1. Aqui, precisamos especificar os valores autorizados verificando **[!UICONTROL Specify a list of authorized valued]** e crie cada valor clicando em **[!UICONTROL Create element]**.

   ![](assets/custom_profile_13.png)

1. Insira o **[!UICONTROL Label]** e **[!UICONTROL Value]** em seguida, clique em **[!UICONTROL Add]**. Para este exemplo, precisamos criar o valor ouro, prata e bronze. Clique em **[!UICONTROL Confirm]** ao concluir.

   ![](assets/custom_profile_14.png)

1. Selecione a guia **[!UICONTROL Screen definition]**. No **[!UICONTROL Detail screen configuration]** lista suspensa, verificação **[!UICONTROL Add personalized fields]** para criar uma nova seção em nosso perfil.

   ![](assets/custom_profile_4.png)

1. Clique no botão **[!UICONTROL Add an element]** para criar sua nova seção. Selecione o **[!UICONTROL Type]**: **[!UICONTROL Input field]**, **[!UICONTROL Value]** ou **[!UICONTROL List]**, em seguida, o campo a ser adicionado nesta nova seção.

   ![](assets/custom_profile_5.png)

1. Você também pode adicionar um título à sua seção no campo **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   Clique em **[!UICONTROL Save]** quando a configuração for concluída.

   ![](assets/custom_profile_6.png)

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** para começar a publicar o recurso personalizado.
1. Clique em **[!UICONTROL Prepare publication]** quando a preparação estiver concluída, clique no botão **[!UICONTROL Publish]** botão.

   ![](assets/custom_profile_7.png)

O novo campo de perfil agora está pronto para ser usado e selecionado pelos recipients.

![](assets/custom_profile_8.png)

## Etapa 2: Estender os logs de envio com o campo de perfil {#step-2--extend-the-sending-logs-with-the-profile-field}

Agora que seu campo de perfil foi criado, precisamos estender os logs de envio com nosso campo de perfil para criar a dimensão de perfil personalizado associada nos relatórios dinâmicos.

Antes de estender o log com nosso campo de perfil, verifique se a janela PII foi aceita para ter acesso ao **[!UICONTROL Sending logs extension]** guia . Para obter mais informações, consulte esta [página](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

>[!NOTE]
>
>Os logs só podem ser estendidos com campos de perfil por administrador.

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** em seguida, **[!UICONTROL Profile (profile)]** recurso personalizado.
1. Abra o **[!UICONTROL Sending logs extension]** lista suspensa.
1. Clique no botão **[!UICONTROL Create element]**.

   ![](assets/custom_profile_9.png)

1. Selecione o campo criado anteriormente e clique em **[!UICONTROL Confirm]**.
1. Verificar **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** para criar sua dimensão de perfil personalizada.

   ![](assets/custom_profile_10.png)

   Essa opção só estará disponível se a janela PII tiver sido aceita. Para obter mais informações, consulte esta [página](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

1. Clique em **[!UICONTROL Add]** em seguida, salve o recurso personalizado.
1. Como o recurso personalizado foi modificado, precisamos publicá-lo para implementar as novas alterações.

   No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** para começar a publicar o recurso personalizado.

1. Clique em **[!UICONTROL Prepare publication]** quando a preparação estiver concluída, clique no botão **[!UICONTROL Publish]** botão.

   ![](assets/custom_profile_7.png)

Seu perfil personalizado agora está disponível como uma dimensão de perfil personalizada em seus relatórios.

Agora que seu campo foi criado e que os logs de envio foram estendidos com esse campo de perfil, você pode começar a direcionar recipients nos deliveries.

## Etapa 3: Criar um delivery direcionado a recipients inscritos no programa de fidelidade {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

Depois que o campo de perfil for publicado, você poderá iniciar o delivery. Neste exemplo, queremos direcionar cada recipient inscrito no programa de fidelidade.

1. Na guia **[!UICONTROL Marketing activities]**, clique em **[!UICONTROL Create]** e selecione **[!UICONTROL Email]**.
1. Escolha um **[!UICONTROL Email type]** em seguida, insira as propriedades do email.
1. Para direcionar recipients inscritos no programa de fidelidade, arraste e solte a variável **[!UICONTROL Profiles (attributes)]** atividade .
1. Selecione o campo criado anteriormente no **[!UICONTROL Field]** lista suspensa.

   ![](assets/custom_profile_16.png)

1. Selecione seu **[!UICONTROL Filter conditions]**. Aqui, queremos direcionar os recipients que fazem parte de um dos três níveis do programa de fidelidade.

   ![](assets/custom_profile_17.png)

1. Clique em **[!UICONTROL Confirm]** em seguida, ao concluir a filtragem, clique em **[!UICONTROL Next]**.
1. Defina e personalize o conteúdo da mensagem, o nome do remetente e o assunto. Para obter mais informações sobre criação de email, consulte esta seção [página](../../designing/using/designing-content-in-adobe-campaign.md).

   Em seguida, clique em **[!UICONTROL Create]**.

1. Quando estiver pronto, você poderá visualizar e enviar sua mensagem. Para obter mais informações sobre como preparar e enviar sua mensagem, consulte esta seção [página](../../sending/using/preparing-the-send.md).

Depois que o email for enviado corretamente aos recipients selecionados, você poderá começar a filtrar os dados e rastrear o sucesso do delivery com relatórios.

## Etapa 4: Criar um relatório dinâmico para filtrar recipients com a dimensão de perfil personalizada {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

Após enviar o delivery, é possível detalhar os relatórios usando a dimensão de perfil personalizada do **[!UICONTROL Profile]** tabela.

1. No **[!UICONTROL Reports]** selecione um relatório pronto para uso ou clique no link **[!UICONTROL Create]** botão para iniciar um do zero.

   ![](assets/custom_profile_18.png)

1. No **[!UICONTROL Dimensions]** categoria , clique em **[!UICONTROL Profile]** em seguida, arraste e solte seu **Programa de fidelidade** dimensão de perfil à tabela de forma livre.

   ![](assets/custom_profile_19.png)

1. Arraste e solte a **[!UICONTROL Processed/Sent]** e **[!UICONTROL Open]** para começar a filtrar seus dados.

   ![](assets/custom_profile_20.png)

1. Arraste e solte uma visualização em seu espaço de trabalho, se necessário.

   ![](assets/custom_profile_21.png)

**Tópicos relacionados:**

* [Usar dados de perfil personalizados para criar relatórios abrangentes](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
