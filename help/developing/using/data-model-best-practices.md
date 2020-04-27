---
title: Práticas recomendadas de modelo de dados no Adobe Campaign Standard
description: Saiba mais sobre as práticas recomendadas ao projetar seu modelo de dados Adobe Campaign Standard.
page-status-flag: never-activated
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 4e0468da-3052-4ce5-8174-45aba1f5c4ed
context-tags: cusResource,overview;eventCusResource,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# Práticas recomendadas do modelo de dados{#data-model-best-practices}

Este documento descreve as principais recomendações ao projetar seu modelo de dados de Adobe Campaign.


>[!NOTE]
>
>Para criar e modificar recursos a fim de estender o modelo de dados predefinido do Adobe Campaign, consulte [esta seção](../../developing/using/key-steps-to-add-a-resource.md).
>
>Você pode encontrar uma representação de modelo de dados dos recursos incorporados [nesta página](../../developing/using/datamodel-introduction.md).

## Visão geral {#overview}

O sistema de Adobe Campaign é extremamente flexível e pode ser estendido além da implementação inicial. No entanto, embora as possibilidades sejam infinitas, é fundamental tomar decisões sábias e criar bases fortes para o start do design de seu modelo de dados.

Este documento fornece casos de uso comuns e práticas recomendadas para aprender como arquitetar corretamente sua ferramenta Adobe Campaign.

## Arquitetura do modelo de dados {#data-model-architecture}

O Adobe Campaign Standard é um poderoso sistema de gestões de campanha entre canais que pode ajudá-lo a alinhar suas estratégias online e offline para criar experiências personalizadas de clientes.

### Abordagem centrada no cliente {#customer-centric-approach}

Enquanto a maioria dos provedores de serviço de e-mail está se comunicando com os clientes por meio de uma abordagem centrada na lista, o Adobe Campaign depende de um banco de dados relacional para aproveitar uma visualização mais ampla dos clientes e seus atributos.

Esta abordagem centrada no cliente é mostrada no gráfico abaixo. O recurso de **Perfil** em cinza representa a principal tabela do cliente em torno da qual tudo está sendo construído:

![](assets/customer-centric-data-model.png)

O modelo de dados padrão do Adobe Campaign é apresentado nesta [seção](../../developing/using/datamodel-introduction.md).

<!--You can find a datamodel representation for the out-of-the-box resources [here](../../developing/using/datamodel-introduction.md).-->

<!--### What is a customer? {#customer-definition}

If you have customer data in more than one system, you need to determine which solution will allow you to identify records as one person. This work might require rules, eventually a match and merge processes to determine the master record. This master record should be the one sent to Adobe Campaign.

While some of this data cleansing might be performed in Adobe Campaign, the recommendation is to run these processes outside and only import clean data in Adobe Campaign. You should keep Campaign as a marketing solution more than a data cleansing tool.

Be able to provide a master customer record which will be sent to Adobe Campaign.-->

### Dados para Adobe Campaign {#data-for-campaign}

Que dados devem ser enviados para o Adobe Campaign? É importante determinar os dados necessários para suas atividades de marketing.

>[!NOTE]
>
>Adobe Campaign não é um data warehouse. Portanto, não tente importar para o Adobe Campaign todos os clientes possíveis e suas informações associadas.

Para decidir se um atributo seria necessário ou não no Adobe Campaign, determine se seria abrangido por uma destas categorias:
* Atributo usado para **segmentação**
* Atributo usado para processos **de** gestão de dados (cálculo de agregação, por exemplo)
* Atributo usado para **personalização**
* Atributo usado para o **relatórios** (relatórios podem ser criados com base em dados personalizados do perfil)

Se você não cair em nenhum desses, provavelmente não precisará desse atributo no Adobe Campaign.

### Tipos de dados {#data-types}

Para garantir uma boa arquitetura e desempenho do seu sistema, siga as práticas recomendadas abaixo para configurar os dados no Adobe Campaign:
* O comprimento de um campo de string deve ser sempre definido com a coluna. Por padrão, o comprimento máximo em Adobe Campaign é de 255 caracteres, mas a Adobe recomenda manter o campo mais curto se você já souber que o tamanho não excederá um comprimento menor.
* É aceitável ter um campo menor em Adobe Campaign do que no sistema de origem se você tiver certeza de que o tamanho no sistema de origem foi superestimado e não seria atingido. Isso pode significar uma string mais curta ou um número inteiro menor em Adobe Campaign.

