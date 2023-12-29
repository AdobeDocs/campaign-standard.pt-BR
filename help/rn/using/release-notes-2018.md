---
title: Notas de versão de 2018
description: Essa página lista todas as versões de 2018 do Adobe Campaign Standard.
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 17521357-14ae-4751-bd7c-aeabbcf71d07
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '5386'
ht-degree: 6%

---

# Notas de versão de 2018{#release-notes}

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
   <td> As mensagens no aplicativo permitem que você garanta o envolvimento de usuários de aplicativos móveis com mais eficiência, fornecendo interação contextual e permitindo que alcançar os usuários que optaram por notificações por push. Use mensagens no aplicativo em conjunto com notificações por push para criar uma experiência altamente personalizada e relevante. Isso resulta em uma melhor conversão e retenção dos usuários do aplicativo.<br /> Para obter mais informações, consulte <a href="../../channels/using/about-in-app-messaging.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integração do Adobe Launch para aplicativos de dispositivos móveis (beta)<br /> </td> 
   <td> A integração do Adobe Launch com o Adobe Campaign agora simplifica e automatiza o processo de ativação da Propriedade de aplicativo móvel no Campaign usando o Mobile SDK V5.<br /> Para obter mais informações, consulte <a href="https://helpx.adobe.com/br/campaign/kb/configuring-app-sdk.html">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Aprimoramentos**

* O Adobe Campaign Standard agora é compatível com a versão 4 da API do Amazon S3.

**Outras alterações**

