---
title: Notas de versão 2015-2016
seo-title: Notas de versão 2015-2016
description: Notas de versão 2015-2016
seo-description: Esta página lista todas as versões 2015 e 2016 do Adobe Campaign Standard.
page-status-flag: nunca ativado
uuid: d 5 a 0 f 6 cc -0 bed -46 cf -8 dff -1717 fb 624 f 8 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: versões padrão da campanha
discoiquuid: a 3 ce 6 b 80-1858-49 d 1-8880-3543181127 f 4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Release Notes 2015-2016{#release-notes}

Procurando uma versão específica de 2015-2016 do Adobe Campaign Standard?

Cada versão traz novos recursos e correções. Clique em uma versão para exibir seu conteúdo.

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a newer release, consult this [page](../../rn/using/release-notes.md).

## Release 16.11 - November 2016 {#release-16-11---november-2016}

### New capabilities {#new-capabilities}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Deliverability exclusion rules<br /> </td> 
   <td> Uma lista de exclusão global criptografada agora é gerenciada na instância de entrega para evitar que seja bloqueada devido a uma atividade maliciosa, especialmente ao uso de um Spamapping.<br /> Para cada entrega de email, duas regras de tipologia padrão comparam os endereços de email do destinatário com os endereços proibidos ou os nomes de domínio contidos nesta lista. Se houver uma correspondência, o destinatário será excluído da população alvo.<br /> Para obter mais informações, consulte a <a href="../../administration/using/filtering-rules.md#default-deliverability-exclusion-rules">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> General optimization<br /> </td> 
   <td> Esta atualização inclui diversas alterações e correções que corrigem problemas encontrados pelos nossos clientes. The global platform performances have also been optimized. <br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches}

#### General {#general}

* Corrigidos vários problemas de segurança.
* Correção de vários problemas relacionados a campos vazios ou campos duplicados na REST API.
* Agora é possível criar mensagens SMS e notificações por push diretamente na página inicial do aplicativo.

#### Emails and SMS messages {#emails-and-sms-messages}

* Correção de um problema que impedia os usuários de carregarem arquivos postais no editor de conteúdo.
* Correção de um problema que impedia a abertura de uma prova após o envio.
* Fixed an issue that led to an error message displaying when accessing the **[!UICONTROL Hot Clicks]** report on an A/B test email.
* Fixed an issue that prevented modifications made using the **[!UICONTROL Show source]** mode from being applied.
* Correção de um problema que podia impedir a importação de arquivos de modelo de xml de linha de assunto preditiva.
* A new screen dedicated to importing data for the subject line trained model is now available in **[!UICONTROL Administration > Channels > Emails > Predictive Subject Line]** .
* Correção de um problema que permitia que usuários não administradores editassem as máscaras autorizadas na tela de configuração de email.

#### Push notifications {#push-notifications}

* Fixed an issue that prevented sending logs and event logs from being displayed for the recipients after sending a push notification using the **[!UICONTROL Send push on profiles]** template.
* Correção de um problema que podia impedir a criação de novos aplicativos móveis.

#### Workflows {#workflows}

* Fixed a performance issue that occured when using the **[!UICONTROL Subscription]** activity.
* Correção de um problema que impedia o funcionamento de um fluxo de trabalho quando seu nome interno continha um espaço.

#### Integrations {#integrations}

* Fixed an issue that could lead to an error being displayed when using the **Image shared from Adobe Marketing Cloud** option in an email.

#### Custom resources {#custom-resources}

* A visualização de log apis aprimorada entre duas publicações de campos API estendidos.
* Correção de um problema que impedia que um recurso personalizado fosse excluído antes da publicação.
* Correção de um problema que impedia a definição de perfis e as teclas de identificador com um campo dinâmico.
* Correção de um problema que ocorria ao adicionar links em um recurso personalizado.

## Release 16.10 - October 2016 {#release-16-10---october-2016}

### New capabilities {#new-capabilities-1}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Email predictive subject line<br /> </td> 
   <td> Ao editar um e-mail, uma nova opção permite que você experimente linhas de assunto diferentes e obtenha uma estimativa de sua taxa aberta antes de enviá-la. Isso pode ser feito por treinamento de seu próprio modelo com base nos dados de entrega passados ou usando um modelo predefinido específico para o seu setor. Esse recurso está disponível para mensagens de email e para bancos de dados que contenham apenas conteúdo em inglês. <br /> Para obter mais informações sobre como ativá-la e usá-la, consulte a documentação <a href="../../designing/using/personalizing-the-subject-line-of-an-email.md#predictive-subject-line">detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> SMS transactional messaging<br /> </td> 
   <td> O canal SMS foi adicionado aos recursos transacionais de mensagem do Adobe Campaign. Dois canais agora são compatíveis com mensagens transacionais: email e SMS.<br /> Para obter mais informações, consulte a <a href="../../administration/using/configuring-transactional-messaging.md#creating-an-event">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Follow-up message for transactional messaging<br /> </td> 
   <td> Agora é possível criar um fluxo de trabalho direcionado a um evento. Isso significa que você pode enviar uma mensagem de acompanhamento aos clientes que receberam uma mensagem transacional anteriormente. Você pode filtrar a meta pelo tipo de evento, pelos logs broadbroade pelos logs de rastreamento. Na mensagem de acompanhamento, você poderá aproveitar o conteúdo do evento (carga). <br /> Para obter mais informações, consulte a <a href="../../channels/using/follow-up-messages.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Extended Profile &amp; Services API<br /> </td> 
   <td> Agora é possível expor campos estendidos na API de perfil e de serviços. O mecanismo de publicação permite que apis mapeiem os campos estendidos dos recursos personalizados Perfis ou Serviços. For this to work, the <strong>Datamodel</strong> role has been added. Essa nova função permite que o usuário configure um conjunto de administradores que terão acesso ao modelo de dados.<br /> Para obter mais informações, consulte a <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-1}

#### General {#general-1}

* Corrigidos vários problemas de segurança.

#### Emails and SMS messages {#emails-and-sms-messages-1}

* The SMS external account configuration screen ( **[!UICONTROL Administration > Channels > SMS > SMS accounts]** ) has been improved. Several parameters have been added in the **[!UICONTROL SMSC specifics]** section to support error codes in the "Text" field.

#### Push notifications {#push-notifications-1}

* Fixed an issue that prevented the predefined filters from being displayed when editing the audience of a push notification based on the **[!UICONTROL Send via push notification]** (mobileApp) template.
* The mobile application configuration screen ( **[!UICONTROL Administration > Channels > Push Notification > Mobile applications]** ) now displays a message to indicate that the iOS or Android platform has been successfully created.

#### Landing pages {#landing-pages}

* Correção de problemas que impedia que emails de confirmação fossem enviados quando um formulário de página de aterrissagem era enviado.

#### Audiences and queries {#audiences-and-queries}

* Corrigidos vários problemas que ocorriam ao selecionar um perfil no editor de consultas.

#### Transactional messages {#transactional-messages}

* Correção de um erro que impedia a publicação de um modelo transacional.
* Correção de um problema que fazia com que os eventos de acionamento fossem exibidos na lista de eventos.

#### Integrations {#integrations-1}

* Correção de um problema que impedia que um público compartilhado fosse usado em uma entrega depois que o público-alvo era atualizado.
* Fixed an issue that prevented a shared asset ( **[!UICONTROL Image shared from Adobe Marketing Cloud]** option) from being used in a landing page.
* Corrigidos os problemas que ocorria ao editar um público-alvo compartilhado importado do Adobe Audience Manager.

## Release 16.9 - September 2016 {#release-16-9---september-2016}

