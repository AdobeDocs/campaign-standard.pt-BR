---
title: Usar a integração com o Microsoft Dynamics 365
description: Saiba como usar o Microsoft Dynamics 365 com integração com o Campaign Standard
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: fe5d40235abc33c0ea7e929cd2e69b7030cea0b1
workflow-type: tm+mt
source-wordcount: '1607'
ht-degree: 1%

---


# Uso da integração do Microsoft Dynamics 365

Há vários fluxos de dados que a Integração do Adobe Campaign Standard com o Microsoft Dynamics 365 executa. Esses fluxos são detalhados em [esta página](../../integrating/using/d365-acs-self-service-app-workflows.md).

Mais detalhes sobre os fluxos de dados podem ser encontrados mais abaixo neste documento na seção [Fluxos de dados](#data-flows).

## Experiência do usuário Adobe Campaign Standard

Quando um contato é criado, modificado ou excluído (se excluído estiver ativado) no Microsoft Dynamics 365, ele será enviado para o Campaign Standard. Esses contatos estarão visíveis na tela Perfis na Campanha e poderão ser direcionados para campanhas de marketing. Consulte a tela Perfis abaixo.

![](assets/MSdynamicsACS-usage1.png)

Quando um atributo de opção de não participação é modificado na Campanha, ele será refletido no Dynamics 365 se você tiver selecionado a configuração de opção de não participação **Unidirecional (Campanha para Microsoft Dynamics 365)** ou **Bidirecional** e se você tiver esse atributo específico mapeado corretamente.

## Experiência de usuário do Microsoft Dynamics 365

Para saída, os seguintes eventos de marketing por email são enviados da Campanha para o Dynamics 365 e exibidos na visualização de Linha do tempo do Microsoft Dynamics 365 como atividades personalizadas:

* Adobe Campaign Email Send

* Abertura de e-mail da Adobe Campaign

* Clique em URL de email da Adobe Campaign

* Rejeição de e-mail do Adobe Campaign

Para visualização da Linha do tempo de um contato, navegue até a lista de contatos clicando no Hub de vendas no menu suspenso Dinâmicas 365. Em seguida, clique em Contatos na barra de menus esquerda e selecione um contato.

>[!NOTE]
>
>O aplicativo **Adobe Campaign for Microsoft Dynamics 365** no AppSource precisará ser instalado na instância do Microsoft Dynamics 365 para que esses eventos sejam visualizações. [Saiba mais](../../integrating/using/d365-acs-configure-d365.md#install-appsource-app).

Abaixo, você pode ver um instantâneo da tela Contato para &quot;Usuário dinâmico&quot;. Na visualização Linha do tempo, você notará que o Usuário do Dynamics recebeu um email associado ao Nome da Campanha &quot;2019LoyaltyCamp&quot; e ao Nome do Delivery &quot;DM190&quot;. O Usuário do Dynamics abriu o email e também clicou em um URL no email; ambas as ações criaram eventos que também são mostrados abaixo. Se você olhar para o canto direito, verá o cartão do Assistente de relacionamento (RA); atualmente, ele contém uma tarefa para acompanhar o URL clicado.

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Consulte abaixo para obter um close-up da visualização da Linha do tempo para o usuário dinâmico.

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

Abaixo está um close-up do cartão do Assistente de relacionamento (RA). O aplicativo AppSource contém um fluxo de trabalho que observa um evento de clique no URL do Adobe. Quando esse evento ocorre, ele cria uma tarefa e define uma data de vencimento. Isso permite que a tarefa apareça no cartão RA, dando-lhe visibilidade adicional. Há um fluxo de trabalho semelhante para eventos de Rejeição por E-mail de Adobe, adicionando uma tarefa para reconciliar o endereço de e-mail inválido. Esses workflows podem ser desativados na solução.

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

Se você clicar no assunto do evento send, verá um formulário semelhante ao abaixo. Os formulários para eventos abertos e de rejeição são semelhantes.

![](assets/do-not-localize/mirror_page_url_send.png)

O formulário para eventos de cliques em url de email adiciona um atributo adicional para o URL clicado:

![](assets/do-not-localize/mirror_page_url_click.png)

Veja a seguir uma lista dos atributos e uma descrição:

* **Assunto**: Objeto do evento; composto pela ID de Campanha e pela ID de Delivery do delivery de email

* **Proprietário**: O usuário do aplicativo criado nas etapas pós-provisionamento

* **Relativamente**: O nome do contato

* **Nome** da campanha: A ID da Campanha no Campaign Standard

* **Nome** do delivery: A ID do Delivery no Campaign Standard

* **Data de envio/abertura/clique/retorcido**: Data/hora em que o evento foi criado

* **URL** de rastreamento: URL clicado

* **URL** do mirror page: O URL para o mirror page do email que foi enviado/aberto/clicado/retornado. O período de expiração do mirror page de email pode ser modificado na tela de configuração da atividade de canal de email de Campanha correspondente. [Saiba mais](../../administration/using/configuring-email-channel.md#validity-period-parameters).

>[!NOTE]
>
>Para opção de não participação, quando um atributo de opção de não participação é modificado no Microsoft Dynamics 365, ele será refletido na Campanha se você selecionou a configuração de opção **Unidirecional (Campanha para Microsoft Dynamics 365)** ou **Bidirecional** e se você tiver esse atributo específico mapeado corretamente.

## Fluxos de dados {#data-flows}

### Entradas de contato e entidade personalizada

Registros novos, atualizados e excluídos (Observação: deve estar ativado) são enviados da tabela de contatos do Microsoft Dynamics 365 para a tabela de perfis de Campanha.

Os mapeamentos de tabela podem ser configurados na interface do usuário do aplicativo de integração para mapear atributos de tabela do Microsoft Dynamics 365 para atributos de tabela de Campanha. Os mapeamentos de tabela podem ser modificados para adicionar/remover atributos, conforme necessário.

A execução inicial do fluxo de dados foi concebida para transferir todos os registros mapeados, incluindo os marcados como &quot;inativos&quot;; subsequentemente, a integração processará apenas atualizações incrementais. A exceção a isso ocorre se os dados forem repetidos ou se um filtro for configurado; regras básicas de filtragem baseadas em atributos podem ser configuradas para determinar quais registros sincronizar com a Campanha.

As regras básicas de substituição podem ser configuradas na interface do usuário do aplicativo de integração para substituir um valor de atributo por um valor diferente (por exemplo, &quot;verde&quot; para &quot;#00FF00&quot;, &quot;F&quot; para 1 etc.).

Dependendo do volume de registros, seu armazenamento SFTP de Campanha pode precisar ser utilizado para a transferência de dados inicial. [Saiba mais](#initial-data-transfer).

O atributo externalId da tabela do perfil de Campanha deve ser preenchido com o atributo contact contact contact contact contactId do Dynamics 365 para que a entrada do contato funcione. As entidades personalizadas de campanha também devem ser preenchidas com um atributo de ID único do Dynamics 365; no entanto, esse atributo pode ser armazenado em qualquer atributo de entidade personalizada de Campanha (ou seja, não precisa ser externalId).

>[!NOTE]
>
>Para ingressos de entidade personalizados, o rastreamento de alterações deve ser ativado no Dynamics 365 para entidades personalizadas sincronizadas.

#### Entidades personalizadas

A [integração do Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) oferece suporte a entidades personalizadas, permitindo que as entidades personalizadas no Dynamics 365 sejam sincronizadas com os recursos personalizados correspondentes na Campanha.

Os novos dados nos recursos personalizados podem ser usados para vários fins, incluindo segmentação e personalização.

A integração suporta tabelas vinculadas e não vinculadas. A vinculação é suportada até três níveis (ou seja, level1->level2->level3).

>[!IMPORTANT]
>
>Se qualquer registro de recurso personalizado de Campanha contiver informações pessoais, serão aplicadas recomendações específicas. Saiba mais [nesta seção](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-data).


Ao configurar fluxos de dados de entidade personalizados, é importante ter em mente o seguinte:

* Criar e modificar recursos personalizados de Campanha são operações confidenciais que devem ser executadas somente por usuários especialistas.
* Para fluxos de dados de entidade personalizados, o rastreamento de alterações deve ser ativado no Dynamics 365 para entidades personalizadas sincronizadas.
* Se um registro pai e filho vinculado forem criados perto da mesma hora no Dynamics 365, devido ao processamento paralelo da integração, há uma pequena chance de que um novo registro filho possa ser gravado na Campanha antes de seu registro pai.

* Se o pai e o filho estiverem vinculados na Campanha usando a opção **1 cardinality simple link**, o registro filho permanecerá oculto e inacessível (por UI ou API) até que o registro pai chegue na Campanha.

* (Assumindo que **1 cardinality simple link** na Campanha) Se o registro filho for atualizado ou excluído no Dynamics 365 e essa alteração for gravada na Campanha antes que o registro pai seja exibido na Campanha (não é provável, mas uma possibilidade remota), essa atualização ou exclusão não será processada na Campanha e um erro será lançado. Em caso de atualização, o registro em questão terá de ser atualizado novamente no Dynamics 365 para sincronizar o registro atualizado. Em caso de supressão, o registro em questão terá de ser tratado separadamente do lado da Campanha, uma vez que já não existe um registro no Dynamics 365 para eliminar ou atualizar.

* Se você encontrar uma situação em que acredita ter ocultado registros secundários e não ter como acessá-los, é possível alterar temporariamente o tipo de link de cardinalidade para **0 ou 1 simples de cardinalidade** para acessar esses registros.

Uma visão geral mais abrangente dos recursos personalizados da Campanha pode ser encontrada [nesta seção](../../developing/using/key-steps-to-add-a-resource.md).

### Fluxo de evento de marketing por email{#email-marketing-event-flow}

Os eventos de marketing por email são enviados da Campanha para o Microsoft Dynamics 365 para serem exibidos na visualização Linha do tempo.

Tipos de evento de marketing suportados:
* Enviar - email enviado para o recipient
* Abrir - email aberto pelo recipient
* Clique - URL no email clicado pelo recipient
* Rejeição - o e-mail para o recipient teve uma forte rejeição

Os seguintes atributos de evento são exibidos no Dynamics 365:
* Nome da campanha de marketing
* Nome do delivery de email
* Carimbo de data e hora
* URL do mirror page de email
* URL clicado (somente eventos de clique)

Os Eventos de Marketing por email podem ser ativados/desativados por tipo (enviar, abrir, clicar, pular) para que somente os tipos de evento selecionados sejam passados para o Dynamics 365.

### Fluxo de saída {#opt-out-flow}

Os valores de opção de não participação (por exemplo, lista de bloqueios) são sincronizados entre os sistemas; você tem as seguintes opções para escolher ao se conectar:

* **Unidirecional (Microsoft Dynamics 365 para Campanha)**: O Dynamics 365 é fonte de verdade para opções. Os atributos de não participação serão sincronizados em uma direção do Dynamics 365 para o Campaign Standard&quot;
* **Unidirecional (Campanha ao Microsoft Dynamics 365)**: O Campaign Standard é a fonte da verdade para opções. Os atributos de não participação serão sincronizados em uma direção do Campaign Standard para o Dynamics 365
* **Bidirecional**: O Dynamics 365 E o Campaign Standard são duas fontes de verdade. Os atributos de não participação serão sincronizados bidirecionalmente entre o Campaign Standard e o Dynamics 365

Como alternativa, se você tiver um processo separado para gerenciar a sincronização de não participação entre os sistemas, o fluxo de dados de não participação da integração poderá ser desativado.

>[!NOTE]
>
>Na interface do usuário do aplicativo de integração, os **Unidirecionais (Microsoft Dynamics 365 para Campanha)** e os **Bidirecionais** casos de uso de opção de não participação são configurados em um fluxo de trabalho de opção de não participação separado. [Saiba mais](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).
>
>O caso de **Unidirecional (Campanha ao Microsoft Dynamics 365)** opção de não participação é uma exceção; está configurado no fluxo de trabalho de entrada (Entrar em contato com o Perfil).


O mapeamento de fluxo de não participação deve ser especificado pelo cliente, já que os requisitos de negócios podem diferir entre as empresas. No lado da Campanha, somente os atributos de opção de não participação OTB podem ser usados para mapeamento de não participação:

* lista de bloqueios
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* cpaOptOut

No Dynamics 365, a maioria dos campos de opção de não participação têm o prefixo &quot;não&quot;; no entanto, você também pode utilizar outros atributos para fins de não participação se os tipos de dados forem compatíveis.

### Transferência inicial de dados {#initial-data-transfer}

A transferência de dados inicial pode levar algum tempo, dependendo de quantos registros você está ingerindo do Microsoft Dynamics 365. Após a transferência inicial de dados, a integração coletará as atualizações incrementais.
