---
title: '"Caso de uso do fluxo de trabalho: Grupo de controle"'
seo-title: '"Caso de uso do fluxo de trabalho: Grupo de controle"'
description: '"Caso de uso do fluxo de trabalho: Grupo de controle"'
seo-description: '"Caso de uso do fluxo de trabalho: Grupo de controle"'
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,segmentation,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2912e3b75b817347b832f9c89ca2320868cbc355

---


# Caso de uso do fluxo de trabalho: Criação de um grupo de controle {#building-control-group}

Para medir o impacto de uma entrega, você pode querer excluir alguns perfis do seu destino para que eles não recebam uma determinada mensagem. Este grupo de controlo pode ser utilizado para efetuar uma comparação com o comportamento da população-alvo que recebeu a mensagem.

Para fazer isso no Adobe Campaign Standard, crie um fluxo de trabalho que inclua as seguintes atividades:
* Uma atividade de consulta para direcionar uma determinada população.
* Uma atividade de segmentação para isolar um grupo de controle aleatório dessa população.
* Uma atividade de entrega por email para enviar uma mensagem para o destino principal.
* Uma atividade Atualizar dados para atualizar os perfis que foram excluídos do destino (o grupo de controle aleatório).

![](assets/wkf_control-group.png)

## Extensão do recurso Perfil {#extending-profile}

Primeiro, é necessário estender o **[!UICONTROL Profile]** recurso com um novo campo correspondente ao grupo de controle. Depois que o fluxo de trabalho for executado, esse campo será verificado para verificar os perfis que foram excluídos do destino.

1. Em **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom Resources]**, clique em **[!UICONTROL Create]**.
1. Se ainda não o estendeu, selecione **[!UICONTROL Extend an existing resource]** e escolha o **[!UICONTROL Profile]** recurso.
1. Na **[!UICONTROL Data structure]** guia, adicione um novo campo para o grupo de controle e selecione **[!UICONTROL Boolean]** para o **[!UICONTROL Type]** campo.

   ![](assets/wkf_control-group-profile-field.png)

1. Na **[!UICONTROL Screen definition]** guia, desdobre a **[!UICONTROL Detail screen configuration]** seção e selecione o campo que você acabou de criar para que seja exibido para cada perfil.

   ![](assets/wkf_control-group-profile-field-screen.png)

1. Salve as alterações.
1. Atualize a estrutura do banco de dados para publicar o recurso **[!UICONTROL Profile]** estendido. Consulte [Publicação de um recurso](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)personalizado.

Para obter mais informações sobre como estender um recurso personalizado, consulte Etapas [principais para adicionar um recurso](../../developing/using/key-steps-to-add-a-resource.md).

## Criação de um workflow {#creating-a-workflow}

1. Em **[!UICONTROL Marketing Activities]**, clique **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**.

As etapas detalhadas para criar um fluxo de trabalho são apresentadas na seção [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md) .

## Criando uma atividade de consulta {#create-a-query-activity}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arraste e solte um **[!UICONTROL Query activity]**.
1. Clique duas vezes na atividade para definir sua meta.
1. Por exemplo, em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profile]**, selecione **[!UICONTROL Age]** com o operador **[!UICONTROL Greater than]** e digite 25 no **[!UICONTROL Value]** campo.
1. Click **[!UICONTROL Confirm]**.

As etapas detalhadas para criar uma atividade de Consulta são apresentadas na seção [Consulta](../../automating/using/query.md) .

## Criação de uma atividade de segmentação {#creating-a-segmentation-activity}

1. Arraste e solte uma **[!UICONTROL Segmentation]** atividade e clique duas vezes nela.
1. Na **[!UICONTROL Segments]** guia, selecione um segmento para editar.
1. Na **[!UICONTROL Configuration]** guia desse segmento, selecione a **[!UICONTROL Limit the population of this segment]** opção.

   ![](assets/wkf_control-segment-configuration.png)

1. Na **[!UICONTROL Limitation]** guia, verifique se a **[!UICONTROL Random sampling]** opção está selecionada.

   ![](assets/wkf_control-segment-limitation.png)

1. Defina uma porcentagem da população inicial, por exemplo 10%, e clique em **[!UICONTROL Confirm]**. O grupo de controle será composto por 10% da população-alvo, selecionada aleatoriamente.
1. Na **[!UICONTROL Advanced options]** guia, selecione a **[!UICONTROL Generate complement]** opção e preencha os campos **[!UICONTROL Transition label]** e **[!UICONTROL Segment code]** .

   ![](assets/wkf_control-segment-advanced.png)

