---
title: Criação de públicos-alvo
description: Saiba como criar audiências no Adobe Campaign.
page-status-flag: never-activated
uuid: fe99b31b-a949-4832-b0e6-2b36d1c8be80
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: df8bdcfb-be5e-4044-bc26-aa3466accbbe
context-tags: readAudience,main;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Criação de públicos-alvo{#creating-audiences}

## Criando audiências query {#creating-query-audiences}

Esta seção descreve como criar uma audiência de **Query** . Você também pode criar audiências a partir da importação de um arquivo ou direcionamento em um [fluxo de trabalho](../../automating/using/get-started-workflows.md).

Na lista da audiência, é possível criar audiências executando query em perfis Adobe Campaign ou importando uma audiência da Adobe Experience Cloud.

1. Vá para a lista da audiência por meio da **[!UICONTROL Audiences]** guia ou do cartão.

   ![](assets/audiences_query_1.png)

1. Selecione **[!UICONTROL Create]** para acessar a tela para criar uma nova audiência.

   ![](assets/audiences_query.png)

1. Dê um nome à sua audiência. O rótulo da audiência é usado na lista do audiência e na paleta da ferramenta query.
1. Escolha um tipo de **[!UICONTROL Query]** audiência: as audiências definidas por um query são recompostas a cada nova utilização.

   ![](assets/audience_type_selection.png)

1. Em seguida, selecione o **[!UICONTROL Targeting dimension]** que deseja usar para filtrar seus clientes. Cada audiência é feita de um único targeting dimension. Por exemplo, não é possível criar uma audiência composta de perfis, perfis de teste e assinantes. For more on targeting dimensions, refer to [this page](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Crie o query para definir a população da audiência. Consulte a seção sobre [edição de query](../../automating/using/editing-queries.md).
1. Clique no **[!UICONTROL Create]** botão para salvar sua audiência.

>[!NOTE]
>
>É possível adicionar uma descrição a essa audiência e definir as autorizações de acesso por meio do **[!UICONTROL Edit properties]** ícone.

## Criando audiências listas {#creating-list-audiences}

Esta seção descreve como criar uma audiência de **Lista** após a definição de metas em um fluxo de trabalho. Você também pode criar audiências importando um arquivo para um [fluxo de trabalho](../../automating/using/get-started-workflows.md) ou por meio de um query do **[!UICONTROL Audiences]** menu.

To create a **List** audience, the steps are as follows:

1. Na guia **Marketing atividade** , clique em **Criar** e selecione **Fluxo de trabalho**.

   ![](assets/audiences_list_1.png)

1. Arraste e solte e configure as atividades de definição de metas que permitirão selecionar uma população que tenha uma dimensão **conhecida** . A lista de atividades disponíveis e suas configurações são detalhadas na seção [Direcionamento de atividades](../../automating/using/about-targeting-activities.md) .

   É possível usar uma **[!UICONTROL Query]** atividade ou importar dados usando uma **[!UICONTROL Load file]** atividade antes de usar uma **[!UICONTROL Reconciliation]** atividade para identificar a dimensão dos dados importados. Neste caso, queremos público alvo com uma **[!UICONTROL Query]** atividade aos recipient que assinaram a Newsletter Sport .

   ![](assets/audiences_list_2.png)

1. Após a definição de metas, arraste e solte uma **[!UICONTROL Save audience]** atividade no seu fluxo de trabalho. Por exemplo, você pode escolher **[!UICONTROL Create or update an audience]**, isso permite criar e atualizar automaticamente sua audiência com novos dados. Nesse caso, adicione uma **[!UICONTROL Scheduler]** atividade no início do fluxo de trabalho.

   Para obter mais informações sobre como configurar essa atividade, consulte a seção [Salvar audiência](../../automating/using/save-audience.md) .

   ![](assets/audiences_list_3.png)

1. Salve e start o fluxo de trabalho.

   Como o **[!UICONTROL Save audience]** é colocado depois de uma definição de metas com uma dimensão conhecida, as audiências criadas por meio dessa atividade são audiências **Listas** .

   O conteúdo da audiência salva fica disponível na visualização detalhada da audiência que pode ser acessada por meio da lista do audiência. As colunas disponíveis nesta visualização correspondem às colunas da transição de entrada da atividade de salvamento do fluxo de trabalho. Por exemplo: as colunas do arquivo importado, os dados adicionais adicionados de um query.

   ![](assets/audiences_list_4.png)

## Criando audiências de arquivos {#creating-file-audiences}

Esta seção detalha como criar uma audiência de **Arquivo** importando um arquivo para um fluxo de trabalho. Você também pode criar audiências a partir de uma atividade de definição de metas em um [fluxo de trabalho](../../automating/using/get-started-workflows.md) ou por meio de um query do **[!UICONTROL Audiences]** menu.

To create a **File** audience, the steps are as follows:

1. Na guia **Marketing atividade** , clique em **Criar** e selecione **Fluxo de trabalho**.
1. Arraste e solte e configure uma **[!UICONTROL Load file]** atividade que permitirá importar uma população que tenha uma dimensão **desconhecida** quando o fluxo de trabalho for executado. Para obter mais informações sobre como configurar essa atividade, consulte a seção [Carregar arquivo](../../automating/using/load-file.md) .

   ![](assets/audience_files_1.png)

1. Drag and drop a **[!UICONTROL Save audience]** activity after the **[!UICONTROL Load file]** activity. Para obter mais informações sobre como configurar essa atividade, consulte a seção [Salvar audiência](../../automating/using/save-audience.md) .
1. Salve e start o fluxo de trabalho.

   ![](assets/audience_files_2.png)

   Como o **[!UICONTROL Save audience]** é colocado após uma importação, a dimensão de dados é desconhecida e as audiências criadas por meio dessa atividade são audiências **de arquivos** .

   O conteúdo da audiência salva fica disponível na visualização detalhada da audiência que pode ser acessada por meio da lista do audiência. As colunas disponíveis nesta visualização correspondem às colunas da transição de entrada da atividade de salvamento do fluxo de trabalho. Por exemplo: as colunas do arquivo importado, os dados adicionais adicionados de um query.

   ![](assets/audience_files_3.png)

## Criação de audiências da Experience Cloud {#creating-experience-cloud-audiences}

O Adobe Campaign permite que você compartilhe e troque audiências com a Adobe Experience Cloud. Uma audiência do tipo da **Experience Cloud** é importada diretamente do serviço principal de Pessoas para o Adobe Campaign com o fluxo de trabalho **[!UICONTROL Import shared audience]** técnico.

Diferentemente da audiência do tipo de **Query** que irá query de perfil, a audiência da **Experience Cloud** é composta por uma lista de IDs de Visitante.

Para que essa integração funcione, é necessário primeiro configurá-la. Para obter mais informações sobre configuração e como importar ou exportar audiências com o serviço principal de Pessoas, consulte a seguinte [seção](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md).

![](assets/audience_peoplecore.png)

## Edição de audiências {#editing-audiences}

Existem diferentes maneiras de editar uma audiência dependendo do tipo de audiência:

* Para editar uma audiência de **Query** , vá para a lista do audiência pelo **[!UICONTROL Audiences]** menu ou pela **[!UICONTROL Audiences]** placa do home page Adobe Campaign.

   Abra a audiência relevante. Todos os elementos de uma audiência criada anteriormente podem ser editados.

   >[!CAUTION]
   >
   >Se você alterar a configuração **[!UICONTROL Filtering dimension]** no query, as regras que foram definidas anteriormente serão perdidas.

* Para editar uma **Lista** ou audiência **de arquivo** , edite o fluxo de trabalho a partir do qual ela foi criada e modifique a **[!UICONTROL Save audience]** atividade. Start o fluxo de trabalho para que a audiência seja modificada.
* Para editar uma audiência da **Experience Cloud** , consulte a seção [Importar/exportar audiências com os principais serviços](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md) de pessoas.

## Excluindo audiências {#deleting-audiences}

Há duas maneiras de excluir uma ou várias audiências. Primeiro, você pode adicionar uma data de expiração à sua audiência

Para fazer isso:

1. Acesse uma de suas audiências.
1. Clique no ![](assets/edit_darkgrey-24px.png) botão para acessar a configuração do audiência.

   ![](assets/audience_delete_2.png)

1. No **[!UICONTROL Expires on]** campo, adicione uma data de expiração à sua audiência.

   ![](assets/audience_delete_3.png)

1. Clique em **[!UICONTROL Confirm]** e em **[!UICONTROL Save]**.

A data de expiração está configurada. Assim que essa data for atingida, sua audiência será automaticamente excluída.

Ou, se for necessário excluir uma audiência, basta selecionar uma ou várias audiências e clicar no **[!UICONTROL Delete element]** botão.

![](assets/audience_delete_1.png)

