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
translation-type: ht
source-git-commit: 3bd2fdb56fc94cef4e9c21466a33cdad7ac825d2
workflow-type: ht
source-wordcount: '1754'
ht-degree: 100%

---


# API externa {#external-api}

## Descrição {#description}

![](assets/wf_externalAPI.png)

A atividade **[!UICONTROL External API]** traz dados para o workflow de um **sistema externo** por meio de uma chamada à **API HTTP**.

Os pontos de extremidade do sistema externo podem ser pontos de extremidade de API públicos, sistemas de gerenciamento de clientes ou instâncias de aplicativos sem servidor (por exemplo, [Adobe I/O Runtime](https://www.adobe.io/apis/experienceplatform/runtime.html)), para mencionar algumas categorias.

>[!NOTE]
>
>Por motivos de segurança, o uso de JSSPs não é compatível com o Campaign Standard. Se você precisar executar um código, poderá chamar uma instância do Adobe I/O Runtime por meio da atividade API externa.

As principais características dessa atividade são:

* Capacidade de transmitir dados em um formato JSON para um ponto de extremidade de API REST de terceiros
* Capacidade de receber uma resposta JSON de volta, mapeá-la para tabelas de saída e transmiti-la downstream para outras atividades do workflow.
* Gerenciamento de falhas com uma transição específica de saída

### Transição de Beta para GA {#from-beta-to-ga}

Com a versão Campaign Standard 20.3, o recurso de API externa mudou de Beta para GA (Disponibilidade geral).

>[!CAUTION]
>
>Como consequência, se você estava usando atividades beta da API externa, é necessário substituí-las por atividades da API externa do GA em todos os workflows.  Os workflows que usam a versão beta da API externa não funcionarão a partir da versão 20.3.

Ao substituir as atividades de API externas, adicione a nova atividade ao workflow, copie manualmente os detalhes de configuração e exclua a atividade antiga.

>[!NOTE]
>
>Não será possível copiar os valores do cabeçalho, pois eles são mascarados dentro da atividade.

Em seguida, reconfigure no workflow outras atividades que apontam e/ou usam dados da atividade beta da API externa para apontar e/ou usar dados da nova atividade da API externa. Exemplos de atividades: delivery de email (campos de personalização), atividade de enriquecimento, etc.

### Limitações e medidas de proteção {#guardrails}

Aplicam-se a esta atividade as seguintes medidas de proteção:

* Limite de tamanho de dados de resposta http de 50 MB (recomenda-se 5 MB)
* O tempo de espera da solicitação é de 10 minutos
* Não são permitidos redirecionamentos HTTP
* São rejeitados Urls que não sejam HTTPS
* São permitidos cabeçalho de solicitação “Accept: application/json” e cabeçalho de resposta “Content-Type: application/json”

>[!NOTE]
>
>A partir da versão 20.4 do Campaign, o limite de tamanho de dados da resposta http e as medidas de proteção de tempo de espera da resposta serão reduzidos para 5 MB e 1 minuto, respectivamente.  Embora essa alteração afete apenas as novas atividades de API externas, é altamente recomendável que as implementações atuais da atividade de API externa se alinhem a essas novas medidas de proteção para seguir as práticas recomendadas.

Foram colocadas em prática medidas de proteção específicas para o JSON:

* **Profundidade máx. JSON**: limite a profundidade máxima de um JSON aninhado e personalizado que pode ser processado para 10 níveis.
* **Extensão máx. da chave JSON**: limite o comprimento máximo da chave interna gerada para 255. Essa chave está associada à ID da coluna.
* **Chaves máximas de duplicação JSON permitidas**:  limite o número total máximo de nomes de propriedades JSON do duplicado usados como ID da coluna para 150.

A atividade não é compatível com a estrutura JSON como:

* Combinação de objetos de matriz com outros elementos que não são de matriz
* O objeto de matriz JSON é aninhado dentro de um ou mais objetos de matriz intermediários.

>[!CAUTION]
>
>A atividade de API externa se destina à busca de dados em toda a campanha (último conjunto de ofertas, últimas pontuações, etc.), e não para a recuperação de informações específicas para cada perfil, pois pode resultar na transferência de grandes quantidades de dados. Se o caso de uso exigir, recomenda-se usar a atividade [Transferir arquivo](../../automating/using/transfer-file.md).

## Configuração {#configuration}

Arraste e solte uma atividade **[!UICONTROL External API]** no seu workflow e abra a atividade para iniciar a configuração.

### Mapeamento de entrada

O mapeamento de entrada é uma tabela temporária gerada por uma atividade de entrada anterior que será exibida e enviada como JSON na interface.
Com base nessa tabela temporária, o usuário pode fazer modificações nos dados de entrada.

![](assets/externalAPI-inbound.png)

A lista suspensa **Recurso de entrada** permite selecionar a atividade de query que criará a tabela temporária.

A caixa de seleção **Adicionar parâmetro de contagem** adicionará um valor de contagem para cada linha proveniente da tabela temporária. Observe que essa caixa de seleção só estará disponível se a atividade de entrada estiver gerando uma tabela temporária.

A seção **Colunas de entrada** permite que o usuário adicione quaisquer campos a partir da tabela de transição de entrada. As colunas selecionadas serão as chaves no objeto de dados. O objeto de dados no JSON será uma lista de matriz contendo dados para colunas selecionadas de cada linha da tabela de transição de entrada.

A caixa de texto **personalizar parâmetro** permite adicionar um JSON válido com dados adicionais necessários para a API externa. Esses dados adicionais serão adicionados ao objeto params no JSON gerado.

### Mapeamento de saída

Essa guia permite que você defina a **estrutura JSON** de amostra retornada pela chamada à API.

![](assets/externalAPI-outbound.png)

O analisador de JSON foi projetado para hospedar tipos padrão de estrutura JSON, com algumas exceções. Um exemplo de padrão é:`{“data”:[{“key”:“value”}, {“key”:“value”},...]}`

A definição do JSON de amostra deve ter as **seguintes características**:

* Os **elementos da matriz** devem conter propriedades de primeiro nível (níveis mais profundos não são compatíveis).
   Os **nomes de propriedades** acabarão se tornando nomes de colunas para o schema de saída da tabela temporária de saída.
* Os **elementos JSON** capturados devem estar em 10 ou menos níveis de aninhamento na resposta JSON.
* A definição do **nome da coluna** é baseada no primeiro elemento da matriz &quot;data&quot;.
A definição de colunas (adicionar/remover) e o valor de tipo da propriedade podem ser editados na guia **Definição de coluna**.

Comportamento da **Caixa de seleção Nivelar**:

A caixa de seleção Nivelar (desmarcada por padrão) é fornecida para indicar se o JSON deve ser nivelado em um mapa de chave/valor.

* Quando a **caixa de seleção estiver desativada** (desmarcada), a amostra JSON será analisada para procurar um objeto de matriz. O usuário precisará fornecer uma versão reduzida do formato JSON de amostra de resposta da API para que o Adobe Campaign possa determinar exatamente qual matriz o usuário está interessado em usar. No momento da criação do workflow, o caminho para o objeto de matriz aninhado será determinado e registrado, para que possa ser usado no tempo de execução para acessar esse objeto de matriz pelo corpo de resposta JSON recebido da chamada de API.

* Quando a **caixa de seleção estiver ativada** (marcada), a amostra JSON será nivelada e todas as propriedades especificadas na amostra JSON fornecida serão usadas para criar colunas da tabela temporária de saída, e serão exibidas na guia Definições de coluna. Observe que se houver algum objeto de matriz na amostra JSON, todos os elementos desses objetos de matriz também serão nivelados.


Se a **análise for validada**, será exibida uma mensagem com um convite para personalizar o mapeamento de dados na guia &quot;Definição de coluna&quot;. Caso contrário, uma mensagem de erro será exibida.

### Execução

Essa guia permite que você defina o **Ponto de extremidade HTTPS** que enviará dados para o ACS. Se necessário, você poderá inserir informações de autenticação nos campos abaixo.
![](assets/externalAPI-execution.png)

### Propriedades

Essa guia permite controlar as **propriedades gerais** na atividade externa da API, como o rótulo exibido na interface. A ID interna não é personalizável.

![](assets/externalAPI-properties.png)

### Definição de coluna

>[!NOTE]
>
>Essa guia é exibida quando o **formato de dados de resposta** é concluído e validado na guia Mapeamento de saída.

A guia **Definição de coluna** permite especificar com precisão a estrutura dos dados de cada coluna para importar dados que não contenham erros e fazer a correspondência deles com os tipos presentes no banco de dados do Adobe Campaign para operações futuras.

![](assets/externalAPI-column.png)

Por exemplo, você pode alterar o rótulo de uma coluna, selecionar o tipo (sequência, número inteiro, data etc.) ou até mesmo especificar o processamento de erros.

Para obter mais informações, consulte a seção [Carregar arquivo](../../automating/using/load-file.md).

### Transição

Essa guia permite ativar a **transição de saída** e seu rótulo. Essa transição específica é útil em caso de **tempo de espera** ou se a carga exceder o **limite de tamanho de dados**.

![](assets/externalAPI-transition.png)

### Opções de execução

Esta guia está disponível na maioria das atividades de workflow. Para obter mais informações, consulte a seção [Propriedades de atividade](../../automating/using/activity-properties.md).

![](assets/externalAPI-options.png)

## Solução de problemas

Existem dois tipos de mensagens de log adicionados a esta nova atividade de workflow: informações e erros. Elas podem ser úteis na solução de possíveis problemas.

### Informações

Essas mensagens de log são usadas para registrar informações sobre pontos de verificação úteis durante a execução da atividade do workflow. Especificamente, as mensagens de log a seguir são usadas para registrar a primeira tentativa, bem como uma nova tentativa (e o motivo da falha da primeira tentativa) para acessar a API.

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
   <td> <p>Chamando o URL da API 'https://example.com/api/v1/web-coupon?count=2'.</p></td> 
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

Essas mensagens de log são usadas para registrar informações sobre condições de erro inesperadas, que eventualmente podem causar falha na atividade do workflow.

<table> 
 <thead> 
  <tr> 
   <th> Código - Formato da mensagem<br /> </th> 
   <th> Exemplo<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> WKF-560250 - o corpo da solicitação de API excedeu o limite (limite: '%d').</td> 
   <td> <p>O corpo da solicitação de API excedeu o limite (limite: '5242880').</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560239 - A resposta da API excedeu o limite (limite: '%d').</td> 
   <td> <p>O limite de resposta da API excedido (limite: 5242880').</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560245 - O URL da API não pôde ser analisado (erro: '%d').</td> 
   <td> <p>O URL da API não pôde ser analisado (erro: "-2010").</p>
   <p> Observação: esse erro é registrado quando o URL da API apresenta falha nas regras de validação.</p></td>
  </tr> 
  <tr>
   <td> WKF-560244 - O host do URL da API não deve ser “localhost”, nem o endereço IP literal (Host de URL '%s').</td> 
   <td> <p>O host do URL da API não deve ser “localhost” nem o endereço IP literal (Host de URL: ‘localhost’).</p>
    <p>O host do URL da API não deve ser “localhost” nem o endereço IP literal (Host de URL: '192.168.0.5').</p>
    <p>O host do URL da API não deve ser “localhost” nem o endereço IP literal (Host de URL: '[2001]').</p></td>
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
   <p> Observação: este erro é registrado quando a chave do cabeçalho personalizado falha na validação de acordo com a <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC</a></p></td> 
  </tr>
 <tr> 
   <td> WKF-560248 - A chave do cabeçalho HTTP não é permitida (chave do cabeçalho: '%s').</td> 
   <td> <p>A chave do cabeçalho HTTP não é permitida (chave do cabeçalho: 'Accept').</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560247 - O valor do cabeçalho HTTP é incorreto (valor do cabeçalho: '%s').</td> 
   <td> <p>O valor do cabeçalho HTTP é incorreto (valor do cabeçalho: '%s'). </p>
    <p>Observação: este erro é registrado quando o valor do cabeçalho personalizado falha na validação de acordo com a <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC</a></p></td> 
  </tr> 
  <tr> 
   <td> WKF-560240 - A carga JSON tem a propriedade '%s’ incorreta.</td> 
   <td> <p>A carga JSON tem uma propriedade incorreta 'blah'.</p></td>
  </tr> 
  <tr>
   <td> WKF-560241 - Formato JSON malformado ou inaceitável.</td> 
   <td> <p>Formato JSON malformado ou inaceitável.</p>
   <p>Observação: esta mensagem se aplica somente à análise do corpo da resposta a partir da API externa e é registrada ao tentar validar se o corpo da resposta está em conformidade com o formato JSON determinado por essa atividade.</p></td>
  </tr>
  <tr> 
   <td> WKF-560246 - Falha na atividade (motivo: '%s').</td> 
   <td> <p>Quando a atividade falha devido à resposta de erro HTTP 401 - Falha na atividade (motivo: 'HTTP - 401')</p>
        <p>Quando a atividade falha devido a uma falha na chamada interna - Falha na atividade (motivo: 'iRc - -Nn').</p>
        <p>Quando a atividade falha devido a um cabeçalho de tipo de conteúdo inválido. - Falha na atividade (motivo: 'Content-Type - application/html’).</p></td> 
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
