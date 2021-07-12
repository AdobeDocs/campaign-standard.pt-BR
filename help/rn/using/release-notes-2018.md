---
solution: Campaign Standard
product: campaign
title: Notas de versão de 2018
description: Essa página lista todas as versões de 2018 do Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Visão geral
role: User
level: Beginner
exl-id: 17521357-14ae-4751-bd7c-aeabbcf71d07
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '5401'
ht-degree: 10%

---

# Notas de versão de 2018{#release-notes}

Procurando uma versão específica de 2018 do Adobe Campaign Standard?

Cada versão vem com novos recursos e patches. Clique em uma versão para exibir seu conteúdo.

Visualize as [atualizações de documentação](../../rn/using/documentation-updates.md) mais recentes para o Adobe Campaign Standard. Se estiver procurando uma versão mais recente, consulte esta [página](../../rn/using/release-notes.md).

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
   <td> As mensagens no aplicativo permitem que você garanta o envolvimento de usuários de aplicativos móveis com mais eficiência, fornecendo interação contextual e permitindo que alcançar os usuários que optaram por notificações por push. Use as mensagens no aplicativo em conjunto com as notificações por push para criar uma experiência altamente personalizada e relevante. Isso leva a uma melhor conversão e retenção dos usuários do aplicativo.<br /><a href="../../channels/using/about-in-app-messaging.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integração do Adobe Launch para aplicativos móveis (beta)<br /> </td> 
   <td> A integração do Adobe Launch com o Adobe Campaign agora simplifica e automatiza o processo de ativação da Propriedade de aplicativo móvel no Campaign usando o Mobile SDK V5.<br /><a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Melhorias**

* O Adobe Campaign Standard agora é compatível com a versão 4 da API do Amazon S3.

**Outras alterações**