## Configuração da estrutura de dados {#configuring-data-structure}

Esta seção descreve as práticas recomendadas ao [configurar a estrutura](../../developing/using/configuring-the-resource-s-data-structure.md)de dados de um recurso.

### Identificadores {#identifiers}

Os recursos de Adobe Campaign têm três identificadores e é possível adicionar um identificador adicional.

A tabela a seguir descreve esses identificadores e sua finalidade.

>[!NOTE]
>
>O nome de exibição é o nome do campo exibido ao usuário por meio da interface do usuário do Adobe Campaign. O nome técnico é o nome do campo real na definição do recurso (e o nome da coluna da tabela).

| Nome de exibição | Designação técnica | Descrição | Práticas recomendadas |
|--- |--- |--- |--- |
|  | PKey | <ul><li>O PKey é a chave primária física de uma tabela de Adobe Campaign.</li><li>Normalmente, esse identificador é exclusivo de uma instância Adobe Campaign específica.</li><li>No Adobe Campaign Standard, esse valor não é visível para o usuário final (exceto em URLs).</li></ul> | <ul><li>Por meio do sistema [de](../../api/using/about-campaign-standard-apis.md)API, é possível recuperar um valor PKey (que é um valor gerado/hash, não a chave física).</li><li>Não é recomendável usá-lo para nada além de recuperar, atualizar ou excluir registros por meio da API.</li></ul> |
| ID | name ou internalName | <ul><li>Essas informações são um identificador exclusivo de um registro em uma tabela. Esse valor pode ser atualizado manualmente.</li><li>Esse identificador mantém seu valor quando implantado em uma instância diferente do Adobe Campaign. Ele deve ter um nome diferente do valor gerado para ser exportável por meio de um pacote.</li><li>Essa não é a chave primária real da tabela.</li></ul> | <ul><li>Não use caracteres especiais, como o espaço &quot;&quot;, a semircoluna &quot;:&quot; ou o hífen &quot;-&quot;.</li><li>Todos esses caracteres seriam substituídos por um sublinhado &quot;_&quot; (caractere permitido). Por exemplo, &quot;abc-def&quot; e &quot;abc:def&quot; seriam armazenados como &quot;abc_def&quot; e se substituiriam.</li></ul> |
| Rótulo | label | <ul><li>O rótulo é o identificador comercial de um objeto ou registro no Adobe Campaign.</li><li>Esse objeto permite espaços e caracteres especiais.</li><li>Não garante a unicidade de um registro.</li></ul> | <ul><li>É recomendável determinar uma estrutura para seus rótulos de objetos.</li><li>Essa é a solução mais fácil de usar para identificar um registro ou objeto para um usuário Adobe Campaign.</li></ul> |
| ID ACS | acsId | <ul><li>Um identificador adicional pode ser gerado: a ID [](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)ACS.</li><li>Como o PKey não pode ser usado na interface do usuário do Adobe Campaign, essa é uma solução para obter um valor exclusivo gerado durante a inserção de um registro de perfil.</li><li>O valor só pode ser gerado automaticamente se a opção estiver ativada no recurso antes de um registro ser inserido no Adobe Campaign.</li></ul> | <ul><li>Essa UUID pode ser usada como uma chave de reconciliação.</li><li>Uma ID ACS gerada automaticamente não pode ser usada como referência em um fluxo de trabalho ou em uma definição de pacote.</li><li>Esse valor é específico para uma instância Adobe Campaign.</li></ul> |

### Teclas de identificação {#keys}

Cada recurso criado no Adobe Campaign deve ter pelo menos uma chave [de](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)identificação exclusiva.

<!--Most organizations are importing records from external systems. While the physical key of a resource lies behind the PKey attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When an out-of-the-box resource has both an internal auto-generated and an internal custom key, the internal key will be set as a unique index in the physical database table.-->

Ao criar um recurso personalizado, você tem duas opções:

* Uma combinação de chave gerada automaticamente e chave personalizada interna. Essa opção é interessante se a chave do sistema for uma chave composta ou não for um número inteiro. Os inteiros fornecerão desempenho mais alto em tabelas grandes e unirão-se a outras tabelas.
* Usar a chave primária como a chave primária do sistema externo. Essa solução geralmente é preferida, pois simplifica a abordagem de importar e exportar dados, com uma chave consistente entre diferentes sistemas.

