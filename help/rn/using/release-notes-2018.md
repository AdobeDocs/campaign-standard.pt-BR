---
solution: Campaign Standard
product: campaign
title: Notas de versão 2018
description: Essa página lista todas as versões 2018 do Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: tm+mt
source-git-commit: a51943e4da04f5d19aaecdfcf956f5c4f3d804c8
workflow-type: tm+mt
source-wordcount: '5402'
ht-degree: 10%

---


# Notas de versão 2018{#release-notes}

Você está procurando uma versão específica do Adobe Campaign Standard para 2018?

Cada versão traz novos recursos e correções. Clique em uma versão para visualização de seu conteúdo.

Visualização as últimas [atualizações de documentação](../../rn/using/documentation-updates.md) para Adobe Campaign Standard. Se estiver procurando uma versão mais recente, consulte esta [página](../../rn/using/release-notes.md).

## Versão 18.9 - Setembro de 2018 {#release-18-9---september-2018}

**Novidades**

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Mensagens no aplicativo (beta)<br /> </td> 
   <td> As mensagens no aplicativo permitem que você envolva os usuários do aplicativo móvel de modo mais eficiente, fornecendo interação contextual e permitindo que você entre em contato com usuários que possam ter opt out de notificações por push. Use as mensagens no aplicativo em conjunto com as notificações por push para criar uma experiência altamente personalizada e relevante. Isso resulta em melhor conversão e retenção dos usuários do aplicativo.<br /> Para obter mais informações, consulte a <a href="../../channels/using/about-in-app-messaging.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integração do Adobe Launch para aplicativos móveis (beta)<br /> </td> 
   <td> A integração do Adobe Launch com a Adobe Campaign agora simplifica e automatiza o processo de ativação da propriedade do aplicativo móvel na Campanha usando o Mobile SDK V5.<br /> Para obter mais informações, consulte a <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Aprimoramentos**

* A Adobe Campaign Standard agora é compatível com a versão 4 da API Amazon S3.

**Outras alterações**

