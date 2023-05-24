---
title: Práticas recomendadas do modelo de dados no Adobe Campaign Standard
description: Saiba mais sobre as práticas recomendadas ao projetar seu modelo de dados do Adobe Campaign Standard.
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
feature: Data Model
role: Developer
level: Experienced
exl-id: 58d4e02f-3c9a-4e5d-a6aa-fdbcec0d8dda
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 1%

---

# Práticas recomendadas do modelo de dados{#data-model-best-practices}

Este documento descreve as principais recomendações ao projetar o modelo de dados do Adobe Campaign.


>[!NOTE]
>
>Para criar e modificar recursos e estender o modelo de dados predefinido do Adobe Campaign, consulte [nesta seção](../../developing/using/key-steps-to-add-a-resource.md).
>
>Você pode encontrar uma representação do modelo de dados dos recursos incorporados em [esta página](../../developing/using/datamodel-introduction.md).

## Visão geral {#overview}

O sistema Adobe Campaign é extremamente flexível e pode ser estendido além da implementação inicial. No entanto, embora as possibilidades sejam infinitas, é essencial tomar decisões sábias e criar bases sólidas para começar a projetar seu modelo de dados.

Este documento fornece casos de uso comuns e práticas recomendadas para saber como arquitetar corretamente a ferramenta Adobe Campaign.

## Arquitetura do modelo de dados {#data-model-architecture}

O Adobe Campaign Standard é um eficiente sistema de gerenciamento de campanhas em vários canais que pode ajudar você a alinhar suas estratégias online e offline para criar experiências personalizadas de clientes.

### Abordagem centrada no cliente {#customer-centric-approach}

Embora a maioria dos provedores de serviços de email esteja se comunicando com os clientes por meio de uma abordagem centrada em listas, o Adobe Campaign depende de um banco de dados relacional para aproveitar uma visualização mais ampla dos clientes e seus atributos.

Essa abordagem centrada no cliente é mostrada no gráfico abaixo. A variável **Perfil** o recurso em cinza representa a principal tabela do cliente em torno da qual tudo está sendo criado:

![](assets/customer-centric-data-model.png)

O modelo de dados padrão do Adobe Campaign é apresentado nesta [seção](../../developing/using/datamodel-introduction.md).

<!--You can find a datamodel representation for the out-of-the-box resources [here](../../developing/using/datamodel-introduction.md).-->

<!--### What is a customer? {#customer-definition}

If you have customer data in more than one system, you need to determine which solution will allow you to identify records as one person. This work might require rules, eventually a match and merge processes to determine the primary record. This primary record should be the one sent to Adobe Campaign.

While some of this data cleansing might be performed in Adobe Campaign, the recommendation is to run these processes outside and only import clean data in Adobe Campaign. You should keep Campaign as a marketing solution more than a data cleansing tool.

Be able to provide a primary customer record which will be sent to Adobe Campaign.-->

### Dados para o Adobe Campaign {#data-for-campaign}

Quais dados devem ser enviados para o Adobe Campaign? É essencial determinar os dados necessários para suas atividades de marketing.

>[!NOTE]
>
>O Adobe Campaign não é um data warehouse. Portanto, não tente importar todos os clientes possíveis e suas informações associadas para o Adobe Campaign.

Para decidir se um atributo seria necessário ou não no Adobe Campaign, determine se ele se enquadra em uma destas categorias:
* Atributo usado para **segmentação**
* Atributo usado para **processos de gerenciamento de dados** (cálculo agregado por exemplo)
* Atributo usado para **personalização**
* Atributo usado para **relatórios** (relatórios podem ser criados com base em dados de perfil personalizados)

Se não estiver se encaixando em nenhum desses, você provavelmente não precisará desse atributo no Adobe Campaign.

### Tipos de dados {#data-types}

Para garantir uma boa arquitetura e desempenho do sistema, siga as práticas recomendadas abaixo para configurar dados no Adobe Campaign:
* O comprimento de um campo de string deve sempre ser definido com a coluna. Por padrão, o comprimento máximo no Adobe Campaign é de 255 caracteres, mas o Adobe recomenda manter o campo mais curto, se você já souber que o tamanho não excederá um comprimento mais curto.
* É aceitável ter um campo mais curto no Adobe Campaign do que no sistema de origem se você tiver certeza de que o tamanho no sistema de origem foi superestimado e não seria atingido. Isso pode significar uma string menor ou um inteiro menor no Adobe Campaign.