As chaves de identificação não devem ser usadas como referência em workflows.

<!--For more on defining identification keys, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).-->

### Índices {#indexes}

O Adobe Campaign adiciona automaticamente um [índice](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes) a todas as chaves primárias e internas definidas em um recurso.

* A Adobe recomenda definir índices adicionais, pois pode melhorar o desempenho.
* No entanto, não adicione índices demais, pois eles usam espaço no banco de dados. Vários índices também podem ter um impacto negativo no desempenho.
* Selecione cuidadosamente os índices que precisam ser definidos.

<!--For more on defining indexes, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes).

When you are performing an initial import with very high volumes of data insert in Adobe Campaign database, it is recommended to run that import without custom indexes at first. It will allow to accelerate the insertion process. Once you’ve completed this important import, it is possible to enable the index(es).-->

### Links {#links}

A definição de links com outros recursos é apresentada [nesta seção](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).

* Embora seja possível associar qualquer tabela em um fluxo de trabalho, a Adobe recomenda definir links comuns entre recursos diretamente na definição da estrutura de dados.
* O link deve ser definido de acordo com os dados reais em suas tabelas. Uma definição incorreta poderia afetar os dados recuperados por meio de links, por exemplo, duplicando registros inesperadamente.
* Dê um nome consistente ao seu link com o nome do recurso: o nome do link deve ajudar a entender o que é a tabela distante.
* Não nomeie um link com &quot;id&quot; como sufixo. Por exemplo, nomeie-a como &quot;transaction&quot; em vez de &quot;transactionId&quot;.

<!--For more on defining links with other resources, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).-->

## Desempenho {#performance}

Para garantir melhor desempenho a qualquer momento, siga as práticas recomendadas abaixo.

### Recomendações gerais {#general-recommendations}

* Evite usar operações como &quot;CONTAINS&quot; em query. Se você sabe o que é esperado e deseja filtrar, aplique a mesma condição com um &quot;EQUAL TO&quot; ou outros operadores de filtro específicos.
* Evite unir a campos não indexados ao criar dados em workflows.
* Tente garantir que processos como importação e exportação ocorram fora do horário comercial.
* Certifique-se de que existe uma programação para todas as atividades diárias e cumpra a programação.
* Se um ou alguns dos processos diários falharem e se for obrigatório executá-lo no mesmo dia, verifique se não há processos conflitantes em execução quando o processo manual é iniciado, pois isso pode afetar o desempenho do sistema.
* Verifique se nenhuma campanha diária é executada durante o processo de importação ou quando qualquer processo manual é executado.
* Use uma ou várias tabelas de referência em vez de duplicar um campo em cada linha. Ao usar pares de chave/valor, é preferível escolher uma chave numérica.
* Uma string curta permanece aceitável. Caso as tabelas de referências já estejam em vigor em um sistema externo, reutilizar o mesmo facilitará a integração de dados com o Adobe Campaign.

### Relações de um para muitos {#one-to-many-relationships}

* O design de dados afeta a usabilidade e a funcionalidade. Se você projetar seu modelo de dados com muitas relações um para muitos, isso torna mais difícil para os usuários construírem uma lógica significativa no aplicativo. A lógica de filtro um para muitos pode ser difícil para comerciantes não técnicos construírem e entenderem corretamente.
* É bom ter todos os campos essenciais em uma tabela, pois facilita a criação de query pelos usuários. Às vezes, também é bom para o desempenho duplicado alguns campos nas tabelas se puder evitar uma junção.
* Determinadas funcionalidades incorporadas não poderão fazer referência a relações one-to-many, por exemplo, fórmula de Ponderação Oferta e Delivery.

### Tabelas grandes {#large-tables}

Abaixo estão algumas práticas recomendadas que devem ser seguidas ao projetar seu modelo de dados usando tabelas grandes e junções complexas.

* Reduza o número de colunas, principalmente identificando as que não são usadas.
* Otimize as relações do modelo de dados evitando junções complexas, como junções em várias condições e/ou em várias colunas.
* Para teclas de junção, sempre use dados numéricos em vez de sequências de caracteres.
* Reduza o máximo possível a profundidade da retenção de registros. Se precisar de um histórico mais profundo, você pode agregação a computação e/ou manipular tabelas de log personalizadas para armazenar um histórico maior.