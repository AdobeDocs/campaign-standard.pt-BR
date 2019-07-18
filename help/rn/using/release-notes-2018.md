---
title: Notas de versão 2018
seo-title: Notas de versão 2018
description: Notas de versão 2018
seo-description: Esta página lista todas as versões 2018 do Adobe Campaign Standard.
page-status-flag: nunca ativado
uuid: 99 f 92 a 54-4 b 3 d -48 b 9-b 08 d-e 98 b 24 e 75 f 62
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: versões padrão da campanha
discoiquuid: e 54 f 8305-7 e 32-4193-8 e 5 a-b 5 d 87 b 03038 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Release Notes 2018{#release-notes}

Procurando uma versão específica do Adobe Campaign Standard 2018?

Cada versão traz novos recursos e correções. Clique em uma versão para exibir seu conteúdo.

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a newer release, consult this [page](../../rn/using/release-notes.md).

## Release 18.9 - September 2018 {#release-18-9---september-2018}

### What's new? {#what-s-new-}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> In-App messaging (beta)<br /> </td> 
   <td> As mensagens no aplicativo permitem envolver usuários do aplicativo móvel com mais eficácia fornecendo interação contextual e permitindo atingir usuários que podem ter optado por não participar das notificações por push. Use mensagens no aplicativo em conjunto com notificações por push para criar uma experiência altamente personalizada e relevante. Isso leva a uma melhor conversão e retenção de usuários do aplicativo.<br /> Para obter mais informações, consulte a <a href="../../channels/using/about-in-app-messaging.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Launch integration for mobile apps (beta)<br /> </td> 
   <td> A integração do Adobe Launch com o Adobe Campaign agora simplifica e automatiza o processo de ativação da Propriedade de Aplicativo Móvel no Campaign usando o Mobile SDK V 5.<br /> Para obter mais informações, consulte a <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements}

* O Adobe Campaign Standard agora oferece suporte à versão 4 da API do Amazon S 3.

### Other changes {#other-changes}

