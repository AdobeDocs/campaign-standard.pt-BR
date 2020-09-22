---
title: Usar a integração com o Microsoft Dynamics 365
description: Saiba como usar o Microsoft Dynamics 365 com integração com o Campaign Standard
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6078a16c679d368dd85cecbb8b715e2de3da805a
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 1%

---


# Usar a integração com o Microsoft Dynamics 365

Há vários trabalhos que essa integração executa:

* **Ingresso**:

   * Trazer **contatos** do Dynamics 365 para a Campanha

   * **Entidades** personalizadas: Trazer tabelas personalizadas do Dynamics 365 para a Campanha. Saiba mais [nesta seção](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md).

* **Saída**: Trazer eventos de marketing de email do ACS para a D365 (envio de email, abrir, clicar, saltar)

* **Recusar**: Status de opção de não participação de sincronização bidirecional (por exemplo, lista de bloqueios)

Mais detalhes sobre os fluxos de dados podem ser encontrados [nesta seção](#data-flows).

## Experiência do usuário Adobe Campaign Standard

Quando um contato é criado ou modificado (ou excluído, se ativado) no Dynamics 365, ele será enviado para a Campanha.  Esses contatos estarão visíveis na tela Perfis na Campanha e poderão ser direcionados para campanhas de marketing.  Consulte a tela Perfis abaixo.

![](assets/MSdynamicsACS-usage1.png)

Quando um atributo de opção de não participação é modificado na Campanha, ele será refletido no Dynamics 365 se você tiver selecionado a configuração Campanha para dinâmica 365 ou opção de não participação bidirecional e se você tiver esse atributo específico mapeado corretamente.

## Experiência de usuário do Microsoft Dynamics 365

Para saída, os seguintes eventos de marketing por email são enviados da Campanha para o Dynamics 365 e exibidos na visualização Linha do tempo do Dynamics 365 como atividades personalizadas:

* Adobe Campaign Email Send

* Abertura de e-mail da Adobe Campaign

* Clique em URL de email da Adobe Campaign

* Rejeição de e-mail do Adobe Campaign

Para visualização da Linha do tempo de um contato, navegue até a lista de contatos clicando no Hub de vendas no menu suspenso Dinâmicas 365.  Em seguida, clique em Contatos na barra de menus esquerda e selecione um contato.

>[!NOTE]
>
>O aplicativo Adobe Campaign for Dynamics 365 no AppSource precisará ser instalado na instância do Dynamics 365 para visualização desses eventos.

Abaixo, você pode ver um instantâneo da tela Contato para &quot;Usuário dinâmico&quot;.  Na visualização Linha do tempo, você notará que o Usuário do Dynamics recebeu um email associado ao Nome da Campanha &quot;2019LoyaltyCamp&quot; e ao Nome do Delivery &quot;DM190&quot;.  O Usuário do Dynamics abriu o email e também clicou em um URL no email; ambas as ações criaram eventos que também são mostrados abaixo.  Se você olhar para o canto direito, verá o cartão do Assistente de relacionamento (RA); atualmente, ele contém uma tarefa para acompanhar o URL clicado.

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Consulte abaixo para obter um close-up da visualização da Linha do tempo para o usuário dinâmico.

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

Abaixo está um close-up do cartão do Assistente de relacionamento (RA).  O aplicativo AppSource contém um fluxo de trabalho que observa um evento de clique no URL do Adobe.  Quando esse evento ocorre, ele cria uma tarefa e define uma data de vencimento.  Isso permite que a tarefa apareça no cartão RA, dando-lhe visibilidade adicional.  Há um fluxo de trabalho semelhante para eventos de Rejeição por E-mail de Adobe, adicionando uma tarefa para reconciliar o endereço de e-mail inválido.  Esses workflows podem ser desativados na solução.

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

Se você clicar no assunto do evento send, verá um formulário semelhante ao abaixo.  Os formulários para eventos abertos e de rejeição são semelhantes.

![](assets/do-not-localize/mirror_page_url_send.png)

O formulário para eventos de cliques em url de email adiciona um atributo adicional para o URL clicado:

![](assets/do-not-localize/mirror_page_url_click.png)

Veja a seguir uma lista dos atributos e uma descrição:

* Assunto: Objeto do evento; composto pela ID de Campanha e pela ID de Delivery do delivery de email

* Proprietário: O usuário do aplicativo criado nas etapas pós-provisionamento

* Relativamente a: O nome do contato

* Nome da campanha: A ID da Campanha no Campaign Standard

* Nome do delivery: A ID do Delivery no Campaign Standard

* Data de Envio/Abertura/Cliquado/Rejeitado: Data/hora em que o evento foi criado

* URL de rastreamento: URL clicado

* URL do mirror page: O URL para o mirror page do email que foi enviado/aberto/clicado/retornado

>[!NOTE]
>
>O período de expiração do mirror page de email pode ser modificado na tela de configuração da atividade de canal de email de Campanha correspondente (consulte Parâmetros [do período de](../../administration/using/configuring-email-channel.md#validity-period-parameters)validade).

>[!NOTE]
>
>Para opção de não participação, quando um atributo de opção de não participação é modificado no Dynamics 365, ele será refletido na Campanha se você tiver selecionado a configuração de opção de não participação dinâmica 365 para Campanha ou bidirecional e se você tiver esse atributo específico mapeado corretamente.

## Fluxos de dados {#data-flows}

### Entradas de contato e entidade personalizada

Registros novos e atualizados (e excluídos, se ativados) são enviados da tabela de contatos do Dynamics 365 para a tabela de perfis de Campanha.

Os mapeamentos de tabela podem ser configurados para mapear atributos de tabela do Dynamics 365 para atributos de tabela de Campanha. Os mapeamentos de tabela podem ser modificados para adicionar/remover atributos, conforme necessário.

A execução inicial do fluxo de dados foi concebida para transferir todos os registros mapeados, incluindo os marcados como &quot;inativos&quot;; subsequentemente, a integração processará apenas atualizações incrementais. A exceção a isso ocorre se um filtro estiver configurado; regras básicas de filtragem baseadas em atributos podem ser configuradas para determinar quais registros sincronizar com a Campanha.

As regras básicas de substituição podem ser configuradas para substituir um valor de atributo por um valor diferente (por exemplo, &quot;verde&quot; para &quot;#00FF00&quot;, &quot;F&quot; para 1, etc.).

Dependendo do volume de registros, seu armazenamento SFTP de Campanha pode precisar ser utilizado para a transferência de dados inicial.  Consulte a seção &quot;Transferência inicial de dados&quot;.

O atributo externalId da tabela do perfil de Campanha deve ser preenchido com o atributo contact contact contact contact contactId do Dynamics 365 para que a entrada do contato funcione. As entidades personalizadas de campanha também devem ser preenchidas com um atributo de ID único do Dynamics 365; no entanto, esse atributo pode ser armazenado em qualquer atributo de entidade personalizada de Campanha (ou seja, não precisa ser externalId).

>[!NOTE]
>
>Para ingressos de entidade personalizados, o rastreamento de alterações deve ser ativado no Dynamics 365 para entidades personalizadas sincronizadas.

### Fluxo do Evento de marketing por email

Os eventos de marketing por email são enviados da Campanha para o Dynamics 365 para serem exibidos na visualização Linha do tempo.

Tipos de evento de marketing suportados:
* Enviar - email enviado para o recipient
* Abrir - email aberto pelo recipient
* Clique - URL no email clicado pelo recipient
* Rejeição - o e-mail para o recipient teve uma forte rejeição

Os seguintes atributos de evento são exibidos na D365:
* Nome da campanha de marketing
* Nome do delivery de email
* Carimbo de data e hora
* URL do mirror page de email
* URL clicado (somente eventos de clique)

Os Eventos de Marketing por email podem ser ativados/desativados por tipo (enviar, abrir, clicar, pular) para que somente os tipos de evento selecionados sejam passados para o Dynamics 365.

### Fluxo de saída

Os valores de opção de não participação (por exemplo, lista de bloqueios) são sincronizados entre os sistemas; você tem as seguintes opções para escolher ao se conectar:
* O Dynamics 365 é fonte de verdade para opções de não participação: os atributos de opção de não participação serão sincronizados em uma direção do Dynamics 365 para o Campaign Standard
* O Campaign Standard é a fonte da verdade para opções de não participação: os atributos de opção de não participação serão sincronizados em uma direção do Campaign Standard para o Dynamics 365
* O Dynamics 365 E o Campaign Standard são duas fontes de verdade: os atributos de não participação serão sincronizados bidirecionalmente entre o Campaign Standard e o Dynamics 365

Como alternativa, se você tiver um processo separado para gerenciar a sincronização de não participação entre os sistemas, o fluxo de dados de não participação da integração poderá ser desativado.

O mapeamento de fluxo de não participação deve ser especificado pelo cliente, já que os requisitos de negócios podem diferir entre as empresas.  No lado da Campanha, somente os atributos de opção de não participação OTB podem ser usados para mapeamento de não participação:
* lista de bloqueios
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* cpaOptOut

No Dynamics 365, a maioria dos campos de opção de não participação têm o prefixo &quot;não&quot;; no entanto, você também pode utilizar outros atributos para fins de não participação se os tipos de dados forem compatíveis.

### Transferência inicial de dados

As tabelas do Dynamics 365 com mais de 500 mil registros precisam ser exportadas para o armazenamento SFTP da Campanha para serem importadas pelo fluxo de trabalho da Campanha.

A transferência inicial de dados é uma transferência única, baseada em arquivos. Após a transferência de dados, a integração usará APIs para as atualizações incrementais.
