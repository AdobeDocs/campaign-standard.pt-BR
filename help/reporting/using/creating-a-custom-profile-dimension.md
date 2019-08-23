---
title: Criação de uma dimensão personalizada de perfil
seo-title: Criação de uma dimensão personalizada de perfil
description: Criação de uma dimensão personalizada de perfil
seo-description: Saiba como criar uma dimensão de perfil personalizada com base em dados de perfil personalizados.
page-status-flag: nunca ativado
uuid: f 75 e 005 b -5328-4 c 98-9 e 78-51 d 54 fd 0 e 246
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: relatórios
content-type: reference
topic-tags: personalização-relatórios
discoiquuid: b 6 d 3 de 63-3 add -4881-8917-04 a 6 f 8 b 6 be 4 d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# Criação de uma dimensão personalizada de perfil{#creating-a-custom-profile-dimension}

Os relatórios também podem ser criados e gerenciados com base em dados de perfil personalizados criados durante a extensão de recurso personalizado do perfil.

Neste exemplo, queremos criar os programas de fidelidade personalizados de **fidelização** que serão divididos em três níveis: gold, silver e bronze. Esse perfil personalizado será então estendido para ser usado como uma dimensão de perfil personalizada em relatórios dinâmicos.

* [Etapa 1: Criar um novo campo de perfil](../../reporting/using/creating-a-custom-profile-dimension.md#step-1--create-a-new-profile-field)
* [Etapa 2: Estender os registros de envio com o campo de perfil](../../reporting/using/creating-a-custom-profile-dimension.md#step-2--extend-the-sending-logs-with-the-profile-field)
* [Etapa 3: Criar um direcionamento de envio de entrega inscrito no programa de fidelidade](../../reporting/using/creating-a-custom-profile-dimension.md#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [Etapa 4: Criar um relatório dinâmico para filtrar destinatários com a dimensão personalizada do perfil](../../reporting/using/creating-a-custom-profile-dimension.md#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## Etapa 1: Criar um novo campo de perfil {#step-1--create-a-new-profile-field}

Primeiro, precisamos criar o novo campo **de perfil de Fidelidade** que atribuirá nível de fidelidade aos nossos destinatários: gold, silver ou bronze.

>[!NOTE]
>
>Os recursos personalizados podem ser gerenciados somente por um administrador.

Para fazer isso:

1. No menu avançado, selecione **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** e depois o recurso **[!UICONTROL Profile (profile)]** personalizado.

   ![](assets/custom_profile_1.png)

1. Na **[!UICONTROL Data structure]** guia, na **[!UICONTROL Fields]** categoria, clique no **[!UICONTROL Add field]** botão.

   ![](assets/custom_profile_2.png)

1. Digite o **[!UICONTROL Label]** recurso e **[!UICONTROL ID]** selecione o recurso **[!UICONTROL Type]** personalizado. Aqui, selecionamos **[!UICONTROL Text]** , pois os destinatários terão a escolha entre gold, silver e bronze.

   ![](assets/custom_profile_3.png)

1. Clique no ![](assets/custom_profile_22.png) ícone para definir o campo.

   ![](assets/custom_profile_12.png)

1. Aqui, precisamos especificar os valores autorizados verificando **[!UICONTROL Specify a list of authorized valued]** e criando cada valor clicando **[!UICONTROL Create element]** em.

   ![](assets/custom_profile_13.png)

1. Digite o **[!UICONTROL Label]** e **[!UICONTROL Value]** clique **[!UICONTROL Add]** em. Neste exemplo, é necessário criar o valor gold, silver e bronze. Clique **[!UICONTROL Confirm]** em quando concluído.

   ![](assets/custom_profile_14.png)

1. Selecione a **[!UICONTROL Screen definition]** guia. Na seção **[!UICONTROL Detail screen configuration]** suspensa, marque **[!UICONTROL Add personalized fields]** a seção para criar uma nova seção em nosso perfil.

   ![](assets/custom_profile_4.png)

1. Clique no **[!UICONTROL Add an element]** botão para criar a nova seção. Selecione: **[!UICONTROL Type]** ou **[!UICONTROL Input field]****[!UICONTROL Value]**, em seguida, o campo a ser adicionado nesta nova seção.**[!UICONTROL List]**

   ![](assets/custom_profile_5.png)

1. Também é possível adicionar um título à seção no campo **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   Clique **[!UICONTROL Save]** em quando a configuração é feita.

   ![](assets/custom_profile_6.png)

1. No menu avançado, selecione **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publication]** para começar a publicar seu recurso personalizado.
1. Clique **[!UICONTROL Prepare publication]** em e quando a preparação for feita, clique no **[!UICONTROL Publish]** botão.

   ![](assets/custom_profile_7.png)

O novo campo de perfil está pronto para ser usado e selecionado pelos seus destinatários.

![](assets/custom_profile_8.png)

## Etapa 2: Estender os registros de envio com o campo de perfil {#step-2--extend-the-sending-logs-with-the-profile-field}

Agora que o campo de perfil é criado, é necessário estender o envio de registros com nosso campo de perfil para criar a dimensão personalizada associada ao perfil em relatórios dinâmicos.

Antes de estender o log com nosso campo de perfil, certifique-se de que a janela PII foi aceita para ter acesso à **[!UICONTROL Sending logs extension]** guia. Para saber mais sobre isso, consulte esta [página](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

>[!NOTE]
>
>Os logs só podem ser estendidos com campos de perfil por administrador.

1. No menu avançado, selecione **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** e depois o recurso **[!UICONTROL Profile (profile)]** personalizado.
1. Abra o **[!UICONTROL Sending logs extension]** menu suspenso.
1. Clique no **[!UICONTROL Create element]** botão.

   ![](assets/custom_profile_9.png)

1. Selecione o campo criado anteriormente e clique **[!UICONTROL Confirm]** em.
1. Verifique **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** para criar a dimensão personalizada do perfil.

   ![](assets/custom_profile_10.png)

   Essa opção só estará disponível se a janela PII tiver sido aceita. Para saber mais sobre isso, consulte esta [página](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

1. Clique **[!UICONTROL Add]** em, em seguida, salve seu recurso personalizado.
1. Como o recurso personalizado foi modificado, é necessário publicá-lo para implementar as novas alterações.

   No menu avançado, selecione **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publication]** para começar a publicar seu recurso personalizado.

1. Clique **[!UICONTROL Prepare publication]** em e quando a preparação for feita, clique no **[!UICONTROL Publish]** botão.

   ![](assets/custom_profile_7.png)

Seu perfil personalizado agora está disponível como uma dimensão personalizada de perfil em seus relatórios.

Agora que o campo foi criado e que o envio de logs foi estendido com este campo de perfil, é possível iniciar o direcionamento de destinatários em entregas.

## Etapa 3: Criar um direcionamento de envio de entrega inscrito no programa de fidelidade {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

Depois que o campo de perfil é publicado, você pode iniciar sua entrega. Neste exemplo, queremos direcionar cada destinatário inscrito no programa de fidelidade.

1. Na **[!UICONTROL Marketing activities]** guia, clique **[!UICONTROL Create]** em, em seguida, selecione **[!UICONTROL Email]**.
1. Escolha um **[!UICONTROL Email type]** e-mail e insira as propriedades do e-mail.
1. Para direcionar o destinatário inscrito no programa de fidelidade, arraste e solte a **[!UICONTROL Profiles (attributes)]** atividade.
1. Selecione o campo criado anteriormente no **[!UICONTROL Field]** menu suspenso.

   ![](assets/custom_profile_16.png)

1. Selecione sua **[!UICONTROL Filter conditions]**. Aqui, queremos direcionar os destinatários que fazem parte de um dos três níveis do programa de fidelidade.

   ![](assets/custom_profile_17.png)

1. Clique **[!UICONTROL Confirm]** em e depois na filtragem, clique **[!UICONTROL Next]** em.
1. Defina e personalize o conteúdo da mensagem, o nome do remetente e o assunto. Para obter mais informações sobre a criação de email, consulte esta [página](../../designing/using/about-email-content-design.md#about-the-email-designer).

   Em seguida, clique **[!UICONTROL Create]** em.

1. Quando pronto, você pode visualizar e enviar sua mensagem. Para obter mais informações sobre como preparar e enviar a mensagem, consulte esta [página](../../sending/using/preparing-the-send.md).

Depois que seu e-mail é enviado corretamente para os destinatários selecionados, você pode começar a filtrar seus dados e acompanhar o sucesso da entrega com os relatórios.

## Etapa 4: Criar um relatório dinâmico para filtrar destinatários com a dimensão personalizada do perfil {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

Após enviar a entrega, você pode detalhar os relatórios usando a dimensão personalizada do perfil da **[!UICONTROL Profile]** tabela.

1. Na **[!UICONTROL Reports]** guia, selecione um relatório predefinido ou clique no **[!UICONTROL Create]** botão para iniciar um do zero.

   ![](assets/custom_profile_18.png)

1. Na **[!UICONTROL Dimensions]** categoria, clique **[!UICONTROL Profile]** em e arraste e solte a dimensão personalizada **do perfil do programa** Fidelidade na tabela de forma livre.

   ![](assets/custom_profile_19.png)

1. Arraste e solte as **[!UICONTROL Processed/Sent]****[!UICONTROL Open]** métricas para começar a filtrar seus dados.

   ![](assets/custom_profile_20.png)

1. Arraste e solte uma visualização na área de trabalho, se necessário.

   ![](assets/custom_profile_21.png)

**Tópico relacionado:**

* [Uso de dados de perfil personalizados para criar relatórios bem-sucedidos](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
