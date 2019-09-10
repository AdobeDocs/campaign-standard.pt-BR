---
title: entrega SMS
seo-title: entrega SMS
description: entrega SMS
seo-description: A atividade de entrega SMS permite configurar o envio de um SMS único ou um SMS recorrente em um fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 736078 c 6-ac 91-4440-825 b -4 a 6 ae 31894 ef
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: channel-activities
discoiquuid: 978592 b 8-989 a -446 a -8 a 84-12 b 7 fecfc 130
context-tags: sms, main; entrega, smscontent, voltar
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# entrega SMS{#sms-delivery}

## Descrição {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

A **[!UICONTROL SMS delivery]** atividade permite que você configure o envio de um SMS em um fluxo de trabalho. Pode ser **um único SMS enviando** e enviado apenas uma vez, ou pode ser um SMS **recorrente** .

Mensagens SMS de envio único são SMS padrão, enviadas uma vez.

Mensagens SMS recorrentes permitem enviar o mesmo SMS várias vezes para diferentes metas durante um período definido. Você pode agregar as entregas por período para obter relatórios que correspondam às suas necessidades.

## Contexto de uso {#context-of-use}

A **[!UICONTROL SMS delivery]** atividade é geralmente usada para automatizar o envio de um SMS para um destino calculado no mesmo fluxo de trabalho.

Quando vinculados a um agendador, você pode definir mensagens SMS recorrentes.

Os destinatários de SMS são definidos como upstream da atividade no mesmo fluxo de trabalho, por atividades de definição de metas como consultas, interseções etc.

A preparação de mensagens é acionada de acordo com os parâmetros de execução do fluxo de trabalho. No painel de mensagens, você pode selecionar se deseja ou não solicitar ou não uma confirmação manual para enviar a mensagem (obrigatório por padrão). Você pode iniciar o fluxo de trabalho manualmente ou colocar uma atividade de agendamento no fluxo de trabalho para automatizar a execução.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL SMS delivery]** atividade no seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.

   >[!NOTE]
   >
   >Você pode acessar as propriedades gerais e as opções avançadas da atividade (e não da própria entrega) por meio do ![](assets/dlv_activity_params-24px.png) botão na barra de ações do fluxo de trabalho. Esse botão é específico da **[!UICONTROL SMS delivery]** atividade. As propriedades SMS podem ser acessadas por meio da barra de ações no painel SMS.

1. Selecione o modo de envio de SMS:

   * **[!UICONTROL SMS]**: o SMS é enviado uma única vez. Você pode especificar aqui se deseja adicionar uma transição de saída à atividade. Os diferentes tipos de transição são detalhados na etapa 7 desse procedimento.
   * **[!UICONTROL Recurring SMS]**: o SMS é enviado várias vezes, de acordo com a frequência definida em uma **[!UICONTROL Scheduler]** atividade. Selecione o período de agregação dos envios. Isso permite que você recupere todos os envios que ocorrem durante o período definido em uma única exibição que também é chamada **de execução recorrente** e pode ser acessada da lista de atividades de marketing do aplicativo.

      Por exemplo, para um SMS de aniversário recorrente, que é enviado diariamente, você pode optar por agregar os envios por mês. Isso permite que você receba relatórios mensalmente, embora o SMS seja enviado diariamente.

