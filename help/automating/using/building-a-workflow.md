---
title: Criação de um fluxo de trabalho
seo-title: Criação de um fluxo de trabalho
description: Criação de um fluxo de trabalho
seo-description: Esta seção detalha os principais princípios e práticas recomendadas para criar um novo fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 11374 f 64-8 d 34-40 da -937 b -09 f 419250 f 4 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: fluxo de trabalho-geral-operação
discoiquuid: c 26 fcb 0 e -19 d 5-4 bd 5-b 7 d 6-2 d 22 ce 92 ad 90
context-tags: fluxo de trabalho, assistente; fluxo de trabalho, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# Criação de um fluxo de trabalho{#building-a-workflow}

Esta seção apresenta os principais princípios e práticas recomendadas para criar um novo fluxo de trabalho:

* Criação de um fluxo de trabalho.
* Adicionar e vincular atividades.
* Configuração das atividades.

## Criação de um fluxo de trabalho {#creating-a-workflow}

Você pode criar um fluxo de trabalho a partir de um programa, uma campanha ou uma lista de atividades de marketing.

A criação de uma atividade de marketing é detalhada na seção [Criar atividades](../../start/using/marketing-activities.md#creating-a-marketing-activity) de marketing.

1. Depois de começar a criar uma atividade de marketing de tipo de fluxo de trabalho, selecione o modelo que deseja usar.

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >Cada atividade de marketing oferece vários tipos por padrão. Eles permitem pré-configurar determinados parâmetros de acordo com suas necessidades. Para obter mais informações, consulte [a](../../start/using/about-templates.md) seção Gerenciar modelos.

1. Insira as propriedades gerais do fluxo de trabalho.

   ![](assets/workflow_creation_2.png)

   Você pode inserir um nome no campo **Rótulo** e modificar a ID. O nome da atividade e sua ID aparecem na interface, mas não são visíveis pelos destinatários da mensagem.

   >[!NOTE]
   >
   >Você pode criar seu fluxo de trabalho em uma campanha principal da lista de atividades de marketing. Você pode vincular esse fluxo de trabalho a uma campanha selecionando um que já foi criado.

   Você pode adicionar uma descrição que o usuário pode visualizar no conteúdo da campanha.

   Como facilita encontrar e solucionar problemas se não estiverem realizando das formas esperadas, a Adobe recomenda dar aos seus fluxos de trabalho nomes e rótulos próprios: preencha o campo de descrição do fluxo de trabalho para resumir o processo a ser executado para que o operador possa entendê-lo facilmente.

1. Confirme se a atividade e o painel para essa atividade serão exibidos. Para obter mais informações sobre isso, consulte a [seção da interface](../../automating/using/workflow-interface.md) Fluxo de trabalho.

**Tópico relacionado:**

[Criação de](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-workflow-feature-video-use.html) um vídeo de fluxo de trabalho

## Adição e vinculação de atividades {#adding-and-linking-activities}

Agora, você deve definir as várias atividades e vinculá-las em conjunto no diagrama.

>[!NOTE]
>
>Se a paleta não for exibida, clique no primeiro botão da barra de ferramentas para exibi-la.

As atividades são agrupadas por categoria dentro das diferentes seções da paleta.

* A primeira seção contém atividades de definição de metas.
* A segunda seção contém as atividades de execução, que são usadas principalmente para coordenar outras atividades.
* A terceira seção contém atividades que podem ser usadas para enviar mensagens em diferentes canais. As atividades nesta seção podem variar dependendo dos canais que estão ativados na sua instância.
* A quarta seção contém atividades de manipulação de arquivos e gerenciamento de dados.

Para criar o diagrama:

1. Adicione uma atividade arrastando-a da paleta e soltando-a no diagrama.

   Por exemplo, adicione uma atividade **de Início** e uma **atividade de entrega** de email no diagrama.

1. Vincule as atividades ao arrastar a **transição** de atividade Iniciar e soltando-a na atividade **de entrega** de email.

   >[!NOTE]
   >
   >É possível vincular automaticamente uma atividade ao anterior colocando a nova atividade no final da transição do anterior.

1. Adicione as atividades necessárias e vincule-as para concluir seu fluxo de trabalho.

   >[!NOTE]
   >
   >Também é possível duplicar atividades existentes copiando-as. Dessa forma, você mantém as configurações definidas originalmente. Para saber mais sobre isso, consulte [Duplicar atividades](../../automating/using/workflow-interface.md#duplicating-workflow-activities)do fluxo de trabalho.

Uma vez que as atividades de fluxo de trabalho são vinculadas juntas, você pode personalizar as transições com **o rótulo** de sua escolha. Para fazer isso, clique duas vezes na transição para acessar suas propriedades.

Além disso, **[!UICONTROL Targeting]****[!UICONTROL Data management (ETL)]** as atividades permitem definir códigos **de segmento** para suas transições de saída. Você pode então criar relatórios com base nesses códigos de segmento para medir a eficiência das suas campanhas de maketing. For more on this, refer to [this section](../../reporting/using/creating-a-report-workflow-segment.md).

**Casos de uso do fluxo de trabalho:**

* [Caso de uso: Criar uma entrega de email uma vez a semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: Criação de uma entrega segmentada na localização](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: Criação de entregas com um complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: Fluxo de trabalho de redefinição de metas enviando uma nova entrega para não-openers](../../automating/using/workflow-cross-channel-retargeting.md)

## Configuração de atividades {#configuring-activities}

Por padrão, as atividades não são definidas e não processarão os dados corretamente se não estiverem configuradas. Cada atividade contém várias guias para gerenciar configurações específicas e opções genéricas de atividade, como transições de saída, rótulos etc.

1. Verifique se todas as atividades estão corretamente conectadas. Algumas atividades exigem a detecção da estrutura ou da natureza dos dados recebidos para oferecer as opções de configuração corretas.
1. Clique duas vezes em uma atividade ou selecione-a e clique na **[!UICONTROL Edit]** ação contextual para abrir sua janela de configuração.
1. Edite o rótulo da atividade.
1. Defina todas as opções diferentes necessárias para processar os dados. Consulte a seção específica da atividade desta documentação para saber as opções possíveis para cada atividade.
1. Salve a atividade e repita essas operações para cada atividade do fluxo de trabalho.
1. Salve o fluxo de trabalho.