### New capabilities {#new-capabilities-2}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Remarketing Triggers<br /> </td> 
   <td> Integration between the core service <span class="uicontrol">Triggers</span> and Adobe Campaign allows you to send personalized emails to your customers as a reaction to specific behaviors that are tracked on your website by Adobe Analytics (within 15 minutes).<br /> Na Adobe Marketing Cloud, você define os diferentes acionadores, isto é, os comportamentos do cliente que você deseja monitorar, como todos os clientes que abandonaram o carrinho ou o formulário, removem um produto do carrinho ou até mesmo os clientes cuja sessão expirou. Ao criar um acionador, você define a condição do acionador e os dados que serão enviados no evento (carregar) para o Adobe Campaign. <br /> No Adobe Campaign, você seleciona o disparador criado anteriormente, aprimora os dados do evento com dados de dados e define um modelo de mensagem transacional vinculado a esse acionador. Por exemplo, quando um cliente abandona o carrinho, um evento é enviado para o Adobe Campaign, que pode aproveitar esse evento por meio de um email de recomercialização enviado para o cliente em 15 minutos.<br /> Para obter mais informações, consulte a <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional messages: Pause / Unpublish<br /> </td> 
   <td> Agora você pode suspender a publicação de um modelo transacional enquanto atualiza seu conteúdo. As mensagens correspondentes não são mais enviadas, mas são armazenadas no banco de dados. Ao retomar, as mensagens em fila são processadas e enviadas se elas não tiverem expirado.<br /> Para obter mais informações, consulte a <a href="../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication">documentação detalhada</a>.<br /> Agora você pode cancelar a publicação de eventos e modelos transacionais. As mensagens correspondentes não são mais enviadas e não são armazenadas no banco de dados.<br /> Para obter mais informações, consulte a <a href="../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Multibranding<br /> </td> 
   <td> Os clientes com várias marcas agora podem gerenciá-los na mesma instância. A marca é um recurso gerenciado pelo administrador da sua instância do Adobe Campaign, que permite a configuração centralizada de todos os parâmetros relacionados a uma marca dentro do Adobe Campaign. Isso inclui informações como o logotipo para parâmetros mais técnicos, como urls de rastreamento, análises da Web, URL do servidor, nome do domínio etc.<br /> Para obter mais informações, consulte a <a href="../../administration/using/branding.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Responsive email design preview<br /> </td> 
   <td> Esse recurso permite testar a responsividade de seu email em diferentes tipos de dispositivos. In the email preview, a grid has been added to test your email on various screen sizes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push notifications<br /> </td> 
   <td> Um novo canal foi adicionado para permitir que os profissionais de marketing enviem notificações por push personalizadas e segmentadas em dispositivos móveis iOS e Android. As mensagens podem ser enviadas por meio de uma única entrega ou por uma atividade de fluxo de trabalho. A compatibilidade com as mensagens transacionais estará disponível em versões futuras. This channel leverages the Mobile core service’s SDK (available <a href="https://marketing.adobe.com/developer/gallery/marketing-cloud-mobile-libraries">here</a>).<br /> Para obter mais informações, consulte a <a href="../../channels/using/about-push-notifications.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-2}

#### General {#general-2}

* Esta versão introduz novos recursos de filtragem e pesquisa nas listas da interface. Esse novo recurso está disponível, por exemplo, nos registros (entrega, rastreamento), nos serviços (assinatura, histórico de assinaturas), nos públicos-alvo e nas transições de fluxo de trabalho.
* Corrigidos vários problemas de exibição com relação ao número de pontos de contato em um perfil do cliente.
* Correção de vários problemas de tipologia.

#### Emails and SMS messages {#emails-and-sms-messages-2}

* Correção de um erro que permitia a edição de provas errôneas. Agora, eles são somente leitura.
* Correção de um problema que fazia com que um destinatário ficasse bloqueado quando um SMS era muito longo ou causava problemas de codificação.

#### Custom resources {#custom-resources-1}

* Correção de um erro que impedia que todos os resultados fossem exibidos ao usar os filtros avançados de um recurso personalizado.

#### Transactional messages {#transactional-messages-1}

* Um prefixo é adicionado automaticamente ao identificador de uma nova definição de evento.
* O ícone que representa as mensagens transacionais na interface foi alterado.

#### Integrations {#integrations-2}

* Fixed a display error that would occur when a high resolution image was inserted via the **Dynamic image from Adobe Target** option.
* Correção de um erro que permitia que um público-alvo compartilhado fosse salvo mesmo se a ID de destino não fosse definida na Fonte de dados AMC.

## Release 16.7 - July 2016 {#release-16-7---july-2016}

### New capabilities {#new-capabilities-3}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Enriched transactional messages<br /> </td> 
   <td> Agora você pode vincular modelos transacionais com o banco de dados do Adobe Campaign para recuperar informações que permitem aprimorar o conteúdo das mensagens transacionais.<br /> Para obter mais informações, consulte a <a href="../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamic URLs for images<br /> </td> 
   <td> Essa nova funcionalidade permite personalizar uma fonte de imagem inserindo blocos de conteúdo e texto dinâmico para fins de rastreamento e personalização.<br /> Em seguida, torna-se possível, entre outras coisas, valorizar as funcionalidades da mídia dinâmica do AEM Asset (S 7) inserindo parâmetros nos urls da imagem. Por exemplo, você pode enviar um e-mail com imagens personalizadas declarando "Hello Alexandre, obtenha as notícias mais recentes sobre os próximos eventos em Paris!" ou "Hello Frank, obtenha as notícias mais recentes sobre os próximos eventos em Nova York!".<br /> Para obter mais informações, consulte a <a href="../../designing/using/personalizing-urls.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integration with People Core Service<br /> </td> 
   <td> The Adobe Marketing Cloud <strong>Declared IDs</strong> are now covered by the integration between Adobe Campaign and People Core Service (Profiles &amp; Audiences).<br /> Isso significa que você pode importar segmentos e exportar públicos criados de IDs <strong>de visitante</strong>ou <strong>IDs declaradas</strong>.<br /> Para obter mais informações, consulte a <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery logs<br /> </td> 
   <td> The MTA logs (delivery server) now display the complete history of each message, particularly all of the delivery attempts as well as the associated error statuses, and this has no impact on the application's performance.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-3}

#### General {#general-3}

* Corrigido um erro que fazia com que campos irrelevantes fossem exibidos em vez de campos que precisam ser concluídos. Isso ocorria após a modificação do operador de comparação várias vezes ao editar uma condição em uma consulta.
* Fixed the behavior of the option **[!UICONTROL The last X days/months/quarters/years]** when defining a relative filtering condition for a date field. O período calculado agora é um período deslizante relativo à data e à hora do servidor, e não ao calendário.

#### Workflows {#workflows-1}

* Fixed an error that would return an incorrect list of values in the screen for selecting the targeting dimension in the properties of a **[!UICONTROL Query]** activity.
* Fixed an error that would force the **Exists** operator to be selected when adding an average or count aggregate on a collection element in a **[!UICONTROL Query]** activity.

#### Content editing {#content-editing}

* Correção de um erro que resultava em problemas de exibição (design responsivo) ao importar conteúdo HTML: os atributos de estilo não são mais reescritos quando o conteúdo é aberto pela primeira vez após ser importado.
* Correção de um erro de não bloqueio que era causado quando uma condição era adicionada em uma variante de conteúdo dinâmico.
* Correção de um erro causado pela adição de uma caixa de seleção no conteúdo de uma página de aterrissagem. A caixa de seleção não era utilizável.
* Corrigido um erro que ocorria ao excluir o texto em um bloco se o cursor fosse colocado no início do bloco em questão.

#### Transactional messages {#transactional-messages-2}

* Ao integrar um site, você pode definir uma data de expiração para qualquer evento específico. Uma vez que esta data for transmitida, a mensagem correspondente ao evento não poderá mais ser enviada.

## Release 16.6 - June 2016 {#release-16-6---june-2016}