* Há agora uma distinção nos broadlogs entre o número máximo de conexões e o número máximo de mensagens por hora. Quando os limites são atingidos, é possível saber o motivo da taxa de transferência ser limitada. Anteriormente, a mesma mensagem (‘cota atingida’) se aplicava a ambos os casos.
* Ao configurar um aplicativo para dispositivos móveis no Campaign, o usuário agora pode saber se o certificado do iOS e a chave do servidor Android foram carregados com êxito e a data de expiração.

  Para obter mais informações, consulte a documentação detalhada sobre como configurar um aplicativo móvel usando o [SDK V4](https://helpx.adobe.com/br/campaign/kb/configuring-app-sdkv4.html) e [SDK V5](https://helpx.adobe.com/br/campaign/kb/configuring-app-sdk.html).

* Direcione usuários em um Aplicativo móvel específico selecionando um Aplicativo móvel ao definir as propriedades do Campaign. Esse recurso é para os canais de mensagens por push e no aplicativo.

  Para obter mais informações, consulte a [documentação detalhada](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification).

* Ao selecionar um bloco de conteúdo usando a interface do Creative Designer, todos os blocos de conteúdo da lista agora são carregados e exibidos. (CAMP-27311)

  Para obter mais informações, consulte [documentação detalhada](../../designing/using/personalization.md#adding-a-content-block).

**Correções**

* Correção de um problema que mostrava uma discrepância nas contagens de log entre o painel de email e o relatório de resumo de email para emails transacionais. (CAMP-28237
* Correção de um problema em workflows que exibia uma mensagem de erro ao importar um arquivo por meio de uma atividade de transferência de arquivos. (CAMP-27435)
* Correção de um problema com páginas de aterrissagem contendo mais de 25 serviços, que fazia com que os serviços fossem desmarcados aleatoriamente no formulário. (CAMP-26572)
* Correção de um problema em workflows que impedia a configuração de contas externas com um URL SFTP ao usar a atividade de transferência de arquivos. (CAMP-26475)
* Correção de um problema que impedia a atualização do relatório de resumo dos serviços. (CAMP-26301)
* Correção de um problema nos workflows ao usar uma atividade Enriquecimento, que impedia que um campo personalizado exibisse a data correta. (CAMP-26242)
* Correção de um problema que impedia a atualização das datas de assinatura do serviço quando importadas por meio de uma importação de arquivo.
* Correção de um erro com a atividade de carregamento de arquivo que impedia que os workflows importassem arquivos (CAMP-27068).
* Correção de um problema que exibia o número incorreto de assinaturas nos Relatórios de resumo do serviço (CAMP-25587).
* Correção de um problema de discrepância de dados entre os relatórios Adobe Analytics e Adobe Campaign. (CAMP-25393)
* Correção de um problema que impedia que um usuário de acesso limitado fizesse logon. (CAMP-27381)
* Correção de um problema que impedia a exibição da lista de conteúdos do Adobe Experience Manager ao editar um email usando o Creative Designer. (CAMP-27181)
* Correção de um problema que impedia a abertura do Creative Designer, causando um erro. (CAMP-27304)
* Correção de um problema que impedia que arrastar e soltar funcionasse corretamente no Creative Designer ao usar o Internet Explorer 11.
* Correção de um problema que fazia com que as fotos carregadas de uma câmera e tiradas no modo retrato fossem exibidas em uma posição girada não desejada.
* Correção de um problema que exibia informações de seleção não claras ao usar a interface do editor de consultas no Creative Designer.
* Correção de um problema que impedia a duplicação correta de um elemento ao usar a interface do editor de consultas no Creative Designer.
* Correção de um problema que fazia com que mensagens SMS fossem enviadas a recipients na inclui na lista de bloqueios, mesmo após o cancelamento de subscrição por meio de uma resposta automática. (CAMP-27128)
* Correção de um problema que impedia a exibição dos erros que causavam a **Limpeza do Banco de Dados** fluxo de trabalho para falhar. (CAMP-26876)
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
   <td> Sinalizador de alta prioridade para notificações por push no Android<br /> </td> 
   <td> Sinalizador de alta prioridade para Android - Permite a entrega de uma notificação por push com alta prioridade para aplicativos Android, o que faz com que o dispositivo em espera seja ativado e execute algum processamento limitado. Observe que a prioridade padrão é Normal, o que pode atrasar a entrega da mensagem para economizar bateria. <br /> Para obter mais informações, consulte <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Filtro de tipologia para assinantes de aplicativos para dispositivos móveis<br /> </td> 
   <td> Assinaturas compatíveis com o filtro de tipologia - Ao especificar os critérios de filtragem para uma regra de tipologia, as assinaturas de aplicativo podem ser selecionadas como as dimensões de filtragem e direcionamento, fornecendo a capacidade de filtrar atributos para usuários com ou sem um perfil. <br /> Para obter mais informações, consulte <a href="../../sending/using/about-typology-rules.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Importação automatizada de conteúdo de um URL durante a preparação da mensagem<br /> </td> 
   <td> Agora é possível importar conteúdo de email de um URL durante a fase de preparação. Para deliveries de email recorrentes, o conteúdo de HTML mais recente é recuperado sempre que a mensagem é preparada, garantindo que o conteúdo esteja sempre atualizado no momento em que o email é enviado. Esse recurso também permite criar um delivery agendado com conteúdo de um URL, mesmo que o conteúdo ainda não esteja pronto.<br /> Para obter mais informações, consulte <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mensagem de notificação de versão da campanha<br /> </td> 
   <td> Uma mensagem pop-up agora é exibida quando um usuário faz logon após a instância ser atualizada para uma nova versão. A mensagem indica o número da versão e inclui um link para as notas de versão. Você pode optar por ocultar a mensagem até a próxima versão. <br /> </td> 
  </tr> 
  <tr> 
   <td> Gerenciamento de usuários<br /> </td> 
   <td> O recurso de unidade geográfica agora está indisponível para novas instâncias de Campaign Standard, bem como instâncias existentes sem unidades geográficas criadas, a partir da versão 18.7.<br /> Para obter mais informações, consulte esta <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=pt-BR#release-notes">página</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Aprimoramentos**

* A integração do Adobe Campaign e do Adobe Target agora permite aproveitar o Target [Permissões](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html?lang=pt-BR) recurso. Ao incluir uma imagem dinâmica do Adobe Target em um email, agora é possível especificar uma Propriedade do Target (código at_property).
* Os recursos personalizados que têm um link de owncopy para o recurso de perfis agora são considerados pelas solicitações de acesso/exclusão de Privacidade do GDPR. Para links simples de cardinalidade 1 e links de coleção de cardinalidade N, é necessário selecionar &quot;Excluir/duplicar o registro de destino implica excluir/duplicar os registros referenciados pelo link&quot; no recurso personalizado. Para links simples de cardinalidade 0 ou 1, selecione &quot;Excluir/duplicar o registro implica excluir/duplicar o registro de destino referenciado pelo link&quot;.

**Outras alterações**

* O tempo limite de compartilhamento de relatórios foi aumentado de um para quatro minutos para evitar qualquer erro de tempo limite.
* Ao editar o conteúdo de um email, o novo Creative Designer é aberto por padrão. Se desejar, ainda é possível voltar para o editor de conteúdo padrão a qualquer momento depois de salvar suas alterações. Para obter mais informações, consulte [documentação detalhada](../../designing/using/designing-content-in-adobe-campaign.md).
* No Creative Designer, um novo componente de conteúdo agora pode ser adicionado a um email: o carrossel. Para obter mais informações, consulte [documentação detalhada](../../designing/using/designing-from-scratch.md#about-content-components).
* Em um relatório de clique dinâmico de mensagem transacional, ao clicar no ícone **Alterar perfil** , agora somente os perfis de teste vinculados ao evento definido para sua mensagem transacional serão listados.

**Correções**

* Correção de um problema com o filtro de consulta byEmail que não retornava resultados. (CAMP-23420)
* Correção de um problema que permitia que um usuário padrão acessasse determinados recursos ou telas restritas aos administradores (/rest/head/&#42; endpoints, telas de mensagens transacionais, perfis e públicos (telas de importação).
* Correção de um problema que impedia que solicitações de exclusão de Privacidade do GDPR processassem recursos personalizados se o nome começasse por um número.
* Correção de um erro que impedia a atividade Salvar público-alvo de compartilhar assinantes de aplicativos no Adobe Experience Cloud.
* Correção de um problema com a atividade Transferência de arquivo que poderia ocorrer quando o nome do arquivo continha espaços em branco. (CAMP-25936)
* Correção de um problema que poderia ocorrer ao usar o botão de reconexão após uma sessão expirar. (CAMP-25560)
* Correção de um problema que resultava em exclusões ao enviar entregas com otimização de fuso horário associada a regras de fadiga. (CAMP-25425)
* Correção de um problema ao usar o recurso GDPR da API, que poderia impedir a exclusão de dados com um link do tipo 0-1.
* Correção de um problema que poderia resultar em uma mensagem de erro ao cancelar a edição de uma regra de tipologia de fadiga.
* Correção de um problema que poderia ocorrer ao visualizar um conteúdo de delivery após ele ser editado.
* Correção de um problema que ocorria ao processar arquivos zip CSV ao usar a opção de Descompactação.
* Correção de um problema no Creative Designer que resultava em fonte e formatação de cor indesejadas ao alterar algum texto com estilo incorporado a um link ou ao editar esse link. (CAMP-26001)
* Correção de um problema que impedia que o relatório de cliques ativos exibisse as porcentagens de cada condição nos deliveries com conteúdo dinâmico. Anteriormente, somente os cliques na variante padrão eram exibidos.

## Versão 18.6 - Junho de 2018 {#release-18-6---june-2018}

**Aprimoramentos**

* A variável **[!UICONTROL History]** A API foi adicionada ao Adobe.IO. Ele permite acessar informações relacionadas ao histórico de marketing de um perfil: número de pontos de contato, deliveries enviados, URL de mirror page, etc. Para obter mais informações, consulte [caso de uso dedicado](../../api/using/interacting-with-marketing-history.md) .
* A variável **[!UICONTROL Database cleanup]** o fluxo de trabalho técnico foi otimizado para garantir melhor desempenho do backup de banco de dados.
* O Creative Designer para email agora também está disponível em francês e alemão.

**Outras alterações**

* A **[!UICONTROL Compute stats]** foi adicionado um botão no **[!UICONTROL Deployment]** janela de deliveries enviados. Ele permite recuperar os KPIs mais recentes, por exemplo, se os resultados do envio demorarem muito para serem atualizados ou não tiverem sido considerados. Para obter mais informações, consulte esta [seção](../../sending/using/confirming-the-send.md).
* No **Atualização para entregabilidade** workflow técnico pronto para uso, os administradores funcionais agora podem definir o número de erros consecutivos a serem ignorados no **Atualizar regras** atividade javascript. Por padrão, o valor do campo é definido como 0, o que significa que todos os erros serão ignorados.
* O SQL gerado ao gerenciar as condições de restrição de acesso à unidade foi otimizado.
* A variável **[!UICONTROL Update]** A atividade agora permite adicionar, atualizar ou excluir dados relacionados às assinaturas (tabela nms:appSubscriptionRcp).
* A variável **[!UICONTROL Update delivery execution]** o workflow técnico foi dividido em dois workflows para otimizar o desempenho: - **[!UICONTROL Update delivery execution]**: atualiza o rastreamento do delivery. Ele é iniciado a cada 10 minutos por padrão. **[!UICONTROL Update delivery indicators]**: atualiza os KPIs do delivery, que é iniciado a cada hora por padrão. Para obter mais informações sobre workflows técnicos, consulte esta [seção](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* Quando um delivery está enviando mensagens, o status no campo **[!UICONTROL Deployment]** A seção agora pode ter dois valores: **[!UICONTROL Sending]**: as mensagens estão sendo enviadas. **[!UICONTROL Sending (retry)]**: uma nova tentativa de passar está em andamento.
* Usuários com o **[!UICONTROL Delivery preparation]** agora as funções podem enviar provas. (CAMP-24313)
* A variável **Habilitar TLS em SMPP** A opção foi adicionada à variável **Roteamento de SMS via SMPP** conta externa. Para obter mais informações, consulte [esta seção](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

**Correções**

* Correção de um problema que impedia o envio de emails ao incluir uma imagem dinâmica do Adobe Target (CAMP-24848).
* Correção de um problema com o **[!UICONTROL Privacy Access/Delete Request]** fluxos de trabalho técnicos, que não eram concluídos se qualquer uma das solicitações falhasse.
* Correção de um problema que impedia o Serviço principal de privacidade de receber atualizações de status de solicitação do Campaign.
* Correção de um problema que poderia impedir a **[!UICONTROL Import shared audience]** fluxo de trabalho técnico funcione corretamente (CAMP-25465).
* Correção de um problema que impedia que solicitações de privacidade do Campaign fossem marcadas como concluídas no Privacy Service principal.
* Correção de um problema que impedia determinados usuários de fazer logon no Campaign Standard por meio da autenticação IMS quando o Adobe ID era muito longo. (CAMP-24095)
* Correção de um problema no Creative Designer que poderia ocorrer ao remover módulos de conteúdo. (CAMP-25242)
* Correção de um problema ao usar regras de fadiga de notificações por push para assinantes sem perfil no banco de dados. (CAMP-25344)
* Correção de um problema que poderia exibir uma mensagem de erro ao acessar logs de exclusão de deliveries. (CAMP-24724)
* Correção de um problema que impedia que provas fossem preparadas em instâncias com logs de envio estendidos.
* Correção de dois problemas que poderiam ocorrer ao publicar recursos personalizados com o **[!UICONTROL Sending log]** extensão ativada.
* Correção de um problema que poderia ocorrer com a duração do delivery não considerada em deliveries recorrentes.
* Correção de um problema que poderia ocorrer ao classificar dados no **[!UICONTROL Client data]** para recursos personalizados com mais de 100 mil registros. (CAMP-24308)
* Correção de um problema com dimensões de perfil personalizadas que não eram consideradas ao usar a função de pesquisa em Relatórios dinâmicos.
* Correção de um problema com a exibição de dados internacionais para níveis de Conta em Relatórios dinâmicos.
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
   <td> GDPR: Integração de serviço principal<br /> </td> 
   <td> A Integração do Privacy Core Service permite automatizar suas solicitações de GDPR em um contexto com várias soluções por meio de uma única chamada de API JSON. <br /> As solicitações de GDPR enviadas pelo Privacy Core Service para todas as soluções de Experience Cloud agora são tratadas automaticamente pelo Campaign. <br /> Para obter mais informações, consulte <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy.html">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Melhorias nas notificações por push: feedback detalhado do delivery<br /> </td> 
   <td> O Adobe Campaign agora oferece a capacidade de receber feedback detalhado (enviando logs e logs de exclusão) sobre mensagens por push dos provedores (APNS/GCM) por meio do MCPNS.<br /> Para obter mais informações, consulte <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Extensão de logs de entrega<br /> </td> 
   <td> A extensão de logs do delivery permite estender logs de envio com dados de perfil e código de segmento provenientes de workflows. Essas informações podem ser usadas em Relatórios dinâmicos e permitem manter um instantâneo de algumas informações no momento de envio de um delivery.<br /> Há mais dois casos de uso:<br /> 
    <ul> 
     <li> Exportar broadlogs estendidos com dados "congelados": como profissional de marketing, gostaria de exportar todos os perfis com código de segmento igual a "A" (proveniente do mecanismo de fluxo de trabalho). </li> 
     <li> Segmentação em dados "congelados": como profissional de marketing, eu gostaria de <strong>redirecionar</strong> todos os perfis que ganharam 1000 pontos de fidelidade desde o último envio ou onde o código de segmento era igual a "A". </li> 
    </ul> Para obter mais informações, consulte a <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Relatórios dinâmicos com Dados de perfil personalizados<br /> </td> 
   <td> Esse recurso permite criar e gerenciar relatórios com base nos dados de perfil personalizados criados durante a extensão de recurso de perfil. Você pode detalhar relatórios por atributo de perfil, como programa de fidelidade, canal preferido etc.<br /> Para obter mais informações, consulte <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Aprimoramentos**

* O uso geral de memória e CPU do aplicativo foi aprimorado

**Outras alterações**

* A atividade de fluxo de trabalho Ler público-alvo agora pode ler públicos-alvo Experience Cloud. Anteriormente, essa atividade só podia ler públicos-alvo de Consulta e Lista. Consulte a [documentação detalhada](../../automating/using/read-audience.md). (CAMP-23623)
* O identificador da fonte de dados compartilhada padrão agora está no modo somente leitura e não pode mais ser alterado. A alteração desse identificador pode causar alguns problemas ao compartilhar públicos-alvo com o Experience Cloud.
* Agora a importação de audiências do Audience Manager funciona com arquivos divididos. Anteriormente, somente o último arquivo do segmento era importado pelo workflow técnico importSharedAudience.
* As contas externas do AWS S3 agora oferecem suporte a regiões e ao mecanismo de autenticação da versão 4. Consulte a [documentação detalhada](../../administration/using/external-accounts.md).
* A janela de seleção de ativos agora deve carregar mais rápido, permitir a seleção de um ativo e depois sair da janela sem nenhum problema.
* As propriedades e a estrutura dos workflows técnicos agora podem ser modificadas por usuários com direitos administrativos e pertencentes a &quot;Todas&quot; as unidades organizacionais e geográficas.
* Foram feitos aprimoramentos na interface da atividade de Segmentação ao criar novos segmentos: a guia Limitação agora aparece diretamente após adicionar uma limitação. Os nomes dos novos segmentos agora são incrementados (&quot;Segmento 1&quot;, &quot;Segmento 2&quot; etc.).
* Um campo &quot;nextProcessingDate&quot; é adicionado ao recurso Workflow. Esse campo só é visível por meio de chamadas REST API, ele permite visualizar workflows nas próximas datas de processamento.
* O campo &quot;sourceId&quot; agora é exposto no recurso de logs de rastreamento (nms:trackingLog).
* Os valores &quot;Total opens&quot; e &quot;Total clicks&quot; agora podem ser exportados em um arquivo simples por meio de um fluxo de trabalho. (CAMP-24186)
* &quot;English - Danmark&quot; agora está disponível na lista de Idiomas preferidos em perfis. (CAMP-23728)
* Ao usar uma atividade Segmentação com um link de Dados adicionais (targetData), uma mensagem agora informa que os dados não estão disponíveis fora do fluxo de trabalho. Essa mensagem é exibida ao clicar no botão Count ou Preview da atividade de Segmentação. (CAMP-23651)
* Foram feitos aprimoramentos para otimizar o espaço em disco usado pelos workflows: (CAMP-21979): os arquivos processados pela atividade &quot;Carregar arquivo&quot; agora são excluídos por padrão. Uma opção permite mantê-los para necessidades específicas. Quando um workflow é excluído, sua pasta dedicada é automaticamente suprimida do diretório do servidor.

**Correções**

* Correção de um problema em que alguns eventos brutos de relatórios não tinham eventos de rastreamento associados porque o campo eventDate não estava preenchido corretamente.
* Correção de um problema que impedia que campos personalizados fossem exibidos na janela de pré-visualização de um delivery de notificação por push.
* Correção de um problema que impedia o texto de quebrar o corpo da mensagem de uma notificação por push na janela de pré-visualização.
* Correção de um problema ao enviar um delivery recorrente de um workflow quando o target principal estava vazio.
* Correção de um problema que impedia o acesso a um target mapping se ele estivesse vinculado a um esquema inexistente.
* Correção de um problema que poderia ocorrer ao importar um arquivo zip por meio de uma atividade File load. (CAMP-24309)
* Correção de um problema que resultava em um erro PostgreSQL ao enviar um delivery recorrente. (CAMP-23613)
* Correção de um problema que exibia uma mensagem de erro ao enviar uma solicitação da API REST com um atributo JSON vazio. (CAMP-23506)
* Correção de um problema em perfis que definia para maiúsculas os caracteres após o caractere &quot;ß&quot;. (CAMP-23136)
* Correção de um problema ao enviar deliveries usados com personalização ou condição de elegibilidade do bloco de conteúdo dinâmico ao usar atributos de um esquema vinculado de perfil. (CAMP-22751)
* Correção de um problema que impedia a exclusão de serviços. (CAMP-22050)
* Correção de um problema que impedia a alteração dos valores de País ou Estado em um perfil de Teste. (CAMP-20426)
* Correção de um problema que impedia o carregamento do Creative Designer. (CAMP-24573)
* Correção de um problema que removia caracteres adicionados após campos de personalização no assunto do email. (CAMP-24113)

## Versão 18.4 - Abril de 2018 {#release-18-4---april-2018}

**Correções**

_Platform_

* Correção de um erro que poderia impedir o processamento correto de solicitações de acesso ou exclusão do GDPR. Esse comportamento foi observado em alguns casos raros em que os dados extraídos continham um dos seguintes caracteres: &amp; &lt; > &quot; &#39;.

_Emails, mensagens SMS e correspondência direta_

* Correção de um problema que poderia resultar na substituição de KPIs com valores incorretos se a sincronização de broadlog levasse mais de uma hora.

_Workflows_

* Gerenciamento de memória aprimorado e desempenhos otimizados em workflows.

_Relatórios_

* O fluxo de trabalho de compartilhamento de KPI agora recupera valores de entrega dos últimos 2 meses, em vez dos últimos 6 meses. Correção de um problema em que a conta externa de compartilhamento de KPI exibia datas truncadas.
* Correção de um problema que poderia resultar na não consideração de determinadas mensagens no **Enviado**, **Entregue** e **Rejeição** métricas.
* Correção de um erro que ocorria quando o intervalo de tempo escolhido no **Relatório de resumo da entrega** era muito longo.

_Recursos personalizados_

* Correção de um erro que causava a falha da preparação de recursos personalizados.

## Versão 18.3 — março de 2018 {#release-18-3---march-2018}

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
   <td> O GDPR é a nova lei de privacidade da União Europeia que concilia e moderniza os requisitos de proteção de dados, entrando em efeito em 25 de Maio de 2018. O GDPR aplica-se aos clientes do Adobe Campaign que coletam dados de residentes da UE.<br /> Além dos recursos de privacidade já disponíveis no Adobe Campaign (incluindo gerenciamento de consentimento, configurações de retenção de dados e funções de usuário), aproveitamos a oportunidade, em função do nosso papel como Processador de dados, para incluir recursos adicionais que ajudam o Controlador de dados a estar de acordo com determinadas solicitações do GDPR:<br /> 
    <ul> 
     <li> Direito de acesso: permite que o Titular de dados receba uma cópia de seus dados pessoais capturados pelos Controladores de dados, possivelmente incluindo dados armazenados no Adobe Campaign. </li> 
     <li> Direito de exclusão: permite que o Titular de dados apague seus dados pessoais capturados pelos Controladores de dados, possivelmente incluindo os dados armazenados no Adobe Campaign. </li> 
    </ul> Para obter mais informações, consulte a <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy.html">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer para Email (Beta)<br /> </td> 
   <td> O novo Creative Designer da Adobe Campaign oferece uma experiência de criação totalmente integrada no Campaign, permitindo a criação visual rápida e sem esforços de emails atraentes e personalizados individualmente, sem a necessidade de criar scripts para uma única linha de código. Por meio de sua poderosa interface de arrastar e soltar, o Creative Designer ajuda a dimensionar a criação de emails, independentemente de os usuários começarem de uma página em branco ou aproveitarem os Fragmentos ou modelos de conteúdo existentes. <br /> Os principais recursos incluem:<br /> 
    <ul> 
     <li> Projete visualmente e crie emails responsivos e totalmente personalizados por meio de uma interface de arrastar e soltar, aumentada por integrações de Creative Cloud nativas </li> 
     <li> Crie e salve um modelo de conteúdo de email e utilize os modelos salvos para ajudar a dimensionar a criação de emails </li> 
     <li> Criar e salvar fragmentos de conteúdo (como um cabeçalho, rodapé, artigo, etc.) para simplificar a criação de conteúdo e garantir a consistência da marca </li> 
     <li> Alterne facilmente entre criar na interface de arrastar e soltar e editar diretamente o HTML de um email com apenas um clique </li> 
    </ul> O Creative Designer para Email está disponível somente em inglês.<br /> Para obter mais informações, consulte <a href="../../designing/using/designing-content-in-adobe-campaign.md">documentação detalhada</a> e assista a isto <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">vídeo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Deliveries de push multilíngues<br /> </td> 
   <td> A mesma interface multilíngue simples, que já existe nos canais de email e SMS, foi adicionada ao canal Push para ajudar você a engajar os clientes, independentemente do idioma preferido.<br /> Esse recurso oferece uma solução escalável e automática para clientes que gerenciam campanhas por push abrangendo várias regiões e que desejam direcionar os usuários em seu idioma preferido. Ele permite fazer upload de todas as variantes linguais por meio de uma planilha com modelo para um único delivery por push com um único clique. O Adobe Campaign realiza uma segmentação automática com base na preferência de idioma dos usuários, ajudando a reduzir as redundâncias simplificando os fluxos de trabalho e os relatórios.<br /> Para obter mais informações, consulte <a href="../../channels/using/creating-a-multilingual-push-notification.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Uso de recursos personalizados em mensagens transacionais<br /> </td> 
   <td> Além dos campos prontos para uso, as mensagens transacionais agora permitem que você use recursos personalizados para enriquecer o conteúdo de suas mensagens.<br /> Por exemplo:<br /> 
    <ul> 
     <li> Usar campos personalizados como critérios de reconciliação para corresponder uma mensagem transacional a um perfil </li> 
     <li> Aproveite perfis completos, serviços e dados vinculados para personalizar ainda mais as mensagens transacionais </li> 
    </ul> Para obter mais informações, consulte a <a href="../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Platform_

* Correção de um problema que impedia a exportação de mais de 5000 registros de uma lista.
* Correção de um problema ao exportar dados para arquivos nomeados com campos de personalização.

_Emails, mensagens SMS e correspondência direta_

* Correção de um problema que fazia com que o SMS de várias partes fosse truncado porque o tamanho das partes era calculado em caracteres em vez de bytes.
* Adicionada uma opção que permite a **[!UICONTROL Delivered]** ou **[!UICONTROL Bounces + Errors]** KPIs a serem atualizados em tempo real após o envio do delivery. Eles são recalculados diretamente do SR (relatório de status) recebido do provedor.
* Correção de um problema com o widget de calendário no agendador de delivery.
* Correção de um problema de exibição ao abrir um target pela segunda vez em um delivery enviado.
* Correção de um problema que resultava em uma mensagem de erro solicitando uma data de início, ao criar um template de email com uma data de envio atrasada.
* Correção de um problema que poderia causar problemas de renderização de imagem ao editar o conteúdo de um delivery.
* Correção de um problema com provas ao duplicar uma campanha.
* Correção de um problema que resultava em uma mensagem de erro ao acessar um template de campanha por meio da barra de navegação após adicionar um delivery ao workflow.
* Correção de um problema que impedia que o vencedor de um email de teste A/B fosse selecionado automaticamente, resultando no não envio do email. Esse comportamento pode ocorrer se o delivery estiver em **[!UICONTROL retryInProgress]** estado.
* Correção de um problema que poderia resultar na exibição de uma mensagem de erro ao reabrir os parâmetros de um email de teste A/B.

_Públicos-alvo e consultas_

* Correção de um problema que impedia o acesso aos dados e a configuração de queries para recipients replicados do Adobe Campaign Classic para o Standard.
* Correção de um problema que ocorria ao usar um campo de tipo de filtro no editor de query, após usar o **Contagem** ou **Visualizar** botões.

_Workflows_

* A variável **Faturamento** O fluxo de trabalho do foi otimizado para melhorar o atraso de preparação do delivery.
* Correção de um problema que impedia a exibição de dados de população em uma transição de saída ao usar uma atividade de delivery recorrente.
* Correção de um problema que impedia que registros de rejeição fossem exibidos em uma transição após um **Atualizar dados** atividade.
* Correção de um problema que poderia causar **deliverabilityUpdate** fluxo de trabalho técnico que falhará.

_Integrações_

* Correção de um problema que impedia que caracteres internacionais fossem enviados corretamente para o Adobe Analytics.
* Os ativos agora devem ser carregados mais rapidamente ao tentar inserir uma imagem da biblioteca de ativos Experience Cloud em uma mensagem.
* Correção de um problema que poderia impedir que a janela de seleção de ativos fosse fechada em alguns casos.
* Em um detalhe de fonte de dados, agora é possível acessar diretamente o fluxo de trabalho relacionado para verificar o estado do fluxo de trabalho.
* Agora você pode atualizar o esquema Acionadores diretamente ao definir ou editar um evento de acionador. Com essa alteração, não é mais necessário cancelar a publicação do acionador e criar outro.

_Mensagens transacionais_

* Correção de um erro com o template de mensagem transacional quando o recurso de delivery era estendido.
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
   <td> Assinatura - assine ou cancele a assinatura de uma lista de perfis para vários serviços<br /> </td> 
   <td> A variável <strong>Serviços de assinatura</strong> a atividade de workflow agora permite assinar ou cancelar a assinatura de uma lista de perfis para vários serviços. No fluxo de trabalho, importe um arquivo contendo os perfis e, para cada perfil, o tipo de operação e o serviço. A variável <strong>Serviços de assinatura</strong> A atividade do poderá usar essas informações e lidar dinamicamente com todas as assinaturas de perfis e cancelamentos de assinaturas de uma só vez.<br /> Para obter mais informações, consulte <a href="../../automating/using/subscription-services.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Atividade de Enriquecimento - enriqueça os dados com base em transições anteriores<br /> </td> 
   <td> O novo <span class="uicontrol">Enriquecimento</span> a atividade de workflow permite aproveitar as transições de entrada e concluir a transição de saída com dados adicionais. Se você selecionar perfis, a atividade de enriquecimento permitirá enriquecer as informações dos perfis com dados adicionais que não estão armazenados no banco de dados (provenientes de um arquivo importado, por exemplo).<br /> Para obter mais informações, consulte <a href="../../automating/using/enrichment.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Platform_

* A barra superior da interface do Adobe Campaign foi atualizada com o novo menu Experience Cloud.
* Correção de um problema que impedia o link para **[!UICONTROL Offers]** de ser exibido na lista suspensa solução.

_Emails, mensagens SMS e correspondência direta_

* A fase de preparação da entrega foi aprimorada para melhorar o desempenho.
* Correção de vários problemas que poderiam fazer com que os logs de rastreamento fossem corrompidos em algumas situações de nicho.
* Correção de um problema de atualização da data de contato que ocorria quando a data de contato era alterada entre a preparação da entrega e a confirmação. Agora, ao alterar a data de contato após a preparação, é necessário preparar o delivery novamente antes de poder confirmar o envio. Consulte a [documentação detalhada](../../sending/using/preparing-the-send.md).

_Notificações por push_

* Correção de um erro que impedia que alguns campos de personalização funcionassem em notificações por push do iOS.
* Correção de um erro que exibia as taxas de clique e abertura como 0% no painel de notificação por push.

_Relatórios_

* Correção de um erro que mostrava a lista de relatórios como vazia em alguns navegadores.
* Correção de um erro que ocorria no **[!UICONTROL Report sharing]** fluxo de trabalho técnico antes de seu limite de expiração ser atingido.

_Workflows_

* Correção de um problema que impedia que as atividades ficassem acessíveis após arrastá-las e soltá-las.
* Correção de um problema que poderia causar a ordem das transições de saída de um **[!UICONTROL Segmentation]** atividade a ser alterada em algumas situações.
* Correção de um erro que ocorria ao ler um público-alvo contendo um campo do tipo lista discriminada e que tinha sido salvo anteriormente de um fluxo de trabalho
* Correção de um problema que causava a **[!UICONTROL Request confirmation before sending messages]** opção para permanecer marcada mesmo após desmarcá-la ao definir as propriedades de agendamento de um delivery criado em um workflow.
* A remoção automática de linhas duplicadas (cláusula DISTINCT) agora pode ser desativada no **[!UICONTROL Query]** por meio de uma nova opção localizada no campo **[!UICONTROL Additional data]** guia. A desativação dessa opção é recomendada ao definir muitos (mais de 100) elementos adicionais, por motivos de desempenho.

_Integrações_

* Foram introduzidas algumas melhorias no **[!UICONTROL Data sources]** tela de configuração.

_Problemas conhecidos_

Recomendamos que você não use o Internet Explorer versão 11 devido a possíveis problemas de exibição.

Alguns problemas podem ocorrer ao usar links de ajuda contextual da interface do Campaign. Eles serão corrigidos no 18.3.

## Versão 18.1 – Janeiro de 2018 {#release-18-1---january-2018}

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
   <td> Os relatórios para gerenciamento de fadiga são um relatório dedicado e configurável que exibe o impacto das regras de fadiga nas entregas nos canais de email, push, SMS e correspondência direta dentro de um intervalo de datas especificado antes do envio. Com a visão adicional de poder ver rapidamente todas as campanhas conflitantes em uma única visualização, os profissionais de marketing podem planejar campanhas de marketing de acordo com as regras de fadiga definidas com mais eficiência e priorizar comunicações.<br /> Para obter mais informações, consulte <a href="../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Compartilhamento de relatórios<br /> </td> 
   <td> O Compartilhamento de relatórios permite compartilhar seus relatórios com usuários do Adobe Campaign como um anexo de email, incluindo de forma automatizada e recorrente. Os usuários que recebem relatórios recorrentes podem cancelar a inscrição dessas comunicações por meio de um link dedicado em cada email.<br /> Para obter mais informações, consulte <a href="../../reporting/using/reporting-interface.md#share-tab">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Enviar novos recursos<br /> </td> 
   <td> Visualização das mensagens de push: visualize as notificações das mensagens de push em dispositivos iOS e Android de dentro do editor de conteúdo de notificações de mensagens de push para ver exatamente o que os destinatários verão antes de testar ou executar o envio.<br /> Para obter mais informações, consulte <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">documentação detalhada</a>.<br /> Conteúdo disponível: quando aplicativos não são abertos por longos períodos de tempo, seus dados podem se tornar obsoletos. Isso resulta na atualização ou substituição dos dados no momento em que um usuário finalmente abre o aplicativo, o que pode causar atrasos no uso do aplicativo. Com a ajuda adicional do Conteúdo disponível, os usuários do Adobe Campaign podem ativar o aplicativo para atualizar os dados em segundo plano ao enviar uma notificação por push, permitindo maior consistência e controle sobre a experiência no aplicativo de um usuário.<br /> Conteúdo variável: com a ajuda adicional do conteúdo variável, os usuários do Adobe Campaign agora podem aproveitar as extensões de aplicativos para dispositivos móveis para modificar ainda mais o conteúdo ou a apresentação de notificações de mensagens de push enviadas pelo Adobe Campaign. Por exemplo, os usuários podem aproveitar o conteúdo mutável para: <br /> 
    <ul> 
     <li> descriptografar dados que foram entregues em formato criptografado </li> 
     <li> baixar imagens ou outros arquivos de mídia e adicioná-los como anexos a uma notificação </li> 
     <li> alterar o texto do corpo ou do título de uma notificação </li> 
     <li> adicionar um identificador de thread a uma notificação </li> 
    </ul> Para obter mais informações sobre Conteúdo disponível e Conteúdo mutável, consulte a <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">documentação detalhada</a>.<br /> <strong>Aviso:</strong> essas atualizações nas notificações por push exigem que os clientes atualizem seus aplicativos móveis. Consulte <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/push-payload.html">esta nota técnica</a> para obter mais informações.<br /> </td> 
  </tr> 
  <tr> 
   <td> Deliveries otimizados para fuso horário<br /> </td> 
   <td> Programe notificações por email, SMS e por push recorrentes para serem entregues em um dia/hora específico no fuso horário de cada recipient, garantindo que suas mensagens sejam entregues na hora certa, sem configurar vários deliveries. <br /> Para obter mais informações, consulte <a href="../../automating/using/scheduler.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Acionamento da atividade de sinal da API<br /> </td> 
   <td> Agora é possível acionar uma atividade de sinal para seus workflows diretamente da API do Adobe Campaign Standard.<br /> Para obter mais informações, consulte <a href="/help/api/using/triggering-a-signal-activity.md">documentação detalhada</a> .<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Platform_

* A pesquisa de perfil foi otimizada para melhorar o desempenho.
* O identificador interno de grupos de segurança padrão agora está no modo somente leitura para usuários padrão.

_Emails, mensagens SMS e correspondência direta_

* Correção de um problema de exibição que ocorria ao inserir emojis no conteúdo dos deliveries.
* Correção de um problema que permitia ao usuário acessar logs de envio quando o delivery ainda estava em edição.
* A variável **[!UICONTROL Scheduler]** A atividade agora permite enviar os deliveries dependendo do fuso horário do recipient.
* SMS: a opção **[!UICONTROL Store incoming MO]** no banco de dados foi adicionado a contas externas. Quando marcado, todo o SMS de entrada será armazenado na variável **inSMS** tabela.
* SMS: os serviços agora estão anexados a um evento em vez de um template transacional.
* SMS: o tempo limite da conexão SMTP padrão foi reduzido para 30 segundos.

_Notificações por push_

* Correção de um erro que impedia que os deliveries de notificação por push fossem interrompidos.
* Adicionada uma opção nas opções avançadas de notificação por push para ativar o aplicativo com uma notificação por push.
* Adição de um botão Pausar para o vídeo de visualização de notificação por push.
* A pré-visualização de notificação por push agora está disponível para diferentes dispositivos, como iPhone, Android, tablets.

_Relatórios_

* Correção de um erro que exibia taxas acima de 100%.
* Correção de um problema que impedia usuários de baixar relatórios em CSV.
* Adição de um novo **[!UICONTROL Report]** item na página inicial.

_Workflows_

* Correção de um problema que resultava em uma mensagem de erro ao usar dados adicionais em um query e adicionar aliases contendo espaços. Os caracteres não alfanuméricos agora são substituídos por &quot;_&quot;.
* Correção de um problema em que o workflow técnico que calcula KPIs podia ser interrompido por padrão em alguns casos.

_Perfis e públicos_

* Correção de um erro que ocorria ao adicionar vários filtros no query de um público.
* Correção de um problema de exibição que ocorria ao alterar a imagem de um perfil.
* Adição de uma dica de ferramenta exibindo o número exato do resultado após a contagem da população de um query.
* Correção de um problema que impedia um usuário de selecionar um público ou fechar a janela do seletor de público.
* A lista de funções disponíveis no editor de expressão foi atualizada. A variável **FormatCurrency** e **ConvertCurrency** As funções do foram removidas.
