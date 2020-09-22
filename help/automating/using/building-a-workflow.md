---
title: Criar um workflow
description: Esta seção detalha os principais princípios e as práticas recomendadas para criar um novo workflow.
page-status-flag: never-activated
uuid: 11374f64-8d34-40da-937b-09f419250f4c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: c26fcb0e-19d5-4bd5-b7d6-2d22ce92ad90
context-tags: workflow,wizard;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bbb059c2094558ec02661cb6f41d50a91038d58b
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 100%

---


# Criar um workflow{#building-a-workflow}

Esta seção detalha os principais princípios e as práticas recomendadas para criar um novo workflow.

## Princípios operacionais do workflow{#workflow-operating-principles}

Um workflow é uma **sequência de atividades configuráveis**. Cada atividade tem uma função específica no processo. O resultado de cada atividade é encaminhado à atividade seguinte por uma **transição**, representada por uma seta.

O tipo de dados trocado entre uma atividade e outra pode afetar a forma como as atividades seguintes são configuradas. Por exemplo, se uma população for estabelecida antes da atividade de delivery de email, ela poderá servir como destino do email em questão.

É possível abrir atividades para verificar ou editar parâmetros antes ou depois de executar o workflow.

É possível abrir transições para verificar se os dados enviados estão corretos durante ou após a execução do workflow. Para acessar a visualização detalhada das transições, é necessário marcar a opção **[!UICONTROL Keep interim results]** na seção **[!UICONTROL Execution]** das propriedades do workflow.

>[!CAUTION]
>
>Essa opção consome bastante espaço do disco e foi projetada para ajudar a criar um fluxo de trabalho e garantir a configuração e o comportamento adequados. Deixe-a desmarcada nas instâncias de produção.

![](assets/workflow_overview.png)


## Criação de um workflow {#creating-a-workflow}

Você pode criar um workflow a partir de um programa, de uma campanha ou da lista de atividades de marketing.

