---
title: Usar a integração com o Microsoft Dynamics 365
description: Saiba como usar o Microsoft Dynamics 365 com integração Campaign Standard
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: fb464183-13bf-4b47-ac27-4b785bafef37
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1607'
ht-degree: 1%

---

# Usar a integração com o Microsoft Dynamics 365

Há vários fluxos de dados que a Integração do Adobe Campaign Standard com o Microsoft Dynamics 365 executa. Esses fluxos são detalhados em [esta página](../../integrating/using/d365-acs-self-service-app-workflows.md).

More details on the data flows can be found further down in this document in the [Data Flows](#data-flows)  section.

## Adobe Campaign Standard user experience

Quando um contato é criado, modificado ou excluído (se excluído estiver habilitado) no Microsoft Dynamics 365, ele será enviado para o Campaign Standard. Esses contatos estarão visíveis na tela Perfis no Campaign e podem ser direcionados para campanhas de marketing. Consulte a tela Perfis abaixo.

![](assets/MSdynamicsACS-usage1.png)

Quando um atributo de opt out é modificado no Campaign, ele será refletido no Dynamics 365 se você tiver selecionado a variável **Unidirecional (Campanha para Microsoft Dynamics 365)** ou **Bidirecional** configuração de não participação e se você tiver esse atributo específico mapeado corretamente.

## Experiência do usuário do Microsoft Dynamics 365

Para saída, os seguintes eventos de marketing por email são enviados do Campaign para o Dynamics 365 e exibidos na linha do tempo do Microsoft Dynamics 365 como atividades personalizadas:

* Envio de email do Adobe Campaign

* Adobe Campaign Email Open

* Clique no URL de email do Adobe Campaign

* Rejeição de email do Adobe Campaign

Para visualizar a Linha do tempo de um contato, navegue até a lista de contatos clicando em Central de vendas no menu suspenso Dynamics 365 . Em seguida, clique em Contacts (Contatos) na barra de menu à esquerda e selecione um contato.

>[!NOTE]
>
>O **Adobe Campaign para Microsoft Dynamics 365** O aplicativo no AppSource precisará ser instalado na instância do Microsoft Dynamics 365 para exibir esses eventos. [Saiba mais](../../integrating/using/d365-acs-configure-d365.md#install-appsource-app).

Abaixo você pode ver um instantâneo da tela Contato para &quot;Usuário dinâmico&quot;. Na exibição Linha do tempo, você observará que o Usuário do Dynamics recebeu um email associado ao Nome da campanha &quot;2019LoyaltyCamp&quot; e ao Nome do delivery &quot;DM190&quot;. O usuário do Dynamics abriu o email e também clicou em um URL no email; ambas as ações criaram eventos que também são mostrados abaixo. Se você observar o canto direito, verá o cartão do Assistente de relacionamento (RA); no momento, ele contém uma tarefa para acompanhar o URL clicado.

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Veja abaixo um fechamento da exibição Linha do tempo para o usuário do Dynamics.

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

Abaixo está um fechamento do cartão do Assistente de relacionamento (RA). O aplicativo AppSource contém um fluxo de trabalho que assiste a um evento de clique no URL de email do Adobe. Quando esse evento ocorre, ele cria uma tarefa e define uma data de vencimento. Isso permite que a tarefa seja exibida no cartão RA, dando a ela visibilidade adicional. Há um workflow semelhante para eventos Adobe Email Bounce, adicionando uma tarefa para reconciliar o endereço de email inválido. Esses workflows podem ser desativados na solução .

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

Se clicar no assunto do evento de envio, você verá um formulário semelhante ao abaixo. Os formulários para eventos de abertura e rejeição são semelhantes.

![](assets/do-not-localize/mirror_page_url_send.png)

O formulário para eventos de clique em url de email adiciona um atributo adicional para o URL que foi clicado:

![](assets/do-not-localize/mirror_page_url_click.png)

Veja a seguir uma lista dos atributos e uma descrição:

* **Assunto**: Objeto do evento; composto pela ID da campanha e pela ID de entrega do delivery de email

* **Proprietário**: O usuário do aplicativo criado nas etapas pós-provisionamento

* **Relativo**: O nome do contato

* **Nome da campanha**: A ID da campanha no Campaign Standard

* **Nome do delivery**: A ID de entrega no Campaign Standard

* **Date Sent/Opened/Clicked/Bounced**: Date/time when the event was created

* **URL de rastreamento**: URL que foi clicado

* **URL da Mirror Page**: O URL para a mirror page do email que foi enviado/aberto/clicado/retornado. The expiry period of the email mirror page can be modified in the configuration screen of the corresponding Campaign email channel activity. [Saiba mais](../../administration/using/configuring-email-channel.md#validity-period-parameters).

>[!NOTE]
>
>For opt-out, when an opt-out attribute is modified in Microsoft Dynamics 365, it will be reflected in Campaign if you selected the **Unidirectional (Campaign to Microsoft Dynamics 365)** or **Bidirectional** opt-out configuration, and if you have that particular attribute mapped correctly.

## Fluxos de dados {#data-flows}

### Entrada de entidade personalizada e de contato

New, updated, and deleted records (Note: deleted must be enabled) are sent from the Microsoft Dynamics 365 contact table to the Campaign profile table.

Os mapeamentos de tabela podem ser configurados na interface do usuário do aplicativo de integração para mapear os atributos de tabela do Microsoft Dynamics 365 para atributos de tabela do Campaign. Os mapeamentos da tabela podem ser modificados para adicionar/remover atributos, conforme necessário.

The initial run of the data flow is designed to transfer all mapped records, including those marked as &quot;inactive&quot;; subsequently, the integration will only process incremental updates. A exceção a isso ocorre se os dados forem repetidos ou se um filtro for configurado; regras básicas de filtragem baseadas em atributos podem ser configuradas para determinar quais registros sincronizar com o Campaign.

As regras básicas de substituição podem ser configuradas na interface do usuário do aplicativo de integração para substituir um valor de atributo por um valor diferente (por exemplo, &quot;verde&quot; para &quot;#00FF00&quot;, &quot;F&quot; para 1, etc.).

Dependendo do volume de registros, o armazenamento SFTP do Campaign pode precisar ser utilizado para a transferência inicial de dados. [Saiba mais](#initial-data-transfer).

O atributo externalId da tabela de perfil do Campaign deve ser preenchido com a ID de contato do atributo de contato do Dynamics 365 para que a entrada de contato funcione. As entidades personalizadas do Campaign também devem ser preenchidas com um atributo de ID único do Dynamics 365; no entanto, esse atributo pode ser armazenado em qualquer atributo de entidade personalizada do Campaign (ou seja, não precisa ser externalId).

>[!NOTE]
>
>Para entradas de entidade personalizadas, o rastreamento de alterações deve ser ativado no Dynamics 365 para entidades personalizadas sincronizadas.

#### Entidades personalizadas

O [Integração do Microsoft Dynamics 365 com o Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) O suporta entidades personalizadas, permitindo que entidades personalizadas no Dynamics 365 sejam sincronizadas com os recursos personalizados correspondentes no Campaign.

The new data in the custom resources can be used for several purposes, including segmentation and personalization.

A integração oferece suporte a tabelas vinculadas e não vinculadas. A vinculação é compatível até três níveis (ou seja, nível1->nível2->nível3).

>[!IMPORTANT]
>
>Se qualquer registro de recurso personalizado do Campaign contiver informações pessoais, recomendações específicas serão aplicadas. Saiba mais [nesta seção](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-data).

Ao configurar fluxos de dados de entidade personalizados, é importante estar ciente do seguinte:

* A criação e a modificação de recursos personalizados do Campaign são operações confidenciais que devem ser executadas apenas por usuários especialistas.
* Para fluxos de dados de entidade personalizados, o rastreamento de alterações deve ser ativado no Dynamics 365 para entidades personalizadas sincronizadas.
* Se um registro pai e um registro filho vinculado forem criados próximo ao mesmo tempo no Dynamics 365, devido ao processamento paralelo da integração, há uma pequena chance de que um novo registro filho possa ser gravado no Campaign antes de seu registro pai.

* If the parent and child are linked on the Campaign side using the **1 cardinality simple link** option, the child record will remain hidden and inaccessible (via UI or API) until the parent record arrives in Campaign.

* (Assumindo **1 cardinalidade simple link** no Campaign) Se o registro filho for atualizado ou excluído no Dynamics 365 e essa alteração for gravada no Campaign antes que o registro pai seja exibido no Campaign (não é provável, mas uma possibilidade remota), essa atualização ou exclusão não será processada no Campaign e um erro será lançado. No caso de atualização, o registro em questão precisará ser atualizado novamente no Dynamics 365 para sincronizar o registro atualizado. No caso de exclusão, o registro em questão precisará ser tratado separadamente no lado da campanha, pois não há mais um registro no Dynamics 365 para excluir ou atualizar.

* Se você encontrar uma situação em que acredita ter ocultado registros secundários e não ter como acessá-los, poderá alterar temporariamente o tipo de link de cardinalidade para **0 ou 1 cardinalidade simple link** para acessar esses registros.

Uma visão geral mais abrangente dos recursos personalizados do Campaign pode ser encontrada [nesta seção](../../developing/using/key-steps-to-add-a-resource.md).

### Fluxo de evento de marketing por email{#email-marketing-event-flow}

Os eventos de marketing por email são enviados do Campaign para o Microsoft Dynamics 365 para serem exibidos na exibição Linha do tempo.

Supported marketing event types:
* Send – email sent to recipient
* Open – email opened by recipient
* Clique em - URL no email clicado por recipient
* Rejeição - email para recipient teve uma rejeição permanente

Os seguintes atributos de evento são exibidos no Dynamics 365:
* Nome da campanha de marketing
* Nome do delivery de email
* Carimbo de data e hora
* URL da mirror page de email
* URL clicado (somente eventos de clique)

Os Eventos de marketing de email podem ser ativados/desativados por tipo (enviar, abrir, clicar, retornar) para que somente os tipos de evento selecionados sejam passados para o Dynamics 365.

### Fluxo de rejeição {#opt-out-flow}

Os valores de rejeição (por exemplo, lista de bloqueios) são sincronizados entre os sistemas; você tem as seguintes opções para escolher ao integrar:

* **Unidirecional (Microsoft Dynamics 365 para Campaign)**: O Dynamics 365 é fonte de verdade para opções de não participação. Os atributos de rejeição serão sincronizados em uma direção do Dynamics 365 para o Campaign Standard&quot;
* **Unidirecional (Campanha para Microsoft Dynamics 365)**: O Campaign Standard é a fonte de verdade para opções de não participação. Os atributos de rejeição serão sincronizados em uma direção do Campaign Standard para o Dynamics 365
* **Bidirecional**: O Dynamics 365 E o Campaign Standard são ambas fontes de verdade. Os atributos de rejeição serão sincronizados bidirecionalmente entre o Campaign Standard e o Dynamics 365

Como alternativa, se você tiver um processo separado para gerenciar a sincronização de opt-out entre os sistemas, o fluxo de dados de opt-out da integração poderá ser desativado.

>[!NOTE]
>
>Na interface do usuário do aplicativo de integração, a variável **Unidirecional (Microsoft Dynamics 365 para Campaign)** e **Bidirecional** os casos de uso de recusa são configurados em um fluxo de trabalho de recusa separado. [Saiba mais](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).
>
>O **Unidirecional (Campanha para Microsoft Dynamics 365)** o caso de uso de opt-out é uma exceção; ele é configurado no workflow ingress (Contact to Profile) .

O mapeamento de fluxo de rejeição deve ser especificado pelo cliente, pois os requisitos comerciais podem diferir entre as empresas. No lado da Campanha, somente os atributos de não participação do OOTB podem ser usados para o mapeamento de não participação:

*  lista de bloqueios
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* ccpaOptOut

No Dynamics 365, a maioria dos campos de opção de não participação tem o prefixo &quot;não&quot;; no entanto, também é possível utilizar outros atributos para fins de recusa se os tipos de dados forem compatíveis.

### Transferência inicial de dados {#initial-data-transfer}

A transferência inicial de dados pode demorar um pouco, dependendo de quantos registros você está assimilando do Microsoft Dynamics 365. Após a transferência inicial de dados, a integração selecionará as atualizações incrementais.