* Há agora uma distinção nos broadlogs entre o número máximo de conexões e o número máximo de mensagens por hora. Quando os limites são atingidos, é possível saber o motivo da taxa de transferência ser limitada. Anteriormente, a mesma mensagem (‘cota atingida’) se aplicava a ambos os casos.
* Ao configurar um aplicativo móvel no Campaign, o usuário pode saber se o certificado do iOS e a chave do servidor Android foram carregados com êxito e a data de expiração.

   Para obter mais informações, consulte a documentação detalhada sobre como configurar um aplicativo móvel usando [SDK V4](https://helpx.adobe.com/br/campaign/kb/configuring-app-sdkv4.html) e [SDK V5](https://helpx.adobe.com/br/campaign/kb/configuring-app-sdk.html).

* Direcione usuários em um aplicativo móvel específico selecionando um aplicativo móvel enquanto define as propriedades da campanha. Esse recurso é para canais de mensagens de push e no aplicativo.

   Para obter mais informações, consulte a [documentação detalhada](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification).

* Ao selecionar um bloco de conteúdo usando a interface do Creative Designer, todos os blocos de conteúdo da lista agora são carregados e exibidos. (CAMP-27311)

   Para obter mais informações, consulte a [documentação detalhada](../../designing/using/personalization.md#adding-a-content-block).

**Correções**

* Correção de um problema que mostrava uma discrepância nas contagens de log entre o painel de email e o relatório de resumo de email para emails transacionais. (CAMP-28237
* Correção de um problema em workflows que poderia exibir uma mensagem de erro ao importar um arquivo por meio de uma atividade File transfer . (CAMP-27435)
* Correção de um problema com landing pages contendo mais de 25 serviços, que resultava na desseleção aleatória de serviços no formulário. (CAMP-26572)
* Correção de um problema em workflows que impedia a configuração de contas externas com um URL SFTP ao usar a atividade de transferência de arquivo . (CAMP-26475)
* Correção de um problema que impedia a atualização do relatório de resumo de serviços. (CAMP-26301)
* Correção de um problema em workflows ao usar uma atividade Enrichment , que impedia que um campo personalizado exibisse a data correta. (CAMP-26242)
* Correção de um problema que impedia que as datas da assinatura do serviço fossem atualizadas quando importadas por meio de uma importação de arquivo.
* Correção de um erro com a atividade de carregamento de arquivo que impedia os workflows de importar arquivos (CAMP-27068).
* Correção de um problema que exibia o número incorreto de subscrições nos Relatórios de resumo do serviço (CAMP-25587).
* Correção de um problema de discrepância de dados entre relatórios do Adobe Analytics e do Adobe Campaign. (CAMP-25393)
* Correção de um problema que impedia que um usuário de acesso limitado fizesse logon. (CAMP-27381)
* Correção de um problema que impedia a exibição da lista de conteúdos do Adobe Experience Manager ao editar um email usando o Creative Designer. (CAMP-27181)
* Correção de um problema que impedia a abertura do Creative Designer, causando um erro. (CAMP-27304)
* Correção de um problema que impedia o funcionamento correto do recurso de arrastar e soltar no Creative Designer ao usar o Internet Explorer 11.
* Correção de um problema que fazia com que as fotos carregadas de uma câmera e capturadas no modo retrato fossem exibidas em uma posição girada indesejada.
* Correção de um problema que exibia informações de seleção não claras ao usar a interface do editor de consultas no Creative Designer.
* Correção de um problema que impedia a duplicação correta de um elemento ao usar a interface do editor de consultas no Creative Designer.
* Correção de um problema que mantinha o delivery de mensagens SMS aos recipients na  da lista de bloqueios, mesmo que a subscrição tenha sido cancelada por meio de uma resposta automática. (CAMP-27128)
* Correção de um problema que impedia a exibição dos erros que causavam a falha do workflow **Database Cleanup**. (CAMP-26876)
* Correção de um problema que poderia impedir a exclusão de campos personalizados em uma definição de notificação por push. (CAMP-25588)

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
   <td> Sinalizador de alta prioridade para Android - Habilite a entrega de uma notificação por push com alta prioridade para aplicativos Android, o que faz com que o dispositivo de espera desperte e execute algum processamento limitado. Observe que a prioridade padrão é Normal, o que pode atrasar a entrega de mensagens para economizar bateria. <br /><a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Filtro de tipologia para assinantes de aplicativos móveis<br /> </td> 
   <td> Assinaturas de suporte no filtro de tipologia - ao especificar os critérios de filtragem para uma regra de tipologia, as assinaturas do aplicativo podem ser selecionadas como dimensões de filtragem e direcionamento, fornecendo a capacidade de filtrar em atributos para usuários com ou sem perfil. <br /><a href="../../sending/using/about-typology-rules.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Importação de conteúdo automatizada de um URL durante a preparação da mensagem<br /> </td> 
   <td> Agora é possível importar conteúdo de email de um URL durante a fase de preparação. Para deliveries de email recorrentes, o conteúdo HTML mais recente é recuperado toda vez que a mensagem é preparada, garantindo que o conteúdo esteja sempre atualizado no momento em que o email é enviado. Esse recurso também permite criar um delivery agendado com conteúdo de um URL, mesmo se o conteúdo ainda não estiver pronto.<br /><a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mensagem de notificação de versão da campanha<br /> </td> 
   <td> Uma mensagem pop-up agora é exibida quando um usuário faz logon depois que a instância é atualizada para uma nova versão. A mensagem indica o número da versão e inclui um link para as notas de versão. Você pode optar por ocultar a mensagem até o próximo lançamento. <br /> </td> 
  </tr> 
  <tr> 
   <td> Gerenciamento de usuários<br /> </td> 
   <td> O recurso de unidade geográfica agora está indisponível para novas instâncias do Campaign Standard, bem como instâncias existentes sem unidades geográficas criadas, a partir da versão 18.7.<br /><a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=pt-BR#release-notes"> Para obter mais informações, consulte esta página</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Melhorias**

* A integração Adobe Campaign e Adobe Target agora permite aproveitar o recurso [Permissões](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html?lang=pt-BR) do Target. Ao incluir uma imagem dinâmica do Adobe Target em um email, agora você pode especificar uma Propriedade do Target (código at_property).
* Os recursos personalizados que têm um link de cópia própria para o recurso de perfis agora são considerados pelas solicitações de acesso/exclusão da Privacidade de GDPR. Para 1 cardinalidade links simples e N links de coleção de cardinalidade, é necessário selecionar &quot;Excluir/Duplicar o registro de destino implica excluir/duplicar os registros referenciados pelo link&quot; no recurso personalizado. Para links simples de cardinalidade 0 ou 1, selecione &quot;Excluir/Duplicar o registro implica na exclusão/duplicação do registro de destino referenciado pelo link&quot;.

**Outras alterações**

* O tempo limite de compartilhamento de relatórios foi aumentado de um para quatro minutos para evitar tempo limite.
* Ao editar o conteúdo de um email, o novo Creative Designer é aberto por padrão. Se desejar, ainda é possível voltar para o editor de conteúdo padrão a qualquer momento após salvar as alterações. Para obter mais informações, consulte a [documentação detalhada](../../designing/using/designing-content-in-adobe-campaign.md).
* No Creative Designer, um novo componente de conteúdo agora pode ser adicionado a um email: o carrossel. Para obter mais informações, consulte a [documentação detalhada](../../designing/using/designing-from-scratch.md#about-content-components).
* Em um relatório de cliques ativos de mensagem transacional, ao clicar no botão **Change profile**, agora somente os perfis de teste vinculados ao evento que você definiu para a mensagem transacional são listados.

**Correções**

* Correção de um problema com o filtro de query byEmail que não retornava resultados. (CAMP-23420)
* Correção de um problema que permitia que um usuário padrão acessasse determinados recursos ou telas restritas a administradores (/rest/head/* endpoints, telas de mensagens transacionais, perfis e públicos-alvo importando telas).
* Correção de um problema que impedia a exclusão de solicitações de Privacidade de GDPR do processamento de recursos personalizados se o nome começasse por um número.
* Correção de um erro que impedia que a atividade Salvar público-alvo compartilhasse assinantes de aplicativos no Adobe Experience Cloud.
* Correção de um problema com a atividade Transferência de arquivo que ocorria quando o nome do arquivo continha espaços em branco. (CAMP-25936)
* Correção de um problema que poderia ocorrer ao usar o botão de reconexão após a expiração de uma sessão. (CAMP-25560)
* Correção de um problema que poderia resultar em exclusões ao enviar deliveries com otimização de fuso horário associada às regras de fadiga. (CAMP-25425)
* Correção de um problema ao usar o recurso do GDPR da API, que poderia impedir a exclusão de dados com um link do tipo 0-1.
* Correção de um problema que poderia resultar em uma mensagem de erro ao cancelar a edição de uma regra de tipologia de fadiga.
* Correção de um problema que poderia ocorrer ao visualizar um conteúdo de delivery após ele ter sido editado.
* Correção de um problema que poderia ocorrer ao processar arquivos CSV zip ao usar a opção Descompactação .
* Correção de um problema no Creative Designer que resultava em fonte e formatação de cor indesejada ao alterar algum texto com estilo incorporado para um link ou ao editar esse link. (CAMP-26001)
* Correção de um problema que impedia que o relatório de cliques ativos exibisse as porcentagens de cada condição nos deliveries que continham conteúdo dinâmico. Anteriormente, somente os cliques na variante padrão eram exibidos.

## Versão 18.6 - Junho de 2018 {#release-18-6---june-2018}

**Melhorias**

* A API **[!UICONTROL History]** foi adicionada ao Adobe.IO. Ele permite acessar informações relacionadas ao histórico de marketing de um perfil: número de pontos de contato, deliveries enviados, URL da mirror page etc. Para obter mais informações, consulte o [caso de uso dedicado](../../api/using/interacting-with-marketing-history.md) .
* O workflow técnico **[!UICONTROL Database cleanup]** foi otimizado para garantir melhor desempenho para backup de banco de dados.
* O Creative Designer for Email agora também está disponível em francês e alemão.

**Outras alterações**

* Um botão **[!UICONTROL Compute stats]** foi adicionado na janela **[!UICONTROL Deployment]** de deliveries enviados. Ela permite recuperar os KPIs mais recentes, por exemplo, se os resultados do envio levarem muito tempo para serem atualizados ou não tiverem sido considerados. Para obter mais informações, consulte esta [seção](../../sending/using/confirming-the-send.md).
* No workflow técnico pronto para uso **Update for deliverability**, os administradores funcionais agora podem definir o número de erros consecutivos a serem ignorados na atividade **Update rules** do javascript. Por padrão, o valor do campo é definido como 0, o que significa que todos os erros serão ignorados.
* O SQL gerado ao gerenciar condições de restrição de acesso à unidade foi otimizado.
* A atividade **[!UICONTROL Update]** agora permite adicionar, atualizar ou excluir dados relacionados às assinaturas (tabela nms:appSubscriptionRcp ).
* O workflow técnico **[!UICONTROL Update delivery execution]** foi dividido em dois workflows para otimizar o desempenho: - **[!UICONTROL Update delivery execution]**: atualiza o rastreamento do delivery. Ele é iniciado a cada 10 minutos por padrão. **[!UICONTROL Update delivery indicators]**: atualiza os KPIs do delivery, ele é iniciado a cada hora por padrão. Para obter mais informações sobre workflows técnicos, consulte esta [seção](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* Quando um delivery está enviando mensagens, o status na seção **[!UICONTROL Deployment]** agora pode ter dois valores: **[!UICONTROL Sending]**: as mensagens estão sendo enviadas. **[!UICONTROL Sending (retry)]**: está em curso uma nova tentativa.
* Os usuários com a função **[!UICONTROL Delivery preparation]** agora podem enviar provas. (CAMP-24313)
* A opção **Enable TLS over SMPP** foi adicionada ao **SMS routing via conta externa SMPP**. Para obter mais informações, consulte [esta seção](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

**Correções**

* Correção de um problema que impedia o envio de emails ao incluir uma imagem dinâmica do Adobe Target (CAMP-24848).
* Correção de um problema com os workflows técnicos **[!UICONTROL Privacy Access/Delete Request]**, que não eram concluídos se qualquer solicitação falhasse.
* Correção de um problema que impedia o serviço Principal de Privacidade de receber atualizações de status de solicitação do Campaign.
* Correção de um problema que poderia impedir que o workflow técnico **[!UICONTROL Import shared audience]** funcionasse corretamente (CAMP-25465).
* Correção de um problema que impedia que solicitações de privacidade do Campaign fossem marcadas como concluídas no Privacy Service principal.
* Correção de um problema que impedia determinados usuários de fazer logon no Campaign Standard por meio da autenticação IMS quando a Adobe ID era muito longa. (CAMP-24095)
* Correção de um problema no Creative Designer que poderia ocorrer ao remover módulos de conteúdo. (CAMP-25242)
* Correção de um problema ao usar regras de fadiga de notificações por push para assinantes sem perfil no banco de dados. (CAMP-25344)
* Correção de um problema que poderia exibir uma mensagem de erro ao acessar logs de exclusão de deliveries. (CAMP-24724)
* Correção de um problema que impedia a preparação de provas em instâncias com logs de envio estendidos.
* Correção de dois problemas que poderiam ocorrer ao publicar recursos personalizados com a extensão **[!UICONTROL Sending log]** ativada.
* Correção de um problema que poderia ocorrer com a duração do delivery não levada em conta em deliveries recorrentes.
* Correção de um problema que poderia ocorrer ao classificar dados no menu **[!UICONTROL Client data]**, para recursos personalizados com mais de 100 mil registros. (CAMP-24308)
* Correção de um problema com dimensões de perfil personalizadas que não eram consideradas ao usar a função de pesquisa em Relatórios dinâmicos.
* Correção de um problema com a exibição de dados internacionais para níveis de Conta em Relatórios dinâmicos.
* Agora é possível criar um serviço sem uma mensagem de confirmação de assinatura ou unsubscription.

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
   <td> GDPR: Integração de serviços principais<br /> </td> 
   <td> A Integração do serviço principal de privacidade permite automatizar as solicitações do GDPR em um contexto de várias soluções por meio de uma única chamada de API JSON. <br /> As solicitações do GDPR enviadas do Serviço principal de privacidade para todas as soluções do Experience Cloud agora são tratadas automaticamente pelo Campaign. <br /><a href="https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=pt-BR"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aprimoramentos de push - feedback detalhado do delivery<br /> </td> 
   <td> O Adobe Campaign agora oferece a capacidade de receber feedback detalhado (logs de envio e exclusão) sobre mensagens de push dos provedores (APNS/GCM) por meio do MCPNS.<br /><a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Extensão Logs do delivery<br /> </td> 
   <td> A extensão Logs do delivery permite estender logs de envio com dados de perfil e código de segmento provenientes de workflows. Essas informações podem ser usadas em Relatórios dinâmicos e permitem manter um instantâneo de algumas informações no momento do envio de um delivery.<br /> Há mais 2 casos de uso :<br /> 
    <ul> 
     <li> Exportar broadlogs estendidos com dados "congelados": Como profissional de marketing, eu gostaria de exportar todos os perfis nos quais o código do segmento é igual a "A" (proveniente do mecanismo de fluxo de trabalho). </li> 
     <li> Segmentação em dados "congelados": Como comerciante, eu gostaria de <strong>redirecionar</strong> todos os perfis que ganharam 1000 pontos de fidelidade desde o último envio ou onde o código do segmento era igual a "A". </li> 
    </ul> Para obter mais informações, consulte a <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Relatórios dinâmicos com dados de perfil personalizados<br /> </td> 
   <td> Esse recurso permite criar e gerenciar relatórios com base em dados de perfil personalizados criados durante a extensão de recurso de perfil. Você pode detalhar relatórios por atributo de perfil, como programa de fidelidade, canal preferido, etc.<br /><a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Melhorias**

* A memória geral e o uso da CPU do aplicativo foram aprimorados

**Outras alterações**

* A atividade de workflow Ler público-alvo agora pode ler Experience Cloud audiences. Anteriormente, essa atividade só podia ler públicos-alvo Query e List . Consulte a [documentação detalhada](../../automating/using/read-audience.md). (CAMP-23623)
* O identificador da fonte de dados compartilhada padrão agora está no modo somente leitura e não pode mais ser alterado. Alterar esse identificador pode levar a alguns problemas ao compartilhar públicos com o Experience Cloud.
* Agora a importação de audiências do Audience Manager funciona com arquivos divididos. Anteriormente, somente o último arquivo do segmento era importado pelo workflow técnico importSharedAudience.
* As contas externas do AWS S3 agora oferecem suporte para regiões e ao mecanismo de autenticação da versão 4. Consulte a [documentação detalhada](../../administration/using/external-accounts.md).
* A janela de seleção de Ativo agora deve carregar mais rápido e permitir selecionar um ativo e sair da janela sem nenhum problema.
* As propriedades e a estrutura dos workflows técnicos agora podem ser modificadas por usuários com direitos administrativos e pertencentes às unidades organizacionais e geográficas &quot;Todas&quot;.
* Foram feitos aprimoramentos na interface da atividade de Segmentação ao criar novos segmentos: A guia Limitação agora aparece diretamente após adicionar uma limitação. Os nomes dos novos segmentos agora são incrementados (&quot;Segmento 1&quot;, &quot;Segmento 2&quot;, etc.).
* Um campo &quot;nextProcessingDate&quot; é adicionado ao recurso Fluxo de trabalho. Este campo só é visível por meio de chamadas REST API, e permite visualizar workflows nas próximas datas de processamento.
* O campo &quot;sourceId&quot; agora é exposto no recurso de logs de rastreamento (nms:trackingLog).
* Os valores &quot;Total de aberturas&quot; e &quot;Total de cliques&quot; agora podem ser exportados em um arquivo simples por meio de um workflow. (CAMP-24186)
* O &quot;Inglês - Danmark&quot; está agora disponível na lista de idiomas preferidos em perfis. (CAMP-23728)
* Ao usar uma atividade de Segmentação com um link Additional data (targetData) , uma mensagem agora informa que os dados não estão disponíveis fora do fluxo de trabalho. Essa mensagem é exibida ao clicar no botão Count ou Preview da atividade de Segmentação. (CAMP-23651)
* Foram feitos aprimoramentos para otimizar o espaço em disco usado por workflows: (CAMP-21979): Os arquivos processados pela atividade &quot;Carregar arquivo&quot; agora são excluídos por padrão. Uma opção permite mantê-las para necessidades específicas. Quando um workflow é excluído, sua pasta dedicada é automaticamente suprimida do diretório do servidor.

**Correções**

* Correção de um problema em que alguns eventos de relatório brutos não tinham eventos de rastreamento associados porque o campo eventDate não era preenchido corretamente.
* Correção de um problema que impedia que campos personalizados fossem exibidos na janela de pré-visualização de um delivery de notificação por push.
* Correção de um problema que impedia o texto de vincular o corpo da mensagem de uma notificação por push na janela de visualização.
* Correção de um problema ao enviar um delivery recorrente de um workflow quando o target principal estava vazio.
* Correção de um problema que impedia o acesso a um target mapping se ele estivesse vinculado a um schema inexistente.
* Correção de um problema que poderia ocorrer ao importar um arquivo zip por meio de uma atividade File load . (CAMP-24309)
* Correção de um problema que resultava em um erro PostgreSQL ao enviar um delivery recorrente. (CAMP-23613)
* Correção de um problema que exibia uma mensagem de erro ao enviar uma solicitação de API REST com um atributo JSON vazio. (CAMP-23506)
* Correção de um problema em perfis que criavam maiúsculas e minúsculas como caracteres após o caractere &quot;ß&quot;. (CAMP-23136)
* Correção de um problema ao enviar deliveries usados com a condição de qualificação do bloco de conteúdo dinâmico ou de personalização ao usar atributos de um schema vinculado de perfil. (CAMP-22751)
* Correção de um problema que impedia a exclusão de serviços. (CAMP-22050)
* Correção de um problema que impedia a alteração dos valores de País ou Estado em um perfil de Teste . (CAMP-20426)
* Correção de um problema que impedia o carregamento do Creative Designer. (CAMP-24573)
* Correção de um problema que removia caracteres adicionados após campos de personalização no assunto do email. (CAMP-24113)

## Versão 18.4 - Abril de 2018 {#release-18-4---april-2018}

**Correções**

_Plataforma_

* Correção de um erro que poderia impedir o processamento correto das solicitações de acesso ou exclusão do GDPR. Esse comportamento foi observado em alguns casos raros, onde os dados extraídos continham um dos seguintes caracteres: &amp; &lt; > &quot; &quot;.

_Emails, mensagens SMS e mala direta_

* Correção de um problema que resultava na substituição de KPIs por valores incorretos se a sincronização de broadlog levasse mais de uma hora.

_Fluxos de trabalho_

* Gerenciamento de memória aprimorado e desempenho otimizado em workflows.

_Relatório_

* O fluxo de trabalho de compartilhamento de KPI agora recupera valores de delivery dos últimos 2 meses em vez dos últimos 6 meses. Correção de um problema em que a conta externa de compartilhamento KPI mostrava datas truncadas.
* Correção de um problema que poderia resultar em determinadas mensagens não serem consideradas nas métricas **Enviadas**, **Entregues** e **Rejeição**.
* Correção de um erro que ocorria quando o intervalo de tempo escolhido no **Relatório de Resumo de Delivery** era muito longo.

_Recursos personalizados_

* Correção de um erro que causava a falha da preparação de recursos personalizados.

## Versão 18.3 - março de 2018 {#release-18-3---march-2018}

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
   <td> Creative Designer para Email (Beta)<br /> </td> 
   <td> O novo Creative Designer da Adobe Campaign oferece uma experiência de criação totalmente integrada no Campaign, permitindo a criação visual rápida e sem esforços de emails envolventes e personalizados individualmente sem a necessidade de criar scripts para uma única linha de código. Por meio de sua poderosa interface de arrastar e soltar, o Creative Designer ajuda a dimensionar a criação de emails, independentemente de os usuários começarem de uma tabulação em branco ou aproveitarem os Fragmentos ou modelos de conteúdo existentes. <br /> Os principais recursos incluem:<br /> 
    <ul> 
     <li> Projete visualmente e crie emails totalmente personalizados e responsivos por meio de uma interface de arrastar e soltar, aumentada por integrações de Creative Cloud nativas </li> 
     <li> Crie e salve um modelo de conteúdo de email e aproveite os modelos salvos para ajudar a ampliar a criação de email </li> 
     <li> Criar e salvar Fragmentos de conteúdo (como um cabeçalho, rodapé, artigo etc.) para simplificar a criação de conteúdo e garantir a consistência da marca </li> 
     <li> Alterne facilmente entre criar na interface de arrastar e soltar e editar diretamente o HTML de um email ao clicar em um botão </li> 
    </ul> O Creative Designer for Email só está disponível em inglês.<br /> Para obter mais informações, consulte a documentação  <a href="../../designing/using/designing-content-in-adobe-campaign.md">detalhada </a> e assista a este  <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">vídeo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Deliveries de push multilíngues<br /> </td> 
   <td> A mesma interface multilíngue simples, que já existe nos canais de Email e SMS, foi adicionada ao Canal de push, ajudando você a envolver os clientes independentemente do idioma preferencial.<br /> Esse recurso oferece uma solução escalável e automática para clientes que gerenciam campanhas de push que abrangem várias regiões e desejam direcionar usuários em seu idioma preferido. Ele permite fazer upload de todas as variantes língues por meio de uma planilha modelada para um único delivery de push, com um único clique. O Adobe Campaign executa uma segmentação automática com base na preferência de idioma dos usuários, ajudando a reduzir as redundâncias, simplificando os fluxos de trabalho e os relatórios.<br /><a href="../../channels/using/creating-a-multilingual-push-notification.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Uso de recursos personalizados em mensagens transacionais<br /> </td> 
   <td> Além dos campos prontos, as mensagens transacionais agora permitem usar recursos personalizados para enriquecer o conteúdo de suas mensagens.<br /> Por exemplo:<br /> 
    <ul> 
     <li> Usar campos personalizados como critérios de reconciliação para corresponder uma mensagem transacional a um perfil </li> 
     <li> Aproveite perfis, serviços e dados vinculados completos para personalizar ainda mais as mensagens transacionais </li> 
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
* Adição de uma opção que permite que os KPI **[!UICONTROL Delivered]** ou **[!UICONTROL Bounces + Errors]** sejam atualizados em tempo real após o envio do delivery. Eles são recalculados diretamente do SR (Relatório de Status) recebido do provedor.
* Correção de um problema com o widget de calendário no agendador de delivery.
* Correção de um problema de exibição ao abrir um target por uma segunda vez em um delivery enviado.
* Correção de um problema que resultava em uma mensagem de erro solicitando uma data de início, ao criar um template de email com uma data de envio atrasada.
* Correção de um problema que poderia causar problemas de renderização de imagem ao editar o conteúdo de um delivery.
* Correção de um problema com provas ao duplicar uma campanha.
* Correção de um problema que resultava em uma mensagem de erro ao acessar um template de campanha por meio da barra de navegação, após adicionar um delivery ao workflow.
* Correção de um problema que impedia que o vencedor de um email de teste A/B fosse selecionado automaticamente, fazendo com que o email não fosse enviado. Esse comportamento pode ocorrer se o delivery estiver no estado **[!UICONTROL retryInProgress]**.
* Correção de um problema que resultava na exibição de uma mensagem de erro ao reabrir os parâmetros de um email de teste A/B.

_Públicos-alvo e consultas_

* Correção de um problema que impedia o acesso a dados e a configuração de consultas para recipients replicados do Adobe Campaign Classic para o Standard.
* Correção de um problema que ocorria ao usar um campo de tipo de filtro no Editor de consultas, após usar os botões **Count** ou **Preview** .

_Fluxos de trabalho_

* O workflow **Faturamento** foi otimizado para melhorar o atraso de preparação do delivery.
* Correção de um problema que impedia a exibição de dados de população em uma transição de saída ao usar uma atividade de delivery recorrente.
* Correção de um problema que impedia a exibição de registros de rejeição em uma transição após uma atividade **Update data** .
* Correção de um problema que poderia causar falha no workflow técnico **deliverabilityUpdate** .

_Integrações_

* Correção de um problema que impedia o envio correto de caracteres internacionais para o Adobe Analytics.
* Os ativos agora devem carregar mais rápido ao tentar inserir uma imagem da biblioteca de Experience Cloud asset em uma mensagem.
* Correção de um problema que impedia o fechamento da janela de seleção de ativos em alguns casos.
* Em um detalhe de fonte de dados, agora é possível acessar diretamente seu fluxo de trabalho relacionado para verificar o estado do fluxo de trabalho.
* Agora você pode atualizar o schema de acionadores diretamente ao definir ou editar um evento de acionador. Com essa alteração, não é mais necessário desfazer a publicação do acionador e criar outro.

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
   <td> A atividade de workflow <strong>Subscription Services</strong> agora permite assinar ou cancelar a assinatura de uma lista de perfis para vários serviços. No seu fluxo de trabalho, importe um arquivo contendo os perfis e, para cada perfil, o tipo de operação e o serviço. A atividade <strong>Subscription Services</strong> poderá usar essas informações e lidar dinamicamente com todas as assinaturas e unsubscriptions de perfis de uma só vez.<br /><a href="../../automating/using/subscription-services.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Atividade de Enriquecimento - enriqueça os dados com base em transições anteriores<br /> </td> 
   <td> A nova atividade de workflow <span class="uicontrol">Enrichment</span> permite aproveitar as transições de entrada e concluir a transição de saída com dados adicionais. Se você direcionar perfis, a atividade de enriquecimento permitirá enriquecer as informações dos perfis com dados adicionais que não são armazenados no banco de dados (provenientes de um arquivo importado, por exemplo).<br /><a href="../../automating/using/enrichment.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Plataforma_

* A barra superior da interface do Adobe Campaign foi atualizada com o novo menu Experience Cloud.
* Correção de um problema que impedia a exibição do link para **[!UICONTROL Offers]** na lista suspensa da solução.

_Emails, mensagens SMS e mala direta_

* A fase de preparação do delivery foi aprimorada para melhorar o desempenho.
* Correção de vários problemas que resultavam na corrupção de logs de rastreamento em algumas situações de nicho.
* Correção de um problema de atualização da data de contato que ocorria quando a data de contato era alterada entre a preparação do delivery e a confirmação. Agora, quando você alterar a data de contato após a preparação, será necessário preparar o delivery novamente antes de poder confirmar o envio. Consulte a [documentação detalhada](../../sending/using/preparing-the-send.md).

_Notificações por push_

* Correção de um erro que impedia que alguns campos de personalização funcionassem em notificações por push do iOS.
* Correção de um erro que exibia as taxas de clique e de abertura como 0% no painel de notificação por push.

_Relatórios_

* Correção de um erro que exibia a lista de relatórios como vazia em alguns navegadores.
* Correção de um erro que ocorria no workflow técnico **[!UICONTROL Report sharing]** pouco antes de o limite de expiração ser atingido.

_Fluxos de trabalho_

* Correção de um problema que impedia o acesso das atividades após arrastar e soltar.
* Correção de um problema que poderia fazer com que a ordem das transições de saída de uma atividade **[!UICONTROL Segmentation]** fosse alterada em algumas situações.
* Correção de um erro que ocorria ao ler um público-alvo contendo um campo do tipo enumeração e que havia sido salvo anteriormente de um workflow
* Correção de um problema que fazia com que a opção **[!UICONTROL Request confirmation before sending messages]** permanecesse marcada mesmo após desmarcá-la ao definir as propriedades de agendamento de um delivery criado em um workflow.
* A remoção automática de linhas duplicadas (cláusula DISTINCT) agora pode ser desativada em **[!UICONTROL Query]** atividades, por meio de uma nova opção localizada na guia **[!UICONTROL Additional data]** . A desativação dessa opção é recomendada ao definir muitos (mais de 100) elementos adicionais, por motivos de desempenho.

_Integrações_

* Foram feitos alguns aprimoramentos na tela de configuração **[!UICONTROL Data sources]**.

_Problemas conhecidos_

Recomendamos que você não use o Internet Explorer versão 11 devido a possíveis problemas de exibição.

Alguns problemas podem ocorrer ao usar links de ajuda contextual da interface do Campaign. Serão fixadas no ponto 18.3.

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
   <td> Relatório para gerenciamento de fadiga<br /> </td> 
   <td> O relatório para gerenciamento de fadiga é um relatório dedicado e configurável que exibe o impacto das regras de fadiga nos deliveries nos canais de Email, Push, SMS e Mala direta dentro de um intervalo de datas especificado antes do envio. Com o insight adicional de poder ver rapidamente todas as campanhas conflitantes em uma única visualização, os profissionais de marketing são capazes de planejar campanhas de marketing de acordo com o conjunto de regras de fadiga com mais eficiência e priorizar as comunicações.<br /><a href="../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Compartilhamento de relatórios<br /> </td> 
   <td> O Compartilhamento de relatórios permite compartilhar seus relatórios com usuários do Adobe Campaign como um anexo de email, incluindo de forma recorrente automatizada. Os usuários que recebem relatórios recorrentes têm a capacidade de cancelar a assinatura dessas comunicações por meio de um link dedicado em cada email.<br /><a href="../../reporting/using/reporting-interface.md#share-tab"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Encaminhar novos recursos<br /> </td> 
   <td> Visualização das mensagens de push : visualize as notificações das mensagens de push em dispositivos iOS e Android de dentro do editor de conteúdo de notificações de mensagens de push para ver exatamente o que os destinatários verão antes de testar ou executar o envio.<br /><a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification"> Para obter mais informações, consulte a documentação</a> detalhada.<br /> Conteúdo disponível : quando aplicativos não são abertos por longos períodos de tempo, seus dados podem se tornar obsoletos. Isso resulta nos dados terem de ser atualizados ou substituídos no momento em que um usuário finalmente abre o aplicativo, o que pode causar atrasos no uso do aplicativo. Com o suporte adicional de Conteúdo disponível, os usuários do Adobe Campaign podem acordar seu aplicativo para atualizar seus dados em segundo plano ao fornecer uma notificação por push, permitindo maior consistência e controle sobre a experiência do usuário no aplicativo.<br /> Conteúdo variável : com a ajuda adicional do conteúdo variável, os usuários do Adobe Campaign agora podem aproveitar as extensões de aplicativos para dispositivos móveis para modificar ainda mais o conteúdo ou a apresentação de notificações de mensagens de push enviadas pelo Adobe Campaign. Por exemplo, os usuários podem aproveitar o Conteúdo variável para: <br /> 
    <ul> 
     <li> descriptografar dados que foram entregues em um formato criptografado </li> 
     <li> baixar imagens ou outros arquivos de mídia e adicioná-los como anexos a uma notificação </li> 
     <li> alterar o texto do corpo ou do título de uma notificação </li> 
     <li> adicionar um identificador de thread a uma notificação </li> 
    </ul> Para obter mais informações sobre Conteúdo disponível e Conteúdo mutável, consulte a <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">documentação detalhada</a>.<br /> <strong>Aviso:</strong> essas atualizações nas notificações por push exigem que os clientes atualizem seus aplicativos móveis. Consulte <a href="https://helpx.adobe.com/br/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html">esta nota técnica</a> para obter mais informações.<br /> </td> 
  </tr> 
  <tr> 
   <td> Deliveries otimizados para fuso horário<br /> </td> 
   <td> Programe emails, SMS e notificações por push recorrentes para serem entregues em um dia/hora específico em cada fuso horário dos recipients, garantindo que suas mensagens sejam entregues no horário certo sem configurar vários deliveries. <br /><a href="../../automating/using/scheduler.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Acionamento da atividade de Sinal da API<br /> </td> 
   <td> Agora é possível acionar uma atividade de sinal para os workflows diretamente da API do Adobe Campaign Standard.<br /><a href="/help/api/using/triggering-a-signal-activity.md"> Para obter mais informações, consulte a documentação detalhada</a> .<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Plataforma_

* A pesquisa de perfil foi otimizada para melhorar o desempenho.
* O identificador interno de grupos de segurança padrão agora está no modo somente leitura para usuários padrão.

_Emails, mensagens SMS e mala direta_

* Correção de um problema de exibição que ocorria ao inserir emojis no conteúdo dos deliveries.
* Correção de um problema que permitia ao usuário acessar logs de envio quando o delivery ainda estava na edição.
* A atividade **[!UICONTROL Scheduler]** agora permite enviar os deliveries, dependendo do fuso horário do recipient.
* SMS: A opção **[!UICONTROL Store incoming MO]** no banco de dados foi adicionada a contas externas. Quando marcado, todo o SMS recebido será armazenado na tabela **inSMS**.
* SMS: Os serviços agora são anexados a um evento em vez de a um modelo transacional.
* SMS: O tempo limite da conexão SMTP padrão foi reduzido para 30 segundos.

_Notificações por push_

* Correção de um erro que impedia a interrupção dos deliveries de notificações por push.
* Adicionada uma opção nas opções avançadas de notificação por push para ativar o aplicativo com uma notificação por push.
* Adição de um botão pausar para o vídeo de visualização da notificação por push.
* A visualização da notificação por push agora está disponível para diferentes dispositivos, como iPhone, Android, tablets.

_Relatórios_

* Correção de um erro que exibia taxas acima de 100%.
* Correção de um problema que impedia usuários de baixar relatórios em CSV.
* Adição de um novo item **[!UICONTROL Report]** na página inicial.

_Fluxos de trabalho_

* Correção de um problema que resultava em uma mensagem de erro ao usar dados adicionais em um query e adicionar aliases contendo espaços. Os caracteres não alfanuméricos agora são substituídos por &quot;_&quot;.
* Correção de um problema em que o workflow técnico que calcula KPIs poderia ser interrompido por padrão em alguns casos.

_Perfis e públicos_

* Correção de um erro que ocorria ao adicionar vários filtros em um query de público.
* Correção de um problema de exibição que ocorria ao alterar a imagem de um perfil.
* Adição de uma dica de ferramenta que exibe o número exato do resultado após a contagem da população de um query.
* Correção de um problema que impedia um usuário de selecionar um público ou fechar a janela do seletor de público.
* A lista de funções disponíveis no editor de expressão foi atualizada. As funções **FormatCurrency** e **ConvertCurrency** foram removidas.