### New capabilities {#new-capabilities-4}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Profiles and Services API<br /> </td> 
   <td> The Adobe Campaign <span class="uicontrol">Profiles and Services</span> API is available in the <a href="https://www.adobe.io/products/campaign">adobe.io</a> portal. Isso permite que os perfis do Adobe Campaign sejam atualizados, adicionados e excluídos, e para que sejam inscritos ou cancelados de serem assinados nos serviços por chamadas REST.<br /> Para obter mais informações, consulte a descrição <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">detalhada da API</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-4}

#### General {#general-4}

* Dicas de ferramentas agora são desativadas em dispositivos móveis para garantir que as informações exibidas na tela sejam fáceis de ler.
* Corrigido um erro que impedia que o usuário rolasse o conteúdo de determinadas zonas na tela do ipad.
* Corrigidos vários erros de compatibilidade encontrados ao editar o conteúdo no Internet Explorer 11.
* Correção de um erro que podia impedir que logs detalhados fossem acessados quando a importação de dados falhava pela primeira vez.
* Correção de um erro que impedia o salvamento de um filtro de intervalo.
* Corrigido um erro que impedia que elementos de um recurso fossem exibidos ao configurar a forma como uma lista é exibida.
* Corrigido um erro no editor de consulta. Os resultados retornados pelo campo de pesquisa foram mantidos no histórico de pesquisa e continuaram a ser exibidos em cada nova pesquisa.

#### Emails and SMS messages {#emails-and-sms-messages-3}

* Correção de um erro que impedia que as informações vinculadas a rejeições fossem recuperadas em registros de entrega.
* Corrigido um erro que impedia que o contexto em um bloco de conteúdo dinâmico de uma mensagem transacional fosse acessado.
* Corrigido um erro que impedia que um link de URL fosse definido em texto dinâmico no conteúdo de um email.
* Correção da exibição da barra superior do assistente de criação de entrega.
* A chave primária de uma entrega não pode mais ser usada como um campo de personalização.

#### Workflows {#workflows-2}

* As transições entre duas atividades de um fluxo de trabalho agora exibem a contagem de elementos computados e transferidos de uma atividade para outra.
* Incompatible fields are now hidden when additional data is added in a **[!UICONTROL Query]** activity.
* A janela de definição agregada, exibida ao adicionar dados adicionais, foi aprimorada somente para oferecer opções compatíveis com os dados em uso (por exemplo: calcular uma média só é possível para dados numéricos).
* Iniciar ou reiniciar um fluxo de trabalho técnico fora da caixa agora só pode ser executado por um usuário com direitos de administração.

#### Landing pages {#landing-pages-1}

* Correção de um erro que truncava chaves de codificação AES de 32 bits nas propriedades de uma página de aterrissagem.
* Correção de um erro que impedia a exibição correta do editor de consultas ao definir uma condição de visibilidade ou ao adicionar conteúdo dinâmico a uma página de aterrissagem.

#### Custom resources {#custom-resources-2}

* The **[!UICONTROL Switch to parameters]** option is now hidden when defining a filter related to a profile's subscriptions to a service.
* Correção de um erro que ocorria quando um link de tipo 0-1 era configurado de um recurso personalizado.
* Fixed an error that, where relevant, could prevent the defined **Constant default value** from being edited when adding a **Date and time** type field in a custom resource.

## Release 16.5 - May 2016 {#release-16-5---may-2016}

### New capabilities {#new-capabilities-5}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Predefined filters<br /> </td> 
   <td> Os administradores agora podem criar filtros avançados que aparecem no editor de consultas na forma de regras pré-configuradas. A seleção desses filtros permite que os usuários desenvolvam configurações complexas com mais facilidade em uma interface simplificada ao definir um público-alvo, por exemplo.<br /> Para obter mais informações, consulte a <a href="../../developing/using/configuring-filter-definition.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Subscription Services<br /> </td> 
   <td> A new <span class="uicontrol">Subscription Services</span> activity offers the possibility of subscribing several profiles to a service or unsubscribing them from a service with in a single action.<br /> Essa atividade pode ser usada depois de ter realizado um direcionamento ou importado um arquivo com dados identificados.<br /> Para obter mais informações, consulte a <a href="../../automating/using/subscription-services.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: data enrichment<br /> </td> 
   <td> The <span class="uicontrol">Additional data</span> tab is now available in <span class="uicontrol">Query</span> type activities. Essa funcionalidade permite aprimorar os dados direcionados pela consulta e transferir esses dados para as seguintes atividades do fluxo de trabalho onde ele pode ser explorado.<br /> Após ter adicionado dados adicionais, é possível aplicar um nível de filtro adicional aos dados inicialmente direcionados ao criar condições com base nos dados adicionais definidos.<br /> Para obter mais informações, consulte a <a href="../../automating/using/query.md#enriching-data">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Contextual help<br /> </td> 
   <td> Uma função de ajuda contextual agora está disponível em diferentes telas do Adobe Campaign. Isso significa que, em um único clique, você pode acessar diretamente a documentação sobre a funcionalidade usada atualmente. Para exibir a ajuda contextual, clique em "?" icon in the upper-right corner of the screen, as shown in the example below.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-5}

#### General {#general-5}

* Várias interfaces Novos recursos que seguem os padrões da Marketing Cloud.
* Padronização de tipos de listas suspensas diferentes.

#### Emails and SMS messages {#emails-and-sms-messages-4}

* Correção de um erro que impedia o envio de emails caso a máscara de endereço de erro fosse especificada.
* O protocolo TLS agora é compatível com a entrega por email. Uma nova coluna no gerenciamento MX permite definir o comportamento de TLS desejado para cada domínio.
* A interface SMS foi aprimorada.

#### Workflows {#workflows-3}

* Vários recursos da interface de fluxo de trabalho Novos recursos.
* Correção de um erro que ocorria ao exibir Ações Rápidas.
* Fixed an error that could cause a workflow to fail when using a **[!UICONTROL Segmentation]** type activity containing a 1-N link.
* Corrigido um erro que impedia a abertura das transições de um fluxo de trabalho em um dispositivo híbrido.
* Correção de um erro que impedia a exibição do botão pausar ao iniciar um fluxo de trabalho pela primeira vez.

#### Content editor {#content-editor}

* O editor de conteúdo agora permite personalizar qualquer URL contido em um email ou em uma página de aterrissagem. Refer to the [detailed documentation](../../designing/using/personalizing-urls.md).
* Corrigido um erro que fazia com que as imagens fossem perdidas quando eram adicionadas no assistente de criação da entrega e seu conteúdo era modificado depois.

#### Custom resources {#custom-resources-3}

* Correção de um erro que ocorria ao adicionar um link personalizado de tipo de 1 N na tela de configuração de um recurso personalizado.
* Melhoria na exibição da barra de progresso ao preparar e publicar recursos personalizados.
* Correção de um erro que ocorria ao exibir a lista de links de um recurso personalizado.

#### Transactional messages {#transactional-messages-3}

* A amigabilidade do usuário da interface, bem como o desempenho e a solidez do mecanismo de mensagem transacional foram otimizados.
* Agora é possível suspender temporariamente a publicação de um modelo de mensagem transacional. For more on this, refer to the [detailed documentation](../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication).
* Corrigido um erro que fazia com que um bloco de conteúdo com uma dimensão de definição de metas incompatível fosse adicionado em um modelo de mensagem transacional.
* Correção de um erro que impedia a exibição da visualização da API em uma tela de configuração de evento.

#### Audiences and queries {#audiences-and-queries-1}

