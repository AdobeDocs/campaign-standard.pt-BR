---
title: Gerenciamento de dados de formulário de landing page
description: Saiba como gerenciar dados de formulário de landing page.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
feature: Landing Pages
role: User
level: Intermediate
exl-id: 7083447c-4cac-41cb-8453-369819e0c7c1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 15%

---

# Gerenciamento de dados de formulário de landing page{#managing-landing-page-form-data}

No conteúdo da landing page, os campos de entrada são usados para armazenar ou atualizar dados do banco de dados do Campaign.

Para fazer isso, esses campos devem ser mapeados para campos de banco de dados.

Você pode definir e gerenciar o mapeamento por meio da seção **[!UICONTROL Form data]** na paleta esquerda.

![](assets/lp_form-data.png)

## Mapeamento de campos de formulário {#mapping-form-fields}

Para atualizar o banco de dados do Campaign de acordo com suas necessidades, vincule campos de banco de dados relevantes à zona de entrada, ao botão de opção ou aos blocos de tipo de caixa de seleção da landing page.

Para fazer isso, siga as etapas abaixo:

1. Selecione um bloco no conteúdo da landing page.

   >[!NOTE]
   >
   >Os campos padrão das landing pages incorporadas são pré-configurados. Você pode modificá-los conforme necessário.

1. Acesse a seção **[!UICONTROL Form data]** na paleta esquerda.

