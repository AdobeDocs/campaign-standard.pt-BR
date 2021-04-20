---
solution: Campaign Standard
product: campaign
title: Chamada de workflow com parâmetros externos
description: Esta seção detalha como chamar um workflow com parâmetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 1%

---


# Personalização de um workflow com parâmetros externos {#customizing-a-workflow-with-external-parameters}

Depois que o fluxo de trabalho é acionado, os parâmetros são assimilados nas variáveis de eventos e podem ser usados para personalizar as atividades do fluxo de trabalho.

Eles podem, por exemplo, ser usados para definir qual público-alvo ler na atividade **[!UICONTROL Read audience]** , o nome do arquivo a ser transferido na atividade **[!UICONTROL Transfer file]** etc. (consulte [esta página](../../automating/using/customizing-workflow-external-parameters.md)).

## Uso de variáveis de eventos {#using-events-variables}

As variáveis de eventos são usadas em uma expressão que deve respeitar a [Sintaxe padrão](../../automating/using/advanced-expression-editing.md#standard-syntax).

A sintaxe para usar variáveis de eventos deve seguir o formato abaixo e usar o nome do parâmetro que foi definido na atividade **[!UICONTROL External signal]** (consulte [Declaração dos parâmetros na atividade de sinal externo](../../automating/using/declaring-parameters-external-signal.md)):

```
$(vars/@parameterName)
```

Nessa sintaxe, a função **$** retorna o tipo de dados **string**. Se quiser especificar outro tipo de dados, use as seguintes funções:

* **$long**: número inteiro.
* **$float**: número decimal.
* **$boolean**: true/false.
* **$datetime**: timestamp.

Ao usar uma variável em uma atividade, a interface fornece ajuda para chamá-la.

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png): selecione a variável events entre todas as variáveis disponíveis no workflow.

   ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png): editar expressões que combinam variáveis e funções (consulte  [esta página](../../automating/using/advanced-expression-editing.md)).

   ![](assets/wkf_test_activity_variables_expression.png)

   Esta lista fornece funções que permitem fazer uma filtragem complexa. Essas funções são detalhadas em [this section](../../automating/using/list-of-functions.md).

   Além disso, você pode usar as funções abaixo, que estão disponíveis em todas as atividades que permitem usar variáveis de eventos após chamar um workflow com parâmetros externos (consulte [esta seção](../../automating/using/customizing-workflow-external-parameters.md#customizing-activities-with-events-variables)):

   | Nome | Descrição | Sintaxe |
   ---------|----------|---------
   | EndWith | Indica se uma string (primeiro parâmetro) termina com uma string específica (segundo parâmetro). | EndWith(&lt;Cadeia de caracteres>,&lt;Cadeia de caracteres>) |
   | startWith | Indica se uma string (primeiro parâmetro) começa com uma string específica (segundo parâmetro). | startWith(&lt;Cadeia de caracteres>,&lt;Cadeia de caracteres>) |
   | Extract | Retorna os primeiros caracteres de uma string usando um separador. | Extract(&lt;Cadeia de caracteres>,&lt;Separador>) |
   | ExtractRight | Retorna os últimos caracteres de uma string usando um separador. | ExtractRight(&lt;Cadeia de caracteres>,&lt;Separador>) |
   | DateFormat | Formata uma data usando o formato especificado no segundo parâmetro (por exemplo:  &#39;%4Y%2M%2D&#39;) | DateFormat(&lt;Data>,&lt;Formato>) |
   | FileName | Retorna o nome de um caminho de arquivo. | FileName(&lt;Cadeia de caracteres>) |
   | FileExt | Retorna a extensão de um caminho de arquivo. | FileExt(&lt;Cadeia de caracteres>) |
   | GetOption | Retorna o valor da função especificada. | GetOption(&lt;optionName>) |
   | IsNull | Indica se uma string ou uma data é nula. | IsNull(&lt;Cadeia de caracteres/data>) |
   | UrlUtf8Encode | Codifica um URL em UTF8. | UrlUtf8Encode(&lt;Cadeia De Caracteres>) |

## Personalização de atividades com variáveis de eventos {#customizing-activities-with-events-variables}

As variáveis de Eventos podem ser usadas para personalizar várias atividades, listadas na seção abaixo. Para obter mais informações sobre como chamar uma variável de uma atividade, consulte [esta seção](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables).

**[!UICONTROL Read audience]** atividade : defina o público-alvo com base nas variáveis de eventos. Para obter mais informações sobre como usar a atividade, consulte [esta seção](../../automating/using/read-audience.md).

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** atividade : crie condições com base nas variáveis de eventos. Para obter mais informações sobre como usar a atividade, consulte [esta seção](../../automating/using/test.md).

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** atividade : personalize o arquivo a ser transferido com base nas variáveis de eventos. Para obter mais informações sobre como usar a atividade, consulte [esta seção](../../automating/using/transfer-file.md).

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** atividade : parâmetros podem ser referenciados em uma query usando expressões que combinam variáveis e funções de eventos. Para fazer isso, adicione uma regra e clique no link **[!UICONTROL Advanced mode]** para acessar a janela de edição de expressão (consulte [Advanced expression editing](../../automating/using/advanced-expression-editing.md)).

Para obter mais informações sobre como usar a atividade, consulte [esta seção](../../automating/using/query.md).

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** atividades: personalize deliveries com base em variáveis de eventos.

>[!NOTE]
>
>Os valores dos parâmetros de delivery são recuperados toda vez que o delivery for preparado.
>
>A preparação de deliveries recorrentes é baseada no **período de agregação** do delivery. Por exemplo, se o período de agregação for &quot;por dia&quot;, o delivery será repreparado apenas uma vez por dia. Se o valor de um parâmetro de delivery for modificado durante o dia, ele não será atualizado no delivery, pois já foi preparado uma vez.
>
>Se você planeja chamar o workflow várias vezes por dia, use a opção [!UICONTROL No aggregation] para que os parâmetros de delivery sejam atualizados sempre. Para obter mais informações sobre configuração de deliveries recorrentes, consulte [esta seção](/help/automating/using/email-delivery.md#configuration).

Para personalizar um delivery com base nas variáveis de eventos, primeiro declare na atividade de delivery as variáveis que deseja usar:

1. Selecione a atividade e clique no botão ![](assets/dlv_activity_params-24px.png) para acessar as configurações.
1. Selecione a guia **[!UICONTROL General]** e adicione as variáveis de eventos que estarão disponíveis como campos de personalização no delivery.

   ![](assets/extsignal_activities_delivery.png)

1. Clique no botão **[!UICONTROL Confirm]**.

As variáveis de eventos declaradas agora estão disponíveis na lista de campos de personalização. Você pode usá-los no delivery para executar as ações abaixo:

* Defina o nome do template a ser usado para o delivery.

   >[!NOTE]
   >
   >Essa ação está disponível somente para **deliveries recorrentes**.

   ![](assets/extsignal_activities_template.png)

* Personalize o delivery: ao selecionar um campo de personalização para configurar um delivery, as variáveis de eventos ficam disponíveis no elemento **[!UICONTROL Workflow parameters]** . Você pode usá-los como qualquer campo de personalização, por exemplo, para definir o assunto do delivery, o remetente etc.

   A personalização de delivery é detalhada em [this section](../../designing/using/personalization.md).

   ![](assets/extsignal_activities_perso.png)

**Códigos** de segmento: defina o código do segmento com base nas variáveis de eventos.

>[!NOTE]
>
>Essa ação pode ser executada de qualquer atividade que permite definir um código de segmento como, por exemplo, **[!UICONTROL Query]** ou **[!UICONTROL Segmentation]** atividades.

![](assets/extsignal_activities_segment.png)

**Rótulo** do delivery: defina o rótulo do delivery com base nas variáveis de eventos.

![](assets/extsignal_activities_label.png)