* Vários patches relativos ao uso de datas no editor de consultas. Refer to the [detailed documentation](../../automating/using/editing-queries.md#creating-queries).

#### Administration {#administration}

* Corrigido um erro com relação ao nome do grupo de segurança "Usuários padrão", que impedia o logon dos usuários.

## Release 16.3 - March 2016 {#release-16-3---march-2016}

### New capabilities {#new-capabilities-6}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Interface and navigation<br /> </td> 
   <td> A interface do Adobe Campaign foi aprimorada para tornar a navegação e as operações simples e intuitivas.<br /> Agora você navega da barra superior do aplicativo. The advanced menus are accessible by selecting the <strong>Adobe Campaign</strong> logo.<br /> Para obter mais informações, consulte a <a href="../../start/using/interface-description.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Save audience<br /> </td> 
   <td> A new option, <span class="uicontrol">Create then update an audience</span> , is now available in the <span class="uicontrol">Save audience</span> activity. Esta opção permite inserir manualmente uma etiqueta de público-alvo. Se a etiqueta inserida corresponde a um público existente, ela será atualizada. Se o público não existir, ele será criado.<br /> Além disso, o público-alvo será atualizado sempre que o fluxo de trabalho for executado (novamente).<br /> Você sempre pode selecionar o modo de atualização de público-alvo: preencha o público com novos dados ou substitua todos os dados do público-alvo por execução.<br /> Para obter mais informações, consulte a <a href="../../automating/using/save-audience.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Segmentation<br /> </td> 
   <td> The <span class="uicontrol">Segmentation</span> activity now allows the user to segment the data of a temporary resource. Por exemplo: os dados de um arquivo importado.<br /> Para obter mais informações, consulte a <a href="../../automating/using/segmentation.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-6}

#### General {#general-6}

* Correção de um erro de exibição que ocorria ao classificar uma lista: a seta que indica a ordem de classificação de uma coluna só pode ser ramificada por certos tipos de dados.
* Correção de um erro que limitava o número de elementos exibidos em um menu suspenso quando uma regra era adicionada em uma consulta.

#### Emails and SMS messages {#emails-and-sms-messages-5}

* Corrigido um erro que poderia impedir o acesso ao relatório de renderização de email.
* A preparação para enviar estágio para uma mensagem retorna um erro se o endereço do remetente não for fornecido.

#### Workflows {#workflows-4}

* Algumas opções de formatação de arquivo eram visíveis, mas não eram consideradas quando um arquivo de formato CSV era extraído. Essas opções agora não estão mais visíveis.
* Fixed an error caused when the **[!UICONTROL Delete the source files after transfer]** option was checked for a **[!UICONTROL SFTP]** type file transfer.
* Fixed an error that could prevent the counter and preview of **[!UICONTROL Query]** data from being displayed after refreshing the page.
* Correção de um erro causado pela abertura de certas transições em um fluxo de trabalho, principalmente após uma atividade de entrega ou uma consulta em que as dimensões de definição de metas e filtragem eram diferentes.
* Correção de um erro que impedia que um campo de personalização fosse inserido em uma atividade de entrega de um fluxo de trabalho se o fluxo de trabalho não fosse salvo após a adição da atividade.
* Correção de um erro que impedia a exibição da dimensão de direcionamento de transição de saída de uma atividade de entrega de email.

#### Landing pages {#landing-pages-2}

* Corrigido um erro que impedia que os campos de personalização funcionassem corretamente em um bloco de conteúdo localizável em uma página de aterrissagem.

#### Custom resources {#custom-resources-4}

* Fixed an error that prevented a search on a custom resource from being carried out if the **[!UICONTROL Add search fields]** option of the resource screen definition was checked and if several fields were selected in the **[!UICONTROL Filter zone composition]** .

## Release 16.2 - February 2016 {#release-16-2---february-2016}

### New capabilities {#new-capabilities-7}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> A/B test for emails<br /> </td> 
   <td> Agora você pode executar testes A/B no conteúdo, no assunto ou no nome do remetente de seus e-mails. Essa nova funcionalidade pode testar até três variantes de um elemento.<br /> Ao criar um email de um dos novos modelos específicos para testes A/B, uma nova etapa do assistente de criação permite que você defina os parâmetros do teste.<br /> Para obter mais informações, consulte a <a href="../../channels/using/designing-an-a-b-test-email.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Brand management<br /> </td> 
   <td> Agora é possível definir uma ou várias marcas para inserir centralmente os parâmetros que afetam a identidade de uma marca. O Adobe Campaign permite que você crie essas marcas e vincule-as a modelos de entrega ou página de aterrissagem.<br /> Para obter mais informações, consulte a <a href="../../administration/using/branding.md#assigning-a-brand-to-an-email">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Incremental query<br /> </td> 
   <td> A new workflow activity, <span class="uicontrol">Incremental query</span> , allows you to carry out a query which, on every execution, targets only the new results. Os resultados das execuções anteriores são excluídos automaticamente. Linked to a <span class="uicontrol">Scheduler</span> activity, you can define the execution frequency of the <span class="uicontrol">Incremental query</span> .<br /> Para obter mais informações, consulte a <a href="../../automating/using/incremental-query.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional messages<br /> </td> 
   <td> A simpatia do usuário da interface de mensagens transacionais foi aprimorada. All business process management linked to transactional messages is currently centralized in the <span class="uicontrol">Marketing plans</span> &gt; <span class="uicontrol">Transactional messages</span> menu. A configuração do evento também foi aprimorada. Os eventos agora são gerenciados independentemente dos recursos personalizados.<br /> Para obter mais informações, consulte a <a href="../../channels/using/about-transactional-messaging.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-7}

#### General {#general-7}

* Correção de vários erros de exibição em relatórios, listas e consultas.
* Correção de vários erros e exibição de erros em dispositivos móveis.

#### Emails and SMS messages {#emails-and-sms-messages-6}

* Corrigido um erro que fazia com que o botão usado para inserir campos de personalização fosse exibido durante a criação de uma mensagem (e-mail ou SMS).
* Corrigido um erro que poderia impedir que mensagens SMS enviadas via Mblox fossem transmitidas corretamente.

#### Audiences and queries {#audiences-and-queries-2}

* Correção de um erro de contagem que podia ser causado ao adicionar uma condição adicional em uma consulta, após ter modificado a dimensão de filtragem.
* Corrigido um erro que gerava uma paginação incorreta ao visualizar os resultados de uma consulta.

#### Content editing {#content-editing-1}

* Corrigido um erro que fazia com que a configuração de conteúdo dinâmico fosse levada em consideração corretamente ao usar uma enumeração personalizada.

#### Workflows {#workflows-5}

* Fixed an error that could prevent any action in a workflow from being carried out if there was an empty line in the **[!UICONTROL Fields to update]** tab of an **[!UICONTROL Update data]** activity.
* Correção de um erro que impedia a importação de dados que continham informações de unidade geográfica/organizacional.
* Fixed an error caused by adding a **[!UICONTROL Change axis]** type of **[!UICONTROL Exclusion]** rule.
* Fixed an error that could lead to an unwanted additional segment being created when manipulating an outbound transition of a **[!UICONTROL Segmentation]** activity.
* Correção de um erro causado pelo carregamento de um arquivo em um modelo de fluxo de trabalho.
* Fixed an error that could prevent spaces from being used as column separators in a **[!UICONTROL Load file]** activity.

#### Custom resources {#custom-resources-5}

* Correção de um erro que impedia que o status de um recurso personalizado fosse recompilado após a importação de um pacote, se o recurso fosse publicado no momento da exportação.

#### Packages {#packages}

* Correção de um erro que impedia a exportação de um pacote contendo um fluxo de trabalho.
* Corrigido um erro que poderia impedir a seleção de vários elementos do mesmo recurso.

## Release 16.1 - January 2016 {#release-16-1---january-2016}

### New capabilities {#new-capabilities-8}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Reports<br /> </td> 
   <td> The following email specific reports have been added: <span class="uicontrol">Complaints</span> , <span class="uicontrol">Opens</span> , and <span class="uicontrol">Unsubscriptions</span> .<br /> Os seguintes relatórios foram aprimorados: <span class="uicontrol">Resumo</span> de entrega, <span class="uicontrol">Resumo</span> de rejeição, <span class="uicontrol">Entrega de entrega</span> e Indicadores <span class="uicontrol">de rastreamento</span> .<br /> Para obter mais informações, consulte a <a href="../../reporting/using/defining-the-report-period.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Query editing<br /> </td> 
   <td> The query editor has been improved and now allows you to scan the <strong>1-N</strong> type links.<br /> Para obter mais informações, consulte a <a href="../../automating/using/editing-queries.md#creating-queries">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Content personalization<br /> </td> 
   <td> As for email or landing page editing, the input interface for content block display conditions has been improved.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: column definition when importing<br /> </td> 
   <td> The <span class="uicontrol">Load file</span> activity now allows you to configure the columns of an imported file in detail: expected data type, date and time format, processing to apply in case of an empty value or an error, and value remapping.<br /> Para obter mais informações, consulte a <a href="../../automating/using/load-file.md#column-format">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mapping of SMS encodings<br /> </td> 
   <td> Agora é possível definir mapeamentos de codificações de mensagens SMS personalizadas para provedores que não usam a codificação padrão. Um administrador pode realizar a configuração de mapeamentos personalizados e definir a ordem em que devem ser considerados.<br /> Para obter mais informações, consulte a <a href="../../administration/using/configuring-sms-channel.md#smsc-specifics">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-8}

