---
title: Entrega por correio direto
description: A atividade de entrega de mala direta permite que você configure o envio de uma única mala direta de envio ou de uma mala direta recorrente em um fluxo de trabalho.
page-status-flag: nunca ativado
uuid: bfa7b176-a17c-4079-a073-64b8ce4788ed
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: atividades de canal
discoiquuid: b9ddb2a0-54ff-4ada-be6f-8109fa06d461
context-tags: directMail,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Entrega por correio direto{#direct-mail-delivery}

## Descrição {#description}

![](assets/paper.png)

![](assets/recurrentpaper.png)

A **[!UICONTROL Direct mail delivery]** atividade permite que você configure e prepare um arquivo contendo dados de perfil que você deseja usar para uma campanha de mala direta. Esta pode ser uma correspondência direta que é utilizada apenas uma vez, ou pode ser uma correspondência direta **recorrente** .

As mensagens diretas padrão são enviadas uma vez.

Os emails recorrentes permitem que você envie a mesma mala direta várias vezes para alvos diferentes em um período definido. Você pode agregar as entregas por período para obter relatórios que correspondam às suas necessidades.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Direct mail delivery]** atividade é geralmente usada para automatizar a preparação de um arquivo que contém dados de perfil. Esse arquivo pode ser enviado para um parceiro/provedor responsável pelo envio.

Quando vinculado a um programador, você pode definir emails diretos recorrentes.

Os destinatários de mala direta são definidos no upstream da atividade no mesmo fluxo de trabalho, por meio de atividades de direcionamento, como consultas, interseções etc. Os perfis cujo endereço de correspondência não é especificado são excluídos automaticamente quando a mala direta é preparada.

A preparação da mensagem é acionada de acordo com os parâmetros de execução do fluxo de trabalho. No painel de mensagens, você pode selecionar se deseja solicitar ou não uma confirmação manual para enviar a mensagem (obrigatório por padrão). Você pode iniciar o fluxo de trabalho manualmente ou colocar uma atividade do programador no fluxo de trabalho para automatizar a execução.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Direct mail delivery]** atividade em seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.

   >[!NOTE]
   >
   >Você pode acessar as propriedades gerais e as opções avançadas da atividade (e não da entrega em si) por meio do ![](assets/dlv_activity_params-24px.png) botão das ações rápidas da atividade. Esse botão é específico para as atividades do canal. As propriedades da mala direta podem ser acessadas pela barra de ação no painel de mala direta.

1. Selecione o modo de envio de mala direta:

   * **[!UICONTROL Direct mail]**: a correspondência direta é enviada uma única vez. Você pode especificar aqui se deseja ou não adicionar uma transição de saída à atividade. Os diferentes tipos de transição estão detalhados na etapa 7 deste procedimento.
   * **[!UICONTROL Recurring direct mail]**: a correspondência direta é enviada várias vezes, de acordo com a frequência definida numa **[!UICONTROL Scheduler]** atividade. Selecione o período de agregação dos envios. Isso permite agrupar todos os envios que ocorrem durante o período definido em uma única correspondência direta, também chamada de Execução **** recorrente e que podem ser acessados na lista de atividades de marketing do aplicativo.

      Por exemplo, para uma mensagem de aniversário recorrente, que é processada diariamente, você pode escolher agregar os envios por mês. Isso permite que você receba relatórios sobre sua entrega mensalmente, embora o email seja processado todos os dias.

      >[!NOTE]
      >
      >Para emails diretos recorrentes, um novo arquivo é gerado em cada execução do fluxo de trabalho. O período de agregação selecionado não afeta esse comportamento.

1. Selecione um tipo de mala direta. Os tipos de mala direta vêm de modelos definidos no menu **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** .
1. Insira as propriedades gerais da correspondência direta. Você também pode anexá-la a uma campanha existente. A etiqueta da atividade de entrega do fluxo de trabalho é atualizada com a etiqueta de mala direta.
1. Defina o conteúdo da mala direta. Consulte a seção sobre edição [de](../../designing/using/personalization.md)conteúdo.
1. Por padrão, a **[!UICONTROL Direct mail delivery]** atividade não inclui nenhuma transição de saída. Se você deseja adicionar uma transição de saída à sua **[!UICONTROL Direct mail delivery]** atividade, vá para a **[!UICONTROL General]** guia das opções de atividade avançada ( ![](assets/dlv_activity_params-24px.png) botão nas ações rápidas da atividade) e verifique uma das seguintes opções:

   * **[!UICONTROL Add outbound transition without the population]**: isso permite gerar uma transição de saída que contém exatamente a mesma população da transição de entrada. Essa transição contém o arquivo gerado pela atividade de mala direta e a população bruta recebida pela atividade de mala direta.
   * **[!UICONTROL Add outbound transition with the population]**: isso permite gerar uma transição de saída que contém a população para a qual a correspondência direta será enviada. Os membros do alvo excluídos durante a preparação da mala direta (quarentena, endereço inválido, etc.) são excluídos desta transição. A transição também contém o arquivo gerado pela mala direta.

1. Confirme a configuração da atividade e salve o fluxo de trabalho.

Ao reabrir a atividade, você é direcionado diretamente para o painel de mala direta. Somente seu conteúdo pode ser editado.

Por padrão, iniciar um fluxo de trabalho de entrega aciona somente a preparação da mensagem. O envio de mensagens criadas a partir de um fluxo de trabalho ainda precisa ser confirmado depois que o fluxo de trabalho for iniciado. Mas no painel de mensagens, e somente se a mensagem foi criada a partir de um fluxo de trabalho, você pode desativar a **[!UICONTROL Request confirmation before sending messages]** opção. Ao desmarcar essa opção, as mensagens são enviadas sem aviso prévio após a preparação.

## Observações {#remarks}

As entregas criadas em um fluxo de trabalho podem ser acessadas na lista de atividades de marketing do aplicativo. Você pode exibir o status de execução do fluxo de trabalho usando o painel. Os links no painel de resumo de mala direta permitem acessar diretamente os elementos vinculados (fluxo de trabalho, campanha, entrega principal no caso de uma mala direta recorrente).

![](assets/wkf_display_parent_elements_direct_mail.png)

As execuções de entregas recorrentes são mascaradas por padrão. Para exibi-los, marque a opção no painel de pesquisa das atividades de marketing. **[!UICONTROL Show recurring executions]**

![](assets/wkf_display_recurrent_executions_direct_mail.png)

Nas entregas principais, que podem ser acessadas da lista de atividades de marketing ou diretamente por meio das execuções recorrentes associadas, você pode exibir o número total de emails que foram processados (de acordo com o período de agregação especificado quando a **[!UICONTROL Direct mail delivery]** atividade foi configurada). Para fazer isso, abra a exibição detalhada do **[!UICONTROL Deployment]** bloco da entrega pai selecionando ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3_direct_mail.png)

## Exemplo {#example}

Um exemplo de **[!UICONTROL Direct mail delivery]** está disponível no capítulo Mala [direta](../../channels/using/example-of-direct-mail-in-a-workflow.md) .