1. Para alterar o tipo de campo, selecione um valor na lista suspensa **[!UICONTROL HTML type of the field]**.

   ![](assets/lp_html-field-type.png)

   >[!NOTE]
   >
   >Para obter mais informações sobre como usar o tipo de caixa de seleção em uma página de destino, consulte as seções [Atualizar várias assinaturas de serviço](#multiple-subscriptions) e [Caixa de seleção do contrato](#agreement-checkbox).

1. Se você selecionar um tipo de campo incompatível com o campo de banco de dados selecionado atualmente na zona **[!UICONTROL Field]**, será exibida uma mensagem de aviso. Para obter o mapeamento ideal, selecione um valor apropriado.

   ![](assets/lp_field-type-warning.png)

1. Use a zona **[!UICONTROL Field]** para selecionar um campo de banco de dados que será vinculado ao campo de formulário.

   ![](assets/lp_select-database-field.png)

   >[!NOTE]
   >
   >As landing pages só podem ser mapeadas com os recursos **[!UICONTROL Profiles]** ou **[!UICONTROL Service]**.

   Neste exemplo, mapeie o campo **Name** da sua página de aterrissagem para o campo **[!UICONTROL Last name]** do recurso **[!UICONTROL Profiles]**.

   ![](assets/lp_database-field-example.png)

1. Marque a opção **[!UICONTROL Mandatory]**, se necessário. Nesse caso, a landing page só poderá ser enviada se o usuário tiver preenchido esse campo.

   ![](assets/lp_mandatory-option.png)

   Se um campo obrigatório não estiver preenchido, uma mensagem de erro será exibida quando o usuário enviar a página.

1. Clique em **[!UICONTROL Confirm]** para salvar as alterações.

<!--If you choose a mandatory **[!UICONTROL Checkbox]**, make sure that it is of **[!UICONTROL Field]** type.-->

## Armazenamento e reconciliação de dados{#data-storage-and-reconciliation}

Os parâmetros de reconciliação de dados permitem definir como os dados inseridos na landing page serão gerenciados depois que forem enviados por um usuário.

Para fazer isso:

1. Edite as propriedades de landing page acessadas pelo ícone ![](assets/edit_darkgrey-24px.png) no painel da landing page e exiba os parâmetros **[!UICONTROL Job]**.

   ![](assets/lp_parameters_job.png)

1. Selecione o **[!UICONTROL Reconciliation key]**: este campo de banco de dados é usado para determinar se o visitante tem um perfil já conhecido no banco de dados do Adobe Campaign. Pode ser, por exemplo, email, nome, sobrenome. A chave de reconciliação permite atualizar ou criar um perfil, de acordo com o parâmetro **[!UICONTROL Update strategy]** definido abaixo.

1. Defina o **[!UICONTROL Form parameter mapping]**: esta seção permite mapear os parâmetros do campo de landing page e os usados na chave de reconciliação.

1. Selecione o **[!UICONTROL Update strategy]**: se a chave de reconciliação recuperar um perfil de banco de dados, você poderá optar por atualizar esse perfil com os dados inseridos no formulário ou impedir essa atualização.

   ![](assets/lp_parameters_update-strategy.png)

## Várias subscrições de serviço {#multiple-subscriptions}

Você pode usar várias caixas de seleção em uma única página de aterrissagem para permitir que os usuários assinem ou cancelem a inscrição de vários serviços.

Para fazer isso, siga as etapas abaixo:

1. Ao criar a landing page:

   * Selecione um bloco e, na seção **[!UICONTROL Form data]**, escolha **[!UICONTROL Checkbox]** como o tipo de campo.

     ![](assets/lp_field-type-checkbox.png)

   * Se você estiver familiarizado com o HTML, também poderá inserir manualmente uma caixa de seleção usando o botão **[!UICONTROL Show source]**.

     ![](assets/lp_show_source.png)

     Isso permite inserir a caixa de seleção sempre que for conveniente na página.

     ![](assets/lp_manual-checkbox.png)

1. Verifique se a caixa de seleção está marcada no conteúdo. A lista suspensa **[!UICONTROL Type]** é exibida na seção **[!UICONTROL Form data]** da paleta esquerda. Selecione **[!UICONTROL Service and subscription]** na lista.

   ![](assets/lp_service-and-subscription.png)

1. Escolha uma opção na lista suspensa **[!UICONTROL Behavior]**.

   ![](assets/lp_checkbox-behavior.png)

1. Selecione um [serviço](../../audiences/using/creating-a-service.md) na lista correspondente.

   ![](assets/lp_checkbox-service.png)

1. Verifique se a opção **[!UICONTROL Mandatory]** está desmarcada. Caso contrário, seus usuários não terão uma escolha.

   ![](assets/lp_uncheck-mandatory.png)

1. Para adicionar mais caixas de seleção que permitam assinar outros serviços, repita as etapas acima quantas vezes forem necessárias.

   ![](assets/lp_multiple-checkboxes.png)

Quando a landing page for publicada, os usuários poderão marcar várias caixas de seleção para assinar vários boletins informativos da mesma página.

## Caixa de seleção do contrato {#agreement-checkbox}

Você pode adicionar uma caixa de seleção que o perfil precisa marcar antes de enviar a landing page.

Por exemplo, isso permite solicitar o consentimento dos usuários para a política de privacidade ou fazê-los aceitar seus termos e condições, antes de enviarem o formulário.

>[!IMPORTANT]
>
>A seleção dessa caixa de seleção é obrigatória para os usuários. Se não for selecionada, eles não poderão enviar a landing page.

Para inserir e configurar essa caixa de seleção, faça o seguinte:

1. Ao criar a landing page:

   * Selecione um bloco e, na seção **[!UICONTROL Form data]**, escolha **[!UICONTROL Checkbox]** como o tipo de campo.

     ![](assets/lp_field-type-checkbox.png)

   * Se você estiver familiarizado com o HTML, também poderá inserir manualmente uma caixa de seleção usando o botão **[!UICONTROL Show source]**.

     ![](assets/lp_show_source.png)

     <!--Manually insert a checkbox, such as in the example below:

      <!--Click **[!UICONTROL Hide source]**.-->

1. Verifique se a caixa de seleção está marcada.

   ![](assets/lp_select_checkbox.png)

1. A lista suspensa **[!UICONTROL Type]** é exibida na seção **[!UICONTROL Form data]** da paleta esquerda. Selecione **[!UICONTROL Agreement]** na lista.

   ![](assets/lp_form_data_drop-down.png)

   >[!NOTE]
   >
   >O elemento **[!UICONTROL Agreement]** não está mapeado para um campo do banco de dados do Campaign.

1. Clique no ícone ![](assets/lp-properties-icon.png) ao lado de **[!UICONTROL Form data]** para acessar as propriedades avançadas da caixa de seleção.

1. Você pode editar a mensagem, se necessário.

   ![](assets/lp_agreement_message.png)

   Esse texto será exibido como um aviso se o usuário não marcar a caixa de seleção antes de enviar o formulário.

   >[!NOTE]
   >
   >Esta ação é obrigatória por padrão e não pode ser alterada.

1. Clique em **[!UICONTROL Confirm]**.

Agora, sempre que a landing page for exibida, o usuário precisará marcar essa caixa de seleção antes de enviar o formulário. Caso contrário, o aviso será exibido e o usuário não poderá enviar o formulário até que a caixa de seleção seja ativada.