#### General {#general-8}

* Aprimoramento da compatibilidade com o Internet Explorer e o Chrome para dispositivos híbridos/touchscreen.
* Correção de um erro que resultava na perda de todos os dados inseridos para um novo perfil de usuário/perfil/teste se o endereço de email indicado continha erros de sintaxe.

#### Emails and SMS messages {#emails-and-sms-messages-7}

* Correção de um erro que podia impedir a geração da miniatura do conteúdo na tela de visualização de email.
* Corrigido um erro que fazia com que o conteúdo bruto de uma mensagem (e-mail ou SMS) fosse exibido na tela de visualização da mensagem.

#### Audiences and queries {#audiences-and-queries-3}

* Fixed an error that could prevent a **Query** type audience from being created in the **Service** resource.
* Correção de um erro que podia impedir a exibição correta da lista de função ao editar uma condição de uma consulta no modo avançado.
* Fixed an error that could prevent a **Query** type audience from being created if it contained criteria based on collections.
* Correção de um erro que podia impedir a criação de consultas contendo filtros na entrega de kpis.
* Corrigido um erro que poderia impedir que o conteúdo de um público-alvo criado de um fluxo de trabalho fosse visualizado.

#### Custom resources {#custom-resources-6}

* Correção de um erro que resultava em falha de servidor se um recurso personalizado continha um campo com um valor padrão dinâmico.
* Fixed an error caused by moving, then deleting an element in the **[!UICONTROL Detail screen configuration]** section while defining screens of a custom resource.
* Fixed an error that occurred when a default value had been defined for an **integer** list that did not include **0** in its range of possible values.
* Correção de um erro que podia impedir que um elemento fosse adicionado na configuração de tela detalhada de um recurso personalizado após uma reinicialização.

#### Workflows {#workflows-6}

* Corrigido um erro que fazia com que logs de todas as atividades em um fluxo de trabalho fossem exibidos em vez de somente exibirem as da atividade selecionada.
* Fixed an error in the **[!UICONTROL Scheduler]** activity. **[!UICONTROL Day of the month]** A opção não foi levada em consideração corretamente e substituída **[!UICONTROL Week day]** por.
* Fixed an error that could prevent a **[!UICONTROL Scheduler]** activity from working correctly with the expiration mode set to **[!UICONTROL After a certain number of iterations]** .
* Fixed an error that occurred when exporting data using an **[!UICONTROL Extract file]** activity. O número de linhas presente no arquivo de exportação era inferior ao número de elementos exportados.
* Fixed an error that could prevent a file in a **[!UICONTROL Load file]** activity from being selected.
* Fixed an error that prevented fields that were to be updated in an **[!UICONTROL Update data]** activity from being deleted.
* Correção de um erro que impedia que as modificações feitas em um fluxo de trabalho fossem salvas após a abertura dos logs de execução do fluxo de trabalho.
* Fixed an error that caused a **[!UICONTROL Load file]** activity to be executed twice if it was configured to use the file from its inbound transition and this file had been loaded using a **[!UICONTROL Transfer file]** activity.
* Fixed an error that could prevent certain temporary entities from being correctly processed by an **Exclusion** activity.
* Fixed an error that could prevent a **[!UICONTROL Query]** activity from being executed correctly if the targeting dimension and the filtering dimension configured in the activity were different.
* Fixed an error concerning the automatic naming of outbound transitions added to a **[!UICONTROL Fork]** activity that could prevent the workflow from being saved.

#### Content editing {#content-editing-2}

* Corrigido um erro que fazia com que um ícone ou uma barra de pesquisa fosse exibida de forma indesejável ao editar o conteúdo.

#### Landing pages {#landing-pages-3}

* Correção de um erro que impedia a importação de uma página de aterrissagem usando uma importação de pacote.

#### Transactional messages {#transactional-messages-4}

* Agora é possível especificar um endereço IP confiável nos parâmetros de segurança do operador agente de push do Centro de mensagens.
* Corrigido um erro que poderia impedir a criação de um novo tipo de evento.

## Release 15.11 - November 2015 {#release-15-11---november-2015}

### New capabilities {#new-capabilities-9}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> SMS Channel<br /> </td> 
   <td> Agora é possível enviar mensagens SMS com o Adobe Campaign.<br /> Assim como para emails, você pode criar novos envios SMS de suas campanhas e da lista de atividades de marketing. Você também pode criar mensagens SMS de envio único e recorrente a partir de um fluxo de trabalho.<br /> Essas entregas de SMS são baseadas em modelos que podem ser configurados na lista de modelos de entrega. Um modelo padrão está disponível.<br /> Essas entregas SMS usam o protocolo SMPP 3.4, usado pela maioria dos roteadores de SMS.<br /> Para obter mais informações, consulte a <a href="../../channels/using/about-sms-messages.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploring transitions<br /> </td> 
   <td> Agora é possível explorar os dados e sua estrutura na última transição de um fluxo de trabalho. This allows you to check that the processes applied by each activity correspond to your needs.<br /> </td> 
  </tr> 
  <tr> 
   <td> File pre- and post-processing in workflows<br /> </td> 
   <td> You can now carry out additional processing on a data file when importing or exporting it via the <span class="uicontrol">Load file</span> and <span class="uicontrol">Extract file</span> activities.<br /> Por padrão, é possível descompactar e compactar um arquivo GZIP nessas atividades.<br /> Para obter mais informações, consulte a documentação sobre o arquivo <a href="../../automating/using/load-file.md">Carregar</a> e <a href="../../automating/using/extract-file.md">Extrair</a> atividades de arquivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Deliverability reports<br /> </td> 
   <td> Um relatório de renderização de email agora está disponível. Este relatório permite exibir os diferentes renderizações de uma mensagem de acordo com o serviço de suporte e de mensagens usado para lê-lo.<br /> O resumo do relatório também apresenta o número de mensagens recebidas, mensagens de spam, mensagens não recebidas e mensagens que aguardam a recepção.<br /> Para obter mais informações, consulte a <a href="../../sending/using/email-rendering.md#email-rendering-report-description">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Package Management<br /> </td> 
   <td> It is now possible to import and export images in packages.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quick actions<br /> </td> 
   <td> Algumas ações aparecem ao passar o mouse sobre ou depois de selecionar um elemento em uma lista ou um fluxo de trabalho. Algumas dessas ações agora são exibidas como ícones ao redor dos elementos envolvidos para facilitar o acesso. These quick actions can be used to duplicate an element, delete it, show the detail, etc.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-9}