## Configuração da estrutura de dados {#configuring-data-structure}

Esta seção descreve as práticas recomendadas para [configuração da estrutura de dados de um recurso](../../developing/using/configuring-the-resource-s-data-structure.md).

### Identificadores {#identifiers}

Os recursos do Adobe Campaign têm três identificadores e é possível adicionar um identificador adicional.

A tabela a seguir descreve esses identificadores e sua finalidade.

>[!NOTE]
>
>O nome de exibição é o nome do campo exibido para o usuário na interface do usuário do Adobe Campaign. O nome técnico é o nome de campo real na definição de recurso (e o nome da coluna da tabela).

| Nome de exibição | Nome técnico | Descrição | Práticas recomendadas |
|--- |--- |--- |--- |
|  | PKey | <ul><li>A PKey é a chave primária física de uma tabela Adobe Campaign.</li><li>Normalmente, esse identificador é exclusivo de uma instância específica do Adobe Campaign.</li><li>No Adobe Campaign Standard, esse valor não está visível para o usuário final (exceto em URLs).</li></ul> | <ul><li>Através do [Sistema de API](../../api/using/get-started-apis.md), é possível recuperar um valor PKey (que é um valor gerado/com hash, não a chave física).</li><li>Não é recomendável usá-lo para nada além de recuperar, atualizar ou excluir registros por meio da API.</li></ul> |
| ID | name ou internalName | <ul><li>Essas informações são um identificador exclusivo de um registro em uma tabela. Esse valor pode ser atualizado manualmente.</li><li>Esse identificador mantém seu valor quando implantado em uma instância diferente do Adobe Campaign. Ele deve ter um nome diferente do valor gerado para ser exportável por meio de um pacote.</li><li>Essa não é a chave primária real da tabela.</li></ul> | <ul><li>Não use caracteres especiais como espaço &quot;&quot;, semicuna &quot;:&quot; ou hífen &quot;-&quot;.</li><li>Todos esses caracteres seriam substituídos por um sublinhado &quot;_&quot; (caractere permitido). Por exemplo, &quot;abc-def&quot; e &quot;abc:def&quot; seriam armazenados como &quot;abc_def&quot; e se substituiriam.</li></ul> |
| Rótulo | label | <ul><li>O rótulo é o identificador comercial de um objeto ou registro no Adobe Campaign.</li><li>Esse objeto permite espaços e caracteres especiais.</li><li>Isso não garante a exclusividade de um registro.</li></ul> | <ul><li>É recomendável determinar uma estrutura para seus rótulos de objeto.</li><li>Essa é a solução mais simples para identificar um registro ou objeto para um usuário do Adobe Campaign.</li></ul> |
| ID DO ACS | acsId | <ul><li>Um identificador adicional pode ser gerado: o [ID DO ACS](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).</li><li>Como a PKey não pode ser usada na interface do usuário do Adobe Campaign, essa é uma solução para obter um valor exclusivo gerado durante a inserção de um registro de perfil.</li><li>O valor só poderá ser gerado automaticamente se a opção estiver habilitada no recurso antes que um registro seja inserido no Adobe Campaign.</li></ul> | <ul><li>Essa UUID pode ser usada como uma chave de reconciliação.</li><li>Uma ID de ACS gerada automaticamente não pode ser usada como referência em um fluxo de trabalho ou em uma definição de pacote.</li><li>Esse valor é específico para uma instância do Adobe Campaign.</li></ul> |

### Teclas de identificação {#keys}

Cada recurso criado no Adobe Campaign deve ter pelo menos um exclusivo [chave de identificação](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

<!--Most organizations are importing records from external systems. While the physical key of a resource lies behind the PKey attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When an out-of-the-box resource has both an internal auto-generated and an internal custom key, the internal key will be set as a unique index in the physical database table.-->

Ao criar um recurso personalizado, você tem duas opções:

* Uma combinação de chave gerada automaticamente e chave personalizada interna. Essa opção é interessante se a chave do sistema for uma chave composta ou não for um inteiro. Os números inteiros proporcionarão maiores desempenhos em tabelas grandes e em junções com outras tabelas.
* Usar a chave primária como a chave primária do sistema externo. Essa solução geralmente é preferida, pois simplifica a abordagem de importar e exportar dados, com uma chave consistente entre diferentes sistemas.

As chaves de identificação não devem ser usadas como referência em fluxos de trabalho.

<!--For more on defining identification keys, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).-->