* Nos logs broad, agora há uma distinção entre o número máximo de conexões e o número máximo de mensagens por hora. Quando os limites são alcançados, é possível saber por que o resultado é limitado. Anteriormente, a mesma mensagem (' quota cumprida ') era aplicada a ambos os casos.
* Ao configurar um aplicativo móvel no Campaign, o usuário agora pode saber se o certificado do iOS e a chave do servidor Android foram carregados com êxito e sua data de expiração.

   For more on this, refer to the detailed documentation on how to configure a mobile application using [SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) and [SDK V5](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

* Direcione usuários em um aplicativo móvel específico selecionando um aplicativo para dispositivos móveis ao definir as propriedades da campanha. Esse recurso é para os canais de mensagens por push e no aplicativo.

   For more information, refer to the [detailed documentation](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification).

* Ao selecionar um bloco de conteúdo usando a interface do Creative Designer, todos os blocos de conteúdo da lista agora são carregados e exibidos. (CAMP -27311)

   For more on this, refer to the [detailed documentation](../../designing/using/adding-a-content-block.md).

### Patches {#patches}

* Correção de um problema que mostrava uma discrepância nas contagens de log entre o painel de e-mail e o relatório de resumo de e-mail para e-mails transacionais. (CAMP -28237
* Correção de um problema nos fluxos de trabalho que podia exibir uma mensagem de erro ao importar um arquivo por meio de uma atividade de transferência de Arquivo. (CAMP -27435)
* Correção de um problema com páginas de aterrissagem contendo mais de 25 serviços, que fazia com que os serviços ficassem aleatoriamente desmarcados no formulário. (CAMP -26572)
* Correção de um problema em fluxos de trabalho que impossibilitava a configuração de contas externas com um URL SFTP ao usar a atividade de transferência de arquivo. (CAMP -26475)
* Correção de um problema que impedia a atualização do relatório de resumo dos serviços. (CAMP -26301)
* Correção de um problema nos fluxos de trabalho ao usar uma atividade de Enriquecimento, que impedia que um campo personalizado exibisse a data correta. (CAMP -26242)
* Correção de um problema que impedia a atualização das datas de assinatura do serviço quando importadas por meio de uma importação de arquivo.
* Correção de um erro com a atividade do arquivo de carregamento que impedia os fluxos de trabalho de importar arquivos (CAMP -27068).
* Correção de um problema que exibia o número errado de assinaturas nos relatórios de resumo do serviço (CAMP -25587).
* Correção de um problema de discrepância de dados entre os relatórios do Adobe Analytics e do Adobe Campaign. (CAMP -25393)
* Correção de um problema que poderia impedir que um usuário restrito de acesso fizesse logon. (CAMP -27381)
* Correção de um problema que podia impedir a exibição da lista de conteúdos do Adobe Experience Manager ao editar um email usando o Creative Designer. (CAMP -27181)
* Correção de um problema que podia impedir que o Creative Designer fosse aberto, causando um erro. (CAMP -27304)
* Correção de um problema que impedia que o arrastar e soltar funcionasse corretamente no Creative Designer ao usar o Internet Explorer 11.
* Correção de um problema que fazia com que imagens carregadas de uma câmera e tiradas no modo Retrato fossem exibidas em uma posição girada indesejada.
* Correção de um problema que exibia informações de seleção indesejadas ao usar a interface do editor de consulta no Creative Designer.
* Correção de um problema que impossibilitava a duplicação correta de um elemento ao usar a interface do editor de consulta no Creative Designer.
* Correção de um problema que continuava a entregar mensagens SMS para destinatários com lista negra mesmo que eles tivessem sido cancelados por uma resposta automática. (CAMP -27128)
* Fixed an issue that prevented displaying the errors that caused the **Database Cleanup** workflow to fail. (CAMP -26876)
* Correção de um problema que poderia impedir a exclusão de campos personalizados em uma definição de notificação por push. (CAMP -25588)

## Release 18.7 - July 2018 {#release-18-7---july-2018}

### What's new? {#what-s-new--1}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> High priority flag for Android push notifications<br /> </td> 
   <td> Sinalizador de alta prioridade para Android - ative a entrega de uma notificação por push com alta prioridade para aplicativos Android que faz com que o dispositivo flutuante desperte e execute um processamento limitado. Observe que a prioridade padrão é Normal, o que pode atrasar a entrega de mensagens para salvar a bateria. <br /> Para obter mais informações, consulte a <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Typology filter for mobile app subscribers<br /> </td> 
   <td> Assinaturas de suporte no filtro de tipologia - ao especificar os critérios de filtragem para uma regra de tipologia, as assinaturas do aplicativo podem ser selecionadas como filtragem e definição de metas, fornecendo a capacidade de filtrar atributos para usuários com ou sem um perfil. <br /> Para obter mais informações, consulte a <a href="../../administration/using/about-typology-rules.md#typology-rules">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Automated content import from a URL during message preparation<br /> </td> 
   <td> Agora é possível importar conteúdo de email de um URL durante a fase de preparação. Para entregas de email recorrentes, o conteúdo HTML mais recente é recuperado sempre que a mensagem é preparada, assegurando que o conteúdo seja sempre atualizado no momento em que o e-mail é enviado. Esse recurso também permite que você crie uma entrega programada com conteúdo de um URL mesmo que o conteúdo ainda não esteja pronto.<br /> Para obter mais informações, consulte a <a href="../../designing/using/importing-content-from-a-url.md#retrieving-content-from-a-url-automatically-at-preparation-time">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaign release notification message<br /> </td> 
   <td> Uma mensagem pop-up agora aparece quando um usuário faz logon após a instância ter sido atualizada para uma nova versão. A mensagem indica o número da versão e inclui um link para as notas de versão. You can choose to hide the message until the next release. <br /> </td> 
  </tr> 
  <tr> 
   <td> User management<br /> </td> 
   <td> O recurso de unidade geográfica agora está indisponível para novas instâncias do Campaign Standard, bem como instâncias existentes sem unidades geográficas criadas, a partir de 18.7.<br /> Para obter mais informações, consulte esta <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">página</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements-1}

* The Adobe Campaign and Adobe Target integration now allows you to leverage Target’s [Permissions](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html) feature. Ao incluir uma imagem dinâmica do Adobe Target em um email, agora você pode especificar uma propriedade do Target (código em_ propriedade).
* Os recursos personalizados que têm um link tecnológico para o recurso de perfis são considerados pelas solicitações de acesso e exclusão de Privacidade do RGPD. Para links simples de cardinalidade e links de coleção de N cardinalidade, é necessário selecionar "Excluir/Duplicar o registro de destino implica excluir/duplicar os registros referenciados pelo link" no recurso personalizado. Para links simples de 0 ou 1 cardinality, selecione "Excluir/Duplicar o registro implica excluir/duplicar o registro de destino referenciado pelo link".

### Other changes {#other-changes-1}

* O tempo limite do compartilhamento de relatório foi aumentado de um a quatro minutos para evitar o erro de tempo limite.
* Ao editar o conteúdo de um email, o novo Creative Designer é aberto por padrão. Se desejar, você ainda poderá voltar para o editor de conteúdo padrão a qualquer momento depois de salvar suas alterações. For more on this, refer to the [detailed documentation](../../designing/using/about-email-content-design.md).
* No Creative Designer, um novo componente de conteúdo agora pode ser adicionado em um email: o carrossel. For more on this, refer to the [detailed documentation](../../designing/using/defining-the-email-structure.md#about-content-components).
* In a transactional message hot click report, when you click the **Change profile** button, now only the test profiles linked to the event that you defined for your transactional message are listed.

### Patches {#patches-1}

* Correção de um problema com o filtro de consulta do byemail, que não retornava quaisquer resultados. (CAMP -23420)
* Correção de um problema que permitia que um usuário padrão acessasse determinados recursos ou telas restritas a administradores (/rest/head/* endpoints, telas transacionais de mensagem, perfis e públicos-alvo importassem telas).
* Correção de um problema que impedia que Privacidade do RGPD excluísse solicitações de processamento de recursos personalizados se seu nome começasse por um número.
* Corrigido um erro que impedia que a atividade Salvar público-alvo compartilhava assinantes do aplicativo na Adobe Experience Cloud.
* Correção de um problema com a atividade de Transferência de arquivos que ocorria quando o nome do arquivo continha espaços em branco. (CAMP -25936)
* Correção de um problema que ocorria ao usar o botão reconectar depois que uma sessão expirava. (CAMP -25560)
* Correção de um problema que resultava em exclusões ao enviar entregas com otimização de fuso horário associada a regras de fadiga. (CAMP -25425)
* Correção de um problema ao usar o recurso GI RGD, que podia impedir a exclusão de dados com um link de tipo 0-1.
* Solucionado o problema que gerava uma mensagem de erro ao cancelar a edição de uma regra de tipologia de fadiga.
* Correção de um problema que ocorria ao visualizar um conteúdo de entrega após a edição.
* Correção de um problema que ocorria ao processar arquivos zip CSV ao usar a opção Descompactação.
* Correção de um problema no Creative Designer que resultava em fontes e formatação de cores indesejadas ao alterar algum texto com estilo incriado para um link ou ao editar esse link. (CAMP -26001)
* Correção de um problema que impedia que o relatório de cliques em vídeo exibisse as porcentagens de cada condição em entregas contendo conteúdo dinâmico. Anteriormente, somente os cliques na variante padrão eram exibidos.

## Release 18.6 - June 2018 {#release-18-6---june-2018}

### Improvements {#improvements-2}

* The **[!UICONTROL History]** API has been added to Adobe.IO. Ele permite acessar as informações relacionadas ao histórico de marketing de um perfil: número de pontos de contato, envio de entregas, URL de página espelhada etc. For more on this, refer to the [dedicated use case](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#how-to-retrieve-the-mirror-page-for-a-delivery-sent-to-a-profile) .
* The **[!UICONTROL Database cleanup]** technical workflow has been optimized in order to ensure better performance for database backup.
* O Creative Designer para email agora também está disponível em francês e alemão.

### Other changes {#other-changes-2}

* A **[!UICONTROL Compute stats]** button has been added in the **[!UICONTROL Deployment]** window of sent deliveries. Ela permite recuperar os kpis mais recentes, por exemplo, se os resultados do envio demorarem muito para atualizar ou não foram considerados. For more on this, refer to this [section](../../sending/using/confirming-the-send.md).
* In the **Update for deliverability** out-of-the-box technical workflow, functional administrators can now define the number of consecutive errors to ignore in the **Update rules** javascript activity. Por padrão, o valor do campo é definido como 0, o que significa que todos os erros serão ignorados.
* O SQL gerado durante o gerenciamento de condições de restrição de acesso à unidade foi otimizado.
* The **[!UICONTROL Update]** activity now allows you to add, update or delete data related to subscriptions (nms:appSubscriptionRcp table).
* The **[!UICONTROL Update delivery execution]** technical workflow has been divided into two workflows in order to optimize performance: - **[!UICONTROL Update delivery execution]**: updates the delivery's tracking. Ele é iniciado a cada 10 minutos por padrão. **[!UICONTROL Update delivery indicators]**: atualiza o KPI da entrega, ele é iniciado a cada hora por padrão. For more on technical workflows, refer to this [section](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* When a delivery is sending messages, the status in the **[!UICONTROL Deployment]** section can now have two values: **[!UICONTROL Sending]**: the messages are being sent. **[!UICONTROL Sending (retry)]**: uma passagem de nova tentativa está em andamento.
* Users with the **[!UICONTROL Delivery preparation]** role are now able to send proofs. (CAMP -24313)
* **A opção Habilitar TLS acima de SMPP** foi adicionada ao roteamento **de SMS via conta** externa SMPP. For more on this refer to this [section](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

### Patches {#patches-2}

* Correção de um problema que impedia o envio de emails ao incluir uma imagem dinâmica do Adobe Target (CAMP -24848).
* Fixed an issue with the **[!UICONTROL Privacy Access/Delete Request]** technical workflows, which did not complete if any of the requests failed.
* Correção de um problema que impedia o serviço Privacy Core de receber atualizações de status de solicitação do Campaign.
* Correção de um problema que podia impedir que o fluxo de trabalho técnico **[!UICONTROL Import shared audience]** funcionasse corretamente (CAMP-25465).
* Correção de um problema que impedia que solicitações de privacidade da Campanha fossem marcadas como concluídas no Serviço de privacidade principal.
* Correção de um problema que podia impedir certos usuários de fazerem logon no Campaign Standard por meio da autenticação IMS quando a ID da Adobe era longa demais. (CAMP -24095)
* Correção de um problema no Creative Designer que ocorria ao remover módulos de conteúdo. (CAMP -25242)
* Correção de um problema ao usar regras de fadiga de notificações por push para assinantes sem perfil no banco de dados. (CAMP -25344)
* Correção de um problema que exibia uma mensagem de erro ao acessar logs de exclusão de envio. (CAMP -24724)
* Correção de um problema que impedia a preparação de provas em instâncias com registros de envio estendidos.
* Fixed two issues that could occur when publishing custom resources with the **[!UICONTROL Sending log]** extension activated.
* Correção de um problema que fazia com que a duração da entrega não fosse levada em conta em entregas recorrentes.
* Fixed an issue that could occur when sorting data in the **[!UICONTROL Client data]** menu, for custom resources with more than 100K records. (CAMP -24308)
* Correção de um problema com dimensões de perfil personalizadas que não eram consideradas ao usar a função de pesquisa nos relatórios Dinâmicos.
* Correção de um problema com a exibição de dados internacionais para Níveis de conta nos relatórios Dinâmicos.
* Agora é possível criar um serviço sem uma mensagem de confirmação de assinatura ou cancelar a assinatura.

## Release 18.5 - May 2018 {#release-18-5---may-2018}

### What's new? {#what-s-new--2}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> GDPR: Core Service Integration<br /> </td> 
   <td> A Integração de serviço principal de privacidade permite automatizar as solicitações do RGPD em um contexto de várias soluções por meio de uma chamada única de API JSON. <br /> As solicitações de RGPD enviadas do Serviço principal de privacidade para todas as soluções da Experience Cloud agora são automaticamente controladas por Campanha. <br /> Para obter mais informações, consulte a <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push improvements - detailed delivery feedback<br /> </td> 
   <td> O Adobe Campaign agora oferece a capacidade de receber feedback detalhado (enviar registros de exclusão e logs de exclusão) em mensagens de push dos provedores (APNS/GCM) via MCPNS.<br /> Para obter mais informações, consulte a <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery logs extension<br /> </td> 
   <td> A extensão de logs de entrega permite estender o envio de registros com dados de perfil e código de segmento provenientes dos fluxos de trabalho. Estas informações podem ser usadas em Relatórios dinâmicos e permite manter um instantâneo de algumas informações no tempo de envio de uma entrega.<br /> Há mais cinco casos de uso:<br /> 
    <ul> 
     <li> Exportar logs broadestendidos com dados "congelados": Como comerciante, exporte todos os perfis em que o código do segmento é igual a "A" (vindo do mecanismo de fluxo de trabalho). </li> 
     <li> Segmentation on "frozen" data: As a marketer, I would like to <strong>retarget</strong> all profiles who have won 1000 loyalty points since the last sending or where segment code was equal to "A". </li> 
    </ul> For more information, refer to the <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamic reporting with Custom profile data<br /> </td> 
   <td> Esse recurso permite criar e gerenciar relatórios com base em dados de perfil personalizados criados durante a extensão do recurso de perfil. Você pode detalhar os relatórios por atributo de perfil, como programa de fidelidade, canal preferencial, etc.<br /> Para obter mais informações, consulte a <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements-3}

* A memória geral e o uso da CPU do aplicativo foram aprimorados

### Other changes {#other-changes-3}

* A atividade de fluxo de trabalho Leitura do público-alvo agora pode ler públicos-alvo da Experience Cloud. Anteriormente, essa atividade só podia ler os públicos-alvo de Consulta e Lista. Refer to the [detailed documentation](../../automating/using/read-audience.md). (CAMP -23623)
* O identificador da fonte de dados compartilhado padrão agora está no modo somente leitura e não pode mais ser alterado. Alterar esse identificador pode levar a alguns problemas ao compartilhar públicos-alvo com a Experience Cloud.
* Importar públicos-alvo do Audience Manager agora funciona com arquivos divididos. Anteriormente, somente o último arquivo do segmento era importado pelo fluxo de trabalho técnico importsharedaudience.
* As contas externas do AWS S 3 agora são compatíveis com regiões e o mecanismo de autenticação da versão 4. Refer to the [detailed documentation](../../administration/using/external-accounts.md).
* A janela de seleção Ativo agora deve carregar mais rapidamente e permitir que um ativo saia da janela sem qualquer problema.
* As propriedades e a estrutura de fluxos de trabalho técnicos agora podem ser modificadas por usuários com direitos de administração e pertencendo às unidades organizacionais e geográficas "Todas".
* Foram feitos aprimoramentos na interface de atividade de Segmentação ao criar novos segmentos: A guia Limitação agora aparece diretamente após adicionar uma limitação. Os nomes dos novos segmentos agora são incrementados («Segmento 1», «Segmento 2» etc.).
* Um campo "nextprocessingdate" é adicionado ao recurso Fluxo de trabalho. Este campo é visível somente por chamadas REST API, permitindo visualizar fluxos de trabalho próximas datas de processamento.
* O campo "sourceid" agora é exposto nos recursos de registros de rastreamento (nms: Trackinglog).
* Os valores «Total aberto» e «Total de cliques» agora podem ser exportados em um arquivo simples por meio de um fluxo de trabalho. (CAMP -24186)
* " Inglês - dinamarquês "agora está disponível na lista de idiomas preferidos em perfis. (CAMP -23728)
* Ao usar uma atividade de Segmentação com um link de Dados adicionais (targetdata), uma mensagem agora informa que os dados não estão disponíveis fora do fluxo de trabalho. Esta mensagem é exibida ao clicar no botão Contar ou Visualizar da atividade de Segmentação. (CAMP -23651)
* Foram feitos aprimoramentos para otimizar o espaço em disco usado pelos fluxos de trabalho: (CAMP -21979): Os arquivos processados pela atividade «Load file» agora são excluídos por padrão. Uma opção permite que você as mantenha para necessidades específicas. Quando um fluxo de trabalho é excluído, sua pasta dedicada é suprimida automaticamente no diretório do servidor.

### Patches {#patches-3}

* Correção de um problema em que alguns eventos brutos de relatórios não possuíam eventos de rastreamento associados porque o campo eventdate não preenchia adequadamente.
* Correção de um problema que impedia que campos personalizados fossem exibidos na janela de visualização de uma entrega de notificação por push.
* Correção de um problema que impedia o texto de vincular texto ao corpo da mensagem de uma notificação por push na janela de visualização.
* Correção de um problema ao enviar uma entrega de reformulação de um fluxo de trabalho quando o destino principal estava vazio.
* Correção de um problema que impedia o acesso de um mapeamento de destino se ele estivesse vinculado a um esquema não existente.
* Correção de um problema que ocorria ao importar um arquivo zip por meio de uma atividade de carregamento de Arquivo. (CAMP -24309)
* Correção de um problema que resultava em um erro postgresql ao enviar uma entrega recorrente. (CAMP -23613)
* Correção de um problema que exibia uma mensagem de erro ao enviar uma solicitação de REST API com um atributo JSON vazio. (CAMP -23506)
* Correção de um problema em perfis que configuravam como campos os caracteres após o caractere "ß". (CAMP -23136)
* Correção de um problema ao enviar entregas usadas com a condição de qualificação do bloco de conteúdo dinâmico ou de personalização ao usar atributos de um esquema vinculado do perfil. (CAMP -22751)
* Correção de um problema que impedia a exclusão de serviços. (CAMP -22050)
* Correção de um problema que impossibilitava a alteração dos valores de País ou Estado em um perfil de Teste. (CAMP -20426)
* Correção de um problema que podia impedir o carregamento do Creative Designer. (CAMP -24573)
* Correção de um problema que removia os caracteres adicionados após os campos de personalização no assunto do email. (CAMP -24113)

## Release 18.4 - April 2018 {#release-18-4---april-2018}

### Patches {#patches-4}

#### Platform {#platform}

* Corrigido um erro que poderia impedir o processamento correto de acesso ou exclusão de solicitações do RGPD. Esse comportamento foi observado em casos raros em que os dados extraídos estavam contendo um dos seguintes caracteres: &amp; &lt; &gt; ".

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail}

* Correção de um problema que fazia com que kpis fossem substituídos por valores incorretos se a sincronização de glossário demorasse mais de uma hora.

#### Workflows {#workflows}

* Gerenciamento de memória aprimorado e desempenho otimizado nos fluxos de trabalho.

#### Reporting {#reporting}

* O fluxo de trabalho de compartilhamento de KPI recupera os valores de entrega dos últimos 2 meses em vez dos últimos 6 meses. Correção de um problema com a conta externa de compartilhamento de KPI mostrando datas truncadas.
* Fixed an issue which could lead to certain messages not being taken into account in **Sent**, **Delivered** and **Bounce** metrics.
* Fixed an error which occurred when the chosen time range in the **Delivery Summary Report** was too long.

#### Custom resources {#custom-resources}

* Correção de um erro que causava a falha da preparação de recursos personalizados.

## Release 18.3 - March 2018 {#release-18-3---march-2018}

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
   <td> EU General Data Protection Regulation (GDPR)<br /> </td> 
   <td> O RGPD é a nova legislação de privacidade da União Europeia (EU) que harmoniza e moderniza as exigências da proteção de dados em vigor em May 5 de maio de 2018. O RGPD se aplica aos clientes do Adobe Campaign que detêm dados para os Dados de dados residentes na UE.<br /> Além dos recursos de privacidade já disponíveis no Adobe Campaign (incluindo gerenciamento de consentimento, configurações de retenção de dados e funções de usuário), estamos aproveitando essa oportunidade na nossa função como Processador de dados para incluir recursos adicionais, para ajudar a facilitar sua disponibilidade como o Controlador de dados para determinadas solicitações do RGPD:<br /> 
    <ul> 
     <li> Direita para acesso: permite que o Assunto de dados receba uma cópia dos dados pessoais capturados pelos Controladores de dados, inclusive os dados armazenados no Adobe Campaign. </li> 
     <li> Direita para Excluir: autorizam o Assunto de dados a capturar os dados pessoais capturados pelos Controladores de dados, possivelmente incluindo dados armazenados no Adobe Campaign. </li> 
    </ul> For more information, refer to the <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer for Email (Beta)<br /> </td> 
   <td> O novo Creative Designer da Adobe Campaign oferece uma experiência de criação totalmente integrada no Campaign, permitindo a criação visual rápida e sem recursos de emails personalizados e personalizados, sem a necessidade de script de uma única linha de código. Por meio da interface de arrastar e soltar, o Creative Designer ajuda a dimensionar a criação de e-mails, se os usuários começarem de uma slate em branco ou aproveitar o conteúdo existente Fragmentos ou modelos. <br /> Os recursos principais incluem:<br /> 
    <ul> 
     <li> Crie e crie emails totalmente personalizados e totalmente personalizados por meio de uma interface de arrastar e soltar, aumentada por integrações nativas da Creative Cloud </li> 
     <li> Criar e salvar um modelo de conteúdo de email e aproveitar modelos salvos para ajudar a dimensionar a criação de e-mails </li> 
     <li> Criar e salvar fragmentos de conteúdo (como cabeçalho, rodapé, artigo etc.) para simplificar a criação de conteúdo e garantir a consistência da marca </li> 
     <li> Alternar entre criar na interface de arrastar e soltar e editar diretamente HTML de um e-mail com o clique de um botão </li> 
    </ul> O Creative Designer para email está disponível somente em inglês.<br /> Para obter mais informações, consulte a documentação <a href="../../designing/using/about-email-content-design.md#about-the-email-designer">detalhada</a> e assista a este <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">vídeo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Multilingual Push Deliveries<br /> </td> 
   <td> A mesma interface multilíngue simples, que já existe nos canais Email e SMS, foi adicionada ao canal de push que ajuda a envolver clientes, independentemente do idioma preferido.<br /> Esse recurso oferece uma solução escalonável e automática para clientes que gerenciam campanhas de Push abrangendo várias regiões e desejam direcionar os usuários no idioma preferido. Permite carregar todas as variantes língues através de uma planilha modelo a uma única entrega de push, com um único clique. O Adobe Campaign realiza uma segmentação automática com base na preferência de idiomas dos usuários, ajudando a reduzir os despedimentos, simplificando os fluxos de trabalho e os relatórios.<br /> Para obter mais informações, consulte a <a href="../../channels/using/creating-a-multilingual-push-notification.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Use of Custom Resources in Transactional Messaging<br /> </td> 
   <td> Além dos campos predefinidos, as mensagens transacionais agora permitem usar recursos personalizados para aprimorar o conteúdo de suas mensagens.<br /> Por exemplo:<br /> 
    <ul> 
     <li> Utilize campos personalizados como critérios de reconciliação para corresponder a uma mensagem transacional a um perfil </li> 
     <li> Aproveite perfis, serviços e dados vinculados completos para personalizar ainda mais mensagens transacionais </li> 
    </ul> For more information, refer to the <a href="../../administration/using/configuring-transactional-messaging.md">detailed documentation</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-5}

#### Platform {#platform-1}

* Correção de um problema que impedia a exportação de mais de 5000 registros de uma lista.
* Correção de um problema ao exportar dados para arquivos nomeados com campos de personalização.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-1}

* Correção de um problema que fazia com que o SMS de várias partes ficassem truncados, pois o tamanho das partes era calculado em caracteres em vez de bytes.
* Added an option which allows the **[!UICONTROL Delivered]** or **[!UICONTROL Bounces + Errors]** KPIs to be updated in real time after sending your delivery. Eles são recalculados diretamente do SR (Relatório de status) recebido do provedor.
* Correção de um problema com o widget de calendário no agendador de entrega.
* Correção de um problema de exibição ao abrir uma meta pela segunda vez em uma entrega enviada.
* Correção de um problema que resultava em uma mensagem de erro solicitando uma data de início ao criar um modelo de e-mail com uma data de envio atrasada.
* Correção de um problema que causava problemas de renderização de imagem ao editar o conteúdo de uma entrega.
* Correção de um problema com testes ao duplicar uma campanha.
* Correção de um problema que resultava em uma mensagem de erro ao acessar um modelo de campanha por meio da barra de navegação, após adicionar uma entrega ao fluxo de trabalho.
* Correção de um problema que podia impedir que o vencedor de um e-mail de teste A/B fosse selecionado automaticamente, fazendo com que o e-mail não fosse enviado. This behavior could occur if the delivery was in **[!UICONTROL retryInProgress]** state.
* Correção de um problema que resultava em uma mensagem de erro exibida ao reabrir os parâmetros de um email de teste A/B.

#### Audiences &amp; queries {#audiences-e-queries}

* Correção de um problema que impossibilitava o acesso a dados e a configuração de consultas para os destinatários replicados do Adobe Campaign Classic para o Standard.
* Fixed an issue that occurred when using a filter type field in the query editor, after using the **Count** or **Preview** buttons.

#### Workflows {#workflows-1}

* The **Billing** workflow has been optimized to improve the delivery preparation delay.
* Correção de um problema que impedia a exibição dos dados de população em uma transição de saída ao usar uma atividade de entrega recorrente.
* Fixed an issue that prevented reject records from being displayed in a transition after an **Update data** activity.
* Fixed an issue which could cause the **deliverabilityUpdate** technical workflow to fail.

#### Integrations {#integrations}

* Correção de um problema que impedia que caracteres internacionais fossem enviados corretamente para o Adobe Analytics.
* Os ativos agora devem carregar mais rapidamente ao tentar inserir uma imagem da biblioteca de ativos da Experience Cloud em uma mensagem.
* Solucionado o problema que impedia que a janela de seleção de ativos fosse fechada em alguns casos.
* De um detalhe de fonte de dados, agora você pode acessar diretamente seu fluxo de trabalho relacionado para verificar o estado do fluxo de trabalho.
* Agora é possível atualizar o esquema Acionadores diretamente ao definir ou editar um evento de disparo. Com essa alteração, não é mais necessário cancelar a publicação do acionador e criar outra.

#### Transactional messages {#transactional-messages}

* Correção de um erro com modelo de mensagem transacional quando o recurso de entrega era estendido.
* Agora é possível excluir mensagens transacionais.

## Release 18.2 - February 2018 {#release-18-2---february-2018}

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
   <td> Subscription - subscribe or unsubscribe a list of profiles to multiple services<br /> </td> 
   <td> The <strong>Subscription Services</strong> workflow activity now allows you to subscribe or unsubscribe a list of profiles to multiple services. No seu fluxo de trabalho, importe um arquivo contendo os perfis e, para cada perfil, o tipo de operação e o serviço. The <strong>Subscription Services</strong> activity will be able to use this information and handle dynamically all your profiles subscriptions and unsubscriptions at once.<br /> Para obter mais informações, consulte a <a href="../../automating/using/subscription-services.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Enrichment activity - enrich data based on previous transitions<br /> </td> 
   <td> The new <span class="uicontrol">Enrichment</span> workflow activity allows you to leverage the inbound transitions and complete the output transition with additional data. Se você direcionar perfis, a atividade de enriquecimento permite aprimorar as informações de perfil com dados adicionais que não são armazenados no banco de dados (proveniente de um arquivo importado, por exemplo).<br /> Para obter mais informações, consulte a <a href="../../automating/using/enrichment.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-6}

#### Platform {#platform-2}

* A barra superior da interface do Adobe Campaign foi atualizada com o novo menu da Experience Cloud.
* Fixed an issue which prevented the link to **[!UICONTROL Offers]** from being displayed in the solution dropdown list.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-2}

* A fase de preparação da entrega foi aprimorada para melhorar o desempenho.
* Correção de vários problemas que fazia com que os logs de rastreamento ficassem corrompidos em algumas situações niche.
* Correção de um problema de atualização de data de contato que ocorria quando a data de contato era alterada entre a preparação de entrega e a confirmação. Agora, quando você altera a data de contato após a preparação, é necessário preparar a entrega novamente antes de poder confirmar o envio. See the [detailed documentation](../../sending/using/preparing-the-send.md).

#### Push notifications {#push-notifications}

* Correção de um erro que impedia que alguns campos de personalização funcionassem em notificações por push do iOS.
* Correção de um erro que exibia o clique e as taxas de abra como 0% no painel de notificação por push.

#### Reports {#reports}

* Corrigido um erro que exibia a lista de relatórios como vazia em alguns navegadores.
* Fixed an error that occurred in the **[!UICONTROL Report sharing]** technical workflow just before its expiration limit was reached.

#### Workflows {#workflows-2}

* Correção de um problema que impedia que atividades fossem acessíveis depois de arrastá-las e soltá-las.
* Fixed an issue that could cause the order of output transitions of a **[!UICONTROL Segmentation]** activity to change in some situations.
* Corrigido um erro que ocorria ao ler um público contendo um campo de tipo de enumeração e que era salvo anteriormente de um fluxo de trabalho
* Fixed an issue causing the **[!UICONTROL Request confirmation before sending messages]** option to remain checked even after unchecking it when defining the scheduling properties of a delivery created in a workflow.
* Automatic removal of duplicate rows (DISTINCT clause) can now be disabled in **[!UICONTROL Query]** activities, via a new option located in the **[!UICONTROL Additional data]** tab. Desativar essa opção é recomendado ao definir muitos (mais de 100) elementos adicionais, por motivos de desempenho.

#### Integrations {#integrations-1}

* Some improvements were made to the **[!UICONTROL Data sources]** configuration screen.

### Known issues {#known-issues}

Recomendamos que você não use o Internet Explorer versão 11 devido a possíveis problemas de exibição.

Alguns problemas podem ocorrer ao usar links de ajuda contextual da interface da campanha. Eles serão corrigidos em 18.3.

## Release 18.1 - January 2018 {#release-18-1---january-2018}

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
   <td> Reporting for Fatigue Management<br /> </td> 
   <td> O relatório para gerenciamento de fadiga é um relatório dedicado e configurável que exibe o impacto das regras de fadiga em todos os canais de email, push, SMS e mala direta dentro de um intervalo de datas especificado antes de enviar. Com o insight adicionado da capacidade de ver rapidamente todas as campanhas em conflito em uma exibição única, os profissionais de marketing podem planejar campanhas de marketing de acordo com o conjunto das regras de fadiga de forma mais eficaz e priorizar as comunicações.<br /> Para obter mais informações, consulte a <a href="../../administration/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Report sharing<br /> </td> 
   <td> O Compartilhamento de relatórios permite que você compartilhe seus relatórios com usuários do Adobe Campaign como um anexo de email, incluindo uma base recorrente automatizada. Os usuários que recebem relatórios recorrentes têm a capacidade de cancelar a inscrição dessas comunicações por meio de um link dedicado em cada email.<br /> Para obter mais informações, consulte a <a href="../../reporting/using/reporting-interface.md#share-tab">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push New capabilities<br /> </td> 
   <td> Visualização de mensagens de push - Visualize notificações por push em dispositivos iOS e Android a partir do editor de conteúdo de notificação por push para ver exatamente o que os destinatários verão antes de testar ou executar a entrega.<br /> Para obter mais informações, consulte a <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">documentação detalhada</a>.<br /> Conteúdo disponível - quando os aplicativos não são abertos por longos períodos de tempo, seus dados podem ficar desatualizados. Isso resulta nos dados terem que ser atualizados ou substituídos no momento em que um usuário finalmente abre o aplicativo, o que pode causar atrasos no uso do aplicativo. Com a adição adicional de Conteúdo disponível, os usuários do Adobe Campaign podem acordar o aplicativo para atualizar seus dados em segundo plano ao entregar uma notificação por push, permitindo maior consistência e controle sobre a experiência do usuário no aplicativo.<br /> Conteúdo variável - com a ajuda adicional do conteúdo variável, os usuários do Adobe Campaign agora podem aproveitar as extensões de aplicativos móveis para modificar ainda mais o conteúdo ou a apresentação de notificações de mensagens de push enviadas do Adobe Campaign. For example, users can leverage Mutable Content to: <br /> 
    <ul> 
     <li> descriptografar dados que foram entregues em um formato criptografado </li> 
     <li> baixar imagens ou outros arquivos de mídia e adicioná-los como anexos a uma notificação </li> 
     <li> alterar o texto de corpo ou título de uma notificação </li> 
     <li> adicionar um identificador de encadeamento a uma notificação </li> 
    </ul> For more information on Content Available and Mutable Content, refer to the <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">detailed documentation</a>.<br /><strong>Aviso:</strong> essas atualizações em notificações por push exigem que os clientes atualizem seus aplicativos móveis. Refer to <a href="https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html">this technote</a> for more information.<br /> </td> 
  </tr> 
  <tr> 
   <td> Time-zone optimized deliveries<br /> </td> 
   <td> Agende e-mail recorrente, SMS e notificações por push para serem entregues em um dia/hora específico em cada fuso horário dos destinatários garantir que suas mensagens sejam entregues na hora certa sem a configuração de várias entregas. <br /> Para obter mais informações, consulte a <a href="../../automating/using/scheduler.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API Signal activity triggering<br /> </td> 
   <td> Agora é possível acionar uma atividade de sinal para seus fluxos de trabalho diretamente da API do Adobe Campaign Standard.<br /> Para obter mais informações, consulte a <a class="anchorLink" href="https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity" target="_blank">documentação</a> detalhada.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-7}

#### Platform {#platform-3}

* A pesquisa de perfil foi otimizada para melhorar o desempenho.
* O identificador interno dos grupos de segurança padrão agora está no modo somente leitura para usuários padrão.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-3}

* Correção de um problema de exibição que ocorria ao inserir emojis no conteúdo de suas entregas.
* Correção de um problema que permitia ao usuário acessar o envio de logs quando a entrega ainda estava na edição.
* The **[!UICONTROL Scheduler]** activity now allows you to send your deliveries depending on the recipient's time zone.
* SMS: The option **[!UICONTROL Store incoming MO]** in the database has been added to external accounts. When checked, all incoming SMS will be stored into the **inSMS** table.
* SMS: Os serviços estão anexados a um evento em vez de um modelo transacional.
* SMS: O tempo limite da conexão SMTP padrão foi reduzido para 30 segundos.

#### Push notifications {#push-notifications-1}

* Correção de um erro que impedia que as entregas de notificação por push fossem interrompidas.
* Adicionada uma opção nas opções avançadas de notificação por push para acordar o aplicativo com uma notificação por push.
* Um botão de pausa foi adicionado para o vídeo de visualização de notificação por push.
* A visualização de notificação por push agora está disponível para dispositivos diferentes como iphone, Android, tablets.

   todos os canais

#### Reports {#reports-1}

* Correção de um erro que exibia taxas acima de 100%.
* Correção de um problema que impedia os usuários de baixar relatórios em CSV.
* Added a new **[!UICONTROL Report]** item in the homepage.

#### Workflows {#workflows-3}

* Correção de um problema que resultava em uma mensagem de erro ao usar dados adicionais em uma consulta e adicionar alias que continham espaços. Os caracteres não alfanuméricos agora são substituídos por "_".
* Correção de um problema em que o cálculo do fluxo de trabalho técnico de kpis poderia ser interrompido por padrão em alguns casos.

#### Profiles and audiences {#profiles-and-audiences}

* Correção de um erro que ocorria ao adicionar vários filtros na consulta de um público-alvo.
* Correção de um problema de exibição que ocorria ao alterar a imagem de um perfil.
* Adicionada uma dica de ferramenta que exibe o número de resultado exato após contar a população de uma consulta.
* Correção de um problema que podia impedir que um usuário selecionasse um público ou fechasse a janela do seletor de público-alvo.
* A lista de funções disponíveis no editor de expressões foi atualizada. The **FormatCurrency** and **ConvertCurrency** functions have been removed.