* Há agora uma distinção nos broadlogs entre o número máximo de conexões e o número máximo de mensagens por hora. Quando os limites são atingidos, é possível saber o motivo da taxa de transferência ser limitada. Anteriormente, a mesma mensagem (‘cota atingida’) se aplicava a ambos os casos.
* Ao configurar um aplicativo móvel no Campaign, o usuário pode saber se o certificado do iOS e a chave do servidor do Android foram carregados com êxito e sua data de expiração.

   Para obter mais informações, consulte a documentação detalhada sobre como configurar um aplicativo móvel usando [SDK V4](https://helpx.adobe.com/br/campaign/kb/configuring-app-sdkv4.html) e [SDK V5](https://helpx.adobe.com/br/campaign/kb/configuring-app-sdk.html).

* Usuários do público alvo em um aplicativo móvel específico selecionando um aplicativo móvel ao definir as propriedades da Campanha. Este recurso é para canais de mensagens de push e no aplicativo.

   Para obter mais informações, consulte a [documentação detalhada](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification).

* Ao selecionar um bloco de conteúdo usando a interface do Creative Designer, todos os blocos de conteúdo da lista agora são carregados e exibidos. (CAMP-27311)

   Para obter mais informações, consulte a [documentação detalhada](../../designing/using/personalization.md#adding-a-content-block).

**Correções**

* Correção de um problema que mostrava uma discrepância na contagem de log entre o painel de email e o relatório de resumo de email para emails transacionais. (CAMP-28237
* Correção de um problema em workflows que podia exibir uma mensagem de erro ao importar um arquivo por meio de uma atividade de transferência de arquivo. (CAMP-27435)
* Correção de um problema com landings page que continham mais de 25 serviços, que fazia com que os serviços fossem desmarcados aleatoriamente no formulário. (CAMP-26572)
* Correção de um problema em workflows que impedia a configuração do conta externa com um URL SFTP ao usar a atividade de transferência de arquivo. (CAMP-26475)
* Correção de um problema que impedia a atualização do relatório de resumo de serviços. (CAMP-26301)
* Correção de um problema em workflows ao usar uma atividade de Enriquecimento, que impedia que um campo personalizado exibisse a data correta. (CAMP-26242)
* Correção de um problema que impedia que as datas de subscrição de serviço fossem atualizadas quando importadas por meio de uma importação de arquivo.
* Corrigido um erro com a atividade de arquivo de carregamento que impedia workflows de importar arquivos (CAMP-27068).
* Correção de um problema que exibia o número errado de subscrições nos relatórios de resumo do serviço (CAMP-25587).
* Correção de um problema de discrepância de dados entre relatórios do Adobe Analytics e do Adobe Campaign. (CAMP-25393)
* Corrigido um problema que impedia que um usuário de acesso limitado fizesse logon. (CAMP-27381)
* Correção de um problema que impedia a exibição da lista do conteúdo do Adobe Experience Manager ao editar um email usando o Creative Designer. (CAMP-27181)
* Correção de um problema que impedia a abertura do Creative Designer, causando um erro. (CAMP-27304)
* Correção de um problema que impedia que o arrastar e soltar funcionasse corretamente no Creative Designer ao usar o Internet Explorer 11.
* Correção de um problema que fazia com que as fotos carregadas de uma câmera e filmadas no modo retrato fossem exibidas em uma posição girada indesejada.
* Correção de um problema que exibia informações de seleção não claras ao usar a interface do editor de query no Creative Designer.
* Correção de um problema que impedia a duplicação correta de um elemento ao usar a interface do editor de query no Creative Designer.
* Correção de um problema que mantinha a entrega de mensagens SMS a recipient na lista de bloqueios, mesmo que eles tivessem sido cancelados por meio de uma resposta automática. (CAMP-27128)
* Correção de um problema que impedia a exibição dos erros que causavam a falha do fluxo de trabalho **Limpeza do Banco de Dados**. (CAMP-26876)
* Correção de um problema que impedia a exclusão de campos personalizados em uma definição de notificação por push. (CAMP-25588)

## Versão 18.7 - Julho de 2018 {#release-18-7---july-2018}

**Novidades**

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Sinalizador de alta prioridade para notificações por push do Android<br /> </td> 
   <td> Sinalizador de alta prioridade para Android - permite a entrega de uma notificação por push com alta prioridade para aplicativos Android, o que faz com que o dispositivo em espera acorde e execute um processamento limitado. Observe que a prioridade padrão é Normal, o que pode atrasar o delivery da mensagem para salvar a bateria. <br /> Para obter mais informações, consulte a <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Filtro de tipologia para assinantes de aplicativos móveis<br /> </td> 
   <td> Subscrições de suporte no filtro de tipologia: ao especificar os critérios de filtragem para uma regra de tipologia, as subscrições do aplicativo podem ser selecionadas como filtros e targeting dimension, proporcionando a capacidade de filtrar atributos para usuários com ou sem perfis. <br /> Para obter mais informações, consulte a <a href="../../sending/using/about-typology-rules.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Importação de conteúdo automatizada de um URL durante a preparação de mensagens<br /> </td> 
   <td> Agora é possível importar conteúdo de email de um URL durante a fase de preparação. Para delivery de email recorrentes, o conteúdo HTML mais recente é recuperado toda vez que a mensagem é preparada, garantindo que o conteúdo esteja sempre atualizado no momento em que o email é enviado. Esse recurso também permite que você crie um agendo o delivery com conteúdo de um URL, mesmo se o conteúdo ainda não estiver pronto.<br /> Para obter mais informações, consulte a <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mensagem de notificação de versão de campanha<br /> </td> 
   <td> Uma mensagem pop-up agora é exibida quando um usuário faz logon depois que a instância é atualizada para uma nova versão. A mensagem indica o número da versão e inclui um link para as notas de versão. Você pode optar por ocultar a mensagem até a próxima versão. <br /> </td> 
  </tr> 
  <tr> 
   <td> Gerenciamento de usuários<br /> </td> 
   <td> A capacidade da unidade geográfica agora não está disponível para novas instâncias de Campaign Standard, bem como para instâncias existentes sem unidades geográficas criadas, a partir da versão 18.7.<br /><a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=pt-BR#release-notes"> Para saber mais, consulte esta página</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Aprimoramentos**

* A integração entre Adobe Campaign e Adobe Target agora permite que você aproveite o recurso [Permissões](https://docs.adobe.com/content/help/pt-BR/target/using/administer/manage-users/enterprise/properties-overview.html) do Público alvo. Ao incluir uma imagem dinâmica do Adobe Target em um email, agora é possível especificar uma Propriedade de Público alvo (código at_property).
* Os recursos personalizados que têm um link de cópia própria para o recurso de perfis agora são considerados pelas solicitações de acesso/exclusão da Privacidade do RGPD. Para 1 cardinalidade links simples e N links de coleção de cardinalidade, é necessário selecionar &quot;Excluir/Duplicar o registro do público alvo implica excluir/duplicar os registros referenciados pelo link&quot; no recurso personalizado. Para links simples de cardinalidade 0 ou 1, selecione &quot;Excluir/Duplicar o registro implica excluir/duplicar o registro de públicos alvos referenciado pelo link&quot;.

**Outras alterações**

* O tempo limite de compartilhamento de relatórios foi aumentado de um para quatro minutos para evitar erro de tempo limite.
* Ao editar o conteúdo de um email, o novo Creative Designer é aberto por padrão. Se desejar, você ainda poderá voltar para o editor de conteúdo padrão a qualquer momento depois de salvar as alterações. Para obter mais informações, consulte a [documentação detalhada](../../designing/using/designing-content-in-adobe-campaign.md).
* No Creative Designer, um novo componente de conteúdo agora pode ser adicionado a um email: o carrossel. Para obter mais informações, consulte a [documentação detalhada](../../designing/using/designing-from-scratch.md#about-content-components).
* Em um relatório de clique com o botão direito do mouse em um mensagen transacional, quando você clica no botão **Alterar perfil**, agora apenas os perfis de teste vinculados ao evento definido para o seu mensagen transacional são listados.

**Correções**

* Correção de um problema com o filtro de query byEmail que não retornava resultados. (CAMP-23420)
* Correção de um problema que permitia que o usuário padrão acessasse determinados recursos ou telas restritas aos administradores (pontos finais/rest/head/*, telas de mensagens transacionais, perfis e telas de importação do audiência).
* Correção de um problema que impedia que solicitações de exclusão de Privacidade do RGPD processassem recursos personalizados se o nome começasse por um número.
* Correção de um erro que impedia a atividade Salvar Audiência de compartilhar assinantes de aplicativos no Adobe Experience Cloud.
* Correção de um problema com a atividade Transferência de arquivos que ocorria quando o nome do arquivo continha espaços em branco. (CAMP-25936)
* Correção de um problema que ocorria ao usar o botão de reconexão após a expiração de uma sessão. (CAMP-25560)
* Correção de um problema que resultava em exclusões ao enviar delivery com otimização de fuso horário associada às regras de fadiga. (CAMP-25425)
* Correção de um problema ao usar o recurso API GDPR, que poderia impedir a exclusão de dados com um link do tipo 0-1.
* Correção de um problema que resultava em uma mensagem de erro ao cancelar a edição de uma regra de tipologia de fadiga.
* Correção de um problema que ocorria ao visualizar um conteúdo de delivery após ele ter sido editado.
* Correção de um problema que ocorria ao processar arquivos zip CSV ao usar a opção Descompactação.
* Correção de um problema no Creative Designer que resultava em fonte e formatação coloridas indesejadas ao alterar algum texto com estilo incorporado para um link ou ao editar esse link. (CAMP-26001)
* Correção de um problema que impedia que o relatório de cliques ativos exibisse as porcentagens de cada condição em delivery com conteúdo dinâmico. Anteriormente, somente os cliques na variante padrão eram exibidos.

## Versão 18.6 - Junho de 2018 {#release-18-6---june-2018}

**Aprimoramentos**

* A API **[!UICONTROL History]** foi adicionada ao Adobe.IO. Ele permite acessar informações relacionadas ao histórico de marketing: número de pontos de contato, delivery enviados, URL do mirror page etc. Para obter mais informações, consulte [caso de uso dedicado](../../api/using/interacting-with-marketing-history.md).
* O fluxo de trabalho técnico **[!UICONTROL Database cleanup]** foi otimizado para garantir melhor desempenho para backup de banco de dados.
* O Creative Designer for Email agora também está disponível em francês e alemão.

**Outras alterações**

* Um botão **[!UICONTROL Compute stats]** foi adicionado na janela **[!UICONTROL Deployment]** dos delivery enviados. Permite recuperar os KPIs mais recentes, por exemplo, se os resultados do envio levarem muito tempo para serem atualizados ou não tiverem sido levados em conta. Para obter mais informações, consulte esta [seção](../../sending/using/confirming-the-send.md).
* No **Atualização para a capacidade de entrega** fluxo de trabalho técnico predefinido, os administradores funcionais agora podem definir o número de erros consecutivos a serem ignorados na atividade javascript **Atualizar regras**. Por padrão, o valor do campo é definido como 0, o que significa que todos os erros serão ignorados.
* O SQL gerado ao gerenciar condições de restrição de acesso da unidade foi otimizado.
* A atividade **[!UICONTROL Update]** agora permite adicionar, atualizar ou excluir dados relacionados ao subscrição (tabela nms:appSubscriptionRcp).
* O fluxo de trabalho técnico **[!UICONTROL Update delivery execution]** foi dividido em dois workflows para otimizar o desempenho: - **[!UICONTROL Update delivery execution]**: atualiza o rastreamento de delivery. É iniciado a cada 10 minutos por padrão. **[!UICONTROL Update delivery indicators]**: atualiza os KPIs dos delivery, que são iniciados a cada hora por padrão. Para obter mais informações sobre workflows técnicos, consulte esta [seção](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* Quando um delivery está enviando mensagens, o status na seção **[!UICONTROL Deployment]** agora pode ter dois valores: **[!UICONTROL Sending]**: as mensagens estão sendo enviadas. **[!UICONTROL Sending (retry)]**: uma nova aprovação está em andamento.
* Os usuários com a função **[!UICONTROL Delivery preparation]** agora podem enviar provas. (CAMP-24313)
* A opção **Ativar TLS por SMPP** foi adicionada ao roteamento **SMS por meio da conta externa SMPP**. Para obter mais informações, consulte [esta seção](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

**Correções**

* Correção de um problema que impedia o envio de emails ao incluir uma imagem dinâmica do Adobe Target (CAMP-24848).
* Correção de um problema com os workflows técnicos **[!UICONTROL Privacy Access/Delete Request]**, que não eram concluídos se alguma das solicitações falhasse.
* Correção de um problema que impedia que o serviço Privacy Core recebesse atualizações de status de solicitação da Campanha.
* Correção de um problema que impedia o fluxo de trabalho técnico **[!UICONTROL Import shared audience]** de funcionar corretamente (CAMP-25465).
* Correção de um problema que impedia que solicitações de privacidade de Campanha fossem marcadas como concluídas no Privacy Service principal.
* Correção de um problema que impedia que determinados usuários fizessem logon no Campaign Standard por meio da autenticação IMS quando o Adobe ID era muito longo. (CAMP-24095)
* Correção de um problema no Creative Designer que poderia ocorrer ao remover módulos de conteúdo. (CAMP-25242)
* Correção de um problema ao usar regras de fadiga de notificações por push para assinantes sem perfil no banco de dados. (CAMP-25344)
* Correção de um problema que poderia exibir uma mensagem de erro ao acessar os registros de exclusão de delivery. (CAMP-24724)
* Correção de um problema que impedia que provas fossem preparadas em instâncias com registros de envio estendidos.
* Correção de dois problemas que podem ocorrer ao publicar recursos personalizados com a extensão **[!UICONTROL Sending log]** ativada.
* Correção de um problema que ocorria com a duração do delivery não levada em conta em delivery recorrentes.
* Correção de um problema que ocorria ao classificar dados no menu **[!UICONTROL Client data]**, para recursos personalizados com mais de 100 mil registros. (CAMP-24308)
* Correção de um problema com dimensões de perfil personalizadas que não eram levadas em conta ao usar a função de pesquisa nos relatórios dinâmicos.
* Correção de um problema com a exibição de dados internacionais para níveis de Conta em relatórios dinâmicos.
* Agora é possível criar um serviço sem uma mensagem de confirmação de subscrição ou unsubscription.

## Versão 18.5 - Maio de 2018 {#release-18-5---may-2018}

**Novidades**

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> RGPD: Integração do serviço principal<br /> </td> 
   <td> A Integração do Privacy Core Service permite que você automatize suas solicitações de RGPD em um contexto de várias soluções por meio de uma única chamada de API JSON. <br /> As solicitações de RGPD enviadas do Privacy Core Service para todas as soluções de Experience Cloud agora são automaticamente tratadas pela Campanha. <br /> Para obter mais informações, consulte a <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aprimoramentos de push - feedback detalhado do delivery<br /> </td> 
   <td> A Adobe Campaign agora oferece a capacidade de receber feedback detalhado (enviando registros e logs de exclusão) sobre mensagens de push dos provedores (APNS/GCM) via MCPNS.<br /> Para obter mais informações, consulte a <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> extensão de logs do delivery<br /> </td> 
   <td> A extensão de logs do delivery permite estender o envio de registros com dados de perfil e códigos de segmento provenientes de workflows. Essas informações podem ser usadas em Relatórios dinâmicos e permitem manter um instantâneo de algumas informações no momento do envio de um delivery.<br /> Há mais 2 casos de uso:<br /> 
    <ul> 
     <li> Exporte blogues estendidos com dados "congelados": Como comerciante, eu gostaria de exportar todos os perfis onde o código de segmento é igual a "A" (vindo do motor de workflow). </li> 
     <li> Segmentação em dados "congelados": Como comerciante, eu gostaria de <strong>redirecionar</strong> todos os perfis que ganharam 1000 pontos de fidelidade desde o último envio ou onde o código de segmento era igual a "A". </li> 
    </ul> Para obter mais informações, consulte a <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Relatórios dinâmico com dados de perfil personalizados<br /> </td> 
   <td> Esse recurso permite que você crie e gerencie relatórios com base nos dados de perfil personalizados criados durante a extensão do recurso de perfil. É possível detalhar relatórios por atributo de perfil, como programa de fidelidade, canal preferencial etc.<br /> Para obter mais informações, consulte a <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Aprimoramentos**

* A memória geral e o uso da CPU do aplicativo foram aprimorados

**Outras alterações**

* A atividade de fluxo de trabalho Ler Audiência agora pode ler Experience Cloud audiência. Anteriormente, esta atividade só conseguia ler audiências Query e Listas. Consulte a [documentação detalhada](../../automating/using/read-audience.md). (CAMP-23623)
* O identificador da fonte de dados compartilhada padrão agora está no modo somente leitura e não pode mais ser alterado. A alteração desse identificador pode causar alguns problemas ao compartilhar audiências com o Experience Cloud.
* Agora a importação de audiências do Audience Manager funciona com arquivos divididos. Anteriormente, somente o último arquivo do segmento era importado pelo workflow técnico importSharedAudience.
* O AWS S3 conta externa agora suporta regiões e o mecanismo de autenticação da versão 4. Consulte a [documentação detalhada](../../administration/using/external-accounts.md).
* A janela de seleção de Ativo agora deve ser carregada mais rapidamente e permitir a seleção de um ativo, em seguida, sair da janela sem qualquer problema.
* As propriedades e a estrutura dos workflows técnicos podem agora ser modificadas por usuários com direitos administrativos e pertencentes às unidades organizacionais e geográficas &quot;Todos&quot;.
* Foram feitos aprimoramentos na interface de atividade de Segmentação ao criar novos segmentos: A guia Limitação agora aparece diretamente após a adição de uma limitação. Os nomes dos novos segmentos agora são incrementados (&quot;Segmento 1&quot;, &quot;Segmento 2&quot; etc.).
* Um campo &quot;nextProcessingDate&quot; é adicionado ao recurso Fluxo de trabalho. Esse campo só é visível por meio de chamadas REST API, e permite visualizar workflows nas próximas datas de processamento.
* O campo &quot;sourceId&quot; agora é exposto no recurso de logs de rastreamento (nms:trackingLog).
* Os valores &quot;Total de aberturas&quot; e &quot;Total de cliques&quot; agora podem ser exportados em um arquivo simples por meio de um fluxo de trabalho. (CAMP-24186)
* &quot;Inglês - Danmark&quot; está agora disponível na lista de idiomas preferidos em perfis. (CAMP-23728)
* Ao usar uma atividade de Segmentação com um link de Dados adicionais (targetData), uma mensagem informa que os dados não estão disponíveis fora do fluxo de trabalho. Essa mensagem é exibida ao clicar no botão Contagem ou Pré-visualização na atividade Segmentação. (CAMP-23651)
* Foram feitos aprimoramentos para otimizar o espaço em disco usado pelos workflows: (CAMP-21979): Os arquivos processados pela atividade &quot;Carregar arquivo&quot; agora são excluídos por padrão. Uma opção permite mantê-los para necessidades específicas. Quando um fluxo de trabalho é excluído, sua pasta dedicada é automaticamente suprimida do diretório do servidor.

**Correções**

* Correção de um problema em que alguns eventos de relatórios brutos não tinham eventos de rastreamento associados porque o campo eventDate não era preenchido corretamente.
* Correção de um problema que impedia que campos personalizados fossem exibidos na janela pré-visualização de um delivery de notificação por push.
* Correção de um problema que impedia o texto de vincular o corpo da mensagem de uma notificação por push na janela de pré-visualização.
* Correção de um problema ao enviar um delivery de recuperação de um fluxo de trabalho quando o público alvo principal está vazio.
* Correção de um problema que impedia o acesso a um target mapping se ele estivesse vinculado a um schema inexistente.
* Correção de um problema que ocorria ao importar um arquivo zip por meio de uma atividade de carregamento de Arquivo. (CAMP-24309)
* Correção de um problema que resultava em um erro de PostgreSQL ao enviar um delivery recorrente. (CAMP-23613)
* Correção de um problema que exibia uma mensagem de erro ao enviar uma solicitação REST API com um atributo JSON vazio. (CAMP-23506)
* Correção de um problema em perfis que definia como maiúsculas os caracteres após o caractere &quot;ß&quot;. (CAMP-23136)
* Correção de um problema ao enviar delivery usados com a personalização ou a condição de qualificação do bloco de conteúdo dinâmico ao usar atributos de um schema de perfil vinculado. (CAMP-22751)
* Correção de um problema que impedia a exclusão de serviços. (CAMP-22050)
* Correção de um problema que impedia a alteração dos valores de País ou Estado em um perfil de teste. (CAMP-20426)
* Correção de um problema que impedia o carregamento do Creative Designer. (CAMP-24573)
* Correção de um problema que removia caracteres adicionados após campos de personalização no assunto do email. (CAMP-24113)

## Versão 18.4 - Abril de 2018 {#release-18-4---april-2018}

**Correções**

_Plataforma_

* Correção de um erro que impedia o processamento correto do acesso ao RGPD ou a exclusão de solicitações. Esse comportamento foi observado em alguns casos raros, onde os dados extraídos continham um dos seguintes caracteres: &amp; &lt; > &quot; &quot;.

_Emails, mensagens SMS e mala direta_

* Correção de um problema que resultava na substituição de KPIs com valores incorretos se a sincronização de transmissão demorasse mais de uma hora.

_Fluxos de trabalho_

* Gerenciamento de memória aprimorado e desempenho otimizado em workflows.

_Relatório_

* O fluxo de trabalho de compartilhamento de KPI agora recupera valores de delivery dos últimos 2 meses em vez dos últimos 6 meses. Correção de um problema com a conta externa de compartilhamento de KPI mostrando datas truncadas.
* Correção de um problema que resultava na não consideração de determinadas mensagens nas métricas **Enviadas**, **Entregues** e **Rejeitar**.
* Correção de um erro que ocorria quando o intervalo de tempo escolhido no **Relatório de resumo do Delivery** era muito longo.

_Recursos personalizados_

* Correção de um erro que causava a falha na preparação de recursos personalizados.

## Versão 18.3 - Março de 2018 {#release-18-3---march-2018}

**Novos recursos**

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> European General Data Protection Regulation (GDPR)<br /> </td> 
   <td> O GDPR é a nova lei de privacidade da União Europeia que concilia e moderniza os requisitos de proteção de dados, entrando em efeito em 25 de Maio de 2018. O GDPR aplica-se aos clientes do Adobe Campaign que coletam dados de residentes da UE.<br /> Além dos recursos de privacidade já disponíveis no Adobe Campaign (incluindo o gerenciamento de consentimento, as configurações de retenção de dados e as funções de usuários), aproveitamos a oportunidade, em função do nosso papel como Processador de Dados, para incluir recursos adicionais que ajudam o Controlador de Dados a estar de acordo com determinadas solicitações do GDPR:<br /> 
    <ul> 
     <li> Direito de Acesso: permite que o Alvo dos Dados receba uma cópia dos seus dados pessoais capturados pelos Controladores de Dados, incluindo potencialmente dados armazenados no Adobe Campaign. </li> 
     <li> Direito de Exclusão: possibilita que o Assunto dos Dados apague seus dados pessoais capturados pelos Controladores de Dados, possivelmente incluindo os dados armazenados no Adobe Campaign. </li> 
    </ul> Para obter mais informações, consulte a <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer para email (Beta)<br /> </td> 
   <td> O Adobe Campaign Creative Designer oferta uma experiência de criação totalmente integrada na Campanha, permitindo a criação visual rápida e sem esforços de emails cativantes e personalizados individualmente, sem a necessidade de criar scripts para uma única linha de código. Por meio de sua poderosa interface de arrastar e soltar, o Creative Designer ajuda a dimensionar a criação de e-mails, independentemente de os usuários serem start de uma barra em branco, ou aproveitarem os fragmentos ou modelos de conteúdo existentes. <br /> Os principais recursos incluem:<br /> 
    <ul> 
     <li> Projete visualmente e crie emails responsivos e totalmente personalizados por meio de uma interface de arrastar e soltar, aumentada por integrações de Creative Cloud nativas </li> 
     <li> Crie e salve um modelo de conteúdo de email e utilize modelos salvos para ajudar a dimensionar a criação de email </li> 
     <li> Criar e salvar fragmentos de conteúdo (como um cabeçalho, rodapé, artigo etc.) para simplificar a criação de conteúdo e garantir a consistência da marca </li> 
     <li> Alterne facilmente entre criar na interface arrastar e soltar e editar diretamente o HTML de um email com o clique de um botão </li> 
    </ul> O Creative Designer for Email está disponível somente em inglês.<br /> Para obter mais informações, consulte a documentação  <a href="../../designing/using/designing-content-in-adobe-campaign.md">detalhada </a> e assista a este  <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">vídeo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery de push multilíngues<br /> </td> 
   <td> A mesma interface multilíngue simples, que já existe nos canais de email e SMS, foi adicionada ao canal de push, ajudando você a envolver os clientes independentemente do idioma que eles preferirem.<br /> Esse recurso oferta uma solução escalonável e automática para clientes que gerenciam campanhas de push que abrangem várias regiões e desejam público alvo de usuários em seu idioma preferido. Ele permite carregar todas as variantes linguísticas por meio de uma planilha modelada para um único delivery de push, em um clique. Em seguida, a Adobe Campaign realiza uma segmentação automática com base na preferência de idioma dos usuários, ajudando a reduzir as redundâncias, simplificando workflows e relatórios.<br /> Para obter mais informações, consulte a <a href="../../channels/using/creating-a-multilingual-push-notification.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Uso de recursos personalizados em mensagens transacionais<br /> </td> 
   <td> Além dos campos predefinidos, as mensagens transacionais agora permitem que você use recursos personalizados para enriquecer o conteúdo de suas mensagens.<br /> Por exemplo:<br /> 
    <ul> 
     <li> Utilize campos personalizados como critérios de reconciliação para corresponder um mensagen transacional a um perfil </li> 
     <li> Aproveite perfis, serviços e dados vinculados completos para personalizar ainda mais os mensagens transacionais </li> 
    </ul> Para obter mais informações, consulte a <a href="../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Plataforma_

* Correção de um problema que impedia a exportação de mais de 5000 registros de uma lista.
* Correção de um problema ao exportar dados para arquivos nomeados com campos de personalização.

_Emails, mensagens SMS e mala direta_

* Correção de um problema que resultava no truncamento de SMS de várias partes, pois o tamanho das partes era calculado em caracteres em vez de bytes.
* Adicionada uma opção que permite que os KPIs **[!UICONTROL Delivered]** ou **[!UICONTROL Bounces + Errors]** sejam atualizados em tempo real após o envio do delivery. Eles são recalculados diretamente do SR (Status Report) recebido do provedor.
* Correção de um problema com o widget de calendário no scheduler do delivery.
* Correção de um problema de exibição ao abrir um público alvo pela segunda vez em um delivery enviado.
* Correção de um problema que resultava em uma mensagem de erro solicitando uma data de start ao criar um modelo de email com uma data de envio atrasada.
* Correção de um problema que causava problemas de renderização de imagem ao editar o conteúdo de um delivery.
* Correção de um problema com provas ao duplicar uma campanha.
* Correção de um problema que resultava em uma mensagem de erro ao acessar um template de campanha pela barra de navegação, após adicionar um delivery ao fluxo de trabalho.
* Correção de um problema que impedia que o vencedor de um email de teste A/B fosse selecionado automaticamente, fazendo com que o email não fosse enviado. Esse comportamento pode ocorrer se o delivery estiver no estado **[!UICONTROL retryInProgress]**.
* Correção de um problema que resultava na exibição de uma mensagem de erro ao reabrir os parâmetros de um email de teste A/B.

_Audiências e query_

* Correção de um problema que impedia o acesso aos dados e a configuração de query para recipient replicados do Adobe Campaign Classic para o Standard.
* Correção de um problema que ocorria ao usar um campo de tipo de filtro no editor de query, após usar os botões **Count** ou **Pré-visualização**.

_Fluxos de trabalho_

* O fluxo de trabalho **Faturamento** foi otimizado para melhorar o atraso de preparação do delivery.
* Correção de um problema que impedia a exibição de dados de população em uma transição de saída ao usar uma atividade de delivery recorrente.
* Correção de um problema que impedia a exibição de registros de rejeição em uma transição após uma atividade **Atualizar dados**.
* Correção de um problema que resultava em falha do fluxo de trabalho técnico **material de entregaUpdate**.

_Integrações_

* Correção de um problema que impedia que caracteres internacionais fossem enviados corretamente para o Adobe Analytics.
* Os ativos agora devem ser carregados mais rapidamente ao tentar inserir uma imagem da biblioteca de ativos do Experience Cloud em uma mensagem.
* Correção de um problema que impedia o fechamento da janela de seleção de ativos em alguns casos.
* A partir de um detalhe da fonte de dados, agora é possível acessar diretamente seu fluxo de trabalho relacionado para verificar o estado do fluxo de trabalho.
* Agora você pode atualizar o schema Acionadores diretamente ao definir ou editar um evento acionador. Com essa alteração, não é mais necessário desfazer a publicação do acionador e criar outro.

_Mensagens transacionais_

* Correção de um erro com o template de mensagem transacional quando o recurso do delivery era estendido.
* Agora é possível excluir mensagens transacionais.

## Versão 18.2 - Fevereiro de 2018 {#release-18-2---february-2018}

**Novos recursos**

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Subscrição - assine ou cancele a assinatura de uma lista de perfis para vários serviços<br /> </td> 
   <td> A atividade de fluxo de trabalho <strong>Subscrição no serviço</strong> agora permite que você assine ou cancele a assinatura de uma lista de perfis para vários serviços. No fluxo de trabalho, importe um arquivo que contenha os perfis e, para cada perfil, o tipo de operação e o serviço. A atividade <strong>Subscrição no serviço</strong> poderá usar essas informações e manipular dinamicamente todas as subscrições e unsubscription simultaneamente.<br /> Para obter mais informações, consulte a <a href="../../automating/using/subscription-services.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Atividade do enriquecimento - enriqueça os dados com base em transição<br /> anteriores </td> 
   <td> A nova atividade de fluxo de trabalho <span class="uicontrol">Enriquecimento</span> permite que você aproveite as transições de entrada e conclua a transição de saída com dados adicionais. Se você público alvo perfis, a atividade do enriquecimento permite que você enriqueça as informações dos perfis com dados adicionais que não estão armazenados no banco de dados (provenientes de um arquivo importado, por exemplo).<br /> Para obter mais informações, consulte a <a href="../../automating/using/enrichment.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Plataforma_

* A barra superior da interface do Adobe Campaign foi atualizada com o novo menu Experience Cloud.
* Correção de um problema que impedia que o link para **[!UICONTROL Offers]** fosse exibido na lista suspensa da solução.

_Emails, mensagens SMS e mala direta_

* A fase de preparação do delivery foi aprimorada para melhorar o desempenho.
* Correção de vários problemas que resultavam em logs de rastreamento corrompidos em algumas situações de nicho.
* Correção de um problema de atualização de data de contato que ocorria quando a data de contato era alterada entre a preparação e a confirmação do delivery. Agora, ao alterar a data de contato após a preparação, você deverá preparar o delivery novamente antes de poder confirmar o envio. Consulte a [documentação detalhada](../../sending/using/preparing-the-send.md).

_Notificações por push_

* Correção de um erro que impedia que alguns campos de personalização funcionassem em notificações por push do iOS.
* Correção de um erro que exibia as taxas de clique e de abertura como 0% no painel de notificação por push.

_Relatórios_

* Corrigido um erro que exibia a lista do relatório como vazia em alguns navegadores.
* Correção de um erro que ocorria no fluxo de trabalho técnico **[!UICONTROL Report sharing]** antes de seu limite de expiração ser atingido.

_Fluxos de trabalho_

* Correção de um problema que impedia que atividades fossem acessíveis após arrastar e soltar.
* Corrigido um problema que fazia com que a ordem das transições de saída de uma atividade **[!UICONTROL Segmentation]** fosse alterada em algumas situações.
* Corrigido um erro que ocorria ao ler uma audiência contendo um campo de tipo de lista discriminada e que havia sido salvo anteriormente de um fluxo de trabalho
* Correção de um problema que fazia com que a opção **[!UICONTROL Request confirmation before sending messages]** permanecesse marcada mesmo após desmarcá-la ao definir as propriedades de agendamento de um delivery criado em um fluxo de trabalho.
* A remoção automática de linhas de duplicado (cláusula DISTINCT) agora pode ser desabilitada no **[!UICONTROL Query]** atividade, por meio de uma nova opção localizada na guia **[!UICONTROL Additional data]**. A desativação dessa opção é recomendada ao definir muitos (mais de 100) elementos adicionais, por motivos de desempenho.

_Integrações_

* Foram feitos alguns aprimoramentos na tela de configuração **[!UICONTROL Data sources]**.

_Problemas conhecidos_

Recomendamos que você não use o Internet Explorer versão 11 devido a possíveis problemas de exibição.

Alguns problemas podem ocorrer ao usar links de ajuda contextuais da interface de Campanha. Serão fixadas em 18.3.

## Versão 18.1 - Janeiro de 2018 {#release-18-1---january-2018}

**Novos recursos**

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Relatórios para gerenciamento de fadiga<br /> </td> 
   <td> O relatórios para gerenciamento de fadiga é um relatório dedicado e configurável que exibe o impacto das regras de fadiga nos delivery de email, push, SMS e mala direta dentro de um intervalo de datas especificado antes do envio. Com o insight adicional de poder ver rapidamente todas as campanhas conflitantes em uma única visualização, os profissionais de marketing são capazes de planejar campanhas de marketing de acordo com a definição mais eficiente das regras de fadiga e priorizar as comunicações.<br /> Para obter mais informações, consulte a <a href="../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Compartilhamento de relatórios<br /> </td> 
   <td> O Compartilhamento de relatórios permite que você compartilhe seus relatórios com usuários do Adobe Campaign como um anexo de email, inclusive de forma recorrente automatizada. Os usuários que recebem relatórios recorrentes têm a capacidade de cancelar a inscrição dessas comunicações por meio de um link dedicado em cada email.<br /> Para obter mais informações, consulte a <a href="../../reporting/using/reporting-interface.md#share-tab">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Enviar novos recursos<br /> </td> 
   <td> Pré-visualização de mensagem de push - notificações por push de Pré-visualização em dispositivos iOS e Android no editor de conteúdo de notificação por push para ver exatamente o que seus recipient verão antes de testar ou executar o delivery.<br /> Para obter mais informações, consulte a <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">documentação detalhada</a>.<br /> Conteúdo disponível - quando os aplicativos não são abertos por períodos maiores, seus dados podem ficar desatualizados. Isso resulta na atualização ou substituição dos dados no momento em que um usuário finalmente abre o aplicativo, o que pode causar atrasos no uso do aplicativo. Com o suporte adicional de Conteúdo disponível, os usuários da Adobe Campaign podem acordar seu aplicativo para atualizar seus dados em segundo plano ao enviar uma notificação por push, permitindo maior consistência e controle sobre a experiência do usuário no aplicativo.<br /> Conteúdo variável - Com o suporte adicional de Conteúdo variável, os usuários do Adobe Campaign agora podem aproveitar suas extensões de aplicativos para dispositivos móveis para modificar ainda mais o conteúdo ou a apresentação das notificações por push recebidas enviadas pela Adobe Campaign. Por exemplo, os usuários podem aproveitar o Conteúdo variável para: <br /> 
    <ul> 
     <li> descriptografar dados que foram entregues em um formato criptografado </li> 
     <li> baixe imagens ou outros arquivos de mídia e adicione-os como anexos a uma notificação </li> 
     <li> alterar o texto do corpo ou do título de uma notificação </li> 
     <li> adicionar um identificador de thread a uma notificação </li> 
    </ul> Para obter mais informações sobre Conteúdo disponível e Conteúdo variável, consulte a <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">documentação detalhada</a>.<br /> <strong>Aviso:</strong> essas atualizações nas notificações por push exigem que os clientes atualizem seus aplicativos móveis. Consulte <a href="https://helpx.adobe.com/br/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html">this technote</a> para obter mais informações.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery otimizados para fuso horário<br /> </td> 
   <td> Agende emails, SMS e notificações por push recorrentes para serem entregues em um dia/hora específico em cada fuso horário de cada recipient, garantindo que suas mensagens sejam entregues no horário certo sem configurar vários delivery. <br /> Para obter mais informações, consulte a <a href="../../automating/using/scheduler.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> ATIVIDADE de sinal de API acionando<br /> </td> 
   <td> Agora é possível disparar uma atividade de sinal para seus workflows diretamente da API do Adobe Campaign Standard.<br /> Para obter mais informações, consulte a <a href="/help/api/using/triggering-a-signal-activity.md">documentação detalhada</a> .<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Plataforma_

* A pesquisa de perfil foi otimizada para melhorar o desempenho.
* O identificador interno de grupos de segurança padrão agora está no modo somente leitura para usuários padrão.

_Emails, mensagens SMS e mala direta_

* Correção de um problema de exibição que ocorria ao inserir emojis no conteúdo de seus delivery.
* Correção de um problema que permitia que o usuário acessasse o envio de logs quando o delivery ainda estava na edição.
* A atividade **[!UICONTROL Scheduler]** agora permite enviar delivery dependendo do fuso horário do recipient.
* SMS: A opção **[!UICONTROL Store incoming MO]** no banco de dados foi adicionada ao conta externa. Quando marcado, todo o SMS recebido será armazenado na tabela **inSMS**.
* SMS: Agora, os serviços são anexados a um evento em vez de um modelo transacional.
* SMS: O tempo limite de conexão SMTP padrão foi reduzido para 30 segundos.

_Notificações por push_

* Correção de um erro que impedia a interrupção de delivery de notificação por push.
* Adicionada uma opção nas opções avançadas de notificação por push para ativar o aplicativo com uma notificação por push.
* Adição de um botão de pausa para o vídeo de pré-visualização de notificação por push.
* A pré-visualização de notificação por push agora está disponível para diferentes dispositivos, como iPhone, Android e tablets.

_Relatórios_

* Correção de um erro que exibia taxas acima de 100%.
* Correção de um problema que impedia os usuários de baixar relatórios em CSV.
* Adicionado um novo item **[!UICONTROL Report]** na página inicial.

_Fluxos de trabalho_

* Correção de um problema que resultava em uma mensagem de erro ao usar dados adicionais em um query e adicionar aliases contendo espaços. Os caracteres não alfanuméricos agora são substituídos por &quot;_&quot;.
* Correção de um problema em que o fluxo de trabalho técnico que calculava KPIs poderia ser interrompido por padrão em alguns casos.

_Perfis e públicos_

* Correção de um erro que ocorria ao adicionar vários filtros em um query.
* Correção de um problema de exibição que ocorria ao alterar uma imagem de perfil.
* Adicionada uma dica de ferramenta que exibe o número exato do resultado após contar a população de um query.
* Correção de um problema que impedia um usuário de selecionar uma audiência ou fechar a janela do seletor de audiências.
* A lista de funções disponíveis no editor de expressões foi atualizada. As funções **FormatCurrency** e **ConvertCurrency** foram removidas.

