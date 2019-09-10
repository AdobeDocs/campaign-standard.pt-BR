---
title: Entrega por email
seo-title: Entrega por email
description: Entrega por email
seo-description: A atividade de entrega de email permite configurar o envio de um único email de envio ou um email recorrente em um fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 7 de 53431-84 ae -4 d 21-8361-2775 ad 314 ed 2
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: channel-activities
discoiquuid: 5 f 288 cf 6-f 8 ff -4 ac 9-9 c 1 a -8010260554 bb
context-tags: entrega, fluxo de trabalho, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# Entrega por email{#email-delivery}

## Descrição {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

A **[!UICONTROL Email delivery]** atividade permite que você configure o envio de um e-mail em um fluxo de trabalho. Pode ser um **único email de envio** e enviado apenas uma vez, ou pode ser um email **recorrente** .

E-mails de envio único são e-mails padrão, enviados uma vez.

Emails recorrentes permitem enviar o mesmo email várias vezes para diferentes metas durante um período definido. Você pode agregar as entregas por período para obter relatórios que correspondam às suas necessidades.

## Contexto de uso {#context-of-use}

A **[!UICONTROL Email delivery]** atividade é geralmente usada para automatizar o envio de um e-mail para uma meta calculada no mesmo fluxo de trabalho.

Quando vinculados a um agendador, você pode definir emails recorrentes.

Destinatários de email são definidos como upstream da atividade no mesmo fluxo de trabalho, por atividades de definição de metas como consultas, interseções etc.

A preparação de mensagens é acionada de acordo com os parâmetros de execução do fluxo de trabalho. No painel de mensagens, você pode selecionar se deseja ou não solicitar ou não uma confirmação manual para enviar a mensagem (obrigatório por padrão). Você pode iniciar o fluxo de trabalho manualmente ou colocar uma atividade de agendamento no fluxo de trabalho para automatizar a execução.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Email delivery]** atividade no seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.

   >[!NOTE]
   >
   >Você pode acessar as propriedades gerais e as opções avançadas da atividade (e não da própria entrega) por meio do ![](assets/dlv_activity_params-24px.png) botão das ações rápidas da atividade. Esse botão é específico da **[!UICONTROL Email delivery]** atividade. As propriedades do email podem ser acessadas por meio da barra de ações no painel de e-mail.

1. Selecione o modo de envio de email:

   * **[!UICONTROL Email]**: o e-mail é enviado uma única vez. Você pode especificar aqui se deseja adicionar uma transição de saída à atividade. Os diferentes tipos de transição são detalhados na etapa 7 desse procedimento.
   * **[!UICONTROL Recurring email]**: o email é enviado várias vezes, de acordo com a frequência definida em uma **[!UICONTROL Scheduler]** atividade. Selecione o período de agregação dos envios. Isso permite que você recupere todos os envios que ocorrem durante o período definido em um único email que também é chamado **de execução recorrente** e pode ser acessado da lista de atividades de marketing do aplicativo.

      Por exemplo, para um email de aniversário recorrente, que é enviado diariamente, você pode optar por agregar os envios por mês. Isso permite que você receba relatórios mensalmente, embora o email seja enviado diariamente.

1. Selecione um tipo de email. Os tipos de e-mail vêm dos modelos de e-mail definidos no menu **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** .
1. Insira as propriedades gerais do email. Você também pode anexá-lo a uma campanha existente. O rótulo da atividade de entrega do fluxo de trabalho é atualizado com o rótulo de email.
1. Defina o conteúdo de email. Consulte a seção sobre edição [de conteúdo](../../designing/using/about-email-content-design.md).
1. Por padrão, **[!UICONTROL Email delivery]** a atividade não inclui quaisquer transações de saída. Para adicionar uma transição de saída à **[!UICONTROL Email delivery]** atividade, vá para **[!UICONTROL General]** a guia das opções avançadas de atividade ( ![](assets/dlv_activity_params-24px.png) botão nas ações rápidas da atividade) e marque uma das seguintes opções:

   * **[!UICONTROL Add outbound transition without the population]**: isso permite gerar uma transição de saída que contenha exatamente a mesma população que a transição de entrada.
   * **[!UICONTROL Add outbound transition with the population]**: isso permite gerar uma transição de saída contendo a população para a qual o email foi enviado. Os membros do alvo excluídos durante a preparação de entrega (quarentena, e-mail inválido etc.) são excluídos desta transição.

1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

Ao reabrir a atividade, você será direcionado diretamente para o painel de e-mail. Somente seu conteúdo pode ser editado.

Por padrão, iniciar um fluxo de trabalho de entrega apenas aciona a preparação de mensagens. O envio de mensagens criadas a partir de um fluxo de trabalho ainda precisa ser confirmado após a inicialização do fluxo de trabalho. Porém, a partir do painel de mensagens, e somente se a mensagem tiver sido criada a partir de um fluxo de trabalho, você poderá desativar a **[!UICONTROL Request confirmation before sending messages]** opção. Ao desmarcar essa opção, as mensagens são enviadas sem aviso prévio após a conclusão da preparação.

## Observações {#remarks}

As entregas criadas em um fluxo de trabalho podem ser acessadas na lista de atividades de marketing do aplicativo. Você pode visualizar o status de execução do fluxo de trabalho usando o painel. Os links no painel de resumo de email permitem acessar diretamente os elementos vinculados (fluxo de trabalho, campanha, entrega pai no caso de um email recorrente).

![](assets/wkf_display_recurrent_executions_2.png)

Entretanto, as execuções de entregas recorrentes são mascaradas por padrão. Para exibi-los, verifique a **[!UICONTROL Show recurring executions]** opção no painel de pesquisa das atividades de marketing.

![](assets/wkf_display_recurrent_executions.png)

Nas entregas pai, que podem ser acessadas da lista de atividades de marketing ou diretamente por meio das execuções recorrentes associadas, você pode exibir o número total de envios que foram processados (de acordo com o período de agregação especificado quando a **[!UICONTROL Email delivery]** atividade foi configurada). Para fazer isso, abra a exibição detalhada do **[!UICONTROL Deployment]** bloco da entrega pai selecionando ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3.png)

## Exemplo {#example}

![](assets/wkf_delivery_example_1.png)

Este exemplo é um fluxo de trabalho de aniversário. Todos os dias, um email é enviado para perfis cujo aniversário ele está no dia. Para fazer isso:

* Permite **[!UICONTROL Scheduler]** iniciar o fluxo de trabalho todo dia às 8 am h.

   ![](assets/wkf_delivery_example_2.png)

* **[!UICONTROL Query]** A atividade permite calcular os perfis que forneceram um email e cujo aniversário está no dia atual, toda vez que o fluxo de trabalho é executado. O cálculo de aniversário é executado usando um filtro predefinido disponível na paleta na ferramenta de edição de consulta.

   ![](assets/wkf_delivery_example_3.png)

* O **[!UICONTROL Email]** é recorrente. Os envios são agregados por mês. Assim, todos os e-mails enviados em um mês são agregados em uma única exibição. Em um ano, as entregas 365 são executadas, mas são recuperadas em 12 exibições (também chamadas **de execuções recorrentes**) na interface do Adobe Campaign. Os detalhes do histórico e do relatório são exibidos todo mês e não para cada envio.

   ![](assets/wkf_delivery_example_4.png)

**Tópicos relacionados**

* [Caso de uso: Criar uma entrega de email uma vez a semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: Criação de uma entrega segmentada na localização](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: Criação de entregas com um complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: Fluxo de trabalho de redefinição de metas enviando uma nova entrega para não-openers](../../automating/using/workflow-cross-channel-retargeting.md)