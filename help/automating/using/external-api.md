---
title: API externa
seo-title: API externa
description: API externa
seo-description: null
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: atividades de definição de metas
context-tags: Externalapi, fluxo de trabalho, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eb908d4e0ff23319025d3193bb9b22d006b5901e

---


# External API {#external-api}

## Description {#description}

![](assets/wf_externalAPI.png)

The **[!UICONTROL External API]** activity brings data into the workflow from an **external system** via a **REST API** call.

The REST endpoints can be a customer management system, an [Adobe I/O Runtime](https://www.adobe.io/apis/experienceplatform/runtime.html) instance or an Experience Cloud REST endpoints (Data Platform, Target, Analytics, Campaign, etc).

>[!CAUTION]
>
>No momento, esse recurso está em beta público. É necessário aceitar o contrato de uso antes de começar a usar a atividade de API externa. Observe que, como esse recurso beta público ainda não foi lançado comercialmente pela Adobe, ele não é suportado pelo Adobe Client Care, pode conter erros e pode não funcionar bem como outros recursos liberados.

As principais características dessa atividade são:

* Capacidade de passar dados em um formato JSON para um ponto de extremidade REST de REST de terceiros
* Capacidade de receber uma resposta JSON, mapeá-la para saída de tabelas e passar para baixo para outras atividades do fluxo de trabalho.
* Gerenciamento de falha com uma transição específica de saída

Os seguintes controles foram colocados para esta atividade:

* Limite de tamanho de dados de resposta HTTP de 5 MB
* O tempo limite da solicitação é de 60 segundos
* Redirecionamentos HTTP não são permitidos
* Os Urls não HTTPS são rejeitados
* " Accept: application/json "header and and" Content-Type: o cabeçalho de resposta do aplicativo/json é permitido

>[!CAUTION]
>
>Observe que a atividade destina-se a buscar dados em toda a campanha (conjunto mais recente de ofertas, pontuações mais recentes etc.) não para recuperar informações específicas para cada perfil, o que pode resultar em grandes quantidades de dados sendo transferidos. If the use case requires this, the recommendation is to use the [Transfer File](../../automating/using/transfer-file.md) activity.

## Configuration {#configuration}

Drag and drop an **[!UICONTROL External API]** activity into your workflow and open the activity to start the configuration.

### Mapeamento de entrada

O mapeamento de entrada é uma tabela temporária gerada por uma atividade de entrada anterior que será exibida e enviada como JSON na interface do usuário.
Com base nesta tabela temporária, o usuário pode fazer modificações nos dados de entrada.

![](assets/externalAPI-inbound.png)

The **Inbound resource** dropdown lets you select the query activity that will create the temporary table.

The **Add count parameter** checkbox will a count value for each row coming from the temporary table. Observe que essa caixa de seleção está disponível somente se a atividade de entrada estiver gerando uma tabela temporária.

The **Inbound Columns** section allow the user to add any fields from the inbound transition table. As colunas selecionadas serão as chaves no objeto de dados. O objeto de dados no JSON será uma lista de matriz contendo dados das colunas selecionadas de cada linha da tabela de transição de entrada.

The **customize parameter** text box lets you add a valid JSON with additional data needed by the external API. Esses dados adicionais serão adicionados ao objeto params no JSON gerado.

### Mapeamento de saída

This tab lets you define the sample **JSON structure** returned by the API Call.

![](assets/externalAPI-outbound.png)

The JSON structure pattern is: `{“data”:[{“key”:“value”}, {“key”:“value”},...]}`

The sample JSON definition must have the **following characteristics**:

* **é** um nome de propriedade obrigatório no JSON, o conteúdo de "dados" é uma matriz JSON.
* **Os elementos** de matriz devem conter propriedades de primeiro nível (os níveis mais profundos não são suportados).
   **Nomes de propriedade** terminariam se tornassem nomes de colunas para o esquema de saída da tabela temporária de saída.
* **A definição do nome** da coluna baseia-se no primeiro elemento da matriz de "dados".
Columns definition (add/remove) and the type value of the property can be edited in the **Column definition** tab.

If the **parsing is validated** a message appears and invite you to customize the data mapping in the "Column definition" tab. Em outros casos, uma mensagem de erro é exibida.

### Execução

This tab lets you define the **HTTPS Endpoint** that will send data to ACS. If needed, you can enter authentication information in the fields below.
![](assets/externalAPI-execution.png)

### Propriedades

This tab lets you control **general properties** on the external API activity like the displayed label in the UI. A ID interna não é personalizável.

![](assets/externalAPI-properties.png)

### Definição de coluna

>[!NOTE]
>
>This tab appears when the **response data format** is completed and validated in Outbound Mapping tab.

The **Column definition** tab allows you to precisely specify the data structure of each column in order to import data that does not contain any errors and make it match the types that are already present in the Adobe Campaign database for future operations.

![](assets/externalAPI-column.png)

Por exemplo, é possível alterar o rótulo de uma coluna, selecionar o tipo (sequência, número inteiro, data etc.)ou até mesmo especificar o processamento de erros.

For more information, refer to the [Load File](../../automating/using/load-file.md) section.

### Transição

This tab lets you activate the **outbound transition** and its label. This specific transition is useful in case of **timeout** or if the payload exceed the **data size limit**.

![](assets/externalAPI-transition.png)

### Opções de execução

Essa guia está disponível na maioria das atividades do fluxo de trabalho. For more information, consult the [Activity properties](../../automating/using/executing-a-workflow.md#activity-properties) section.

![](assets/externalAPI-options.png)

## Solução de problemas

Há dois tipos de mensagens de registro adicionadas à nova atividade do fluxo de trabalho: informações e erros. Eles podem ajudar a solucionar problemas potenciais.

### Informações

Essas mensagens de registro são usadas para registrar informações sobre pontos de verificação úteis durante a execução da atividade do fluxo de trabalho. Especificamente, as mensagens de registro a seguir são usadas para registrar a primeira tentativa, bem como uma tentativa de tentativa (e motivo para falha na primeira tentativa) para acessar a API.

<table> 
 <thead> 
  <tr> 
   <th> Message format<br /> </th> 
   <th> Example<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Invocar URL de API ' % s '.</td> 
   <td> <p>Invocar URL de API ' https://example.com/api/v1/web-coupon?count=2'.</p></td> 
  </tr> 
  <tr> 
   <td> Nova tentativa de URL de API ' % s ', a tentativa anterior falhou (' % s ').</td> 
   <td> <p>Nova tentativa de URL de API ' https://example.com/api/v1/web-coupon?count=2', a tentativa anterior falhou (' HTTP - 401 ').</p></td>
  </tr> 
  <tr> 
   <td> Transferindo conteúdo de ' % s ' (% s/% s).</td> 
   <td> <p>Transferindo conteúdo de «https://example.com/api/v1/web-coupon?count=2' (1234/1234).</p></td> 
  </tr>
 </tbody> 
</table>

### Erros

Essas mensagens de registro são usadas para registrar informações sobre condições de erro inesperadas, o que eventualmente faz com que a atividade do fluxo de trabalho falhasse.

<table> 
 <thead> 
  <tr> 
   <th> Code - Message format<br /> </th> 
   <th> Example<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> WKF -560250 - Limite de corpo da solicitação de API excedido (limite: ' % d ').</td> 
   <td> <p>Limite de corpo da solicitação da API excedido (limite: ' 5242880 ').</p></td> 
  </tr> 
  <tr> 
   <td> WKF -560239 - A resposta da API excedeu o limite (limite: ' % d ').</td> 
   <td> <p>A resposta da API excedeu o limite (limite: 5242880 ').</p></td> 
  </tr> 
  <tr> 
   <td> WKF -560245 - URL de API não pode ser analisado (erro: ' % d ').</td> 
   <td> <p>O URL da API não pôde ser analisado (erro: ' -2010 ').</p>
   <p> Observação: Esse erro é registrado quando o URL da API falha nas regras de validação.</p></td>
  </tr> 
  <tr>
   <td> WKF -560244 - Host de URL de API não pode ser'localhost'ou'literal de endereço IP ' (host de URL: ' % s ').</td> 
   <td> <p>O host de URL da API não pode ser'localhost'ou'literal de endereço IP ' (host de URL: ' localhost ').</p>
    <p>O host de URL da API não pode ser'localhost'ou'literal de endereço IP ' (host de URL: ' 192.168.0.5 ').</p>
    <p>O host de URL da API não pode ser'localhost'ou'literal de endereço IP ' (host de URL: ' [2001]').</p></td>
  </tr> 
  <tr> 
   <td> WKF -560238 - URL de API deve ser um URL seguro (https) (URL requisitado: ' % s ').</td> 
   <td> <p>O URL da API deve ser um URL seguro (https) (URL requisitado: ' https://example.com/api/v1/web-coupon?count=2').</p></td> 
  </tr> 
  <tr> 
   <td> WKF -560249 - Falha ao criar o JSON do corpo da solicitação. Erro ao adicionar ' % s '.</td> 
   <td> <p>Falha ao criar o JSON do corpo da solicitação. Erro ao adicionar «params».</p>
    <p>Falha ao criar o JSON do corpo da solicitação. Erro ao adicionar "dados".</p></td>
  </tr> 
  <tr> 
   <td> WKF -560246 - A chave do cabeçalho HTTP é incorreta (chave do cabeçalho: ' % s ').</td> 
   <td> <p>A chave do cabeçalho HTTP é incorreta (chave do cabeçalho: ' % s ').</p>
   <p> Observação: Esse erro é registrado quando a tecla de cabeçalho personalizada falha na validação de acordo com [RFC] (https://tools.ietf.org/html/rfc7230#section-3.2.html)</p></td> 
  </tr>
 <tr> 
   <td> WKF -560248 - A chave do cabeçalho HTTP não é permitida (chave do cabeçalho: ' % s ').</td> 
   <td> <p>A chave do cabeçalho HTTP não é permitida (chave do cabeçalho: ' Accept ').</p></td> 
  </tr> 
  <tr> 
   <td> WKF -560247 - O valor do cabeçalho AHTTP é incorreto (valor do cabeçalho: ' % s ').</td> 
   <td> <p>O valor do cabeçalho HTTP é incorreto (valor do cabeçalho: ' % s '). </p>
    <p>Observação: Esse erro é registrado quando o valor do cabeçalho personalizado falha na validação de acordo com [RFC] (https://tools.ietf.org/html/rfc7230#section-3.2.html)</p></td> 
  </tr> 
  <tr> 
   <td> WKF -560240 - A carga JSON tem uma propriedade inválida ' % s '.</td> 
   <td> <p>A carga JSON tem uma propriedade "blah" incorreta.</p></td>
  </tr> 
  <tr>
   <td> WKF -560241 - JSON malformado ou formato inaceitável.</td> 
   <td> <p>JSON malformado ou formato inaceitável.</p>
   <p>Observação: Esta mensagem se aplica somente à análise do corpo da resposta da API externa e é registrado ao tentar validar se o corpo de resposta está em conformidade com o formato JSON enviado por essa atividade.</p></td>
  </tr>
  <tr> 
   <td> WKF -560246 - Falha na atividade (motivo: ' % s ').</td> 
   <td> <p>Quando a atividade falha devido a resposta do erro HTTP 401 - a atividade falhou (motivo: ' HTTP - 401 ')</p>
        <p>Quando a atividade falha devido a uma chamada interna com falha - falha na atividade (motivo: ' Irc - -nn ').</p>
        <p>Quando a atividade falhar devido a um cabeçalho Content-Type inválido. - Falha na atividade (motivo: ' Content-Type - application/html ').</p></td> 
  </tr>
 </tbody> 
</table>

<!--
## Example: Managing coupons with External API Activity

This example illustrates how to **add coupon value** retrieving by a REST call to profiles and then sending an email containing these coupon values.

The workflow is presented as follows:

![](assets/externalAPI_activity_example1.png)

1. Drag and drop an **External API** activity
    1. Parse the JSON sample responsa as {"data":[{"code":"value"}]}.
    1. Add the **Rest endpoint URL** and define authentication setting if needed
    ![](assets/externalAPI_activity_example2.png)
    1. In the **column definition** tab, add a new column called **code** that will store the code value.
        ![](assets/externalAPI_activity_example3.png)
    1. Enabled an **outbound transition** to manage request failures.
1. Drag and drop a **Query** activity
    1. Configure the **Target** tab to query all the **@adobe.com** email. For different Query samples, refer to the [Query](../../automating/using/query.md) section.
    1. In the **additional data** tab, add a new column based on **rowId()** function. This additional column allows you to reconciliate coupon code with the profile ID..
        ![](assets/externalAPI_activity_example4.png)

        >[!NOTE]
        >
        >This reconciliation approach means that the profile query number is equal to the number of coupon values returned by the REST call.
1. Once this two activities are configured, drag and drop an **Enrichment** activity to associate coupon values with profiles.
    1. Select the previous Query activity in the **primarySet** field.
        ![](assets/externalAPI_activity_example5.png)
    1. Create a new relation in the **Advanced relations** tab, and add the following reconciliation criteria:
    1. **@expr1** coming grom the Query activity in the source expression field.
    1. **@lineNum** as an expression that returns the line number for each coupon value in the destination field.
        ![](assets/externalAPI_activity_example6.png)
        More information on the enrichment activity are available [here](../../automating/using/enrichment.md)

    1. The transition **Data Structure** will contain:
        ![](assets/externalAPI_activity_example7.png)
1. Finally drag and drop a **Send via Email** activity.
    You can modify your email template by adding the **code** personnalized field.

-->