#### General {#general-9}

* Corrigido um erro que poderia impedir o acesso aos parâmetros gerais de uma instância de uma conta de administrador.
* **Os dados flutuantes** agora são devidamente considerados nos recursos personalizados.
* Corrigido um erro de exibição na lista de importações simplificadas realizadas, que era gerada quando o status do modelo correspondente tinha sido modificado.

#### Landing pages {#landing-pages-4}

* Corrigidos alguns elementos de modelos de página de aterrissagem que poderiam ser exibidos incorretamente em francês em instâncias em inglês.

#### Audiences {#audiences}

* Corrigido um erro que fazia com que os públicos-alvo importados da Adobe Marketing Cloud fossem exibidos na lista de públicos-alvo.
* Corrigido um erro que poderia forçar a diferenciação entre maiúsculas e minúsculas ao definir uma consulta.
* Corrigido um erro que fazia com que os públicos-alvo fossem filtrados na definição de uma consulta.
* Corrigido um erro que podia impedir que uma ação fosse cancelada em um público-alvo.

#### Workflows {#workflows-7}

* Fixed an error that could prevent the fields that were to be updated in an **[!UICONTROL Update data]** activity from manually being configured.
* Fixed an error that could cause the **[!UICONTROL Query]** activity to load infinitely when opened if the workflow had not been saved after having placed the activity in the diagram.
* Fixed an error that could cause the server to stop while counting or previewing an audience selected from a **[!UICONTROL Query]** in a workflow.
* Correção de um erro não-crítico que podia aparecer quando uma atividade em um fluxo de trabalho era aberta.
* Fixed an error that prevented a **[!UICONTROL Scheduler]** activity from being configured to execute a workflow several times a day.
* Corrigido um erro que fazia com que os campos nos quais não fossem realizados consultas fossem exibidos em determinadas atividades de fluxo de trabalho.
* Fixed an error that could prevent the user from locating the KPIs added from a **[!UICONTROL Query]** on deliveries in the outbound transition.
* Corrigido um erro que poderia impedir a criação de um público-alvo de arquivo após a importação de um arquivo para um fluxo de trabalho.
* Fixed an error that could prevent data from being updated on profiles if the **location/address3** field of the resource was used.
* Corrigido um erro que impedia que coleções heterogéneas de atividades fossem duplicadas em um fluxo de trabalho.
* Correção de um erro que impedia a exibição do SQL, permitindo que erros fossem diagnosticados por uma entrega recorrente em um fluxo de trabalho.

#### Content editor {#content-editor-1}

* Corrigido um erro que fazia com que a pesquisa no código fonte de uma página de aterrissagem ou de um e-mail não fosse possível.

#### Packages {#packages-1}

* Corrigidos vários erros que poderiam impedir que certos tipos de elementos fossem exportados em pacotes (especialmente páginas de aterrissagem, fluxos de trabalho).
* Correção de um erro que fazia com que o rótulo da importação do pacote anterior fosse exibido se a etiqueta tivesse sido modificada.
* Corrigido um erro que fazia com que recursos incompatíveis fossem exibidos na lista de recursos exportáveis.

## Release 15.10 - October 2015 {#release-15-10---october-2015-}

### New capabilities {#new-capabilities-10}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Workflows: Deduplication activity<br /> </td> 
   <td> Uma nova atividade dedicada à desduplicação de dados agora está disponível nos fluxos de trabalho. Essa atividade permite que você filtre quaisquer duplicatas nas metas de acordo com os critérios escolhidos.<br /> Para obter mais informações, consulte a <a href="../../automating/using/deduplication.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Improved diagram<br /> </td> 
   <td> Na área de trabalho do fluxo de trabalho, agora é possível usar vários atalhos do teclado para selecionar, abrir e excluir atividades.<br /> O alinhamento da atividade também foi aprimorado e permite que um fluxo de trabalho seja melhor organizado visualmente.<br /> Para obter mais informações, consulte a <a href="../../automating/using/workflow-interface.md#workspace">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Extract file activity<br /> </td> 
   <td> The date and time of the export is now automatically added to the labels of the files exported using an <span class="uicontrol">Extract file</span> activity. This way the files generated are unique.<br /> </td> 
  </tr> 
  <tr> 
   <td> Simplified data import<br /> </td> 
   <td> The name of the template from which a simplified import was carried out is now visible by default in the import list and in the detail of each import.<br /> </td> 
  </tr> 
  <tr> 
   <td> Custom resources<br /> </td> 
   <td> Improvement and extended possibilities for managing and defining links for custom resources.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-10}

#### Email {#email}

* Corrigido um erro que impedia que um link de cancelamento de assinatura de serviço funcionasse corretamente de uma página espelhada.
* Corrigido um erro que podia impedir que um rótulo de entrega de email fosse exibido corretamente na página de edição de email.
* Fixed an error that could prevent an external **[!UICONTROL Routing]** account from being selected in a duplicated delivery template.

#### Audiences {#audiences-1}

* Correção de um erro causado durante uma contagem de público-alvo se um link de 1 N fosse usado na consulta.
* Correção de um erro que podia impedir a seleção de um perfil no público-alvo de uma entrega de email.

#### Workflows {#workflows-8}

* Corrigido um erro que causava problemas de exibição ao configurar uma entrega de email em um fluxo de trabalho.
* Fixed an error that could prevent the **[!UICONTROL Load file]** activity from working correctly. Uma mensagem de erro em branco apareceria.
* Fixed an error that could prevent the **[!UICONTROL Transfer file]** activity from working correctly. Os direitos de acesso nem sempre eram considerados corretamente.
* Fixed an error that could prevent a file from being exported if the workflow contained a **[!UICONTROL Recurring email]** .
* Correção de um erro que impedia a criação de uma entrega por email em um fluxo de trabalho ou impedia a tomada em consideração do assunto e do conteúdo definido.
* Fixed an error that could prevent a reconciliation key from being selected in an **[!UICONTROL Update data]** activity when configuring the workflow of a simplified import template.
* Correção de um erro que podia impedir que um fluxo de trabalho fosse salvo após a exclusão de uma atividade.

#### Platform {#platform}

* Corrigido um erro que poderia impedir a criação de um novo elemento se um recurso personalizado contivesse um link para o tipo de recurso desse elemento.
* Correção de um erro que fazia com que um atraso de 15 minutos para certos logs fossem gravados.
* Fixed an error that could prevent the marketing activity list from being displayed when sorted by the **[!UICONTROL Date]** or **[!UICONTROL Indicators]** columns.

#### Landing pages {#landing-pages-5}

* Correção de um erro que ocorria ao selecionar um perfil de teste para visualizar uma página de aterrissagem.

#### Transactional messages {#transactional-messages-5}

* Corrigido um erro que fazia com que o aplicativo travasse após a exclusão de um evento em um perfil de teste.

#### Reports {#reports}

* Fixed an error that could cause incorrect data to be sent for the reports **[!UICONTROL deliveryThroughputReport]** and **[!UICONTROL deliveryTrackingReport]** .

#### Content editor {#content-editor-2}

* Correção de um erro de gerenciamento de tags de HTML que ocorria ao processar blocos de conteúdo dinâmico.

## Release 15.8 - August 2015 {#release-15-8---august-2015}