### Índices {#indexes}

O Adobe Campaign adiciona automaticamente uma [índice](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes) para todas as chaves primárias e internas definidas em um recurso.

* A Adobe recomenda definir índices adicionais, pois pode melhorar o desempenho.
* No entanto, não adicione muitos índices, pois eles usam espaço no banco de dados. Vários índices também podem ter um impacto negativo no desempenho.
* Selecione cuidadosamente os índices que precisam ser definidos.

<!--For more on defining indexes, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes).

When you are performing an initial import with very high volumes of data insert in Adobe Campaign database, it is recommended to run that import without custom indexes at first. It will allow to accelerate the insertion process. Once you’ve completed this important import, it is possible to enable the index(es).-->

### Links {#links}

A definição de links com outros recursos é apresentada em [nesta seção](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).

* Embora seja possível unir qualquer tabela em um fluxo de trabalho, o Adobe recomenda definir links comuns entre os recursos diretamente na definição da estrutura de dados.
* O link deve ser definido em alinhamento com os dados reais nas tabelas. Uma definição incorreta poderia afetar os dados recuperados por meio de links, por exemplo, registros duplicados inesperadamente.
* Nomeie o link de forma consistente com o nome do recurso: o nome do link deve ajudar a entender o que é a tabela distante.
* Não nomeie um link com &quot;id&quot; como sufixo. Por exemplo, nomeie-o como &quot;transaction&quot; em vez de &quot;transactionId&quot;.

<!--For more on defining links with other resources, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).-->

## Desempenho {#performance}

Para garantir um melhor desempenho a qualquer momento, siga as práticas recomendadas abaixo.

### Recomendações gerais {#general-recommendations}

* Evite usar operações como &quot;CONTAINS&quot; em consultas. Se você souber o que é esperado e quiser ser filtrado, aplique a mesma condição com um &quot;IGUAL A&quot; ou outros operadores de filtro específicos.
* Evite ingressar em campos não indexados ao criar dados em workflows.
* Tente e certifique-se de que processos como importação e exportação ocorram fora do horário comercial.
* Verifique se há uma programação para todas as atividades diárias e siga a programação.
* Se um ou alguns dos processos diários falharem e for obrigatório executá-los no mesmo dia, verifique se não há processos conflitantes em execução quando o processo manual for iniciado, pois isso pode afetar o desempenho do sistema.
* Certifique-se de que nenhuma das campanhas diárias seja executada durante o processo de importação ou quando qualquer processo manual for executado.
* Use uma ou várias tabelas de referência em vez de duplicar um campo em cada linha. Ao usar pares chave/valor, é preferível escolher uma chave numérica.
* Uma sequência curta permanece aceitável. Caso as tabelas de referência já estejam em vigor em um sistema externo, reutilizar o mesmo facilitará a integração de dados com o Adobe Campaign.

### Relacionamentos um para muitos {#one-to-many-relationships}

* O design de dados afeta a usabilidade e a funcionalidade. Se você projetar seu modelo de dados com várias relações um para muitos, será mais difícil para os usuários criar uma lógica significativa no aplicativo. A lógica de filtro de um para muitos pode ser difícil para profissionais de marketing não técnicos criarem e compreenderem corretamente.
* É bom ter todos os campos essenciais em uma tabela porque facilita a criação de consultas pelos usuários. Às vezes, também é bom que o desempenho duplique alguns campos em tabelas se puder evitar uma associação.
* Certas funcionalidades integradas não poderão fazer referência a relações um para muitos, por exemplo, fórmula de Ponderação da oferta e Entregas.

### Tabelas grandes {#large-tables}

Abaixo estão algumas práticas recomendadas que devem ser seguidas ao projetar seu modelo de dados usando tabelas grandes e associações complexas.

* Reduza o número de colunas, principalmente identificando aquelas que não são usadas.
* Otimize as relações do modelo de dados evitando associações complexas, como associações em várias condições e/ou colunas.
* Para chaves de junção, sempre use dados numéricos em vez de cadeias de caracteres.
* Reduza o máximo possível a profundidade da retenção de registros. Se precisar de um histórico mais profundo, você poderá agregar o cálculo e/ou manipular tabelas de log personalizadas para armazenar um histórico maior.
