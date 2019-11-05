---
title: Notas de versão 2015-2016
description: Esta página lista todas as versões 2015 e 2016 do Adobe Campaign Standard.
page-status-flag: nunca ativado
uuid: d5a0f6cc-0bed-46cf-8dff-1717fb624f8f
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: referência
topic-tags: versões padrão da campanha
discoiquuid: a3ce6b80-1858-49d1-8880-3543181127f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Notas de versão 2015-2016{#release-notes}

Você está procurando uma versão específica 2015-2016 do Adobe Campaign Standard?

Cada versão traz novos recursos e correções. Clique em uma versão para exibir seu conteúdo.

Exiba as atualizações [mais recentes da](../../rn/using/documentation-updates.md) documentação do Adobe Campaign Standard. Se estiver procurando uma versão mais recente, consulte esta [página](../../rn/using/release-notes.md).

## Versão 16.11 - novembro de 2016 {#release-16-11---november-2016}

### Novos recursos {#new-capabilities}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Regras de exclusão de entregabilidade<br /> </td> 
   <td> Agora, uma lista de supressão global criptografada é gerenciada na instância de entrega para evitar ser bloqueada devido a atividades mal-intencionadas, especialmente o uso de uma armadilha.<br /> Para cada entrega de email, duas regras de tipologia padrão comparam os endereços de email do destinatário com os endereços proibidos ou nomes de domínio contidos nessa lista. Se houver uma correspondência, esse destinatário será excluído da população-alvo.<br /><a href="../../administration/using/filtering-rules.md#default-deliverability-exclusion-rules"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Otimização geral<br /> </td> 
   <td> Esta atualização inclui inúmeras alterações e correções que corrigem problemas encontrados por nossos clientes. O desempenho da plataforma global também foi otimizado. <br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correções {#patches}

#### Geral {#general}

* Correção de vários problemas de segurança.
* Correção de vários problemas relacionados a campos vazios ou campos duplicados na API REST.
* Agora você pode criar mensagens SMS e notificações por push diretamente da página inicial do aplicativo.

#### Emails e mensagens SMS {#emails-and-sms-messages}

* Correção de um problema que impedia que os usuários carregassem arquivos zip no editor de conteúdo.
* Correção de um problema que impedia a abertura de uma prova após o envio.
* Correção de um problema que resultava na exibição de uma mensagem de erro ao acessar o **[!UICONTROL Hot Clicks]** relatório em um email de teste A/B.
* Correção de um problema que impedia a aplicação de modificações feitas usando o **[!UICONTROL Show source]** modo.
* Correção de um problema que impedia a importação de arquivos de modelo xml de linha de assunto preditivo.
* Uma nova tela dedicada à importação de dados para o modelo treinado da linha de assunto está disponível em **[!UICONTROL Administration > Channels > Emails > Predictive Subject Line]** .
* Correção de um problema que permitia que usuários não administradores editassem as máscaras autorizadas na tela de configuração de email.

#### Notificações por push {#push-notifications}

* Correção de um problema que impedia que o envio de logs e logs de eventos fossem exibidos para os destinatários após o envio de uma notificação por push usando o **[!UICONTROL Send push on profiles]** modelo.
* Correção de um problema que impedia a criação de novos aplicativos móveis.

#### Workflows {#workflows}

* Correção de um problema de desempenho que ocorria ao usar a **[!UICONTROL Subscription]** atividade.
* Correção de um problema que impedia o funcionamento de um fluxo de trabalho quando seu nome interno continha um espaço.

#### Integrações {#integrations}

* Correção de um problema que resultava na exibição de um erro ao usar a opção **Imagem compartilhada da Adobe Marketing Cloud** em um email.

#### Recursos personalizados {#custom-resources}

* Visualização de log de APIs aprimorada entre duas publicações de campos de API estendidos.
* Correção de um problema que impedia que um recurso personalizado fosse excluído antes de ser publicado.
* Correção de um problema que impedia a extensão de perfis e a definição de chaves de identificador com um campo dinâmico.
* Correção de um problema que ocorria ao adicionar links em um recurso personalizado.

## Versão 16.10 - outubro de 2016 {#release-16-10---october-2016}

### Novos recursos {#new-capabilities-1}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Linha de assunto preditiva de email<br /> </td> 
   <td> Ao editar um email, uma nova opção permite que você experimente diferentes linhas de assunto e obtenha uma estimativa de sua taxa de abertura antes de enviá-lo. Isso é possível treinando seu próprio modelo com base nos dados de entrega anteriores ou usando um modelo predefinido que seja específico para o seu setor. Este recurso está disponível para mensagens de email e bancos de dados que contêm apenas conteúdo em inglês. <br /> Para obter mais informações sobre como ativá-la e usá-la, consulte a documentação <a href="../../designing/using/subject-line.md#predictive-subject-line"></a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mensagens transacionais SMS<br /> </td> 
   <td> O canal SMS foi adicionado aos recursos de mensagens transacionais do Adobe Campaign. Dois canais agora são suportados para mensagens transacionais: email e SMS.<br /><a href="../../administration/using/configuring-transactional-messaging.md#creating-an-event"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mensagem de acompanhamento para mensagens transacionais<br /> </td> 
   <td> Agora é possível criar um fluxo de trabalho direcionado a um evento. Isso significa que você pode enviar uma mensagem de acompanhamento aos clientes que receberam uma mensagem transacional anteriormente. Você pode filtrar o destino pelo tipo de evento, pelos logs de eventos e pelos logs de rastreamento. Na mensagem de acompanhamento, você poderá aproveitar o conteúdo do evento (carga). <br /><a href="../../channels/using/follow-up-messages.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API de serviços e perfis estendidos<br /> </td> 
   <td> Agora é possível expor campos estendidos na API Perfil e serviços. O mecanismo de publicação permite que as APIs mapeiem os campos estendidos dos recursos personalizados Perfis ou Serviços. Para que isso funcione, a função <strong>Datamodel</strong> foi adicionada. Essa nova função permite que o usuário configure um conjunto de administradores que terão acesso ao modelo de dados.<br /><a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correções {#patches-1}

#### Geral {#general-1}

* Correção de vários problemas de segurança.

#### Emails e mensagens SMS {#emails-and-sms-messages-1}

* A tela de configuração da conta externa do SMS ( **[!UICONTROL Administration > Channels > SMS > SMS accounts]** ) foi aprimorada. Vários parâmetros foram adicionados na **[!UICONTROL SMSC specifics]** seção para suportar códigos de erro no campo "Texto".

#### Notificações por push {#push-notifications-1}

* Correção de um problema que impedia a exibição de filtros predefinidos ao editar o público-alvo de uma notificação por push com base no modelo **[!UICONTROL Send via push notification]** (mobileApp).
* A tela de configuração do aplicativo móvel ( **[!UICONTROL Administration > Channels > Push Notification > Mobile applications]** ) agora exibe uma mensagem indicando que a plataforma iOS ou Android foi criada com êxito.

#### Páginas de aterrissagem {#landing-pages}

* Correção de problemas que impedia o envio de emails de confirmação quando um formulário de página inicial era enviado.

#### Públicos-alvo e consultas {#audiences-and-queries}

* Correção de vários problemas que ocorriam ao selecionar um perfil no editor de consultas.

#### Mensagens transacionais {#transactional-messages}

* Correção de um erro que impedia a publicação de um modelo transacional.
* Correção de um problema que resultava na exibição de eventos de disparo na lista de eventos.

#### Integrações {#integrations-1}

* Correção de um problema que impedia que um público-alvo compartilhado fosse usado em uma entrega após a atualização.
* Correção de um problema que impedia que um ativo compartilhado ( **[!UICONTROL Image shared from Adobe Marketing Cloud]** opção) fosse usado em uma página de aterrissagem.
* Correção de problemas que ocorriam ao editar um público compartilhado importado do Adobe Audience Manager.

## Versão 16.9 - setembro de 2016 {#release-16-9---september-2016}

### Novos recursos {#new-capabilities-2}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Acionadores de recomercialização<br /> </td> 
   <td> Integration between the core service <span class="uicontrol">Triggers</span> and Adobe Campaign allows you to send personalized emails to your customers as a reaction to specific behaviors that are tracked on your website by Adobe Analytics (within 15 minutes).<br /> Na Adobe Marketing Cloud, você define os diferentes acionadores, ou seja, os comportamentos do cliente que você gostaria de monitorar, como todos os clientes que abandonaram seu carrinho ou formulário, removeram um produto do carrinho ou até mesmo os clientes cuja sessão expirou. Ao criar um acionador, você define a condição do acionador e os dados que serão enviados no evento (carregar) para o Adobe Campaign. <br /> No Adobe Campaign, você seleciona o acionador que foi criado anteriormente, aprimora os dados do evento com dados do datamart e define um modelo de mensagem transacional vinculado ao acionador. Por exemplo, quando um cliente abandona seu carrinho, um evento é enviado para o Adobe Campaign, que pode aproveitar esse evento por meio de um email de remarketing enviado ao cliente em 15 minutos.<br /><a href="../../integrating/using/about-adobe-experience-cloud-triggers.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mensagens transacionais: Pausar / Cancelar publicação<br /> </td> 
   <td> Agora você pode suspender a publicação de um modelo transacional enquanto atualiza o conteúdo. As mensagens correspondentes não são mais enviadas, mas são armazenadas no banco de dados. Ao retomar, as mensagens em fila são processadas e enviadas se não expiraram.<br /><a href="../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication"> Para obter mais informações, consulte a documentação</a> detalhada.<br /> Agora você também pode cancelar a publicação de eventos e modelos transacionais. As mensagens correspondentes não são mais enviadas e não são armazenadas no banco de dados.<br /><a href="../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Multimarca<br /> </td> 
   <td> Clientes com várias marcas agora podem gerenciá-las na mesma instância. A marca é um recurso gerenciado pelo administrador da instância do Adobe Campaign que permite a configuração centralizada de todos os parâmetros relacionados a uma marca no Adobe Campaign. Isso inclui coisas como o logotipo para parâmetros mais técnicos como URLs de rastreamento, Web Analytics, URL do servidor, nome do domínio etc.<br /><a href="../../administration/using/branding.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Visualização do design de email responsivo<br /> </td> 
   <td> Este recurso permite que você teste a capacidade de resposta de seu email em diferentes tipos de dispositivos. Na visualização de email, uma grade foi adicionada para testar seu email em vários tamanhos de tela.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificações por push<br /> </td> 
   <td> Um novo canal foi adicionado para permitir que os profissionais de marketing enviem notificações por push personalizadas e segmentadas em dispositivos móveis iOS e Android. As mensagens podem ser enviadas por meio de uma única entrega ou por meio de uma atividade de fluxo de trabalho. A compatibilidade com as mensagens transacionais estará disponível em versões futuras. Esse canal utiliza o SDK do serviço principal do Mobile (disponível <a href="https://marketing.adobe.com/developer/gallery/marketing-cloud-mobile-libraries">aqui</a>).<br /><a href="../../channels/using/about-push-notifications.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correções {#patches-2}

#### Geral {#general-2}

* Esta versão apresenta novos recursos de filtragem e pesquisa nas listas de interface. Esse novo recurso está disponível, por exemplo, nos registros (entrega, rastreamento), serviços (assinatura, histórico de assinaturas), públicos-alvo e transições de fluxo de trabalho.
* Correção de vários problemas de exibição relacionados ao número de pontos de contato em um perfil do cliente.
* Correção de vários problemas de tipologia.

#### Emails e mensagens SMS {#emails-and-sms-messages-2}

* Correção de um erro que permitia a edição de provas erradas. Agora são somente leitura.
* Correção de um problema que resultava na lista negra de um destinatário quando um SMS era muito longo ou tinha problemas de codificação.

#### Recursos personalizados {#custom-resources-1}

* Correção de um erro que impedia que todos os resultados fossem exibidos ao usar os filtros avançados de um recurso personalizado.

#### Mensagens transacionais {#transactional-messages-1}

* Agora, um prefixo é adicionado automaticamente ao identificador de uma nova definição de evento.
* O ícone que representa as mensagens transacionais na interface foi alterado.

#### Integrações {#integrations-2}

* Correção de um erro de exibição que ocorria quando uma imagem de alta resolução era inserida por meio da imagem **dinâmica da opção Adobe Target** .
* Correção de um erro que permitia que um público-alvo compartilhado fosse salvo mesmo se a ID de destino não estivesse definida na Fonte de dados AMC.

## Versão 16.7 - julho de 2016 {#release-16-7---july-2016}

### Novos recursos {#new-capabilities-3}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Mensagens transacionais enriquecidas<br /> </td> 
   <td> Agora você pode vincular modelos transacionais ao banco de dados do Adobe Campaign para recuperar informações que permitem enriquecer o conteúdo das mensagens transacionais.<br /><a href="../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> URLs dinâmicos para imagens<br /> </td> 
   <td> Essa nova funcionalidade permite que você personalize uma fonte de imagem inserindo blocos de conteúdo e texto dinâmico para fins de rastreamento e personalização.<br /> Torna-se possível, entre outras coisas, aproveitar as funcionalidades da mídia dinâmica do AEM Asset (S7) inserindo parâmetros nos URLs de imagem. Por exemplo, você pode enviar um email com imagens personalizadas dizendo "Olá Alexandre, obtenha as últimas notícias sobre os próximos eventos em Paris!" ou "Olá Frank, obtenha as últimas notícias sobre os eventos que estão por vir em Nova Iorque!"<br /><a href="../../designing/using/personalization.md#personalizing-urls"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integração com o serviço principal de pessoas<br /> </td> 
   <td> As IDs <strong>declaradas da Adobe Marketing Cloud agora são</strong> cobertas pela integração entre o Adobe Campaign e o serviço principal de pessoas (Perfis e públicos-alvo).<br /><strong> Isso significa que você pode importar segmentos e exportar públicos-alvo compostos por </strong>IDs de<strong>visitante ou </strong>IDs<br />declaradas. Para obter mais informações, consulte a documentação <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md"></a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Logs de entrega<br /> </td> 
   <td> Os registros MTA (servidor de entrega) agora exibem o histórico completo de cada mensagem, especialmente todas as tentativas de entrega, bem como os status de erro associados, e isso não afeta o desempenho do aplicativo.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correções {#patches-3}

#### Geral {#general-3}

* Corrigido um erro que fazia com que campos irrelevantes fossem exibidos em vez de campos que precisam ser concluídos. Isso ocorria depois que o operador de comparação era modificado várias vezes ao editar uma condição em uma consulta.
* Corrigido o comportamento da opção **[!UICONTROL The last X days/months/quarters/years]** ao definir uma condição de filtragem relativa para um campo de data. O período calculado agora é um período deslizante relativo à data e hora do servidor e não baseado no calendário.

#### Workflows {#workflows-1}

* Corrigido um erro que retornava uma lista incorreta de valores na tela para selecionar a dimensão de definição de metas nas propriedades de uma **[!UICONTROL Query]** atividade.
* Correção de um erro que forçava a seleção do operador **Existe** ao adicionar uma média ou um agregado de contagem em um elemento de coleção em uma **[!UICONTROL Query]** atividade.

#### Edição de conteúdo {#content-editing}

* Correção de um erro que resultava em problemas de exibição (design responsivo) ao importar conteúdo HTML: os atributos de estilo não são mais regravados quando o conteúdo é aberto pela primeira vez após ser importado.
* Corrigido um erro de não bloqueio que era causado quando uma condição era adicionada em uma variante de conteúdo dinâmico.
* Correção de um erro causado pela adição de uma caixa de seleção no conteúdo de uma página de aterrissagem. A caixa de seleção estava inutilizável.
* Corrigido um erro que ocorria ao excluir texto em um bloco se o cursor fosse colocado no início do bloco em questão.

#### Mensagens transacionais {#transactional-messages-2}

* Ao integrar um site, agora é possível definir uma data de expiração para qualquer evento. Depois que essa data for passada, a mensagem correspondente ao evento não poderá mais ser enviada.

## Versão 16.6 - junho de 2016 {#release-16-6---june-2016}

### Novos recursos {#new-capabilities-4}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> API de Perfis e Serviços<br /> </td> 
   <td> A API de serviços <span class="uicontrol">e</span> perfis do Adobe Campaign está disponível no portal <a href="https://www.adobe.io/products/campaign">adobe.io</a> . Isso permite que os perfis do Adobe Campaign sejam atualizados, adicionados e excluídos, e que eles sejam inscritos ou cancelados por meio de chamadas REST.<br /> Para obter mais informações, consulte a descrição <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">detalhada da API</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correções {#patches-4}

#### Geral {#general-4}

* As dicas de ferramentas agora estão desativadas em dispositivos móveis para garantir que as informações exibidas na tela sejam fáceis de ler.
* Correção de um erro que impedia o usuário de rolar o conteúdo de determinadas zonas na tela do iPad.
* Correção de vários erros de compatibilidade encontrados durante a edição de conteúdo no Internet Explorer 11.
* Correção de um erro que impedia o acesso de registros detalhados quando a importação de dados falhava pela primeira vez.
* Corrigido um erro que impedia que um filtro de intervalo fosse salvo.
* Correção de um erro que impedia a exibição de elementos de um recurso ao configurar a forma como uma lista é exibida.
* Correção de um erro no explorador do editor de consultas. Os resultados retornados pelo campo de pesquisa foram mantidos no histórico de pesquisa e continuaram a ser exibidos em cada nova pesquisa.

#### Emails e mensagens SMS {#emails-and-sms-messages-3}

* Correção de um erro que impedia a recuperação de informações vinculadas a rejeições em registros de entrega.
* Correção de um erro que impedia que o contexto em um bloco de conteúdo dinâmico de uma mensagem transacional fosse acessado.
* Correção de um erro que impedia que um link de URL fosse definido em texto dinâmico no conteúdo de um email.
* Correção da barra superior do assistente de criação de entrega.
* A chave primária de uma entrega não pode mais ser usada como um campo de personalização.

#### Workflows {#workflows-2}

* As transições entre duas atividades de um fluxo de trabalho agora exibem a contagem de elementos calculados e transferidos de uma atividade para outra.
* Campos incompatíveis agora ficam ocultos quando dados adicionais são adicionados em uma **[!UICONTROL Query]** atividade.
* A janela de definição agregada, exibida ao adicionar dados adicionais, foi aprimorada para oferecer apenas opções compatíveis com os dados em uso (por exemplo: calcular uma média só é possível para dados numéricos).
* Iniciar ou reiniciar um fluxo de trabalho técnico pronto agora só pode ser executado por um usuário com direitos administrativos.

#### Páginas de aterrissagem {#landing-pages-1}

* Corrigido um erro que truncava chaves de codificação AES de 32 bits nas propriedades de uma página inicial.
* Correção de um erro que impedia que o editor de consulta fosse exibido corretamente ao definir uma condição de visibilidade ou ao adicionar conteúdo dinâmico a uma página inicial.

#### Recursos personalizados {#custom-resources-2}

* A **[!UICONTROL Switch to parameters]** opção agora fica oculta ao definir um filtro relacionado às assinaturas de um perfil para um serviço.
* Corrigido um erro que ocorria quando um link do tipo 0-1 era configurado a partir de um recurso personalizado.
* Correção de um erro que, quando relevante, poderia impedir que o valor **padrão** Constante fosse editado ao adicionar um campo de tipo **Data e hora** em um recurso personalizado.

## Versão 16.5 - maio de 2016 {#release-16-5---may-2016}

### Novos recursos {#new-capabilities-5}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Filtros predefinidos<br /> </td> 
   <td> Agora, os administradores podem criar filtros avançados que aparecem no editor de consultas na forma de regras pré-configuradas. Selecionar esses filtros permite que os usuários desenvolvam configurações complexas mais facilmente em uma interface simplificada ao definir um público-alvo, por exemplo.<br /><a href="../../developing/using/configuring-filter-definition.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fluxos de trabalho: Serviços de assinatura<br /> </td> 
   <td> Uma nova atividade dos Serviços <span class="uicontrol">de</span> assinatura oferece a possibilidade de assinar vários perfis para um serviço ou cancelar a assinatura de um serviço com em uma única ação.<br /> Essa atividade pode ser usada após ter realizado uma definição de metas ou importado um arquivo com dados identificados.<br /><a href="../../automating/using/subscription-services.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fluxos de trabalho: enriquecimento dos dados<br /> </td> 
   <td> A guia Dados <span class="uicontrol"></span> adicionais agora está disponível em atividades do tipo <span class="uicontrol">Consulta</span> . Essa funcionalidade permite que você aprimore os dados direcionados pela consulta e transfira esses dados para as seguintes atividades de fluxo de trabalho onde eles podem ser explorados.<br /> Depois de adicionar dados adicionais, você pode aplicar um nível de filtro adicional aos dados direcionados inicialmente criando condições com base nos dados adicionais definidos.<br /><a href="../../automating/using/query.md#enriching-data"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ajuda contextual<br /> </td> 
   <td> Uma função de ajuda contextual agora está disponível em diferentes telas do Adobe Campaign. Isso significa que, em um único clique, você pode acessar diretamente a documentação sobre a funcionalidade que está usando no momento. Para exibir a ajuda contextual, clique em '?' no canto superior direito da tela, como mostrado no exemplo abaixo.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correções {#patches-5}

#### Geral {#general-5}

* Várias interfaces Novos recursos que cumprem os padrões da Marketing Cloud.
* Padronização dos diferentes tipos de lista suspensa.

#### Emails e mensagens SMS {#emails-and-sms-messages-4}

* Correção de um erro que impedia o envio de emails se a máscara de endereço de erro fosse especificada.
* O protocolo TLS agora é compatível com a entrega de email. Uma nova coluna no gerenciamento MX permite definir o comportamento TLS desejado para cada domínio.
* A interface SMS foi aprimorada.

#### Workflows {#workflows-3}

* Várias interfaces de fluxo de trabalho Novos recursos.
* Correção de um erro que ocorria ao exibir ações rápidas.
* Corrigido um erro que causava a falha de um fluxo de trabalho ao usar uma atividade **[!UICONTROL Segmentation]** de tipo contendo um link 1-N.
* Correção de um erro que impedia a abertura das transições de um fluxo de trabalho em um dispositivo híbrido.
* Correção de um erro que impedia a exibição do botão de pausa ao iniciar um fluxo de trabalho pela primeira vez.

#### Content editor {#content-editor}

* O editor de conteúdo agora permite que você personalize qualquer URL contido em um email ou página de aterrissagem. Consulte a documentação [](../../designing/using/personalization.md#personalizing-urls)detalhada.
* Correção de um erro que resultava na perda de imagens quando adicionadas ao assistente de criação da entrega e seu conteúdo era modificado posteriormente.

#### Recursos personalizados {#custom-resources-3}

* Correção de um erro que ocorria ao adicionar um link personalizado do tipo 1-N na tela de configuração de um recurso personalizado.
* Melhoria na exibição da barra de progresso ao preparar e publicar recursos personalizados.
* Correção de um erro que ocorria ao exibir a lista de links de um recurso personalizado.

#### Mensagens transacionais {#transactional-messages-3}

* A facilidade de utilização da interface, bem como o desempenho e a robustez do mecanismo de mensagens transacionais, foram otimizados.
* É agora possível suspender temporariamente a publicação de um modelo de mensagem transacional. For more on this, refer to the [detailed documentation](../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication).
* Corrigido um erro que fazia com que um bloco de conteúdo com uma dimensão de definição de metas incompatível fosse adicionado a um modelo de mensagem transacional.
* Correção de um erro que impedia a exibição da visualização da API em uma tela de configuração de evento.

#### Públicos-alvo e consultas {#audiences-and-queries-1}

* Vários patches relacionados ao uso de datas no editor de consultas. Consulte a documentação [](../../automating/using/editing-queries.md#creating-queries)detalhada.

#### Administração {#administration}

* Correção de um erro relacionado ao nome do grupo de segurança "Usuários padrão", que impedia que os usuários fizessem logon.

## Versão 16.3 - março de 2016 {#release-16-3---march-2016}

### Novos recursos {#new-capabilities-6}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Interface e navegação<br /> </td> 
   <td> A interface do Adobe Campaign foi aprimorada para tornar a navegação e as operações simples e intuitivas.<br /> Agora você navega na barra superior do aplicativo. Os menus avançados podem ser acessados selecionando o logotipo do <strong>Adobe Campaign</strong> .<br /><a href="../../start/using/interface-description.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fluxos de trabalho: Salvar público-alvo<br /> </td> 
   <td> Uma nova opção, <span class="uicontrol">Criar e atualizar um público</span> , agora está disponível na atividade <span class="uicontrol">Salvar público</span> . Essa opção permite que você insira manualmente um rótulo de público-alvo. Se o rótulo inserido corresponder a um público-alvo existente, ele será atualizado. Se o público-alvo não existir, ele será criado.<br /> Além disso, o público-alvo será atualizado sempre que o fluxo de trabalho for executado (novamente).<br /> Você sempre pode selecionar o modo de atualização de público-alvo: complete o público-alvo com novos dados ou substitua todos os dados do público-alvo em cada execução.<br /><a href="../../automating/using/save-audience.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fluxos de trabalho: Segmentação<br /> </td> 
   <td> A atividade de <span class="uicontrol">Segmentação</span> agora permite que o usuário segmente os dados de um recurso temporário.  Por exemplo: os dados de um arquivo importado.<br /><a href="../../automating/using/segmentation.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correções {#patches-6}

#### Geral {#general-6}

* Corrigido um erro de exibição que ocorria ao classificar uma lista: a seta que indica a ordem de classificação de uma coluna só pode ser invertida para determinados tipos de dados.
* Correção de um erro que limitava o número de elementos exibidos em um menu suspenso quando uma regra era adicionada em uma consulta.

#### Emails e mensagens SMS {#emails-and-sms-messages-5}

* Correção de um erro que impedia o acesso ao relatório de renderização de email.
* O estágio preparar envio para uma mensagem agora retornará um erro se o endereço do remetente não for fornecido.

#### Workflows {#workflows-4}

* Algumas opções de formatação de arquivo estavam visíveis, mas não foram levadas em conta quando um arquivo de formato CSV foi extraído. Essas opções agora não estão mais visíveis.
* Correção de um erro causado quando a opção **[!UICONTROL Delete the source files after transfer]** era verificada para uma transferência de arquivo de **[!UICONTROL SFTP]** tipo.
* Correção de um erro que poderia impedir que o contador e a visualização de **[!UICONTROL Query]** dados fossem exibidos após a atualização da página.
* Correção de um erro causado pela abertura de determinadas transições em um fluxo de trabalho, principalmente após uma atividade de entrega ou uma consulta em que as dimensões de definição de metas e filtragem eram diferentes.
* Correção de um erro que impedia a inserção de um campo de personalização em uma atividade de entrega de um fluxo de trabalho se o fluxo de trabalho não fosse salvo após a adição da atividade.
* Correção de um erro que impedia a exibição da dimensão de direcionamento de transição de saída de uma atividade de entrega de email.

#### Páginas de aterrissagem {#landing-pages-2}

* Correção de um erro que impedia que os campos de personalização funcionassem corretamente em um bloco de conteúdo localizado em uma página inicial.

#### Recursos personalizados {#custom-resources-4}

* Correção de um erro que impedia que uma pesquisa em um recurso personalizado fosse realizada se a **[!UICONTROL Add search fields]** opção da definição da tela do recurso estivesse marcada e se vários campos estivessem selecionados no **[!UICONTROL Filter zone composition]** .

## Versão 16.2 - fevereiro de 2016 {#release-16-2---february-2016}

### Novos recursos {#new-capabilities-7}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Teste A/B para emails<br /> </td> 
   <td> Agora você pode realizar testes A/B no conteúdo, assunto ou nome do remetente de seus emails. Essa nova funcionalidade pode testar até três variantes de um elemento.<br /> Ao criar um email a partir de um dos novos modelos específicos para testes A/B, uma nova etapa do assistente de criação permite que você defina os parâmetros do seu teste.<br /><a href="../../channels/using/designing-an-a-b-test-email.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Gerenciamento de marcas<br /> </td> 
   <td> Agora você pode definir uma ou várias marcas para inserir centralmente os parâmetros que afetam a identidade de uma marca. O Adobe Campaign permite que você crie essas marcas e as vincule aos modelos de página de entrega ou de aterrissagem.<br /><a href="../../administration/using/branding.md#assigning-a-brand-to-an-email"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fluxos de trabalho: Consulta incremental<br /> </td> 
   <td> Uma nova atividade de fluxo de trabalho, consulta <span class="uicontrol"></span> incremental, permite que você realize uma consulta que, em cada execução, direciona somente os novos resultados. Os resultados de execuções anteriores são excluídos automaticamente. Vinculado a uma atividade do <span class="uicontrol">Agendador</span> , você pode definir a frequência de execução da consulta <span class="uicontrol"></span> Incremental.<br /><a href="../../automating/using/incremental-query.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mensagens transacionais<br /> </td> 
   <td> A facilidade de utilização da interface de mensagens transacionais foi melhorada. Atualmente, todo o gerenciamento de processos de negócios vinculado a mensagens transacionais está centralizado no menu Planos <span class="uicontrol">de</span> marketing &gt; Mensagens <span class="uicontrol"></span> transacionais. A configuração do evento também foi aprimorada. Os eventos agora são gerenciados independentemente dos recursos personalizados.<br /><a href="../../channels/using/about-transactional-messaging.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correções {#patches-7}

#### Geral {#general-7}

* Correção de vários erros de exibição em relatórios, listas e consultas.
* Correção de vários erros de compatibilidade e exibição em dispositivos móveis.

#### Emails e mensagens SMS {#emails-and-sms-messages-6}

* Corrigido um erro que impedia que o botão usado para inserir campos de personalização fosse exibido ao criar uma mensagem (email ou SMS).
* Correção de um erro que impedia a transmissão correta de mensagens SMS enviadas pelo Mblox.

#### Públicos-alvo e consultas {#audiences-and-queries-2}

* Correção de um erro de contagem que poderia ser causado ao adicionar uma condição adicional em uma consulta, após a modificação da dimensão de filtragem.
* Correção de um erro que resultava em uma paginação incorreta ao visualizar os resultados de uma consulta.

#### Edição de conteúdo {#content-editing-1}

* Corrigido um erro que impedia que a configuração de conteúdo dinâmico fosse considerada corretamente ao usar uma enumeração personalizada.

#### Workflows {#workflows-5}

* Correção de um erro que impedia a execução de qualquer ação em um fluxo de trabalho se houvesse uma linha vazia na **[!UICONTROL Fields to update]** guia de uma **[!UICONTROL Update data]** atividade.
* Correção de um erro que impedia a importação de dados com informações geográficas/de unidades organizacionais.
* Correção de um erro causado pela adição de um **[!UICONTROL Change axis]** tipo de **[!UICONTROL Exclusion]** regra.
* Correção de um erro que resultava na criação de um segmento adicional indesejado ao manipular uma transição externa de uma **[!UICONTROL Segmentation]** atividade.
* Correção de um erro causado pelo carregamento de um arquivo em um modelo de fluxo de trabalho.
* Corrigido um erro que impedia que espaços fossem usados como separadores de colunas em uma **[!UICONTROL Load file]** atividade.

#### Recursos personalizados {#custom-resources-5}

* Corrigido um erro que impedia que o status de um recurso personalizado fosse redesenhado após a importação de um pacote, se o recurso fosse publicado no momento da exportação.

#### Pacotes {#packages}

* Correção de um erro que impedia a exportação de um pacote contendo um fluxo de trabalho.
* Correção de um erro que poderia impedir a seleção de vários elementos do mesmo recurso.

## Versão 16.1 - Janeiro de 2016 {#release-16-1---january-2016}

### Novos recursos {#new-capabilities-8}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Relatórios<br /> </td> 
   <td> Os seguintes relatórios específicos de email foram adicionados: <span class="uicontrol">Reclamações</span> , <span class="uicontrol">Aberturas</span> e <span class="uicontrol">Cancelamento de assinaturas</span> .<br /> Os seguintes relatórios foram aprimorados: Resumo <span class="uicontrol">da</span> entrega, resumo <span class="uicontrol">da</span> rejeição, throughput <span class="uicontrol">da</span> entrega e indicadores <span class="uicontrol">de</span> rastreamento.<br /><a href="../../reporting/using/defining-the-report-period.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edição de consulta<br /> </td> 
   <td> O editor de consultas foi aprimorado e agora permite que você digitalize os links do tipo <strong>1-N</strong> .<br /><a href="../../automating/using/editing-queries.md#creating-queries"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Personalização de conteúdo<br /> </td> 
   <td> Quanto à edição de email ou página inicial, a interface de entrada para as condições de exibição de blocos de conteúdo foi aprimorada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fluxos de trabalho: definição de coluna ao importar<br /> </td> 
   <td> A atividade <span class="uicontrol">Carregar arquivo</span> agora permite configurar as colunas de um arquivo importado em detalhes: tipo de dados esperado, formato de data e hora, processamento a ser aplicado no caso de um valor vazio ou um erro e mapeamento de valor.<br /><a href="../../automating/using/load-file.md#column-format"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mapeamento de codificações SMS<br /> </td> 
   <td> Agora é possível definir mapeamentos de codificações de mensagens SMS personalizadas para provedores que não usam codificação padrão. Um administrador pode realizar a configuração de mapeamentos personalizados e definir a ordem em que eles devem ser levados em conta.<br /><a href="../../administration/using/configuring-sms-channel.md#smsc-specifics"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correções {#patches-8}

#### Geral {#general-8}

* Compatibilidade aprimorada com o Internet Explorer e o Chrome para dispositivos híbridos/de tela sensível ao toque.
* Correção de um erro que resultava na perda de todos os dados inseridos para um novo perfil de usuário/perfil/teste se o endereço de email indicado contivesse erros de sintaxe.

#### Emails e mensagens SMS {#emails-and-sms-messages-7}

* Correção de um erro que impedia a geração da miniatura do conteúdo na tela de visualização de email.
* Corrigido um erro que impedia que o conteúdo bruto de uma mensagem (email ou SMS) fosse exibido na tela de visualização da mensagem.

#### Públicos-alvo e consultas {#audiences-and-queries-3}

* Correção de um erro que poderia impedir a criação de um público-alvo do tipo **Consulta** no recurso **Serviço** .
* Corrigido um erro que impedia que a lista de funções fosse exibida corretamente ao editar uma condição de uma consulta no modo avançado.
* Correção de um erro que poderia impedir a criação de um público-alvo do tipo **Consulta** se contivesse critérios baseados em coleções.
* Correção de um erro que impedia a criação de consultas contendo filtros em KPIs de entrega.
* Correção de um erro que impedia a visualização do conteúdo de um público-alvo criado a partir de um fluxo de trabalho.

#### Recursos personalizados {#custom-resources-6}

* Correção de um erro que resultava em falha de servidor se um recurso personalizado contivesse um campo com um valor padrão dinâmico.
* Correção de um erro causado pela movimentação e exclusão de um elemento na **[!UICONTROL Detail screen configuration]** seção ao definir telas de um recurso personalizado.
* Correção de um erro que ocorria quando um valor padrão era definido para uma lista de **inteiros** que não incluía **0** em seu intervalo de valores possíveis.
* Correção de um erro que impedia a adição de um elemento na configuração de tela detalhada de um recurso personalizado após uma reinicialização.

#### Workflows {#workflows-6}

* Corrigido um erro que fazia com que os registros de todas as atividades em um fluxo de trabalho fossem exibidos em vez de apenas os da atividade selecionada.
* Corrigido um erro na **[!UICONTROL Scheduler]** atividade. A **[!UICONTROL Day of the month]** opção não foi corretamente considerada e substituída por **[!UICONTROL Week day]** .
* Corrigido um erro que impedia que uma **[!UICONTROL Scheduler]** atividade funcionasse corretamente com o modo de expiração definido como **[!UICONTROL After a certain number of iterations]** .
* Correção de um erro que ocorria ao exportar dados usando uma **[!UICONTROL Extract file]** atividade. O número de linhas presentes no arquivo de exportação foi inferior ao número de elementos exportados.
* Correção de um erro que poderia impedir a seleção de um arquivo em uma **[!UICONTROL Load file]** atividade.
* Correção de um erro que impedia a exclusão de campos que eram atualizados em uma **[!UICONTROL Update data]** atividade.
* Correção de um erro que impedia que as modificações feitas em um fluxo de trabalho fossem salvas depois de terem aberto os logs de execução do fluxo de trabalho.
* Correção de um erro que fazia com que uma **[!UICONTROL Load file]** atividade fosse executada duas vezes se fosse configurada para usar o arquivo de sua transição de entrada e esse arquivo tivesse sido carregado usando uma **[!UICONTROL Transfer file]** atividade.
* Correção de um erro que poderia impedir que determinadas entidades temporárias fossem processadas corretamente por uma atividade de **exclusão** .
* Correção de um erro que impedia que uma **[!UICONTROL Query]** atividade fosse executada corretamente se a dimensão de definição de metas e a dimensão de filtragem configuradas na atividade fossem diferentes.
* Correção de um erro relativo à nomeação automática de transições de saída adicionadas a uma **[!UICONTROL Fork]** atividade que poderia impedir que o fluxo de trabalho fosse salvo.

#### Edição de conteúdo {#content-editing-2}

* Correção de um erro que resultava na exibição indesejável de um ícone ou de uma barra de pesquisa ao editar o conteúdo.

#### Páginas de aterrissagem {#landing-pages-3}

* Correção de um erro que impedia a importação de uma página inicial por meio de uma importação de pacote.

#### Mensagens transacionais {#transactional-messages-4}

* Agora é possível especificar um endereço IP confiável nos parâmetros de segurança do operador do agente de push do Centro de mensagens.
* Corrigido um erro que impedia a criação de um novo tipo de evento.

## Versão 15.11 - novembro de 2015 {#release-15-11---november-2015}

### Novos recursos {#new-capabilities-9}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> SMS Channel<br /> </td> 
   <td> Agora você pode enviar mensagens SMS com o Adobe Campaign.<br /> Assim como para emails, você pode criar novas entregas de SMS de suas campanhas e da lista de atividades de marketing. Você também pode criar mensagens SMS recorrentes e de envio únicas a partir de um fluxo de trabalho.<br /> Essas entregas de SMS são baseadas em modelos que você pode configurar na lista de modelos de entrega. Um template padrão está disponível.<br /> Essas entregas SMS usam o protocolo SMPP 3.4, usado pela maioria dos roteadores SMS.<br /><a href="../../channels/using/about-sms-messages.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Explorar transições<br /> </td> 
   <td> Agora você pode explorar os dados e sua estrutura na última transição de um fluxo de trabalho. Isso permite verificar se os processos aplicados por cada atividade correspondem às suas necessidades.<br /> </td> 
  </tr> 
  <tr> 
   <td> Pré e pós-processamento de arquivos em fluxos de trabalho<br /> </td> 
   <td> Agora você pode realizar processamento adicional em um arquivo de dados ao importá-lo ou exportá-lo por meio das atividades <span class="uicontrol">Carregar arquivo</span> e <span class="uicontrol">Extrair arquivo</span> .<br /> Por padrão, você pode descompactar e compactar um arquivo de formato GZIP nessas atividades.<br /> Para obter mais informações, consulte a documentação sobre as atividades <a href="../../automating/using/load-file.md">Carregar arquivo</a> e <a href="../../automating/using/extract-file.md">Extrair arquivo</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> Relatórios de entregabilidade<br /> </td> 
   <td> Um relatório de renderização de email está disponível. Este relatório permite que você visualize as diferentes renderizações de uma mensagem de acordo com o serviço de suporte e mensagem usado para lê-la.<br /> O resumo do relatório também apresenta o número de mensagens recebidas, mensagens de spam, mensagens não recebidas e mensagens que aguardam recepção.<br /><a href="../../sending/using/email-rendering.md#email-rendering-report-description"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Gerenciamento de pacotes<br /> </td> 
   <td> Agora é possível importar e exportar imagens em pacotes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ações rápidas<br /> </td> 
   <td> Determinadas ações são exibidas ao passar o mouse sobre ou depois de selecionar um elemento em uma lista ou fluxo de trabalho. Algumas dessas ações são agora exibidas como ícones em torno dos elementos em questão para facilitar o acesso. Essas ações rápidas podem ser usadas para duplicar um elemento, excluí-lo, mostrar os detalhes etc.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correções {#patches-9}

#### Geral {#general-9}

* Correção de um erro que poderia impedir o acesso aos parâmetros gerais de uma instância de uma conta de administrador.
* **Os dados flutuantes** agora são corretamente levados em conta nos recursos personalizados.
* Correção de um erro de exibição na lista de importações simplificadas executadas que era causado quando o status do modelo correspondente era modificado.

#### Páginas de aterrissagem {#landing-pages-4}

* Correção de certos elementos de modelos de página inicial que podiam ser exibidos incorretamente em francês em instâncias em inglês.

#### Audiences {#audiences}

* Correção de um erro que impedia que públicos-alvo importados da Adobe Marketing Cloud fossem exibidos na lista de públicos-alvo.
* Corrigido um erro que fazia com que a distinção entre maiúsculas e minúsculas fosse forçada ao definir uma consulta.
* Correção de um erro que poderia impedir que os públicos-alvo fossem filtrados ao definir uma consulta.
* Correção de um erro que poderia impedir o cancelamento de uma ação em um público-alvo.

#### Workflows {#workflows-7}

* Corrigido um erro que impedia que os campos que deveriam ser atualizados em uma **[!UICONTROL Update data]** atividade fossem configurados manualmente.
* Corrigido um erro que fazia com que a **[!UICONTROL Query]** atividade fosse carregada infinitamente quando aberta se o fluxo de trabalho não tivesse sido salvo depois de ter colocado a atividade no diagrama.
* Corrigido um erro que fazia com que o servidor parasse ao contar ou visualizar um público-alvo selecionado de um **[!UICONTROL Query]** em um fluxo de trabalho.
* Correção de um erro não crítico que podia aparecer quando uma atividade em um fluxo de trabalho era aberta.
* Correção de um erro que impedia que uma **[!UICONTROL Scheduler]** atividade fosse configurada para executar um fluxo de trabalho várias vezes ao dia.
* Corrigido um erro que fazia com que campos nos quais não é possível realizar uma consulta fossem exibidos em determinadas atividades de fluxo de trabalho.
* Correção de um erro que impedia o usuário de localizar os KPIs adicionados a partir de uma **[!UICONTROL Query]** entrega na transição de saída.
* Correção de um erro que impedia a criação de um público-alvo de arquivo após a importação de um arquivo para um fluxo de trabalho.
* Correção de um erro que impedia a atualização de dados em perfis se o campo **location/address3** do recurso fosse usado.
* Correção de um erro que impedia que coleções heterogêneas de atividades fossem duplicadas em um fluxo de trabalho.
* Correção de um erro que impedia a exibição do SQL, permitindo assim que erros fossem diagnosticados para uma entrega recorrente em um fluxo de trabalho.

#### Content editor {#content-editor-1}

* Corrigido um erro que tornava impossível a pesquisa no código fonte de uma página de aterrissagem ou email.

#### Pacotes {#packages-1}

* Correção de vários erros que poderiam impedir que certos tipos de elementos fossem exportados em pacotes (principalmente páginas de aterrissagem, fluxos de trabalho).
* Corrigido um erro que fazia com que o rótulo de importação do pacote anterior fosse exibido se o rótulo tivesse sido modificado.
* Corrigido um erro que fazia com que recursos incompatíveis fossem exibidos na lista de recursos exportáveis.

## Versão 15.10 - outubro de 2015 {#release-15-10---october-2015-}

### Novos recursos {#new-capabilities-10}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Fluxos de trabalho: Atividade de desduplicação<br /> </td> 
   <td> Uma nova atividade dedicada à desduplicação de dados agora está disponível nos fluxos de trabalho. Essa atividade permite que você filtre quaisquer duplicatas em seus destinos de acordo com seus critérios escolhidos.<br /><a href="../../automating/using/deduplication.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fluxos de trabalho: Diagrama aprimorado<br /> </td> 
   <td> Na área de trabalho do fluxo de trabalho, agora é possível usar vários atalhos do teclado para selecionar, abrir e excluir atividades.<br /> O alinhamento da atividade também foi aprimorado e permite que um fluxo de trabalho seja melhor organizado visualmente.<br /><a href="../../automating/using/workflow-interface.md#workspace"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fluxos de trabalho: Extrair atividade de arquivo<br /> </td> 
   <td> A data e a hora da exportação agora são automaticamente adicionadas aos rótulos dos arquivos exportados usando uma atividade de arquivo <span class="uicontrol"></span> Extract. Dessa forma, os arquivos gerados são exclusivos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Importação de dados simplificada<br /> </td> 
   <td> O nome do modelo a partir do qual foi efetuada uma importação simplificada está agora visível, por padrão, na lista de importação e nos detalhes de cada importação.<br /> </td> 
  </tr> 
  <tr> 
   <td> Recursos personalizados<br /> </td> 
   <td> Melhorias e possibilidades ampliadas para gerenciar e definir links para recursos personalizados.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correções {#patches-10}

#### Email {#email}

* Corrigido um erro que impedia que um link de cancelamento de assinatura de serviço funcionasse corretamente de uma página espelhada.
* Correção de um erro que impedia a exibição correta de um rótulo de entrega de email na página de edição de email.
* Correção de um erro que impedia a seleção de uma **[!UICONTROL Routing]** conta externa em um modelo de entrega duplicado.

#### Audiences {#audiences-1}

* Corrigido um erro causado durante uma contagem de público-alvo se um link 1-N fosse usado na consulta.
* Corrigido um erro que impedia que um perfil fosse selecionado no público-alvo de uma entrega de email.

#### Workflows {#workflows-8}

* Corrigido um erro que causava problemas de exibição ao configurar uma entrega de email em um fluxo de trabalho.
* Corrigido um erro que podia impedir que a **[!UICONTROL Load file]** atividade funcionasse corretamente. Uma mensagem de erro em branco será exibida.
* Corrigido um erro que podia impedir que a **[!UICONTROL Transfer file]** atividade funcionasse corretamente. Os direitos de acesso nem sempre foram considerados corretamente.
* Correção de um erro que poderia impedir a exportação de um arquivo se o fluxo de trabalho contivesse um **[!UICONTROL Recurring email]** .
* Correção de um erro que poderia impedir a criação de uma entrega de email em um fluxo de trabalho ou impedir que o assunto e o conteúdo definido fossem levados em conta.
* Correção de um erro que impedia a seleção de uma chave de reconciliação em uma **[!UICONTROL Update data]** atividade ao configurar o fluxo de trabalho de um modelo de importação simplificado.
* Correção de um erro que impedia que um fluxo de trabalho fosse salvo após uma atividade ser excluída.

#### Plataforma {#platform}

* Correção de um erro que poderia impedir a criação de um novo elemento se um recurso personalizado contivesse um link para o tipo de recurso desse elemento.
* Correção de um erro que resultava em um atraso de 15 minutos para certos registros serem gravados.
* Correção de um erro que poderia impedir que a lista de atividades de marketing fosse exibida quando classificada pelas **[!UICONTROL Date]** colunas ou **[!UICONTROL Indicators]** .

#### Páginas de aterrissagem {#landing-pages-5}

* Correção de um erro que ocorria ao selecionar um perfil de teste para visualizar uma página inicial.

#### Mensagens transacionais {#transactional-messages-5}

* Correção de um erro que resultava em falha do aplicativo após a exclusão de um evento em um perfil de teste.

#### Relatórios {#reports}

* Corrigido um erro que fazia com que dados incorretos fossem enviados para os relatórios **[!UICONTROL deliveryThroughputReport]** e **[!UICONTROL deliveryTrackingReport]** .

#### Content editor {#content-editor-2}

* Correção de um erro do gerenciamento de tags HTML que ocorria ao processar blocos de conteúdo dinâmico.

## Versão 15.8 - agosto de 2015 {#release-15-8---august-2015}

### Novos recursos {#new-capabilities-11}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Importação de dados simplificada<br /> </td> 
   <td> Agora é possível importar dados de uma maneira simplificada.<br /> Os usuários simplesmente selecionam um modelo predefinido por um administrador e carregam o arquivo que contém os dados a serem importados. Um fluxo de trabalho definido no modelo é executado de forma transparente para o usuário, que pode acessar os detalhes do resultado da importação, bem como um log de quaisquer erros.<br /> Os dados desses arquivos podem ser inseridos no banco de dados ou servir como um meio para criar diretamente um público-alvo.<br /><a href="../../automating/using/about-data-import-and-export.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Criação de programas e campanhas<br /> </td> 
   <td> Agora, campanhas e programas são configurados para que o dia em que são criados seja automaticamente usado como a data de início.<br /> A data final é configurada de acordo com a data de início, como:<br /> 
    <ul> 
     <li> D+186 para programas </li> 
     <li> D+61 para campanhas </li> 
    </ul> Para obter mais informações, consulte a <a href="../../start/using/programs-and-campaigns.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email<br /> </td> 
   <td> A lista de URLs rastreados agora é somente leitura.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mensagens transacionais<br /> </td> 
   <td> Agora você pode gerenciar mensagens transacionais personalizadas para eventos como alterações de senha ou confirmações após a criação de uma conta.<br /><a href="../../channels/using/about-transactional-messaging.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Recursos personalizados<br /> </td> 
   <td> Várias funcionalidades adicionadas, como: extensão de um perfil de teste, gerenciamento de status e exclusão de recursos.<br /><a href="../../developing/using/resource-statuses.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correções {#patches-11}

#### Exibir {#display}

* Correção de um erro que resultava na justaposição de dois campos no editor de consulta no Safari.

#### Content editor {#content-editor-3}

* Correção de um erro que impedia que os caracteres '&lt;', '&amp;' e '&gt;' fossem usados em um assunto de email.

#### Email {#email-1}

* Correção de um erro que impedia o usuário de adicionar texto após texto dinâmico.

#### Listas {#lists}

* Correção de um erro que impedia a exportação correta da coluna **Mensagem** nos logs de execução do fluxo de trabalho.

#### Perfis e públicos-alvo {#profiles-and-audiences}

* Correção de um erro que resultava em uma confirmação dupla de quando um elemento era duplicado ou excluído. **Dispositivos híbridos usando apenas** o Internet Explorer 11.

#### Workflows {#workflows-9}

* Correção de um erro que impedia o envio de emails de um fluxo de trabalho.
* Correção de um erro que impedia a execução de um fluxo de trabalho quando o nome do arquivo de rejeição não era especificado em uma **[!UICONTROL Load file]** atividade.
* Correção de um erro que impedia a execução de um fluxo de trabalho quando a configuração **[!UICONTROL Execution frequency]** de uma **[!UICONTROL Schedule]** atividade era definida como **[!UICONTROL Daily]** .

#### Plataforma {#platform-1}

* Correção de um erro que impedia a geração de miniaturas em um ambiente com balanceamento de carga.

## Versão 15.7 - julho de 2015 {#release-15-7---july-2015}

### Novos recursos {#new-capabilities-12}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Exportar listas<br /> </td> 
   <td> Agora você pode exportar conteúdo de suas listas para um arquivo no formato CSV. Essa função está disponível em todas as telas com um modo de <strong>Lista</strong> (por exemplo: lista de perfis).<br /> Os dados exportados são os dados nas colunas exibidas ao exportar. Ao editar a lista, você pode selecionar os dados que deseja exportar.<br /> Para obter mais informações sobre como usar essa funcionalidade, consulte a documentação <a href="../../automating/using/exporting-lists.md"></a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integração com perfis e públicos-alvo da Adobe<br /> </td> 
   <td> Agora você pode compartilhar públicos-alvo entre o Adobe Campaign e suas outras soluções da Adobe Marketing Cloud:<br /> 
    <ul> 
     <li> Exportar: ao salvar um público-alvo composto de perfis em um fluxo de trabalho, uma nova opção <span class="uicontrol">Compartilhar na Adobe Marketing Cloud</span> permite que você adicione perfis a um público-alvo existente ou crie um novo público-alvo. </li> 
     <li> Importar: ao criar um público-alvo do tipo <strong>Lista</strong> na tela de gerenciamento de público-alvo, uma nova opção permite identificá-lo como um Público-alvo <span class="uicontrol">da</span> Adobe Marketing Cloud. Você pode selecionar um público-alvo compartilhado existente para importá-lo para o Adobe Campaign. </li> 
    </ul> Para obter mais informações sobre como configurar e usar essa funcionalidade, consulte a documentação <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md"></a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Editor de conteúdo digital - Conteúdo dinâmico<br /> </td> 
   <td> A interface de conteúdo dinâmico foi aprimorada. As setas agora aparecem para permitir que você navegue entre os diferentes conteúdos dinâmicos, diretamente no corpo do email.<br /> Para obter mais informações sobre como usar essa funcionalidade, consulte a documentação <a href="../../designing/using/personalization.md#defining-dynamic-content-in-an-email"></a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Editor de conteúdo digital - Texto dinâmico<br /> </td> 
   <td> No editor de conteúdo de um email, agora é possível definir um texto dinâmico:<br /> 
    <ul> 
     <li> em um assunto de email, </li> 
     <li> no modo HTML, </li> 
     <li> ou no modo Texto. </li> 
    </ul>  Para obter mais informações sobre como usar essa funcionalidade, consulte a documentação <a href="../../channels/using/defining-dynamic-text.md"></a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Programas e campanhas - Relatórios<br /> </td> 
   <td> A interface e os gráficos dos relatórios foram aprimorados.<br /> Para obter mais informações sobre como usar essa funcionalidade, consulte a documentação <a href="../../reporting/using/defining-the-report-period.md"></a>detalhada.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correções {#patches-12}

#### Instalação {#installation}

* Os nomes de instância do Adobe Campaign agora estão limitados a 32 caracteres.

#### Workflows {#workflows-10}

* Correção de um erro que poderia impedir o direcionamento de um recurso de "entrega" ao editar uma consulta em um fluxo de trabalho.
* Correção de um erro que poderia impedir que determinados recursos vinculados fossem processados ao editar uma consulta em um fluxo de trabalho.
* Correção de um erro que impedia que uma atividade de entrega **** recorrente fosse modificada se o fluxo de trabalho já tivesse sido executado.

#### Emails {#emails}

* Correção de um erro que impedia a verificação de erros de sintaxe JavaScript antes do envio de um email quando um conteúdo dinâmico era adicionado pelo editor de expressões.

#### Páginas de aterrissagem {#landing-pages-6}

* Correção de um erro que impedia a edição de uma página inicial de um tablet.

#### Assets Core Service {#assets-core-service}

* Ao selecionar um recurso compartilhado de um email ou página de aterrissagem que está sendo editada, a lista de recursos disponíveis agora é filtrada para o Adobe Campaign.

## Versão 15.6 - junho de 2015 {#release-15-6---june-2015}

### Novos recursos {#new-capabilities-13}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Fluxos de trabalho: Atividade de reconciliação<br /> </td> 
   <td> Uma nova atividade de <strong>Reconciliação</strong> vincula dados não identificados (por exemplo, após a importação de um arquivo) com recursos existentes em um fluxo de trabalho.<br /> Essa atividade é usada essencialmente para fins de Gerenciamento de dados. Ele responde a dois casos de uso diferentes:<br /> 
    <ul> 
     <li> <strong>Adicionar relações</strong>: uma guia <strong>Relações</strong> permite adicionar links entre dados de entrada e várias outras dimensões do banco de dados do Adobe Campaign. </li> 
     <li> <strong>Identificação</strong>dos dados: uma guia <strong>Identificação</strong> permite simplesmente associar dados de entrada a colunas em uma dimensão existente no banco de dados do Adobe Campaign. Quando deixa a atividade, os dados são identificados como pertencendo à dimensão especificada. </li> 
    </ul> Consulte a documentação <a href="../../automating/using/reconciliation.md"></a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fluxos de trabalho: Extrair atividade de arquivo<br /> </td> 
   <td> Uma nova atividade <strong>Extrair arquivo</strong> permite exportar dados do banco de dados do Adobe Campaign na forma de um arquivo externo de um fluxo de trabalho. <br /> Limitação: no momento, não é possível usar nomes dinâmicos para arquivos de saída.<br /> Consulte a documentação <a href="../../automating/using/extract-file.md"></a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fluxos de trabalho: Atividade do agendador<br /> </td> 
   <td> Widget aprimorado que permite selecionar o tempo de execução da atividade do <strong>Agendador</strong> em um fluxo de trabalho.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fluxos de trabalho: Transferir atividade do ficheiro<br /> </td> 
   <td> O SFTP agora é compatível.<br /> </td> 
  </tr> 
  <tr> 
   <td> Recursos personalizados<br /> </td> 
   <td> O menu <span class="uicontrol">Desenvolvimento</span> agora permite que os usuários com direitos administrativos aprimorem os modelos de dados fornecidos criando seus próprios recursos personalizados, como tabelas de produtos ou compras. <br /> Os recursos predefinidos também podem ser estendidos para adicionar novos campos a eles.<br /> Além disso, a navegação nas telas correspondentes a recursos personalizados novos ou estendidos pode ser configurada.<br /> Consulte a documentação <a href="../../developing/using/data-model-concepts.md"></a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Test profiles<br /> </td> 
   <td> O nome <strong>do</strong> meio e o <strong>título</strong> dos perfis de teste agora podem ser selecionados ao configurar a lista de perfis de teste.<br /> </td> 
  </tr> 
  <tr> 
   <td> Editor de conteúdo: Conteúdo dinâmico<br /> </td> 
   <td> Você pode definir conteúdos diferentes que serão exibidos dinamicamente para o usuário de acordo com as condições definidas pelo editor de expressões.<br /> Consulte a documentação <a href="../../designing/using/personalization.md#defining-dynamic-content-in-an-email"></a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email<br /> </td> 
   <td> Uma coluna de perfis <strong>de</strong> teste agora está disponível nos registros de envio de email.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correções {#patches-13}

#### Listas {#lists-1}

* A exclusão de um elemento de uma lista agora resulta na atualização automática da lista.
* Correção de um erro que impedia a seleção de elementos de uma lista contendo apenas uma coluna.
* Correção de um erro que causava a perda de alterações aplicadas à exibição de uma lista após a atualização da página.
* O nome do meio e o título dos perfis de teste agora podem ser exibidos na lista de perfis de teste.
* Correção de um erro que ocorria ao selecionar uma caixa de seleção em uma lista com o Mozilla Firefox.

#### Audiences {#audiences-2}

* Corrigido um erro que impedia que o **[!UICONTROL Add]** botão fosse usado na interface do público-alvo.

#### Emails {#emails-1}

* Corrigido um erro de JavaScript que impedia que o botão de visualização fosse usado duas vezes seguidas ao editar um email.
* Corrigido um erro que impedia que os botões **[!UICONTROL Edit properties]** e **[!UICONTROL Show proofs]** fossem usados em tablets do Microsoft Surface Pro3 usando o Internet Explorer 11.
* Correção de um erro que impedia a exibição dos registros de envio de email.

#### Páginas de aterrissagem {#landing-pages-7}

* Corrigido um erro que impedia que o bloco de conteúdo do logotipo **da** Marca fosse usado ao editar conteúdo em uma página de aterrissagem.
* Correção de um erro que impedia a exibição de páginas iniciais na lista de atividades de marketing se as datas de validade fossem especificadas para a página inicial.

#### Workflows {#workflows-11}

* Correção de um erro que impedia que a limitação de um segmento no modo de grupo funcionasse corretamente ao configurar uma atividade de **Segmentação** .
* Correção de um erro que impedia a seleção de uma transição após a configuração de uma atividade de **Segmentação** .
* Correção de um erro que impedia a exclusão de uma transição após a configuração de uma atividade de **Segmentação** .
* Correção de um erro que impedia que populações fossem contadas e visualizadas em uma atividade de **Segmentação** .
* Correção de um erro que impedia a exclusão efetiva de um email recorrente.
* Corrigido um erro que fazia com que os dados de uma atividade de arquivo **de** transferência excluída aparecessem em uma nova atividade de arquivo **de** transferência.
* Correção de um erro que impedia que uma regra de exclusão fosse considerada corretamente em uma atividade de **exclusão** .
* Correção de um erro que ocorria ao excluir uma atividade de entrega de email em um fluxo de trabalho. As entregas correspondentes também são removidas da lista de atividades de marketing.

#### Navegação {#navigation}

* Agora você pode usar a tecla tab para navegar corretamente entre os campos na mesma página.

## Versão 15.4 - abril de 2015 {#release-15-4---april-2015}

### Novos recursos {#new-capabilities-14}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Exportações de pacotes / Importações de pacotes<br /> </td> 
   <td> O menu <strong>Implantação</strong> agora permite que usuários com direitos administrativos troquem recursos entre diferentes instâncias do Adobe Campaign exportando e importando pacotes.<br /> Consulte a documentação <a href="../../automating/using/managing-packages.md"></a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Relatórios<br /> </td> 
   <td> Todos os relatórios (exceto o relatório de cliques <strong></strong> ativos) agora podem ser acessados de um programa. Esses relatórios são:<br /> 
    <ul> 
     <li> Taxa de transferência do programa </li> 
     <li> Indicadores de rastreamento do programa </li> 
     <li> Detalhamento do programa por domínio </li> 
     <li> Resultados e rejeições do programa </li> 
     <li> URLs do programa e fluxos de cliques </li> 
    </ul> Esses relatórios podem ser filtrados durante um determinado período (por exemplo, três meses, seis meses, etc.). Os relatórios de campanha também podem ser filtrados.<br /> Consulte a documentação <a href="../../reporting/using/about-dynamic-reports.md"></a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fluxos de trabalho: Atividade de entrega <strong>de</strong> email<br /> </td> 
   <td> A atividade de entrega <strong>de</strong> email nos fluxos de trabalho foi aprimorada. Agora você pode encontrar emails, emails recorrentes e informações detalhadas sobre execuções recorrentes de email na lista de atividades de marketing de aplicativos.<br /> Consulte a documentação <a href="../../automating/using/email-delivery.md"></a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fluxos de trabalho: Atividade <strong>de segmentação</strong><br /> </td> 
   <td> A atividade de <strong>Segmentação</strong> agora está disponível nos fluxos de trabalho. Essa atividade permite criar um ou vários segmentos e vincular um código de segmento a eles a partir de uma população calculada por atividades colocadas em upstream no mesmo fluxo de trabalho. A partir dessa atividade, os segmentos podem ser processados em uma única transição ou em diferentes transições. Agora há opções para filtrar a população e limitar o tamanho de cada segmento para otimizar a personalização. Por exemplo, você pode selecionar aleatoriamente perfis que correspondem a critérios específicos.<br /> Consulte a documentação <a href="../../automating/using/segmentation.md"></a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrações: Serviço principal <strong>do Assets</strong><br /> </td> 
   <td> Agora você pode usar recursos compartilhados por meio do Serviço <strong>principal</strong> do Assets em seu conteúdo de email e página de aterrissagem. Você pode gerenciar seus recursos compartilhados diretamente da Adobe Marketing Cloud.<br /> Consulte a documentação <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md"></a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrações: <strong>Adobe Target</strong><br /> </td> 
   <td> Agora você pode inserir imagens que são computadas dinamicamente pelo <strong>Adobe Target</strong> nos emails do Adobe Campaign. Isso permite oferecer várias versões do mesmo email personalizando o conteúdo de acordo com os critérios definidos nos segmentos do Adobe Target.<br /> Consulte a documentação <a href="../../integrating/using/about-campaign-target-integration.md"></a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Editor de conteúdo digital: Seletor de <strong>bloco</strong><br /> </td> 
   <td> Quando um bloco é selecionado no editor de conteúdo HTML, uma navegação estrutural é exibida na parte inferior da zona de edição. Isso permite que você navegue e selecione elementos diferentes facilmente.<br /> Consulte a documentação <a href="../../channels/using/designing-a-landing-page.md#managing-landing-page-structure-and-style"></a>detalhada.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Versão 15.3 - março de 2015 {#release-15-3---march-2015}

### Novos recursos {#new-capabilities-15}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Relatórios<br /> </td> 
   <td> Os relatórios agora podem ser acessados diretamente de um programa ou campanha. O relatório <strong>de resumo</strong> da entrega foi adicionado no nível do programa.<br /> Consulte a documentação <a href="../../reporting/using/delivery-summary.md"></a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Atualizar dados<br /> </td> 
   <td> Nos fluxos de trabalho, a atividade de dados <strong></strong> Atualizar disponível tem uma nova opção, que permite vincular automaticamente campos de dados de entrada aos campos de um esquema de aplicativo. Isso ajuda a facilitar o processo de seleção para atualizar os campos.<br /> Consulte a documentação <a href="../../automating/using/update-data.md"></a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega por email<br /> </td> 
   <td> Em fluxos de trabalho, as opções avançadas da atividade de entrega <strong>de</strong> email agora podem ser acessadas por meio de um botão específico na barra de ações. Este botão só estará disponível se uma atividade de entrega <strong>por</strong> email estiver selecionada. O principal benefício é que ele permite que você adicione uma transição de saída à atividade e edite o nome da atividade como ela é exibida no fluxo de trabalho.<br /> Consulte a documentação <a href="../../automating/using/email-delivery.md"></a>detalhada.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correções {#patches-14}

#### Geral {#general-10}

* Correção de um erro que impedia a exibição do destinatário ao criar uma entrega.
* Correção de um erro que impedia o uso de um público-alvo baseado em uma condição "Destinatários que abriram".
* Correção de um erro que impedia a exclusão de um perfil vazio.
* Correção de um erro que ocorria ao visualizar uma entrega.
* Correção de um erro que impedia a duplicação de uma atividade de marketing.
* Correção de um erro que ocorria ao excluir uma campanha.