1. Click **[!UICONTROL Confirm]**.

As etapas detalhadas para criar uma atividade de Segmentação são apresentadas na seção [Segmentação](../../automating/using/segmentation.md) .

## Criando uma atividade de email {#creating-an-email-activity}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, arraste e solte um **[!UICONTROL Email Delivery]** depois do segmento de destino principal.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) para editá-la.
1. Selecione **[!UICONTROL Single send email]** e clique em **[!UICONTROL Next]**.
1. Selecione um modelo de email e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do email e clique em **[!UICONTROL Next]**.
1. Para criar o layout do seu email, clique em **[!UICONTROL Use the Email Designer]**.
1. Edite e salve seu conteúdo.
1. Na **[!UICONTROL Schedule]** seção do painel de mensagens, desmarque a opção **[!UICONTROL Request confirm antes de enviar mensagens}** .

As etapas detalhadas para criar uma atividade de Email são apresentadas na seção de entrega [de](../../automating/using/email-delivery.md) Email.

## Criação de uma atividade de dados Update {#creating-update-data-activity}

1. Arraste e solte uma **[!UICONTROL Update data]** atividade após o segmento do grupo de controle.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Na **[!UICONTROL General]** guia, selecione **[!UICONTROL Update]** na lista **[!UICONTROL Operation type]** suspensa.
1. Na **[!UICONTROL Identification]** guia, selecione a **[!UICONTROL Directly using the targeting dimension]** opção.
1. Selecione o **[!UICONTROL Profile]** recurso que você estendeu anteriormente como a dimensão a ser atualizada.

   ![](assets/wkf_control-update-identification.png)

1. Na **[!UICONTROL Fields to update]** guia, selecione o campo do grupo de controle que você adicionou ao **[!UICONTROL Profile]** recurso como o **[!UICONTROL Destination]** e insira true como a condição.

   ![](assets/wkf_control-update-fields-to-update.png)

1. Click **[!UICONTROL Confirm]**.

As etapas detalhadas para criar uma atividade de dados de Atualização são apresentadas na seção [Atualizar dados](../../automating/using/update-data.md) .

## Execução do fluxo de trabalho {#running-the-workflow}

Clique em **[!UICONTROL Start]** para executar o fluxo de trabalho.

Depois que o fluxo de trabalho é executado, a população do grupo de controle é excluída e a mensagem é enviada para o destino principal restante.

O recurso **[!UICONTROL Profile]** é atualizado da seguinte forma: se um perfil estiver no grupo de controle, o campo correspondente será marcado.

![](assets/wkf_control-group-profile-checked.png)

Agora você pode comparar como os destinatários da mensagem reagirão em comparação com o pequeno grupo que foi excluído da mensagem e não a recebeu.

## Reutilizando o mesmo grupo de controle {#reusing-same-control-group}

O exemplo acima permite criar um grupo de controle global, pois ele é armazenado como um atributo de perfil independentemente das entregas. Na verdade, o novo campo "Grupo de controle" criado como parte da extensão de **[!UICONTROL Profile]** recursos é atualizado após a execução do fluxo de trabalho acima.

Consequentemente, da próxima vez que você quiser usar o mesmo grupo de controle, poderá segmentar no novo campo "Grupo de controle" em vez de fazer uma segmentação aleatória.

Para fazer isso:
1. Ao criar a **[!UICONTROL Segmentation]** atividade, selecione o segmento a ser editado na **[!UICONTROL Segments]** guia.
1. Na **[!UICONTROL Configuration]** guia desse segmento, certifique-se de não selecionar a **[!UICONTROL Limit the population of this segment]** opção.
1. Na **[!UICONTROL Filtering]** guia, arraste e solte **[!UICONTROL Profiles (attributes)]** no espaço de trabalho principal.

   ![](assets/wkf_control-group-segment-profiles-attributes.png)

1. Na **[!UICONTROL Add a rule - Profiles (attributes)]** janela, selecione "Grupo de controle" (o campo adicionado ao **[!UICONTROL Profile]** recurso) e selecione **[!UICONTROL Yes]** como a condição de filtro.

   ![](assets/wkf_control-group-segment-profiles-attributes-field.png)