### New capabilities {#new-capabilities-11}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Simplified data import<br /> </td> 
   <td> Agora é possível importar dados de forma simplificada.<br /> Os usuários simplesmente selecionam um modelo predefinido por um administrador e carregam o arquivo que contém os dados a serem importados. Um fluxo de trabalho definido no modelo é executado de forma transparente para o usuário, que pode acessar os detalhes do resultado da importação, bem como um log de erros.<br /> Os dados desses arquivos podem ser inseridos no banco de dados ou servir como um meio para criar diretamente um público-alvo.<br /> Para obter mais informações, consulte a <a href="../../automating/using/about-data-import-and-export.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creating programs and campaigns<br /> </td> 
   <td> Agora, campanhas e programas são configurados de forma que o dia em que são criados seja usado automaticamente como a data de início.<br /> A data final é configurada de acordo com a data de início, como:<br /> 
    <ul> 
     <li> D +186 para programas </li> 
     <li> D +61 para campanhas </li> 
    </ul> For more information, refer to the <a href="../../start/using/programs-and-campaigns.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email<br /> </td> 
   <td> The list of tracked URLs is now read only.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional messages<br /> </td> 
   <td> Agora você pode gerenciar mensagens transacionais personalizadas para eventos como alterações de senha ou confirmações após a criação de uma conta.<br /> Para obter mais informações, consulte a <a href="../../channels/using/about-transactional-messaging.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Custom resources<br /> </td> 
   <td> Várias funcionalidades adicionadas como: estendendo um perfil de teste, gerenciamento de status e excluindo recursos.<br /> Para obter mais informações, consulte a <a href="../../developing/using/resource-statuses.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-11}

#### Display {#display}

* Corrigido um erro que fazia com que dois campos fossem chamados de juxtaded no editor de consultas no Safari.

#### Content editor {#content-editor-3}

* Correção de um erro que impedia que caracteres &lt; &lt;',' &amp;' e ' &gt;' fossem usados em um assunto de email.

#### Email {#email-1}

* Corrigido um erro que impedia o usuário de adicionar texto após um texto dinâmico.

#### Lists {#lists}

* Fixed an error that prevented the **Message** column in workflow execution logs from being exported correctly.

#### Profiles and audiences {#profiles-and-audiences}

* Correção de um erro que resultava em uma confirmação dupla de quando um elemento duplicava ou era excluído. **Dispositivos híbridos usando apenas o Internet Explorer 11**.

#### Workflows {#workflows-9}

* Correção de um erro que impedia que emails fossem enviados de um fluxo de trabalho.
* Fixed an error that could prevent a workflow from executing when the name of the rejection file was not specified in a **[!UICONTROL Load file]** activity.
* Fixed an error that could prevent a workflow from executing when the **[!UICONTROL Execution frequency]** of a **[!UICONTROL Schedule]** activity was set to **[!UICONTROL Daily]** .

#### Platform {#platform-1}

* Correção de um erro que impedia a geração de miniaturas em um ambiente balanceado de carga.

## Release 15.7 - July 2015 {#release-15-7---july-2015}

### New capabilities {#new-capabilities-12}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Exporting lists<br /> </td> 
   <td> Agora é possível exportar conteúdo de suas listas para um arquivo em formato CSV. This function is available in all screens with a <strong>List</strong> mode (for example: profile list).<br /> Os dados exportados são os dados nas colunas exibidos durante a exportação. Ao editar a lista, você pode selecionar os dados que deseja exportar.<br /> Para obter mais informações sobre como usar essa funcionalidade, consulte a documentação <a href="../../automating/using/exporting-lists.md">detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integration with Adobe Profiles &amp; Audiences<br /> </td> 
   <td> You can now share audiences between Adobe Campaign and your other Adobe Marketing Cloud solutions:<br /> 
    <ul> 
     <li> Export: when you save an audience composed of profiles in a workflow, a new <span class="uicontrol">Share in Adobe Marketing Cloud</span> option allows you to add profiles to an existing audience or to create a new audience. </li> 
     <li> Import: by creating a <strong>List</strong> type audience from the audience management screen, a new option allows you to identify it as an <span class="uicontrol">Adobe Marketing Cloud Audience</span> . Você pode selecionar um público-alvo compartilhado existente para importá-lo para o Adobe Campaign. </li> 
    </ul> For more information on configuring and using this functionality, refer to the <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor - Dynamic content<br /> </td> 
   <td> A interface de conteúdo dinâmico foi aprimorada. As setas agora aparecem para permitir que você navegue entre o conteúdo dinâmico diferente, diretamente no corpo do e-mail.<br /> Para obter mais informações sobre como usar essa funcionalidade, consulte a documentação <a href="../../designing/using/defining-dynamic-content-in-a-landing-page.md">detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor - Dynamic text<br /> </td> 
   <td> From the content editor of an email, you can now define dynamic text:<br /> 
    <ul> 
     <li> em um assunto de email, </li> 
     <li> no modo HTML, </li> 
     <li> ou no modo Texto. </li> 
    </ul> For more information on using this functionality, refer to the <a href="../../designing/using/defining-dynamic-text.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Programs and campaigns - Reports<br /> </td> 
   <td> A interface e os gráficos dos relatórios foram aprimorados.<br /> Para obter mais informações sobre como usar essa funcionalidade, consulte a documentação <a href="../../reporting/using/defining-the-report-period.md">detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-12}

#### Installation {#installation}

* Os nomes de instâncias do Adobe Campaign agora estão limitados a 32 caracteres.

#### Workflows {#workflows-10}

* Corrigido um erro que poderia impedir o direcionamento de um recurso de "entrega" ao editar uma consulta em um fluxo de trabalho.
* Corrigido um erro que poderia impedir que certos recursos vinculados fossem processados durante a edição de uma consulta em um fluxo de trabalho.
* Fixed an error that could prevent a **Recurring delivery** activity from being modified if the workflow had already been executed.

#### Emails {#emails}

* Correção de um erro que impedia que erros de sintaxe javascript fossem verificados antes de enviar um e-mail quando um conteúdo dinâmico era adicionado por meio do editor de expressão.

#### Landing pages {#landing-pages-6}

* Corrigido um erro que impedia que uma página de aterrissagem fosse editada de um tablet.

#### Assets Core Service {#assets-core-service}

* Ao selecionar um recurso compartilhado de um email ou página de aterrissagem que está sendo editada, a lista de recursos disponíveis agora é filtrada para o Adobe Campaign.

## Release 15.6 - June 2015 {#release-15-6---june-2015}

### New capabilities {#new-capabilities-13}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Workflows: Reconciliation activity<br /> </td> 
   <td> A new <strong>Reconciliation</strong> activity links unidentified data (for example, after importing a file) with existing resources within a workflow.<br /> Essa atividade é usada principalmente para fins de Gerenciamento de dados. It responds to two different use cases:<br /> 
    <ul> 
     <li> <strong>Adicionar relações</strong>: Uma <strong>guia Relações</strong> permite adicionar links entre os dados de entrada e várias outras dimensões do banco de dados do Adobe Campaign. </li> 
     <li> <strong>Identificação de dados</strong>: uma <strong>guia Identificação</strong> permite simplesmente associar dados de entrada a colunas em uma dimensão existente no banco de dados do Adobe Campaign. Quando ela sai da atividade, os dados são identificados como pertencendo à dimensão especificada. </li> 
    </ul> Refer to the <a href="../../automating/using/reconciliation.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Extract file activity<br /> </td> 
   <td> A new <strong>Extract file</strong> activity allows you to export data from the Adobe Campaign database in the form of an external file from a workflow. <br /> Limitação: não é possível usar nomes dinâmicos para arquivos de saída no momento.<br /> Consulte a <a href="../../automating/using/extract-file.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Scheduler activity<br /> </td> 
   <td> Improved widget that allows you to select the execution time of the <strong>Scheduler</strong> activity in a workflow.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Transfer file activity<br /> </td> 
   <td> SFTP is now supported.<br /> </td> 
  </tr> 
  <tr> 
   <td> Custom resources<br /> </td> 
   <td> The <span class="uicontrol">Development</span> menu now allows users with admin rights to enrich the data templates provided by creating their own custom resources, such as purchase or product tables. <br /> Recursos prontos para uso também podem ser estendidos para adicionar novos campos a eles.<br /> Além disso, a navegação nas telas correspondentes a recursos personalizados novos ou estendidos pode ser configurada.<br /> Consulte a <a href="../../developing/using/data-model-concepts.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Test profiles<br /> </td> 
   <td> The <strong>Middle name</strong> and <strong>Title</strong> of the test profiles can now be selected when configuring the list of test profiles.<br /> </td> 
  </tr> 
  <tr> 
   <td> Content editor: Dynamic content<br /> </td> 
   <td> Você pode definir conteúdos diferentes que serão exibidos dinamicamente para o usuário de acordo com as condições definidas pelo editor de expressão.<br /> Consulte a <a href="../../designing/using/defining-dynamic-content-in-a-landing-page.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email<br /> </td> 
   <td> A <strong>Test profiles</strong> column is now available in an email's sending logs.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-13}