A criação de uma atividade de marketing é detalhada na seção [Criar atividades de marketing](../../start/using/marketing-activities.md#creating-a-marketing-activity).

1. Depois de começar a criar uma atividade de marketing do tipo workflow, selecione o template que você deseja usar.

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >Cada atividade de marketing oferece vários tipos por padrão. Você pode pré-configurar determinados parâmetros de acordo com as suas necessidades. Para obter mais informações, consulte a seção [Gerenciar templates](../../start/using/marketing-activity-templates.md).

1. Insira as propriedades gerais do workflow.

   ![](assets/workflow_creation_2.png)

   É possível inserir um nome no campo **Label** e modificar a ID. O nome da atividade e a ID são exibidos na interface, mas não são visíveis pelos recipients da mensagem.

   >[!NOTE]
   >
   >Você pode criar seu workflow em uma campanha pai a partir da lista de atividades de marketing. Esse workflow pode ser vinculado a uma campanha por meio da seleção de uma campanha que já foi criada.

   É possível adicionar uma descrição que o usuário pode ver no conteúdo da campanha.

   Como facilita a localização e a solução de problemas se não estiverem executando da forma esperada, a Adobe recomenda que os workflows tenham nomes e rótulos adequados: preencha o campo de descrição do workflow para resumir o processo para que o operador possa entender facilmente.

1. Confirme a criação da atividade. Em seguida, o painel da atividade será exibido. Para obter mais informações, consulte a seção [Interface de fluxo de trabalho](../../automating/using/workflow-interface.md).

1. Quando o workflow estiver pronto para ser configurado, você poderá acessar opções adicionais clicando no botão **[!UICONTROL Edit properties]**. Por exemplo, é possível definir um fuso horário específico para usar por padrão em todas as atividades do workflow. Por padrão, o fuso horário do workflow é aquele definido para o operador atual do Campaign.

   ![](assets/workflow_properties.png)

**Tópicos relacionados:**

* Vídeo sobre [Criação de um workflow](https://docs.adobe.com/content/help/pt-BR/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.translate.html)
* [Propriedades do workflow](../../automating/using/managing-execution-options.md)

## Adição e vínculo de atividades {#adding-and-linking-activities}

Você deve definir as várias atividades e as vincular no diagrama.

>[!NOTE]
>
>Se a paleta não for exibida, clique no primeiro botão na barra de ferramentas para exibi-la.

Atividades são agrupadas por categoria dentro das diferentes seções da paleta.

* A primeira seção contém [atividades de direcionamento](../../automating/using/about-targeting-activities.md)
* A segunda seção contém as [atividades de execução](../../automating/using/about-execution-activities.md), que são usadas principalmente para coordenar outras atividades.
* A terceira seção contém atividades que podem ser usadas para enviar mensagens em diferentes [canais](../../automating/using/about-channel-activities.md). As atividades nessa seção podem variar dependendo dos canais que estão ativados na sua instância.
* A quarta seção contém [atividades de manipulação de arquivos e gestão de dados](../../automating/using/about-data-management-activities.md).

Criação do diagrama:

1. Adicione uma atividade, arrastando-a da paleta e soltando-a no diagrama.

   Por exemplo, adicione uma atividade **[Start](../../automating/using/start-and-end.md)** e depois uma atividade **[Email delivery](../../automating/using/email-delivery.md)** no diagrama.

1. Vincule as atividades, arrastando a atividade de transição **Start** e soltando-a na atividade **Email delivery**.

   >[!NOTE]
   >
   >Você pode vincular automaticamente uma atividade à atividade anterior, colocando a nova atividade no final da transição da anterior.

1. Adicione as atividades necessárias e vincule-as para concluir seu workflow.

   >[!NOTE]
   >
   >Você também pode duplicar atividades existentes, copiando-as. Dessa forma, você mantém as configurações que foram originalmente definidas. Para obter mais informações, consulte [Duplicar atividades do workflow](../../automating/using/workflow-interface.md#duplicating-workflow-activities).

Assim que suas atividades de workflow estiverem vinculadas, você poderá personalizar as transições entre elas com o **rótulo** de sua escolha. Para fazer isso, clique duas vezes na transição para acessar suas propriedades.

Além disso, as atividades **[!UICONTROL Targeting]** e **[!UICONTROL Data management (ETL)]** permitem definir **códigos de segmento** para suas transições de saída. Em seguida, você poderá criar relatórios com base nesses códigos de segmento para medir a eficiência das suas campanhas de marketing. Para obter mais informações, consulte [esta seção](../../reporting/using/creating-a-report-workflow-segment.md).

**Casos de uso de workflow:**

* [Caso de uso: criar delivery por email uma vez por semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: criar um delivery segmentado na localização](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: criar deliveries com um complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: workflow de redirecionamento enviando um novo delivery para não abridores](../../automating/using/workflow-cross-channel-retargeting.md)

## Configuração de atividades {#configuring-activities}

Por padrão, as atividades não estão definidas e não processarão os dados corretamente se não estiverem configuradas. Cada atividade contém várias guias para gerenciar configurações específicas e opções genéricas de atividades, como transições de saída, rótulos etc.

1. Verifique se todas as atividades estão conectadas corretamente. Algumas atividades exigem a detecção da estrutura ou da natureza dos dados recebidos para oferecer as opções de configuração corretas.
1. Clique duas vezes em uma atividade ou selecione-a e clique na ação **[!UICONTROL Edit]** contextual para abrir sua janela de configuração.
1. Edite o rótulo da atividade.
1. Defina todas as opções diferentes de que você precisa para processar os dados. Consulte a seção específica da atividade dessa documentação para saber mais sobre as opções possíveis para cada atividade.
1. Salve a atividade e repita essas operações para cada atividade do workflow.
1. Salve o workflow.