1. Selecione um tipo de SMS. Os tipos de SMS vêm dos modelos de SMS definidos no menu **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** .
1. Insira as propriedades gerais do SMS. Você também pode anexá-lo a uma campanha existente. O rótulo da atividade de entrega do fluxo de trabalho é atualizado com o rótulo SMS.
1. Defina o conteúdo SMS. Consulte a seção sobre [como criar uma mensagem SMS](../../channels/using/creating-an-sms-message.md).
1. Por padrão, **[!UICONTROL SMS delivery]** a atividade não inclui quaisquer transações de saída. Para adicionar uma transição de saída à **[!UICONTROL SMS delivery]** atividade, vá para **[!UICONTROL General]** a guia das opções avançadas de atividade ( ![](assets/dlv_activity_params-24px.png) botão nas ações rápidas da atividade) e marque uma das seguintes opções:

   * **[!UICONTROL Add outbound transition without the population]**: isso permite gerar uma transição de saída que contenha exatamente a mesma população que a transição de entrada.
   * **[!UICONTROL Add outbound transition with the population]**: isso permite gerar uma transição de saída contendo a população para a qual o SMS foi enviado. Os membros do alvo excluídos durante a preparação de entrega (quarentena, número inválido etc.) são excluídos desta transição.

1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

Ao reabrir a atividade, você será direcionado diretamente para o painel SMS. Somente seu conteúdo pode ser editado.

Por padrão, iniciar um fluxo de trabalho de entrega apenas aciona a preparação de mensagens. O envio de mensagens criadas a partir de um fluxo de trabalho ainda precisa ser confirmado após a inicialização do fluxo de trabalho. Porém, a partir do painel de mensagens, e somente se a mensagem tiver sido criada a partir de um fluxo de trabalho, você poderá desativar a **[!UICONTROL Request confirmation before sending messages]** opção. Ao desmarcar essa opção, as mensagens são enviadas sem aviso prévio após a conclusão da preparação.

## Observações {#remarks}

As entregas criadas em um fluxo de trabalho podem ser acessadas na lista de atividades de marketing do aplicativo. Você pode visualizar o status de execução do fluxo de trabalho usando o painel. Os links no painel de resumo SMS permitem acessar diretamente os elementos vinculados (fluxo de trabalho, campanha, entrega pai no caso de um SMS recorrente).

Entretanto, as execuções de entregas recorrentes são mascaradas por padrão. Para exibi-los, verifique a **[!UICONTROL Show recurring executions]** opção no painel de pesquisa das atividades de marketing.

Nas entregas pai, que podem ser acessadas da lista de atividades de marketing ou diretamente por meio das execuções recorrentes associadas, você pode exibir o número total de envios que foram processados (de acordo com o período de agregação especificado quando a **[!UICONTROL SMS delivery]** atividade foi configurada). Para fazer isso, abra a exibição detalhada do **[!UICONTROL Deployment]** bloco da entrega pai selecionando ![](assets/wkf_dlv_detail_button.png).

## Exemplo {#example}

![](assets/wkf_sms_example_1.png)

Este exemplo é um fluxo de trabalho de aniversário. Todo dia um SMS é enviado para perfis cujo aniversário está no dia. Para fazer isso:

* Permite **[!UICONTROL Scheduler]** iniciar o fluxo de trabalho todo dia às 8 am h.

   ![](assets/wkf_delivery_example_2.png)

* **[!UICONTROL Query]** A atividade permite calcular os perfis que forneceram um número de telefone móvel e cujo aniversário está no dia atual, toda vez que o fluxo de trabalho é executado. O cálculo de aniversário é executado usando um filtro predefinido disponível na paleta na ferramenta de edição de consulta.

   ![](assets/wkf_delivery_example_3.png)

* O **[!UICONTROL SMS]** é recorrente. Os envios são agregados por mês. Assim, todas as mensagens SMS enviadas em um mês são agregadas a uma única exibição. Em um ano, as entregas 365 são executadas, mas são recuperadas em 12 exibições (também chamadas **de execuções recorrentes**) na interface do Adobe Campaign. Os detalhes do histórico e do relatório são exibidos todo mês e não para cada envio.

   ![](assets/wkf_sms_example_4.png)

Para obter outro exemplo de entrega de SMS em um fluxo de trabalho, consulte [Caso de uso: Fluxo de trabalho de redefinição de metas enviando uma nova entrega para não-openers](../../automating/using/workflow-cross-channel-retargeting.md).