#### Lists {#lists-1}

* A exclusão de um elemento de uma lista agora resulta na atualização automática da lista.
* Correção de um erro que impedia que elementos fossem selecionados de uma lista contendo apenas uma coluna.
* Corrigido um erro que fazia com que as alterações aplicadas à exibição de uma lista fossem perdidas após a atualização da página.
* Agora, o nome do meio e o título dos perfis de teste podem ser exibidos na lista de perfil de teste.
* Correção de um erro que ocorria ao selecionar uma caixa de seleção em uma lista com o Mozilla Firefox.

#### Audiences {#audiences-2}

* Fixed an error that prevented the **[!UICONTROL Add]** button from being used in the audience interface.

#### Emails {#emails-1}

* Correção de um erro de javascript que impedia o uso do botão de visualização duas vezes em uma linha ao editar um e-mail.
* Fixed an error that prevented the **[!UICONTROL Edit properties]** and **[!UICONTROL Show proofs]** buttons from being used on Microsoft Surface Pro3 tablets using Internet Explorer 11.
* Correção de um erro que impedia a exibição de registros de envio de um email.

#### Landing pages {#landing-pages-7}

* Fixed an error that prevented the **Brand logo** content block from being used when editing content in a landing page.
* Correção de um erro que impedia a exibição das páginas iniciais na lista de atividades de marketing se datas de validade fossem especificadas para a página de aterrissagem.

#### Workflows {#workflows-11}

* Fixed an error that prevented limiting a segment in group mode from working correctly when configuring a **Segmentation** activity.
* Fixed an error that prevented a transition from being selected after having configured a **Segmentation** activity.
* Fixed an error that prevented a transition from being deleted after having configured a **Segmentation** activity.
* Fixed an error that prevented populations from being counted and previewed within a **Segmentation** activity.
* Correção de um erro que impedia que um e-mail recorrente fosse efetivamente excluído.
* Fixed an error that caused data from a deleted **Transfer file** activity to appear in a new **Transfer file** activity.
* Fixed an error that prevented an exclusion rule from being correctly taken into account within an **Exclusion** activity.
* Correção de um erro que ocorria ao excluir uma atividade de entrega de email em um fluxo de trabalho. As entregas correspondentes agora também são removidas da lista de atividades de marketing.

#### Navigation {#navigation}

* Agora é possível usar a tecla tab para navegar adequadamente entre os campos na mesma página.

## Release 15.4 - April 2015 {#release-15-4---april-2015}

### New capabilities {#new-capabilities-14}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Package exports / Package imports<br /> </td> 
   <td> The <strong>Deployment</strong> menu now allows users with admin rights to exchange resources between different Adobe Campaign instances by exporting and importing packages.<br /> Consulte a <a href="../../automating/using/managing-packages.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Reports<br /> </td> 
   <td> All reports (except the <strong>Hot clicks</strong> report) can now be accessed from a program. These reports are:<br /> 
    <ul> 
     <li> Disponibilização de programa </li> 
     <li> Indicadores de rastreamento de programa </li> 
     <li> Detalhamento do programa por domínio </li> 
     <li> Programa não fornecido e rejeições </li> 
     <li> Urls de programa e cliques em fluxos </li> 
    </ul> Esses relatórios podem ser filtrados em determinado período (por exemplo, três meses, seis meses, etc.). Os relatórios de campanha também podem ser filtrados.<br /> Consulte a <a href="../../reporting/using/about-dynamic-reports.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: <strong>Email delivery</strong> activity<br /> </td> 
   <td> The <strong>Email delivery</strong> activity in the workflows has been improved. Agora você pode encontrar emails, emails recorrentes e informações detalhadas sobre execuções de email recorrentes da lista de atividades de marketing de aplicativos.<br /> Consulte a <a href="../../automating/using/email-delivery.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: <strong>Segmentation</strong> activity<br /> </td> 
   <td> The <strong>Segmentation</strong> activity is now available in the workflows. Essa atividade permite criar um ou vários segmentos e vincular um código de segmento a partir de uma população calculada pelas atividades colocadas a upstream no mesmo fluxo de trabalho. A partir dessa atividade, os segmentos podem ser processados em uma única transição ou em várias transações diferentes. Agora há opções para filtrar a população e limitar o tamanho de cada segmento para otimizar a personalização. Por exemplo, você pode selecionar perfis aleatoriamente que correspondam a critérios específicos.<br /> Consulte a <a href="../../automating/using/segmentation.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrations: <strong>Assets Core Service</strong><br /> </td> 
   <td> You can now use shared resources via <strong>Assets Core Service</strong> in your email and landing page contents. Você pode gerenciar seus recursos compartilhados diretamente da Adobe Marketing Cloud.<br /> Consulte a <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrations: <strong>Adobe Target</strong><br /> </td> 
   <td> You can now insert images that are dynamically computed by <strong>Adobe Target</strong> into your Adobe Campaign emails. Isso permite oferecer várias versões do mesmo email, personalizando o conteúdo de acordo com os critérios definidos nos segmentos do Adobe Target.<br /> Consulte a <a href="../../integrating/using/about-campaign-target-integration.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor: <strong>Block selector</strong><br /> </td> 
   <td> Quando um bloco é selecionado no editor de conteúdo HTML, uma navegação estrutural é exibida na parte inferior da zona de edição. Isso permite que você navegue facilmente e selecione elementos diferentes.<br /> Consulte a <a href="../../designing/using/managing-landing-page-structure-and-style.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Release 15.3 - March 2015 {#release-15-3---march-2015}

### New capabilities {#new-capabilities-15}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Reports<br /> </td> 
   <td> Os relatórios podem ser acessados diretamente de um programa ou campanha. The <strong>Delivery summary</strong> report has been added at a program level.<br /> Consulte a <a href="../../reporting/using/delivery-summary.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Update data<br /> </td> 
   <td> In the workflows, the available <strong>Update data</strong> activity has a new option, which allows you to automatically link inbound data fields with the fields of an application schema. Isso ajuda a facilitar o processo de seleção para atualizar campos.<br /> Consulte a <a href="../../automating/using/update-data.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email delivery<br /> </td> 
   <td> In workflows, the advanced options of the <strong>Email delivery</strong> activity can now be accessed via a specific button in the action bar. This button is only available if an <strong>Email delivery</strong> activity is selected. O principal benefício é que ele permite que você adicione uma transição de saída à atividade e edite o nome da atividade conforme ela é exibida no fluxo de trabalho.<br /> Consulte a <a href="../../automating/using/email-delivery.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-14}

#### General {#general-10}

* Correção de um erro que impedia a exibição do destinatário durante a criação de uma entrega.
* Correção de um erro que impedia que um público-alvo baseado em uma condição "Destinatários que abrissem" fosse usado.
* Correção de um erro que impedia a exclusão de um perfil vazio.
* Correção de um erro que ocorria ao visualizar uma entrega.
* Corrigido um erro que impedia que uma atividade de marketing fosse duplicada.
* Correção de um erro que ocorria ao excluir uma campanha.

