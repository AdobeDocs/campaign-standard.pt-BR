---
title: Entrega por email
description: A atividade de entrega de email permite configurar o envio de um único email de envio ou de um email recorrente em um fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: atividades de canal
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-801026055bb
context-tags: entrega,fluxo de trabalho,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Entrega por email{#email-delivery}

## Descrição {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

A **[!UICONTROL Email delivery]** atividade permite configurar o envio de um email em um fluxo de trabalho. Pode ser um **único email de envio** e enviado apenas uma vez, ou um email **recorrente** .

Os emails de envio único são emails padrão, enviados uma vez.

Os emails recorrentes permitem que você envie o mesmo email várias vezes para destinos diferentes em um período definido. Você pode agregar as entregas por período para obter relatórios que correspondam às suas necessidades.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Email delivery]** atividade é geralmente usada para automatizar o envio de um email para um destino calculado no mesmo fluxo de trabalho.

Quando vinculado a um programador, você pode definir emails recorrentes.

Os destinatários de email são definidos como upstream da atividade no mesmo fluxo de trabalho, por meio de atividades de definição de metas, como consultas, interseções etc.

A preparação da mensagem é acionada de acordo com os parâmetros de execução do fluxo de trabalho. No painel de mensagens, você pode selecionar se deseja solicitar ou não uma confirmação manual para enviar a mensagem (obrigatório por padrão). Você pode iniciar o fluxo de trabalho manualmente ou colocar uma atividade do programador no fluxo de trabalho para automatizar a execução.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Email delivery]** atividade em seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.

   >[!NOTE]
   >
   >Você pode acessar as propriedades gerais e as opções avançadas da atividade (e não da entrega em si) por meio do ![](assets/dlv_activity_params-24px.png) botão das ações rápidas da atividade. Esse botão é específico para a **[!UICONTROL Email delivery]** atividade. As propriedades do email podem ser acessadas pela barra de ação no painel de email.

1. Selecione o modo de envio de email:

   * **[!UICONTROL Email]**: o email é enviado uma única vez. Você pode especificar aqui se deseja ou não adicionar uma transição de saída à atividade. Os diferentes tipos de transição estão detalhados na etapa 7 deste procedimento.
   * **[!UICONTROL Recurring email]**: o email é enviado várias vezes, de acordo com a frequência definida em uma **[!UICONTROL Scheduler]** atividade. Selecione o período de agregação dos envios. Isso permite que você agrupe todos os envios que ocorrem durante o período definido em um único email, também chamado de Execução **** recorrente e que podem ser acessados na lista de atividades de marketing do aplicativo.

      Por exemplo, para um email de aniversário recorrente, que é enviado diariamente, você pode escolher agregar os envios por mês. Isso permite que você receba relatórios sobre a sua entrega mensalmente, embora o email seja enviado todos os dias.

1. Selecione um tipo de email. Os tipos de email vêm de modelos de email definidos no menu **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** .
1. Insira as propriedades gerais do email. Você também pode anexá-la a uma campanha existente. A etiqueta da atividade de entrega do fluxo de trabalho é atualizada com a etiqueta de email.
1. Defina o conteúdo do email. Consulte a seção sobre edição [de](../../designing/using/overview.md)conteúdo.
1. Por padrão, a **[!UICONTROL Email delivery]** atividade não inclui nenhuma transição de saída. Se você deseja adicionar uma transição de saída à sua **[!UICONTROL Email delivery]** atividade, vá para a **[!UICONTROL General]** guia das opções de atividade avançada ( ![](assets/dlv_activity_params-24px.png) botão nas ações rápidas da atividade) e verifique uma das seguintes opções:

   * **[!UICONTROL Add outbound transition without the population]**: isso permite gerar uma transição de saída que contém exatamente a mesma população da transição de entrada.
   * **[!UICONTROL Add outbound transition with the population]**: isso permite que você gere uma transição de saída contendo a população para a qual o email foi enviado. Os membros do destino excluídos durante a preparação de entrega (quarentena, email inválido etc.) são excluídos desta transição.

1. Confirme a configuração da atividade e salve o fluxo de trabalho.

Ao reabrir a atividade, você é direcionado diretamente para o painel de email. Somente seu conteúdo pode ser editado.

Por padrão, iniciar um fluxo de trabalho de entrega aciona somente a preparação da mensagem. O envio de mensagens criadas a partir de um fluxo de trabalho ainda precisa ser confirmado depois que o fluxo de trabalho for iniciado. Mas no painel de mensagens, e somente se a mensagem foi criada a partir de um fluxo de trabalho, você pode desativar a **[!UICONTROL Request confirmation before sending messages]** opção. Ao desmarcar essa opção, as mensagens são enviadas sem aviso prévio após a preparação.

## Observações {#remarks}

As entregas criadas em um fluxo de trabalho podem ser acessadas na lista de atividades de marketing do aplicativo. Você pode exibir o status de execução do fluxo de trabalho usando o painel. Os links no painel de resumo de email permitem acessar diretamente os elementos vinculados (fluxo de trabalho, campanha, entrega principal no caso de um email recorrente).

![](assets/wkf_display_recurrent_executions_2.png)

No entanto, as execuções de entregas recorrentes são mascaradas por padrão. Para exibi-los, marque a opção no painel de pesquisa das atividades de marketing. **[!UICONTROL Show recurring executions]**

![](assets/wkf_display_recurrent_executions.png)

Nas entregas principais, que podem ser acessadas da lista de atividades de marketing ou diretamente por meio das execuções recorrentes associadas, você pode exibir o número total de envios que foram processados (de acordo com o período de agregação especificado quando a **[!UICONTROL Email delivery]** atividade foi configurada). Para fazer isso, abra a exibição detalhada do **[!UICONTROL Deployment]** bloco da entrega pai selecionando ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3.png)

## Exemplo {#example}

![](assets/wkf_delivery_example_1.png)

Este exemplo é um fluxo de trabalho de aniversário. Todos os dias um email é enviado para perfis cujo aniversário é naquele dia. Para fazer isso:

* O **[!UICONTROL Scheduler]** permite que você inicie o fluxo de trabalho todos os dias às 8h.

   ![](assets/wkf_delivery_example_2.png)

* A **[!UICONTROL Query]** atividade permite calcular os perfis que forneceram um email e cujo aniversário é no dia atual, toda vez que o fluxo de trabalho é executado. O cálculo de aniversário é realizado usando um filtro predefinido disponível na paleta na ferramenta de edição de consulta.

   ![](assets/wkf_delivery_example_3.png)

* O **[!UICONTROL Email]** é recorrente. Os envios são agregados por mês. Assim, todos os emails enviados em um mês são agregados em uma única exibição. Em um ano, 365 entregas são executadas, mas são agrupadas em 12 exibições (também chamadas de execuções **** recorrentes) na interface do Adobe Campaign. Os detalhes do histórico e do relatório são exibidos todos os meses e não para cada envio.

   ![](assets/wkf_delivery_example_4.png)

**Tópicos relacionados**

* [Caso de uso: Criar uma entrega de email uma vez por semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: Criação de uma entrega segmentada no local](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: Criação de entregas com um complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: Fluxo de trabalho de redefinição de metas enviando uma nova entrega para não iniciantes](../../automating/using/workflow-cross-channel-retargeting.md)