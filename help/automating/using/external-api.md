---
title: API externa
description: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: externalAPI,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8f3c8f9a167f11ba5ded2be34a50b52edeeb6412

---


# API externa {#external-api}

## Descrição {#description}

![](assets/wf_externalAPI.png)

A **[!UICONTROL External API]** atividade traz dados para o fluxo de trabalho de um sistema **** externo por meio de uma chamada de API **** REST.

Os pontos finais REST podem ser um sistema de gerenciamento de clientes, uma instância de tempo de execução [de E/S da](https://www.adobe.io/apis/experienceplatform/runtime.html) Adobe ou pontos finais REST da Experience Cloud (Plataforma de dados, Target, Analytics, Campaign etc).

>[!NOTE]
>
>Por motivos de segurança, o uso de JSSPs não é suportado no Campaign Standard. Se precisar executar o código, você pode chamar uma instância do Tempo de execução de E/S da Adobe por meio da atividade da API externa.

>[!IMPORTANT]
>
>Esse recurso está atualmente em beta. É necessário aceitar o contrato de uso antes de começar a usar a atividade de API externa. Observe que, como esse recurso beta ainda não foi lançado comercialmente pela Adobe, ele não é suportado pelo Adobe Client Care, ele pode conter erros e pode não funcionar assim como outros recursos lançados.

As principais características desta atividade são:

* Capacidade de transmitir dados em um formato JSON para um terminal de API REST de terceiros
* Capacidade de receber uma resposta JSON de volta, mapeá-la para tabelas de saída e passar downstream para outras atividades de fluxo de trabalho.
* Gerenciamento de falhas com uma transição específica de saída

Foram criados os seguintes painéis de proteção para esta atividade:

* Limite de tamanho de dados de resposta http de 50 MB
* O tempo limite da solicitação é de 10 minutos
* Redirecionamentos HTTP não são permitidos
* Urls que não sejam HTTPS são rejeitados
* &quot;Aceitar: cabeçalho de solicitação application/json&quot; e &quot;Content-Type: o cabeçalho de resposta application/json é permitido

>[!CAUTION]
>
>Observe que a atividade se destina a buscar dados de toda a campanha (último conjunto de ofertas, pontuações mais recentes etc.) não para recuperar informações específicas para cada perfil, pois isso pode resultar na transferência de grandes quantidades de dados. Se o caso de uso exigir isso, a recomendação é usar a atividade [Transferir arquivo](../../automating/using/transfer-file.md) .

## Configuração {#configuration}

Arraste e solte uma **[!UICONTROL External API]** atividade em seu fluxo de trabalho e abra a atividade para iniciar a configuração.

### Mapeamento de entrada

O mapeamento de entrada é uma tabela temporária gerada por uma atividade de entrada anterior que será exibida e enviada como JSON na interface do usuário.
Com base nessa tabela temporária, o usuário pode fazer modificações nos dados de entrada.

![](assets/externalAPI-inbound.png)

A lista suspensa Recurso **de** entrada permite selecionar a atividade de consulta que criará a tabela temporária.

A caixa de seleção **Adicionar parâmetro** de contagem apresentará um valor de contagem para cada linha proveniente da tabela temporária. Observe que essa caixa de seleção só estará disponível se a atividade de entrada estiver gerando uma tabela temporária.

A seção Colunas **de** entrada permite que o usuário adicione quaisquer campos da tabela de transição de entrada. As colunas selecionadas serão as chaves no objeto de dados. O objeto de dados no JSON será uma lista de matriz contendo dados para colunas selecionadas de cada linha da tabela de transição de entrada.

A caixa de texto **personalizar parâmetro** permite adicionar um JSON válido com dados adicionais necessários para a API externa. Esses dados adicionais serão adicionados ao objeto params no JSON gerado.

### Mapeamento de saída

Essa guia permite que você defina a estrutura **** JSON de amostra retornada pela Chamada de API.

![](assets/externalAPI-outbound.png)

O padrão de estrutura JSON é: `{“data”:[{“key”:“value”}, {“key”:“value”},...]}`

A definição do JSON de amostra deve ter as **seguintes características**:

* **data** é um nome de propriedade obrigatório no JSON, o conteúdo de &quot;data&quot; é uma matriz JSON.
* **Os elementos** da matriz devem conter propriedades de primeiro nível (níveis mais profundos não são suportados).
   **Nomes** de propriedades acabariam se tornando nomes de colunas para o esquema de saída da tabela temporária de saída.
* **A definição do nome** da coluna é baseada no primeiro elemento da matriz &quot;data&quot;.
A definição de colunas (adicionar/remover) e o valor de tipo da propriedade podem ser editados na guia Definição **de** coluna.

Se a **análise for validada** , uma mensagem será exibida e convidará você a personalizar o mapeamento de dados na guia &quot;Definição de coluna&quot;. Em outros casos, uma mensagem de erro é exibida.

### Execução

Essa guia permite que você defina o Ponto de extremidade **HTTPS** que enviará dados para o ACS. Se necessário, você pode inserir informações de autenticação nos campos abaixo.
![](assets/externalAPI-execution.png)

### Propriedades

Essa guia permite controlar as propriedades **** gerais na atividade externa da API, como o rótulo exibido na interface do usuário. A ID interna não é personalizável.

![](assets/externalAPI-properties.png)

### Definição de coluna

>[!NOTE]
>
>Essa guia é exibida quando o formato **de dados de** resposta é concluído e validado na guia Mapeamento de saída.

A guia Definição **de** coluna permite especificar com precisão a estrutura de dados de cada coluna para importar dados que não contêm erros e fazer com que eles correspondam aos tipos que já estão presentes no banco de dados do Adobe Campaign para operações futuras.

![](assets/externalAPI-column.png)

Por exemplo, você pode alterar o rótulo de uma coluna, selecionar seu tipo (string, número inteiro, data etc.) ou até mesmo especifique o processamento de erros.

For more information, refer to the [Load File](../../automating/using/load-file.md) section.

### Transição

Essa guia permite ativar a transição **de** saída e seu rótulo. Essa transição específica é útil em caso de **tempo limite** ou se a carga exceder o limite **de tamanho de** dados.

![](assets/externalAPI-transition.png)

### Opções de execução

Esta guia está disponível na maioria das atividades do fluxo de trabalho. Para obter mais informações, consulte a seção Propriedades [da](../../automating/using/executing-a-workflow.md#activity-properties) atividade.

![](assets/externalAPI-options.png)

## Solução de problemas

Existem dois tipos de mensagens de registro adicionadas a esta nova atividade de fluxo de trabalho: informações e erros. Eles podem ajudá-lo a solucionar possíveis problemas.

### Informações

Essas mensagens de log são usadas para registrar informações sobre pontos de verificação úteis durante a execução da atividade do fluxo de trabalho. Especificamente, as mensagens de log a seguir são usadas para registrar a primeira tentativa, bem como uma tentativa de nova tentativa (e o motivo da falha da primeira tentativa) para acessar a API.

<table> 
 <thead> 
  <tr> 
   <th> Formato de mensagem<br /> </th> 
   <th> Exemplo<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Chamando o URL da API '%s'.</td> 
   <td> <p>Invocando URL da API 'https://example.com/api/v1/web-coupon?count=2'.</p></td> 
  </tr> 
  <tr> 
   <td> Tentando novamente o URL da API '%s', falha na tentativa anterior ('%s').</td> 
   <td> <p>Tentando novamente o URL da API 'https://example.com/api/v1/web-coupon?count=2', falha na tentativa anterior ('HTTP - 401').</p></td>
  </tr> 
  <tr> 
   <td> Transferindo conteúdo de '%s' (%s / %s).</td> 
   <td> <p>Transferência de conteúdo de 'https://example.com/api/v1/web-coupon?count=2' (1234 / 1234).</p></td> 
  </tr>
 </tbody> 
</table>

### Erros

Essas mensagens de registro são usadas para registrar informações sobre condições de erro inesperadas, que podem eventualmente causar falha na atividade do fluxo de trabalho.

<table> 
 <thead> 
  <tr> 
   <th> Código - Formato da mensagem<br /> </th> 
   <th> Exemplo<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> WKF-560250 - O corpo da solicitação de API excedeu o limite (limite: '%d').</td> 
   <td> <p>O corpo da solicitação de API excedeu o limite (limite: '5242880').</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560239 - Resposta da API excedeu o limite (limite: '%d').</td> 
   <td> <p>Limite de resposta da API excedido (limite: 5242880').</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560245 - O URL da API não pôde ser analisado (erro: '%d').</td> 
   <td> <p>O URL da API não pôde ser analisado (erro: "-2010").</p>
   <p> Observação: Esse erro é registrado quando o URL da API falha nas regras de validação.</p></td>
  </tr> 
  <tr>
   <td> WKF-560244 - O host do URL da API não deve ser 'localhost', nem o literal de endereço IP (host do URL: '%s').</td> 
   <td> <p>O host do URL da API não deve ser 'localhost' ou o literal de endereço IP (host do URL: 'localhost').</p>
    <p>O host do URL da API não deve ser 'localhost' ou o literal de endereço IP (host do URL: "192.168.0.5").</p>
    <p>O host do URL da API não deve ser 'localhost' ou o literal de endereço IP (host do URL: '[2001]').</p></td>
  </tr> 
  <tr> 
   <td> WKF-560238 - O URL da API deve ser um URL seguro (https) (URL solicitado: '%s').</td> 
   <td> <p>O URL da API deve ser um URL seguro (https) (URL solicitado: 'https://example.com/api/v1/web-coupon?count=2').</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560249 - Falha ao criar o corpo de solicitação JSON. Erro ao adicionar '%s'.</td> 
   <td> <p>Falha ao criar o corpo de solicitação JSON. Erro ao adicionar 'params'.</p>
    <p>Falha ao criar o corpo de solicitação JSON. Erro ao adicionar 'data'.</p></td>
  </tr> 
  <tr> 
   <td> WKF-560246 - A chave do cabeçalho HTTP está incorreta (chave do cabeçalho: '%s').</td> 
   <td> <p>A chave do cabeçalho HTTP está incorreta (chave do cabeçalho: '%s').</p>
   <p> Observação: Este erro é registrado quando a chave do cabeçalho personalizado falha na validação de acordo com a <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC</a></p></td> 
  </tr>
 <tr> 
   <td> WKF-560248 - A chave do cabeçalho HTTP não é permitida (chave do cabeçalho: '%s').</td> 
   <td> <p>A chave do cabeçalho HTTP não é permitida (chave do cabeçalho: 'Aceitar').</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560247 - O valor do cabeçalho HTTP é incorreto (valor do cabeçalho: '%s').</td> 
   <td> <p>O valor do cabeçalho HTTP é incorreto (valor do cabeçalho: '%s'). </p>
    <p>Observação: Este erro é registrado quando o valor do cabeçalho personalizado falha na validação de acordo com a <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC</a></p></td> 
  </tr> 
  <tr> 
   <td> WKF-560240 - A carga JSON tem a propriedade '%s' incorreta.</td> 
   <td> <p>A carga JSON tem uma propriedade ruim "blá".</p></td>
  </tr> 
  <tr>
   <td> WKF-560241 - Formato JSON malformado ou inaceitável.</td> 
   <td> <p>Formato JSON malformado ou inaceitável.</p>
   <p>Observação: Esta mensagem se aplica somente à análise do corpo da resposta da API externa e é registrada ao tentar validar se o corpo da resposta está em conformidade com o formato JSON mandatado por essa atividade.</p></td>
  </tr>
  <tr> 
   <td> WKF-560246 - Falha na atividade (motivo: '%s').</td> 
   <td> <p>Quando a atividade falha devido à resposta de erro HTTP 401 - A atividade falhou (motivo: 'HTTP - 401')</p>
        <p>Quando a atividade falha devido a uma falha de chamada interna - a atividade falhou (motivo: 'iRc - -Nn').</p>
        <p>Quando a atividade falha devido a um cabeçalho Content-Type inválido. - Falha na atividade (motivo: 'Content-Type - application/html').</p></td> 
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
