---
title: Usar a integração com o Microsoft Dynamics 365
description: Saiba como usar o Microsoft Dynamics 365 com integração de Campaign Standard
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

# Uso da integração com o Microsoft Dynamics 365

Há vários fluxos de dados que a Integração do Adobe Campaign Standard com o Microsoft Dynamics 365 executa. Esses fluxos são detalhados em [esta página](../../integrating/using/d365-acs-self-service-app-workflows.md).

Mais detalhes sobre os fluxos de dados podem ser encontrados mais abaixo neste documento na [Fluxos de dados](#data-flows)  seção.

## Experiência do usuário do Adobe Campaign Standard

Quando um contato é criado, modificado ou excluído (se excluído estiver ativado) no Microsoft Dynamics 365, ele é enviado para o Campaign Standard. Esses contatos estarão visíveis na tela Perfis no Campaign e poderão ser direcionados em campanhas de marketing. Consulte a tela Perfis abaixo.

![](assets/MSdynamicsACS-usage1.png)

Quando um atributo de recusa é modificado no Campaign, ele será refletido no Dynamics 365 se você tiver selecionado o **Unidirecional (Campaign para Microsoft Dynamics 365)** ou **Bidirecional** configuração de recusa e se você tiver esse atributo específico mapeado corretamente.

## Experiência do usuário do Microsoft Dynamics 365

Para saída, os seguintes eventos de marketing por email são enviados do Campaign para o Dynamics 365 e exibidos na exibição Linha do tempo do Microsoft Dynamics 365 como atividades personalizadas:

* Envio de email do Adobe Campaign

* Abertura de email do Adobe Campaign

* Clique no URL de email do Adobe Campaign

* Rejeição de email do Adobe Campaign

Para exibir a Linha do tempo de um contato, navegue até a lista de contatos clicando em Hub de vendas no menu suspenso Dynamics 365. Em seguida, clique em Contatos na barra de menu à esquerda e selecione um contato.

>[!NOTE]
>
>A variável **Adobe Campaign para Microsoft Dynamics 365** O aplicativo no AppSource precisará ser instalado na instância do Microsoft Dynamics 365 para exibir esses eventos. [Saiba mais](../../integrating/using/d365-acs-configure-d365.md#install-appsource-app).

Abaixo você pode ver um instantâneo da tela Contato para &quot;Usuário do Dynamics&quot;. Na exibição Linha do tempo, você perceberá que o usuário do Dynamics recebeu um email associado ao Nome da campanha &quot;2019LoyaltyCamp&quot; e ao Nome da entrega &quot;DM190&quot;. O usuário do Dynamics abriu o email e também clicou em uma URL nele. Ambas as ações criaram eventos que também aparecem abaixo. Se você olhar para o canto direito, verá o cartão Assistente de relacionamento (RA); atualmente, ele contém uma tarefa para acompanhar o URL clicado.

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Veja abaixo um resumo da exibição Linha do tempo para usuários do Dynamics.

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

Veja abaixo um close-up da placa RA (Assistente de Relacionamento). O aplicativo AppSource contém um fluxo de trabalho que observa um evento Adobe Email URL Click. Quando esse evento ocorre, ele cria uma tarefa e define uma data de vencimento. Isso permite que a tarefa seja exibida na placa RA, dando visibilidade adicional a ela. Há um fluxo de trabalho semelhante para eventos de Rejeição de email do Adobe, adicionando uma tarefa para reconciliar o endereço de email inválido. Esses fluxos de trabalho podem ser desativados na solução.

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

Se clicar no assunto do evento de envio, você verá um formulário semelhante ao abaixo. Os formulários para eventos abertos e rejeitados são semelhantes.

![](assets/do-not-localize/mirror_page_url_send.png)

O formulário para eventos de clique de URL de email adiciona um atributo adicional para o URL que foi clicado:

![](assets/do-not-localize/mirror_page_url_click.png)

Veja a seguir uma lista dos atributos e uma descrição:

* **Assunto**: Assunto do evento; composto da ID da campanha e da ID de entrega do delivery de email

* **Proprietário**: o usuário da aplicação criado nas etapas de pós-provisionamento

* **Sobre**: o nome do contato

* **Nome da campanha**: a ID da campanha no Campaign Standard

* **Nome da entrega**: a ID do delivery no Campaign Standard

* **Data de envio/abertura/clique/rejeição**: Data/hora em que o evento foi criado

* **URL de rastreamento**: URL que foi clicado

* **URL da página espelhada**: o URL para a mirror page do email que foi enviado/aberto/clicado/rejeitado. O período de expiração da mirror page do email pode ser modificado na tela de configuração da atividade correspondente do canal de email do Campaign. [Saiba mais](../../administration/using/configuring-email-channel.md#validity-period-parameters).

>[!NOTE]
>
>Para recusa, quando um atributo de recusa é modificado no Microsoft Dynamics 365, ele será refletido no Campaign se você selecionar a opção **Unidirecional (Campaign para Microsoft Dynamics 365)** ou **Bidirecional** configuração de recusa e se você tiver esse atributo específico mapeado corretamente.

## Fluxos de dados {#data-flows}

### Contato e entrada de entidade personalizada

Registros novos, atualizados e excluídos (Observação: as exclusões devem ser habilitadas) são enviados da tabela de contatos do Microsoft Dynamics 365 para a tabela de perfis do Campaign.

Os mapeamentos de tabela podem ser configurados na interface do aplicativo de integração para mapear atributos de tabela do Microsoft Dynamics 365 para atributos de tabela do Campaign. Os mapeamentos de tabela podem ser modificados para adicionar/remover atributos, conforme necessário.

A execução inicial do fluxo de dados foi projetada para transferir todos os registros mapeados, incluindo os marcados como &quot;inativos&quot;. Posteriormente, a integração processará apenas atualizações incrementais. A exceção a isso é se os dados forem repetidos ou se um filtro for configurado; regras de filtragem básicas, baseadas em atributos, podem ser configuradas para determinar quais registros sincronizar com o Campaign.

Regras básicas de substituição podem ser configuradas na interface do usuário do aplicativo de integração para substituir um valor de atributo por um valor diferente (por exemplo, &quot;green&quot; para &quot;#00FF00&quot;, &quot;F&quot; para 1 etc.).

Dependendo do volume de registros, talvez seja necessário usar o armazenamento SFTP do Campaign para a transferência inicial de dados. [Saiba mais](#initial-data-transfer).

O atributo externalId da tabela de perfis do Campaign deve ser preenchido com contactId do atributo de contato do Dynamics 365 para que a entrada do contato funcione. As entidades personalizadas da campanha também devem ser preenchidas com um atributo de ID exclusivo do Dynamics 365; no entanto, esse atributo pode ser armazenado em qualquer atributo de entidade personalizado do Campaign (ou seja, não precisa ser externalId).

>[!NOTE]
>
>Para entrada de entidade personalizada, o controle de alterações deve ser habilitado no Dynamics 365 para entidades personalizadas sincronizadas.

#### Entidades personalizadas

A variável [Integração com o Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) O oferece suporte a entidades personalizadas, permitindo que as entidades personalizadas no Dynamics 365 sejam sincronizadas com os recursos personalizados correspondentes no Campaign.

Os novos dados nos recursos personalizados podem ser usados para várias finalidades, incluindo segmentação e personalização.

A integração oferece suporte a tabelas vinculadas e não vinculadas. A vinculação é suportada em até três níveis (ou seja, nível1->nível2->nível3).

>[!IMPORTANT]
>
>Se qualquer registro de recurso personalizado do Campaign contiver informações pessoais, recomendações específicas serão aplicadas. Saiba mais [nesta seção](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-data).
>

Ao configurar fluxos de dados de entidade personalizados, é importante estar ciente do seguinte:

* A criação e a modificação dos recursos personalizados do Campaign são operações confidenciais que só devem ser executadas por usuários especialistas.
* Para fluxos de dados de entidade personalizados, o controle de alterações deve ser habilitado no Dynamics 365 para entidades personalizadas sincronizadas.
* Se um registro primário e um registro secundário vinculado forem criados quase ao mesmo tempo no Dynamics 365, devido ao processamento paralelo da integração, haverá uma pequena chance de um novo registro secundário ser gravado no Campaign antes do registro primário.

* Se o pai e o filho estiverem vinculados no lado da Campanha usando o **Link simples de cardinalidade 1** o registro secundário permanecerá oculto e inacessível (por meio da interface do usuário ou da API) até que o registro primário chegue ao Campaign.

* (Presumindo **Link simples de cardinalidade 1** no Campaign) Se o registro filho for atualizado ou excluído no Dynamics 365 e essa alteração for gravada no Campaign antes que o registro pai seja exibido no Campaign (não é provável, mas uma possibilidade remota), essa atualização ou exclusão não será processada no Campaign e um erro será lançado. No caso de atualização, o registro em questão precisará ser atualizado no Dynamics 365 novamente para sincronizar o registro atualizado. No caso de exclusão, o registro em questão precisará ser tratado separadamente no lado da campanha, pois não há mais um registro no Dynamics 365 para excluir ou atualizar.

* Se você encontrar uma situação em que acredita ter registros secundários ocultos e não tiver como acessá-los, poderá alterar temporariamente o tipo de link de cardinalidade para **Link simples de cardinalidade 0 ou 1** para acessar esses registros.

Uma visão geral mais abrangente dos recursos personalizados do Campaign pode ser encontrada [nesta seção](../../developing/using/key-steps-to-add-a-resource.md).

### Fluxo de eventos de marketing por email{#email-marketing-event-flow}

Os eventos de marketing por email são enviados do Campaign para o Microsoft Dynamics 365 para serem exibidos na exibição Linha do tempo.

Tipos de evento de marketing compatíveis:
* Enviar - email enviado ao recipient
* Abrir - email aberto pelo destinatário
* Clique - URL no email clicado pelo recipient
* Rejeição - o email para o recipient sofreu uma rejeição permanente

Os seguintes atributos de evento são exibidos no Dynamics 365:
* Nome da campanha de marketing
* Nome do delivery de email
* Carimbo de data e hora
* URL da mirror page de email
* URL clicado (somente eventos de clique)

Os Eventos de marketing por email podem ser ativados/desativados por tipo (enviar, abrir, clicar, rejeição) para que somente os tipos de evento selecionados sejam passados para o Dynamics 365.

### Fluxo de recusa {#opt-out-flow}

Os valores de recusa (por exemplo, inclui na lista de bloqueios) são sincronizados entre sistemas; você tem as seguintes opções para escolher quando integrar:

* **Unidirecional (Microsoft Dynamics 365 para Campaign)**: o Dynamics 365 é a fonte da verdade para cancelamentos. Os atributos de recusa serão sincronizados em uma direção do Dynamics 365 para o Campaign Standard&quot;
* **Unidirecional (Campaign para Microsoft Dynamics 365)**: o Campaign Standard é a fonte da verdade para os cancelamentos. Os atributos de recusa serão sincronizados em uma direção do Campaign Standard para o Dynamics 365
* **Bidirecional**: Dynamics 365 E Campaign Standard são ambas fontes da verdade. Os atributos de recusa serão sincronizados bidirecionalmente entre o Campaign Standard e o Dynamics 365

Como alternativa, se você tiver um processo separado para gerenciar a sincronização de recusa entre os sistemas, o fluxo de dados de recusa da integração poderá ser desativado.

>[!NOTE]
>
>Na interface do aplicativo de integração, a variável **Unidirecional (Microsoft Dynamics 365 para Campaign)** e a variável **Bidirecional** os casos de uso de recusa são configurados em um fluxo de trabalho de recusa separado. [Saiba mais](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).
>
>A variável **Unidirecional (Campaign para Microsoft Dynamics 365)** o caso de uso de recusa é uma exceção; ele é configurado no fluxo de trabalho de entrada (Contato para perfil).
>

O mapeamento do fluxo de recusa deve ser especificado pelo cliente, pois as necessidades comerciais podem diferir entre as empresas. No lado do Campaign, somente os atributos de recusa do OOTB podem ser usados para mapeamento de recusa:

* ➡ incluir na lista de bloqueios
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* ccpaOptOut

No Dynamics 365, a maioria dos campos de recusa tem o prefixo &quot;donot&quot;; no entanto, você também pode utilizar outros atributos para fins de recusa, se os tipos de dados forem compatíveis.

### Transferência inicial de dados {#initial-data-transfer}

A transferência inicial de dados pode demorar um pouco, dependendo de quantos registros você está assimilando do Microsoft Dynamics 365. Após a transferência inicial dos dados, a integração selecionará as atualizações incrementais.
