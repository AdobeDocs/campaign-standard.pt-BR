---
title: Entrega por correio direto
description: A atividade de delivery de mala direta permite configurar o envio de uma única mala direta de envio ou de uma mala direta recorrente em um fluxo de trabalho.
page-status-flag: never-activated
uuid: bfa7b176-a17c-4079-a073-64b8ce4788ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: b9ddb2a0-54ff-4ada-be6f-8109fa06d461
context-tags: directMail,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 1%

---


# Entrega por correio direto{#direct-mail-delivery}

## Descrição {#description}

![](assets/paper.png)

![](assets/recurrentpaper.png)

A **[!UICONTROL Direct mail delivery]** atividade permite que você configure e prepare um arquivo contendo dados de perfil que deseja usar para uma campanha de mala direta. Esta pode ser uma correspondência direta que é utilizada apenas uma vez, ou pode ser uma correspondência direta **recorrente** .

Os emails diretos padrão são enviados uma vez.

Os emails recorrentes permitem que você envie a mesma mala direta várias vezes para públicos alvos diferentes em um período definido. Você pode agregação os delivery por período para obter relatórios que correspondam às suas necessidades.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Direct mail delivery]** atividade geralmente é usada para automatizar a preparação de um arquivo que contém dados de perfil. Esse arquivo pode ser enviado para um parceiro/provedor responsável pelo envio.

Quando vinculado a um scheduler, você pode definir emails diretos recorrentes.

Os recipient de mala direta são definidos a montante da atividade no mesmo fluxo de trabalho, por meio de atividades de direcionamento, como query, interseções etc. Perfis cujo endereço de correspondência não é especificado são excluídos automaticamente quando a mala direta é preparada.

A preparação da mensagem é acionada de acordo com os parâmetros de execução do fluxo de trabalho. No painel da mensagem, você pode selecionar se deseja solicitar ou não uma confirmação manual para enviar a mensagem (obrigatório por padrão). Você pode start o fluxo de trabalho manualmente ou colocar uma atividade de scheduler no fluxo de trabalho para automatizar a execução.

**Tópicos relacionados:**

* [Caso de uso: Conexão de delivery de email e de mala direta](../../automating/using/coupling-email-direct-mail.md)
* [Sobre o correio direto](../../channels/using/about-direct-mail.md)

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Direct mail delivery]** atividade no seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.

   >[!NOTE]
   >
   >Você pode acessar as propriedades gerais e as opções avançadas da atividade (e não do próprio delivery) por meio do ![](assets/dlv_activity_params-24px.png) botão das ações rápidas da atividade. Esse botão é específico para as atividades do canal. As propriedades da mala direta podem ser acessadas pela barra de ação no painel de mala direta.

1. Selecione o modo de envio de mala direta:

   * **[!UICONTROL Direct mail]**: a correspondência direta é enviada uma única vez. Você pode especificar aqui se deseja ou não adicionar uma transição de saída à atividade. Os diferentes tipos de transições são detalhados na etapa 7 deste procedimento.
   * **[!UICONTROL Recurring direct mail]**: a correspondência direta é enviada várias vezes, de acordo com a frequência definida numa **[!UICONTROL Scheduler]** atividade. Selecione o período de agregação dos envios. Isso permite que você agrupe todos os envios que ocorrem durante o período definido em uma única correspondência direta, também chamada de Execução **** recorrente e que podem ser acessados a partir da lista de atividade de marketing do aplicativo.

      Por exemplo, para uma mensagem de aniversário recorrente, que é processada diariamente, você pode optar por agregação dos envios por mês. Isso permite que você receba relatórios em seu delivery mensalmente, embora o email seja processado todos os dias.

      >[!NOTE]
      >
      >Para emails diretos recorrentes, um novo arquivo é gerado em cada execução do fluxo de trabalho. O período de agregação selecionado não afeta esse comportamento.

1. Selecione um tipo de mala direta. Os tipos de mala direta vêm de modelos definidos no menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** .
1. Insira as propriedades gerais da mala direta. Também é possível anexá-lo a uma campanha existente. A etiqueta da atividade de delivery do fluxo de trabalho é atualizada com a etiqueta de mala direta.
1. Defina o conteúdo da mala direta. Consulte a seção sobre edição [de](../../designing/using/personalization.md)conteúdo.
1. Por padrão, a **[!UICONTROL Direct mail delivery]** atividade não inclui nenhuma transição de saída. Se você quiser adicionar uma transição de saída à sua **[!UICONTROL Direct mail delivery]** atividade, vá para a guia **[!UICONTROL General]** das opções avançadas de atividade ( ![](assets/dlv_activity_params-24px.png) botão nas ações rápidas de atividade) e depois verifique uma das seguintes opções:

   * **[!UICONTROL Add outbound transition without the population]**: isso permite gerar uma transição de saída que contém exatamente a mesma população da transição de entrada. Esta transição contém o arquivo gerado pela atividade de mala direta e a população bruta recebida pela atividade de mala direta.
   * **[!UICONTROL Add outbound transition with the population]**: isso permite gerar uma transição de saída que contém a população para a qual a correspondência direta será enviada. Os membros do público alvo foram excluídos durante a preparação da mala direta (quarentena, endereço inválido, etc.) são excluídos desta transição. A transição também contém o arquivo gerado pela correspondência direta.

1. Confirme a configuração da atividade e salve o fluxo de trabalho.

Ao reabrir a atividade, você é levado diretamente para o painel de mala direta. Somente seu conteúdo pode ser editado.

Por padrão, iniciar um fluxo de trabalho de delivery aciona somente a preparação da mensagem. O envio de mensagens criadas a partir de um fluxo de trabalho ainda precisa ser confirmado depois que o fluxo de trabalho for iniciado. Mas a partir do painel de mensagem e somente se a mensagem tiver sido criada a partir de um fluxo de trabalho, você poderá desativar a **[!UICONTROL Request confirmation before sending messages]** opção. Ao desmarcar essa opção, as mensagens são enviadas sem aviso prévio após a preparação.

## Observações {#remarks}

Os delivery criados em um fluxo de trabalho podem ser acessados na lista de atividade de marketing do aplicativo. Você pode visualização o status de execução do fluxo de trabalho usando o painel. Os links no painel de resumo de mala direta permitem acessar diretamente os elementos vinculados (fluxo de trabalho, campanha, delivery pai no caso de uma mala direta recorrente).

![](assets/wkf_display_parent_elements_direct_mail.png)

As execuções de delivery recorrentes são mascaradas por padrão. Para visualização, marque a opção **[!UICONTROL Show recurring executions]** no painel de pesquisa do atividade de marketing.

![](assets/wkf_display_recurrent_executions_direct_mail.png)

Nos delivery principais, que podem ser acessados a partir da lista de atividade de marketing ou diretamente por meio das execuções recorrentes associadas, é possível visualização o número total de emails que foram processados (de acordo com o período de agregação especificado quando a **[!UICONTROL Direct mail delivery]** atividade foi configurada). Para fazer isso, abra a visualização detalhada do bloco pai do delivery **[!UICONTROL Deployment]** selecionando o ![](assets/wkf_dlv_detail_button.png) botão.

![](assets/wkf_display_recurrent_executions_3_direct_mail.png)
