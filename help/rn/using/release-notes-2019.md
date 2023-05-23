---
title: Notas de versão de 2019
description: Essa página lista todas as versões de 2019 do Adobe Campaign Standard.
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 6a53e6f5-9b69-4068-ab7d-10e22e266277
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '7556'
ht-degree: 9%

---

# Notas de versão de 2019{#release-notes-2019}

## Versão 19.4 - dezembro de 2019 {#release-19-4---october-2019}

**Novidades**

<table> 
 <thead> 
  <tr> 
   <th> <strong>California Consumer Privacy Act (CCPA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A CCPA é a nova lei de privacidade do estado da Califórnia que adequa e moderniza os requisitos de proteção de dados que entram em vigor em 01 de janeiro de 2020. O CCPA se aplica aos clientes do Adobe Campaign que coletam dados de residentes da Califórnia.</p>
   <p>Além dos recursos de privacidade já disponíveis no Adobe Campaign (incluindo gerenciamento de consentimento, configurações de retenção de dados e funções de usuário), estamos aproveitando esta oportunidade para incluir recursos adicionais, de forma a ajudar a facilitar sua preparação para a CCPA:</p>
   <ul>
    <li>Direito de acesso e direito de exclusão: estamos nos beneficiando dos recursos que foram adicionadas ao GDPR. <a href="https://helpx.adobe.com/content/help/br/campaign/kb/acs-privacy.html#righttoaccess">Saiba mais</a> </li>
    <li><p>Ao criar uma solicitação de privacidade, o tipo de regulamento (GDPR ou CCPA) foi adicionado ao Serviço principal de privacidade. Esse é método que você deve usar para todas as solicitações de acesso e exclusão. O uso da API e da interface do Campaign para solicitações de acesso e exclusão ficará obsoleto.  Consulte o <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=pt-BR#release-notes">artigo Recursos obsoletos e removidos</a>.</p></li>
    <li>A <strong>Recusa da CCPA</strong> O campo foi adicionado ao recurso Perfis para permitir que os usuários do Adobe Campaign rastreiem se um consumidor optou por não participar da venda de Informações pessoais. <a href="https://helpx.adobe.com/content/help/br/campaign/kb/acs-privacy.html#ccpa">Saiba mais</a>.</li>
  </ul>
    <p>Consulte o <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">vídeo de instruções</a>.</p>
</td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integração do Microsoft Dynamics 365 (GA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 
    <p>A integração entre o Adobe Campaign Standard e o Microsoft Dynamics 365 está disponível. Você poderá transferir seus registros de contato e entidade personalizados do Dynamics 365 para o Campaign e obter dados de eventos de email do Campaign para o Dynamics 365 para melhorar o alinhamento de vendas/marketing.</p>
    <p>Consulte a <a href="../../integrating/using/d365-acs-get-started.md">documentação detalhada</a> para configurar essa integração.</p>
  </td>
  </tr> 
 </tbody> 
</table>

**Aprimoramentos**

* A janela pop-up de consentimento para os relatórios dinâmicos foi atualizada para incluir a integração do Adobe Campaign Standard e do Microsoft Dynamics 365. Ao aceitar os termos, os dados do perfil serão incluídos ao usar a integração Adobe Campaign Standard/Microsoft Dynamics 365 e os Relatórios dinâmicos. [Leia mais](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) (CAMP-29766)
* Correção de um problema que exibia datas de contato incorretas ao receber alertas de entrega.
* Quando um evento de mensagem transacional é enviado com um parâmetro de contexto desconhecido, o Campaign agora retorna uma mensagem de erro &quot;400&quot; em vez de &quot;500&quot;. (CAMP-28632)
* Um novo **Excluir prova** segmento foi adicionado em Relatórios dinâmicos. Esse segmento agora é selecionado por padrão para filtrar seus relatórios. [Leia mais](../../reporting/using/list-of-components-.md#segments)
* A variável **Expiração da mensagem** foi adicionada uma opção à notificação por push. Ela permite especificar uma data de expiração na qual a mensagem não será mais enviada pelo Apple (APNS) ou pelo Android (FCM). [Leia mais](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* Foram introduzidas melhorias no **Carregar arquivo** atividade: os logs de workflow ficaram mais claros e detalhados sobre o erro que ocorre quando um arquivo não é carregado. A transição de saída gerada ao ativar o **Manter as recusas em um arquivo** A opção foi renomeada **Rejeições**. [Leia mais](../../automating/using/load-file.md)
* Registros multilíngues relacionados foram adicionados aos registros de envio para entender melhor as falhas de envio devido à falta de idiomas nos arquivos CSV carregados.

**Melhorias de segurança**

* Correção de um problema ao excluir informações de um perfil em quarentena por meio de uma solicitação de privacidade, que removia todos os dados, exceto o endereço de email na lista de quarentena.
* A segurança foi aprimorada para proteção contra injeções em cabeçalhos de email.
* A segurança foi aprimorada para proteção contra ataques de SSRF, onde expressões xtk podem ser usadas (HTML de email, conteúdo e assunto de texto, conteúdo de SMS e notificação por push).

**Aprimoramentos do Email Designer**

* Correção de um problema que impedia que links de unsubscription, subscrições e landing pages fossem rastreados quando inseridos em um email. (CAMP-37809)
* Correção de um problema que poderia resultar em erros ao criar um novo email e selecionar um modelo. (CAMP-38000)
* Ao editar um link usando o Designer de email, agora é possível usar o **Sublinhar link** opção. Além disso, uma **Target** foi adicionada com o valor padrão definido como **Nenhum**. [Leia mais](../../designing/using/styles.md#about-styling-links)
* Correção de um problema de cor em links em componentes de texto no corpo de um email. (CAMP-37330)
* Correção de um problema que impedia a remoção de links associados ao excluir uma imagem. (CAMP-37234)
* Correção de um problema que impedia o salvamento de modificações no **Pedido** configurações de conteúdo dinâmico em uma condição. (CAMP-36883)
* Correção de um problema ao pesquisar landing pages. A pesquisa foi estendida dos 50 criados inicialmente para todo o banco de dados. (CAMP-36839)
* Correção de um problema ao salvar modificações no remetente de email na **De: Nome** campo. (CAMP-36606)
* O aviso de compatibilidade do componente Carrossel foi modificado para refletir os clientes de email compatíveis.
* Correção de um problema de exibição em dispositivos móveis. Agora, o atributo height é sempre definido como &quot;height: auto&quot; ao adicionar ou fazer upload de uma nova imagem em um email. (CAMP-35497)
* Correção de um problema que deixava as metatags e o estilo no HTML ao excluir um fragmento de um componente de estrutura. (CAMP-35390)
* Correção de um problema com fragmentos ao atualizar conteúdo reutilizável. (CAMP-35186)
* Correção de um problema ao exibir conteúdo condicional somente para dispositivos móveis em emails. (CAMP-35155)
* Correção de um problema que exibia aleatoriamente espaços não separáveis de largura zero. (CAMP-35116)
* Correção de um problema com a posição dos botões no **Salvar como fragmento** caixa de diálogo.
* Correção de um problema de visualização ao adicionar uma tag HTML em um título de imagem e texto alternativo.
* Correção de um problema ao editar, no Designer de email, links criados em emails do editor herdado.
* Correção de um problema que deixava tags de estilo duplicadas no conteúdo.
* Correção de um problema com o formato de data ao inserir um campo de personalização em um email.
* Correção de um problema de gravação ao alternar do modo HTML para texto sem formatação.
* Correção de um problema ao clicar na opção bloquear e desbloquear, que adicionava valores de margem no painel de propriedade do estilo em linha.
* Correção de um problema com o tamanho da visualização móvel para melhorar a renderização.
* Correção de um problema com o tamanho dos botões em modelos e fragmentos.
* Correção de um problema com o tamanho das imagens quando inseridas em um componente de botão.

**Outras alterações**

* O intervalo de tempo padrão para o qual os dados são mostrados nas páginas de KPI do delivery e na página Dynamic Reporting foi alinhado para evitar discrepância nos resultados do relatório. (CAMP-35148)
* Uma mensagem de erro foi adicionada aos logs quando o certificado do aplicativo expirou.
* A pré-visualização do cálculo de carga agora inclui o tamanho de campo personalizado para evitar falhas de notificação por push. (CAMP-35303)
* O nome do **Rejeita arquivo** no **Carregar arquivo** A atividade do agora pode ser personalizada da mesma forma que na **Exportação de arquivo** atividade.
* Todas as entidades personalizadas que não estão vinculadas a nenhuma entidade predefinida agora podem ser acessadas por meio da API.
* Desempenho de banco de dados aprimorado em recursos grandes.
* As descrições de alguns erros que ocorrem ao enviar mensagens SMS foram tornadas mais claras. (CAMP-36558)
* Uma mensagem de erro agora é exibida ao executar a **Scheduler** atividade conectada a si mesma, diretamente ou por meio de várias atividades, pois isso pode causar o travamento do servidor de workflow da instância.
* Foram feitos aprimoramentos para ajudar a solucionar problemas de mensagens transacionais: o link &quot;Dados&quot; foi renomeado para &quot;Últimos eventos transacionais&quot; na tela de configuração do evento. Agora ele lista os eventos recebidos em ordem decrescente. Além disso, um novo status de evento transacional foi criado: &quot;targetingFailed&quot;. Quando o módulo de mensagens transacionais falha ao enriquecer um link usado para o direcionamento de mensagens, o evento transacional agora estará nesse novo estado (em vez do status &quot;routingFailed&quot;).
* Foram feitos aprimoramentos na interface ao restringir o acesso à página de aterrissagem a unidades geográficas ou organizacionais específicas. O objetivo é avisar que a landing page pode estar sujeita a condições de visibilidade: a seleção de uma unidade geográfica e organizacional ao criar uma landing page agora é obrigatória. Um banner com informações relacionadas agora é exibido assim que uma unidade é selecionada. A mensagem de erro exibida ao testar a landing page ficou mais clara.
* Nas APIs de Campaign Standard, as chaves personalizadas não podem ser modificadas usando uma operação PATCH se o valor da chave for diferente da chave de origem ou se você estiver usando sua própria chave comercial como URI em vez da fornecida pelo Adobe.
* O idioma &quot;albanês - Macedônia&quot; foi adicionado à lista suspensa de idioma preferencial. (CAMP-35396)

**Correções**

* Correção de um problema que impedia que relatórios agendados fossem classificados ou pesquisados.
* Correção de um problema com regras de Acionadores que fazia com que as regras E e OU fossem misturadas.
* Correção de um problema que exibia a propriedade Mobile como Excluído no Launch. (CAMP-35382)
* Correção de um problema que impedia a sincronização das propriedades móveis do Adobe Launch no Adobe Campaign. (CAMP-35411, CAMP-35089, CAMP-35014, CAMP-35487)
* Correção de um problema em que as mensagens de push transacionais falhavam quando eventos eram enriquecidos com dados de perfil. (CAMP-34385)
* Correção de um problema com propriedades móveis não sincronizadas em vários ambientes. (CAMP-37060)
* Correção de um problema ao selecionar, em uma notificação por push, um modelo usando uma fórmula de data de contato. (CAMP-35300)
* Correção de um problema que resultava em falha do serviço de envio de mensagens. (CAMP-35287)
* Correção de um problema com malas diretas recorrentes que foram todas definidas com a data do primeiro evento. (CAMP-35139)
* Correção de um problema com a nova extensão **Perfis** recursos personalizados que não estavam disponíveis para consultas. (CAMP-35119)
* Corrigido o **Reparar estrutura do banco de dados** para instâncias com a configuração Compartilhamento ativada. (CAMP-35118)
* Correção de um problema que resultava em um erro de log SQL ao adicionar dados agregados em broadlogs. (CAMP-35034)
* Correção de um problema com transições ao criar uma **Segmentação** atividade. (CAMP-35033)
* Correção de um problema no **Query** atividade que impediu a **encryption_aescbcDecrypt** da descriptografia da função **encryption_aescbcEncrypt** função. (CAMP-34952)
* Correção de um problema que poderia impedir a **Logs de rastreamento** de ser exibido nos deliveries. (CAMP-34855)
* Correção de um problema ao usar uma **Otimização da hora de envio** fórmula de data personalizada, que pode impedir o envio de notificações por push devido a erros com os dados adicionais do fluxo de trabalho. (CAMP-30336)
* Correção de um problema que impedia a publicação de recursos personalizados. (CAMP-37425)
* Correção de um problema que impedia usuários administradores de modificar pacotes de importação.  (CAMP-37176)
* Correção de um problema em workflows que impedia o envio de provas, se a atividade de delivery estivesse conectada a um vazio **Ler público** atividade. (CAMP-37164)
* Correção de um problema que impedia a importação de recursos personalizados para um novo ambiente. (CAMP-36506)
* Correção de um problema nos relatórios de cliques ativos que poderia resultar na ocultação de porcentagens por imagens (CAMP-36407)
* Correção de um problema que ocorria ao tentar exportar um campo de descrição de delivery. (CAMP-35467)
* Correção de um problema que poderia deixar o estado de uma entrega como &quot;Início pendente&quot;, embora a entrega tivesse sido concluída. (CAMP-35355)
* Correção de um problema que impedia a exibição de logs de workflow após a ativação e, em seguida, a desativação de logs SQL.

## Versão 19.3 - Julho de 2019 {#release-19-3---july-2019}

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
   <td> Atividade de API externa (Beta público)<br /> </td> 
   <td> <p>Para maior personalização, a Atividade da API externa permite trazer dados de sistemas externos para um fluxo de trabalho por meio de uma chamada de API REST. Os endpoints REST podem ser um sistema de gerenciamento de clientes, Adobe I/O Runtime ou endpoint REST do Adobe Experience Cloud (por exemplo, Plataforma de dados, Target, Analytics, Campaign).</p><p>No momento, esse recurso está em beta público.</p><p>Para saber mais, consulte a <a href="../../automating/using/external-api.md">documentação detalhada</a> e o <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">vídeo de instruções</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Relatório no segmento do fluxo de trabalho<br /> </td> 
   <td> <p>Esse recurso permite que os profissionais de marketing analisem seu desempenho de entrega por código de segmento. Ao criar um fluxo de trabalho e usar uma atividade de segmentação para atribuir segmentos à população de entrega, esses segmentos agora podem fazer parte da mesma entrega. Isso permite exibir as estatísticas de aberturas/cliques com base em vários segmentos em uma única entrega.</p><p>Para saber mais, consulte a <a href="../../reporting/using/creating-a-report-workflow-segment.md">documentação detalhada</a> e o <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">vídeo de instruções</a>.</p></td>
  </tr> 
 </tbody> 
</table>

**Melhorias de segurança**

* Correção de um problema de segurança para impedir ataques de negação de serviço (DoS) em solicitações inválidas para obter imagens. (CAMP-33454)

**Aprimoramentos do Email Designer**

* Correção de um problema que adicionava tags de estilo de HTML a um modelo de HTML sempre que um componente era adicionado, o que poderia aumentar drasticamente o tamanho do modelo. (CAMP-34694)
* Correção de um problema que poderia impedir que algumas opções de menu da barra de ferramentas superior direita estivessem disponíveis. (CAMP-34577)
* Correção de um problema que ocorria quando o bloco de conteúdo do URL da página espelhada era inserido em um conteúdo de email. (CAMP-34779)
* Correção de um problema que ocorria ao usar o código JSPP em um email, dificultando a edição do conteúdo. (CAMP-34574)
* Correção de um problema que resultava em imagens truncadas na parte superior quando um hiperlink era adicionado a elas. (CAMP-34382)
* Correção de um problema de exibição ao usar o Email Designer com o Firefox. (CAMP-34364)
* Correção de vários problemas que ocorriam com o modo Avançado ao definir o conteúdo dinâmico em um email. (CAMP-34351, CAMP-34333, CAMP-34331)
* Correção de vários problemas que ocorriam com o editor de regras de conteúdo dinâmico (CAMP-34304, CAMP-34303).
* Correção de um problema que impedia a exibição do campo Link no painel Configurações do Designer de email (CAMP-33749).
* Correção de um problema com o ícone YouTube que era muito grande nos emails enviados. (CAMP-33726)
* Correção de um problema de segurança que tornava o conteúdo da mirror page editável. (CAMP-33691)
* Correção de um problema que afetava a saída de HTML ao usar o símbolo maior que no conteúdo dinâmico. (CAMP-33688)
* Correção de um problema que ocorria ao usar a opção Desfazer ao editar texto no Designer de email. (CAMP-32565)
* Correção de um problema que criava tags extras ao desfazer estilos em vez de removê-los. (CAMP-32359)
* Agora é possível definir se cada componente usado em um email será mostrado apenas em dispositivos desktop ou apenas em dispositivos móveis.
* Agora é possível definir a largura e a altura de um componente de Conteúdo social.
* Correção de um problema que impedia que o código-fonte antigo do conteúdo dinâmico fosse removido após a exclusão desse conteúdo dinâmico.
* Correção de um problema que impedia que o assunto de um email fosse atualizado após sua modificação.
* Correção de um problema que impedia que uma estrutura de coluna n:n fosse selecionada depois de colocada no espaço de trabalho.
* Correção de um problema que fazia com que a miniatura da mensagem parecesse borrada no painel do email.
* Correção de um problema que impedia a exibição correta do plano de fundo para emails recebidos no Outlook.
* Correção de alguns problemas de classificação na página inicial do Designer de email.
* Correção de um problema que ocorria na duplicação de variantes ao usar conteúdo dinâmico.
* Alguns campos indesejados foram removidos do painel Configurações do Designer de email.

**Outras melhorias**

* Por meio da integração com os Serviços de localização da Adobe Experience Platform, o Adobe Campaign agora é compatível para enviar mensagens de marketing baseadas em localização aos assinantes do aplicativo móvel por meio do SDK do Experience Platform. Para obter mais informações, consulte a [documentação detalhada](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md).
* O recurso de relatórios foi aprimorado para obter uma melhor experiência. Para usar esse recurso, você precisa aceitar o Contrato de uso dos Relatórios dinâmicos. Para obter mais informações, consulte [documentação detalhada](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* Nos fluxos de trabalho, uma nova opção foi adicionada para visualizar as próximas dez execuções de um fluxo de trabalho. Para obter mais informações, consulte [documentação detalhada](../../automating/using/scheduler.md).
* Na atividade Scheduler, uma nova opção permite selecionar um dia específico de uma semana específica para deliveries mensais. Para obter mais informações, consulte [documentação detalhada](../../automating/using/scheduler.md).
* Ao criar deliveries recorrentes sem período de agregação, o painel de delivery agora permite solicitar confirmação antes que o delivery seja enviado. Para obter mais informações, consulte [documentação detalhada](../../sending/using/confirming-the-send.md).
* Agora você pode personalizar um rótulo de delivery com variáveis de evento que foram declaradas na atividade de sinal externo do fluxo de trabalho. Para obter mais informações, consulte [documentação detalhada](../../automating/using/calling-a-workflow-with-external-parameters.md).
* A consulta de exclusão do GDPR foi aprimorada para melhorar o desempenho. (CAMP-33504)
* A opção &quot;ftp&quot; foi removida da interface de configuração da conta externa. (CAMP-34472)
* Agora é possível ativar e desativar a opção de modo de teste SMTP para cada mensagem de email. Para obter mais informações, consulte [documentação detalhada](../../administration/using/configuring-email-channel.md#smtp-test-mode). (CAMP-34602)

**Outras alterações**

* Um aviso foi adicionado à interface de propriedades de entrega. Ele especifica que os deliveries são preparados com base no período de agregação e descongela para chamar o workflow várias vezes por dia. Você deve garantir que eles não tenham nenhum período. (CAMP-34393)
* Um aviso foi adicionado nas telas de configuração de recursos personalizados. Recomendamos o uso de no máximo 30 caracteres para IDs de recursos personalizados. Isso também se aplica a campos de recursos personalizados, chaves, índices e links.
* Agora é exibida uma mensagem ao tentar excluir uma mensagem transacional usada por uma landing page como uma mensagem de confirmação.
* Um aviso agora é exibido nos logs de workflows quando uma atividade está em execução por mais de 6 horas. Isso não se aplica às atividades de notificação por push, Delivery, Signal, Start, End, Fork , AND-join, Schedule e Wait.
* Agora um aviso é exibido nos logs de workflows ao atingir o número máximo de workflows executados simultaneamente.
* Os workflows com status de pausa ou falha por mais de 7 dias agora são interrompidos para consumir menos espaço em disco. A tarefa de limpeza é exibida nos logs do fluxo de trabalho.
* Ao usar uma atividade &quot;Transfer file&quot;, um erro agora é registrado se o tamanho do arquivo exceder o espaço disponível em disco.
* A ação Redirecionar para URL de destino não pode mais ser selecionada para o botão secundário em Mensagens no aplicativo.

**Correções**

* Correção de um problema que causava a falha de solicitações de acesso do GDPR.
* Correção de um problema que resultava no descarte de acionadores quando vários acionadores eram recebidos para um perfil exclusivo.
* Correção de um problema que poderia resultar em uma mensagem de erro de publicação de recurso personalizado incorreta após o logon.
* Correção de um problema que exibia uma página em branco ao criar ou estender um recurso personalizado.
* Correção de um problema que impedia que um público-alvo com appSubscriptionrcp como dimensão de direcionamento ficasse disponível para direcionamento em uma entrega móvel.
* Correção de um erro que impedia que endereços de email de rejeições permanentes fossem colocados em quarentena. (CAMP-24587)
* Correção de um problema que ocorria ao adicionar uma regra de tipologia e, em seguida, excluí-la antes de salvar a tipologia. (CAMP-32789)
* Correção de um problema que impedia a exibição do conteúdo da página de aterrissagem ao desabilitar o conteúdo dinâmico. (CAMP-32924)
* Correção de um problema com entregas recorrentes que ocorria ao usar personalização nos atributos de uma entrega primária. (CAMP-32983)
* Correção de um problema em workflows que impedia a leitura de resultados de uma transição contendo dados de mensagens SMS de entrada. (CAMP-33134)
* Correção de um problema em workflows que ocorria ao combinar atividades de bifurcação e exclusão para criar públicos. (CAMP-33401)
* Correção de um problema que impedia a exibição do conteúdo da mirror page e o envio de mensagens de prova para entregas recorrentes. (CAMP-33413)
* Correção de um problema que resultava em erro ao usar uma atividade Union entre perfis e públicos. Esse problema era causado por uma incompatibilidade das chaves de identificação em transições de entrada. (CAMP-33713)
* Correção de um problema nas atividades Test que impedia que a expressão &quot;recCount&quot; usasse a sintaxe correta ao clicar duas vezes nela. (CAMP-33756)
* Correção de um problema que poderia resultar em uma mensagem de erro ao abrir os logs do workflow técnico de faturamento. (CAMP-34313)
* Correção de um problema nas páginas de aterrissagem que poderia ocorrer ao configurar campos de caixa de seleção com assinaturas. (CAMP-34369)
* Correção de um problema que ocorria ao configurar uma lista e adicionar o campo &quot;icon&quot; a ela. (CAMP-34585)
* Correção de um problema que impedia o uso dos símbolos &quot;|&quot; e &quot;%&quot; como separadores de data ou hora nas atividades de fluxo de trabalho Carregar arquivo. (CAMP-34706)
* Correção de um problema que ocorria ao usar condições de visibilidade com caixas de seleção em landing pages. (CAMP-34802)
* Correção de um problema na atividade Enriquecimento que impedia a exibição de campos na guia &quot;Dados adicionais&quot;, se a dimensão do filtro fosse definida como logs de rastreamento e a dimensão de destino como perfil.
* Correção de um problema que resultava em uma mensagem de erro ao exportar um recurso &quot;workflowTemplate&quot;.
* Correção de um problema ao criar um novo perfil, que impedia que o campo &quot;Código do país/região&quot; fosse salvo se fosse selecionado na caixa de diálogo.
* Correção de vários problemas que ocorriam ao usar o modelo de importação de Correspondência direta (updateQuarantinesDeliveryLogsDirectMail).
* Correção de um problema relacionado à integração do Assets on Demand.
* Correção de um problema que ocorria ao aumentar o zoom na exibição Linha do tempo. (CAMP-33628)
* Correção de um problema que impedia que provas fossem enviadas instantaneamente para mensagens de email com data e hora programadas. (CAMP-33723)
* Correção de um problema relacionado a mensagens transacionais que geravam logs de erro quando um usuário fazia logoff. (CAMP-31698)
* Correção de um erro que poderia ocorrer em ambientes específicos ao agendar uma mensagem de email.
* Correção de um problema que causava a falha do fluxo de trabalho Atualizar execução de delivery.
* Correção de um problema de segurança que resultava em falha do conteúdo do email quando o assunto continha várias linhas.


## Versão 19.2.7 - Julho de 2019 {#release-19-2-7---july-2019}

**Aprimoramentos**

* A consulta de exclusão do GDPR foi aprimorada para melhorar o desempenho.
* Correção de um problema que poderia causar falhas da Web após a atualização 19.2. (CAMP-34862)
* Correção de um problema que impedia usuários não administradores de salvar ou agendar relatórios. (CAMP-31133)
* Correção de um problema ao usar &quot;|&quot; como separador de data na atividade de workflow Carregar arquivo. (CAMP-34706)

## Versão 19.2.4 - Junho de 2019 {#release-19-2-4---june-2019}

**Email Designer**

* Correção de um problema que impedia os usuários de editar fragmentos quando tags de estilo vazias eram usadas no HTML. Esta é uma correção de acompanhamento para CAMP-33778 na versão 19.2.3.

## Versão 19.2.3 - Junho de 2019 {#release-19-2-3---june-2019}

**Email Designer**

Uma série de melhorias e correções foram introduzidas para otimizar fragmentos na versão 19.2. Fragmentos recém-criados funcionarão perfeitamente. Os fragmentos criados anteriormente foram esmaecidos e precisam ser migrados para o novo formato. Para fazer isso, clique em cada fragmento e valide a migração para o novo formato. Recomendamos testar alguns fragmentos antes de migrar todos eles.

* Correção de um problema que impedia os usuários de editar um fragmento após desbloqueá-lo. Isso estava afetando fragmentos existentes ao atualizar para a versão 19.2. (CAMP-33778)
* Correção de um problema ao usar conteúdo dinâmico. Espaços extras foram adicionados no HTML.

**Outras melhorias**

* Correção de um problema que impedia que o envio de SMS fosse retomado após uma desconexão do conector SMS.
* Correção de um problema que poderia fechar conexões SMPP quando o TLS era habilitado.
* Correção de um problema que poderia fechar conexões SMPP quando o TLS era habilitado.
* A opção &quot;Launch_URL_Campaign&quot; foi adicionada ao Campaign para gerenciar propriedades de aplicativos móveis criados com o SDK do Adobe Experience Platform Mobile.
* Correção de um erro que resultava na desmarcação da opção de ambiente Sandbox após o upload do certificado de uma propriedade móvel recém-criada e a saída da página de propriedades do aplicativo móvel.
* Correção de um problema que impedia o enriquecimento de um conteúdo de mensagem transacional com informações do recurso Serviço. (CAMP-33707)
* Correção de um problema nas páginas de aterrissagem de inclui na lista de bloqueios que ocorria ao tentar cancelar a assinatura de perfis de um serviço.

## Versão 19.2 - Maio de 2019 {#release-19-2---may-2019}

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
   <td> Painel de controle<br /> </td> 
   <td> <p>Para ajudar a aumentar a eficiência do seu trabalho como usuário administrador, é possível monitorar facilmente a capacidade e gerenciar as configurações de suas instâncias (começando pelo gerenciamento de servidores SFTP).</p><p>Para saber mais, consulte a <a href="https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=pt-BR">documentação detalhada</a> e o <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/control-panel-overview.html?lang=pt-BR">vídeo de instruções</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Notificações locais<br /> </td> 
   <td> <p>As mensagens de notificação locais permitem informar aos usuários quando novos dados são disponibilizados em seus aplicativos móveis, mesmo sem ter acesso à Internet ou o aplicativo móvel em execução em primeiro plano. As notificações locais são acionadas por um aplicativo móvel em um horário específico e dependendo de um evento.</p><p>Para obter mais informações, consulte a <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">documentação detalhada</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Aprimoramento do fluxo de trabalho - Adicione um conteúdo à atividade de sinal externo<br /> </td> 
   <td> <p>Inicie um workflow com uma carga quando as condições definidas forem atendidas com êxito de outro workflow ou uma chamada à API REST para integrar com seus sistemas externos. Inclui também uma nova <strong>test</strong> atividade na qual você pode executar testes nesta funcionalidade.</p><p>Para saber mais, consulte a <a href="../../automating/using/calling-a-workflow-with-external-parameters.md">documentação detalhada</a> e o <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/execution-activities/external-signal-activity.html">vídeo de instruções</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Aprimoramento das páginas de destino - Google reCAPTCHA<br /> </td> 
   <td> <p>Aproveite o Google reCAPTCHA para evitar spam em suas páginas de aterrissagem sem solicitar uma ação de seus clientes.</p><p>Para obter mais informações, consulte a <a href="../../channels/using/configuring-landing-page.md#setting-google-recaptcha">documentação detalhada</a>.</p></td> 
  </tr> 
 </tbody> 
</table>

**Aprimoramentos de segurança**

* Correção de um problema potencial de segurança de clickjacking no espaço de trabalho de relatórios.

**Aprimoramentos do Email Designer**

* Correção de um problema que ocorria ao duplicar fragmentos e tentar usá-los no Designer de email. (CAMP-33193)
* Correção de um problema que criava espaços indesejados ao usar elementos em linha na interface do Designer de email. (CAMP-32163)
* Correção de um problema que excluía alguns atributos adicionais de tag HTML adicionados pelo usuário após salvar conteúdo de email no Designer de email. (CAMP-32162)
* Correção de um problema que exibia uma tag do Microsoft Office no modo HTML do Designer de email mesmo após removê-la. (CAMP-32141)
* Se você criou um email usando uma versão anterior do Designer de email, ao abrir esse conteúdo de email, uma janela pop-up agora solicita que o usuário atualize para a versão mais recente. (CAMP-31529)
* Correção de um problema que poderia distorcer imagens de um email criado com o Designer de email quando entregues a alguns clientes de mensagens. (CAMP-31407)
* Correção de um problema que impedia que alguns elementos, como listas ou botões, fossem exibidos corretamente no modo de texto sem formatação quando criados no modo HTML. (CAMP-32582, CAMP-32542)
* Correção de um problema que impedia a exibição de mais de 50 unidades organizacionais em um modelo de conteúdo ou propriedades de fragmento. (CAMP-32932)
* Correção de um problema com a cor de fundo do visor ao receber um email criado com o Designer de email no Outlook. (CAMP-31402)
* Correção de um problema que impedia que o conteúdo de email criado com o Designer de email fosse responsivo quando aberto no Outlook. (CAMP-31400)
* Correção de um problema que impedia o funcionamento correto do conteúdo dinâmico quando usado em um assunto de email. (CAMP-32837)
* Correção de um problema relacionado ao assunto do email que não era evitado corretamente.
* Correção de um problema que impedia o carregamento de fragmentos na paleta esquerda do Email Designer.
* Correção de um problema que impedia a exibição de fragmentos criados durante a edição de conteúdo de email na paleta esquerda do Designer de email ao atualizar a lista de fragmentos.
* Correção de vários problemas que ocorriam ao usar conteúdo dinâmico em um email.
* Correção de um problema que ocorria com o seletor de cores ao tentar definir uma cor usando valores de RGB.
* Correção de um problema que impedia que a mirror page respondesse ao receber o email em um dispositivo móvel.

**Aprimoramentos de mensagens transacionais**

Várias melhorias foram adicionadas ao canal de mensagens transacionais para otimizar a operação e o desempenho.

* A duração da mensagem transacional foi estendida para garantir que todas as mensagens sejam enviadas antes de expirarem, especialmente quando houver novas tentativas.
* O desempenho das mensagens transacionais foi aumentado com a distribuição da carga em diferentes threads de envio.
* O processo de mensagens transacionais foi otimizado para poder iniciar em paralelo várias análises da mesma mensagem.
* Correção de um problema que resultava em taxa de transferência e latência inconsistentes para notificações por push transacionais.
* Correção de um problema que exibia um público-alvo incorreto para entregas de execução de mensagem transacional.
* Correção de um problema que ocorria ao importar um pacote com uma configuração de evento e a mensagem transacional associada. Para obter mais informações, consulte [documentação detalhada](../../channels/using/getting-started-with-transactional-msg.md#exporting-and-importing-transactional-messages).
* Correção de um problema que excluía os dados de coleção dos perfis de teste criados para uma mensagem transacional contendo listas de produtos.

**Outras alterações**

* Uma nova opção foi adicionada à conta externa do SMS. Ela permite limitar o número máximo de processos MTA que enviam SMS para controlar melhor o número de conexões paralelas. Para obter mais informações, consulte [Protocolo e configurações do conector de SMS](https://helpx.adobe.com/br/campaign/kb/sms-connector-protocol-and-settings.html) nota técnica.
* Ao publicar um recurso com extensão de API, se a API já tiver sido publicada, ela será atualizada automaticamente sempre que for publicada novamente. Anteriormente, essa ação era manual e a falha na atualização da API poderia quebrar o perfil ou o recurso de serviço dessa API. Para obter mais informações, consulte [documentação detalhada](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* A dimensão CEP foi removida do Dynamic Reporting. Recomendamos usar as dimensões Cidade, País, Estado.
* O acionador de evento de ciclo de vida &quot;Primeira inicialização&quot; para mensagens no aplicativo foi removido.
* Ao exportar um pacote com grupos de segurança, ele agora contém as funções atribuídas a cada grupo. (CAMP-32960)
* Na atividade Load file, uma nova opção permite verificar se as colunas do arquivo que você está fazendo upload correspondem à definição da coluna. Para obter mais informações, consulte a [documentação detalhada](../../automating/using/load-file.md). (CAMP-32229)
* Os workflows agora podem ser iniciados com uma carga, permitindo que você use e compartilhe parâmetros externos entre atividades no workflow. Para obter mais informações, consulte a [documentação detalhada](../../automating/using/calling-a-workflow-with-external-parameters.md). (CAMP-29412 E CAMP-29413)
* As APIs Campaign Standard agora permitem atualizar as unidades geográficas e organizacionais dos perfis usando uma carga. Para obter mais informações, consulte a [documentação detalhada](../../api/using/get-started-apis.md).
* As mensagens de erro quando um objeto do banco de dados não está acessível ficaram mais claras.
* Na atividade Extract file, os recursos JavaScript foram atualizados ao definir o nome de um arquivo a ser exportado. Somente a função formatDate agora está disponível para uso no campo Output. Para obter mais informações, consulte a [documentação detalhada](../../automating/using/extract-file.md).
* A geração de ID de sequência automática foi aprimorada para recursos personalizados. As chaves primárias para novos recursos personalizados agora estão em 64 bits por padrão.
* O modo de teste de publicação de recursos personalizados foi aprimorado. Uma mensagem de aviso agora é exibida para os usuários se a última publicação de recurso personalizado falhar e não for corrigida. Após uma falha de publicação de recurso personalizado, é possível reverter para a última versão em funcionamento. Para obter mais informações, consulte a [documentação detalhada](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
* Uma nova opção foi adicionada na atividade Transfer file. Ela permite classificar os arquivos ao usar a ação Download de arquivo, no modo SFTP. Para obter mais informações, consulte a [documentação detalhada](../../automating/using/transfer-file.md). (CAMP-33109)

**Correções**

* Correção de um problema que poderia causar vazamento de memória para o MTA quando as configurações de SMS eram recarregadas.
* Correção de um problema que impedia a publicação de atualizações do banco de dados no modo de reparo.
* Correção de um problema que causava discrepância entre os Relatórios do Adobe Analytics e os Relatórios dinâmicos do Adobe Campaign. (CAMP-25393)
* Correção de um erro que causava a falha do fluxo de trabalho Compartilhamento de relatórios.
* Correção de um erro que impedia os usuários de enviar mensagens no aplicativo apenas com URL de mídia.
* Correção de um problema que exibia um aplicativo móvel mesmo se o certificado não fosse carregado na instância.
* Correção de um erro que impedia que campos de personalização funcionassem ao usar o **Direcionar todos os usuários de um aplicativo móvel** modelo.
* Novas instâncias do Campaign Standard foram provisionadas. (CAMP-32635 E CAMP-32344)
* Correção de um erro que impedia a personalização da fórmula de data em um workflow. (CAMP-30336)
* Correção de um problema ao definir uma fórmula de data personalizada que poderia impedir que os campos &quot;Dados adicionais&quot; e &quot;Código do segmento&quot; estivessem disponíveis na lista suspensa. (CAMP-32383)
* Correção de um problema que impedia que as atividades &quot;Transferir arquivo&quot; e &quot;Extrair arquivo&quot; localizassem os arquivos rejeitados se eles estivessem criptografados. (CAMP-32377)
* Correção de um problema nas APIs que impedia que o filtro lineCount renderizasse a contagem total exata. (CAMP-31424)
* Correção de um problema nas páginas de aterrissagem que impedia que os campos de entrada mostrassem o valor atualizado depois de ele ser modificado. (CAMP-31401)
* Correção de um problema que poderia resultar na ativação inesperada de uma atividade de sinal.
* Correção de um problema que impedia a exibição da pré-visualização de email quando o público-alvo estava vazio.
* Correção de um problema na atividade &quot;Extrair arquivo&quot; que poderia gerar um arquivo enquanto a opção &quot;Não gerar um arquivo se a transição de entrada estiver vazia&quot; estava ativada.
* Correção de um problema que resultava na desativação do fluxo de trabalho Capacidade de delivery se ele não fosse concluído com êxito.
* Correção de um problema que impedia os usuários de salvar ou agendar relatórios. (CAMP-31133)

## Versão 19.1.3 - Março de 2019 {#release-19-1-3---march-2019}

**Aprimoramentos do Email Designer**

* Correção de um problema que impedia a modificação de um modelo após salvá-lo.
* Correção de vários problemas ao usar um modelo criado anteriormente em um email.
* Correção de um problema que impedia que os componentes ficassem ocultos em modelos importados.

**Outras melhorias**

* Correção de um erro ao exibir regras de tipologia. (CAMP-32059 E CAMP-31849)
* Correção de um problema que impedia a edição das regras de tipologia. (CAMP-31750)
* Correção de um problema com o processo inMail que poderia parar inesperadamente. (CAMP-31238)

## Versão 19.1 - Fevereiro de 2019 {#release-19-1---february-2019}

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
   <td> Melhorias nos relatórios do canal de push<br /> </td> 
   <td> <p>Vários aprimoramentos foram adicionados aos relatórios do canal de push para permitir medir o engajamento do usuário de forma mais intuitiva. Com esta versão, estamos expandindo a lista de métricas do canal de push para três métricas diferentes: Impressões, cliques, aberturas (abertura do aplicativo) para ajudar você a medir e analisar a interação dos usuários com notificações de push com mais eficiência. Além disso, estamos padronizando a definição e a implementação dessas métricas. O relatório integrado Notificação por push também foi aprimorado com visualizações e métricas usadas com frequência.</p><p> Para obter mais informações, consulte a <a href="../../reporting/using/push-notification-report.md">documentação detalhada</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Integração do Launch para aplicativos de dispositivos móveis<br /> </td> 
   <td> <p>Esta versão contém a integração do Adobe Campaign com as versões do Android e das extensões do iOS disponíveis no mercado para Adobe Campaign Standard em SDKs móveis e da Adobe Experience Platform Launch. Essas extensões oferecem suporte a mensagens por push, mensagens no aplicativo e atualizações de perfis de aplicativos móveis.</p><p> Para obter mais informações, consulte a <a href="https://helpx.adobe.com/br/campaign/kb/configuring-app-sdk.html">documentação detalhada</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mensagens no aplicativo móvel<br /> </td> 
   <td> <p>Esta versão contém a versão comercial do canal no aplicativo no Campaign. De uma perspectiva funcional, as adições mais notáveis da versão Beta são os Relatórios dinâmicos para o Canal no aplicativo e um handshake seguro entre o SDK móvel e o MCIAS (Serviço de mensagens no aplicativo do Marketing Cloud, que fornece as regras no aplicativo para o SDK). O handshake seguro garante que os dados PII de seus usuários não caiam em mãos mal-intencionadas, além de permitir que você mantenha a privacidade dos usuários em um dispositivo compartilhado, limpando o cache de mensagens sempre que o usuário fizer logout.</p><p>Para obter mais informações, consulte <a href="../../channels/using/about-in-app-messaging.md">documentação detalhada</a> e a equipe <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/in-app/in-app-message-overview.html">Tutorial no aplicativo</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Melhorias no fluxo de trabalho<br /> </td> 
   <td> <p>Os seguintes recursos de fluxo de trabalho foram adicionados:</p> 
    <ul> 
     <li> Agora é possível copiar e colar atividades em um fluxo de trabalho ou outro fluxo de trabalho da mesma instância do Campaign. Dessa forma, é possível duplicar facilmente todo um fluxo de trabalho ou atividades específicas e manter as configurações definidas inicialmente. Para obter mais informações, consulte a <a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">documentação detalhada</a>. (CAMP-20014) </li> 
     <li> Ao usar o <strong>Carregar arquivo</strong> atividade, agora é possível adicionar um carimbo de data e hora ao nome do arquivo que contém os registros rejeitados. Para obter mais informações, consulte a <a href="../../automating/using/load-file.md#configuration">documentação detalhada</a>. </li> 
     <li> <strong>Query</strong> e <strong>Segmentação</strong> agora, as atividades permitem ativar uma transição de saída se as atividades não recuperarem dados. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Melhorias de segurança**

* O código de HTML da página de aterrissagem gerado foi atualizado para impedir a indexação do mecanismo de pesquisa.

**Aprimoramentos do Email Designer**

* Um conjunto dos quatro melhores modelos de email responsivo criados por artistas do Behance está disponível.

   Para obter mais informações, consulte a [documentação detalhada](../../designing/using/using-reusable-content.md#content-templates).

* Nossa nova experiência de integração ajuda você a começar a criar emails mais rapidamente e a facilitar o acesso à documentação e aos tutoriais.

   Para obter mais informações, consulte a [documentação detalhada](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page).

* Agora, você tem a flexibilidade para configurar o número de colunas e a largura com base nas suas necessidades.

   Para obter mais informações, consulte a [documentação detalhada](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

* Ao editar na exibição para dispositivos móveis, você pode ocultar determinados componentes apenas na exibição para dispositivos móveis para obter um uso eficaz do espaço.

   Para obter mais informações, consulte a [documentação detalhada](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

* Agora você pode adicionar canais sociais personalizados ao seu modelo de email, além daqueles que já estão disponíveis.
* Correção de um problema que impedia a rolagem para baixo do menu de estrutura ao usar mais de 18 estruturas. (CAMP-31173)
* Correção de um problema que exibia o pré-cabeçalho sobre o conteúdo ao encaminhar um email contendo um pré-cabeçalho enviado com o Adobe Campaign. (CAMP-30736)
* Correção de um problema que impedia a atualização da linha de assunto ao clicar no **Atualizar conteúdo AEM** depois de modificar o assunto no Adobe Experience Manager. (CAMP-29984)
* Correção de vários problemas que impediam o uso de imagens dinâmicas do Adobe Target.
* Correção de um problema que impedia a atualização da visualização ao recuperar o conteúdo no momento da preparação se o conteúdo tivesse sido importado anteriormente de um URL.
* O ícone do YouTube foi adicionado à variável **Social** componente de conteúdo.
* A variável **Lista** A visualização foi adicionada para componentes de conteúdo e fragmentos exibidos na paleta do Designer de email.

**Outras melhorias**

* Agora, o Adobe Campaign é totalmente compatível com o FCM para aplicativos SDK V4 e SDK AEP.
* O Adobe Campaign é compatível com notificações por push em Wear OS pelo Android, bem como com o watchOS pelo Apple.
* As mensagens de aviso e erro que podem ser exibidas ao navegar na interface ficaram mais claras e fáceis de entender.
* Agora é possível adicionar às colunas da lista de perfis relacionadas a aceitação e recusa (campos &quot;Não entrar em contato mais...&quot;).
* A lista suspensa Time zone na tela Profile creation foi movida da seção Address para a seção superior da interface.
* Agora é possível adicionar separadores ao configurar telas de recursos personalizadas, permitindo organizar seus campos em categorias.

   Para obter mais informações, consulte a [documentação detalhada](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration).

**Outras alterações**

* A Adobe Campaign e a Adobe Experience Cloud descontinuarão o suporte ao Microsoft Internet Explorer 11 a partir do segundo trimestre de 2019, e da versão Campaign Standard 19.2. Use o Microsoft Edge ou outro navegador compatível. Consulte [Recursos obsoletos e removidos](../../rn/using/deprecated-features.md) página.
* A variável **Código do país** O campo do recurso Perfil foi renomeado para **Código do país/região**.

**Correções**

* Correção de um problema que impedia o envio da mensagem ao adicionar um perfil de teste a uma mensagem transacional de email. (CAMP-29854)
* Correção de um problema que atrasava o envio de mensagens de outros canais se o envio fosse baixo para um canal quando o envio de mensagens de todos os canais era acionado simultaneamente.
* Correção de um problema que fazia com que o MTA começasse a enviar mensagens SMS quando a conexão de conta externa ainda não tinha sido estabelecida.
* Correção de um problema que ocorria com a frequência de execução da atividade Scheduler e a hora de início. (CAMP-30745)
* Correção de um problema que poderia ocorrer com a geração de PKEY ao usar recursos de perfil estendido. (CAMP-30285)
* Correção de um problema que poderia ocorrer com regras de Fadiga baseadas em dias do calendário. (CAMP-30136)
* Correção de um problema que ocorria ao tentar acessar recursos personalizados com nomes que terminavam com &quot;Base&quot;. (CAMP-30109)
* Correção de um problema que impedia o uso de uma chamada de PATCH para assinar um perfil para um serviço. (CAMP-29728)
* Correção de um problema que poderia corromper um workflow ao importar um arquivo XML por meio da atividade Carregar arquivo. (CAMP-29208 e CAMP-28205)
* Correção de um problema ao vincular recursos personalizados que poderia impedir a geração de links de cardinalidade reversa. (CAMP-30476)
* Correção de um problema que impedia a extensão de logs do delivery ao usar somente o código do segmento.
* Correção de um problema que poderia duplicar linhas ao usar a atividade Transferência de arquivo em workflows.
* Correção de um problema que impedia o envio de relatórios agendados no horário escolhido.
* Correção de um problema que causava discrepância entre os KPIs &quot;Para entrega&quot; e &quot;Enviado&quot; para uma entrega no aplicativo em um fluxo de trabalho.
* Correção de um problema que impedia o funcionamento do rastreamento em uma mensagem no aplicativo criada com um HTML personalizado.
* Correção de um problema que impedia que o conteúdo do delivery no aplicativo fosse salvo quando usado em um workflow.
* Correção de um problema que impedia a exibição de aplicativos móveis para administradores.
* Correção de um problema que causava a falha do fluxo de trabalho técnico Atualização da capacidade de entrega. (CAMP-26387)
* Correção de um problema que causava discrepância entre os perfis direcionados ao criar um delivery no aplicativo e os exibidos no painel do delivery. (CAMP-28722)
* Correção de um problema com a integração do Campaign e do Serviço principal de ativos que podia impedir a seleção de um ativo compartilhado em um email.

## Versão 19.0 – Janeiro de 2019 {#release-19-0---january-2019}

**Novidades**

<table> 
 <colgroup><col style="width: 30%"><col style="width: 70%"></colgroup>
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Disponibilidade geral do Designer de email<br /> </td> 
   <td> <p>O novo intuitivo Designer de email (anteriormente conhecido como Creative Designer) foi movido para GA. Agora, ele é compatível com todos os recursos do editor de conteúdo herdado, incluindo:</p> 
    <ul> 
     <li> A utilização de <a href="../../integrating/using/adding-target-dynamic-content.md">imagens dinâmicas do Adobe Target</a> </li> 
     <li> A capacidade de <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">recuperar conteúdo de um URL automaticamente no momento da preparação</a> </li> 
     <li> Totalmente compatível <a href="../../designing/using/using-reusable-content.md#content-templates">modelos de conteúdo prontos para uso</a>. </li> 
    </ul> 
    <p>Para saber mais, consulte a <a href="../../designing/using/designing-content-in-adobe-campaign.md">documentação detalhada</a> e o <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html">vídeo de instruções</a>. Os aprimoramentos e correções estão listados abaixo.</p><p>Como consequência, o editor herdado de conteúdo de email agora está obsoleto. Para obter mais informações, consulte esta <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=pt-BR#release-notes">página</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Listas de produtos em emails transacionais<br /> </td> 
   <td> <p>Agora você pode fazer referência a uma ou mais coleções de produtos em uma mensagem de email transacional. Por exemplo, você pode enviar um email de abandono de carrinho automaticamente listando todos os produtos que estavam no carrinho do usuário com uma imagem, preço e link para cada produto.</p><p>Para saber mais, consulte a <a href="../../designing/using/using-product-listings.md">documentação detalhada</a> e o <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html">vídeo de instruções</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Exibição de publicação de conteúdo para dispositivos móveis no Designer de email<br /> </td> 
   <td> <p>Agora você pode alternar para uma exibição móvel dedicada ao editar conteúdo de email. Isso permite ajustar o design responsivo de um email editando separadamente todas as opções de estilo para exibição em dispositivos móveis, como margens adaptáveis, fonte menor, cor de fundo diferente etc.</p><p> Para obter mais informações, consulte a <a href="../../designing/using/plain-text-html-modes.md#switching-to-mobile-view">documentação detalhada</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Melhorias beta nas Mensagens no aplicativo<br /> </td> 
   <td> <p>O recurso beta de Mensagens no aplicativo foi aprimorado com os seguintes recursos:</p> 
    <ul> 
     <li> O canal beta no aplicativo é compatível com o GDPR </li> 
     <li> Integração com APIs do Analytics para preencher menus suspensos de Acionadores </li> 
     <li> Aparência intuitiva e descrição de modelos de entrega </li> 
     <li> Aprimoramentos na interface de criação do ponto de vista de utilização </li> 
    </ul> <p>Para obter mais informações, consulte a <a href="../../channels/using/about-in-app-messaging.md">documentação detalhada</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

**Aprimoramentos**

* Uma nova opção na atividade Load data agora permite aplicar uma etapa de pós-processamento ao arquivo que contém os registros rejeitados (por exemplo, compactação no formato Zip). (CAMP-24521)
* Uma nova opção na atividade Update data agora permite configurar o tamanho máximo do lote para upload dos dados. (CAMP-28400)
* Seleção de estado de endereço dos perfis aprimorada. Ao selecionar um país, a lista suspensa &quot;Estado&quot; agora é atualizada automaticamente com valores de estados relevantes. (CAMP-28874)
* Uma nova opção na atividade Extract file agora impede a geração de um arquivo se a transição de entrada estiver vazia. Isso evita criar e carregar arquivos vazios em servidores SFTP.
* O relatório de resumo da entrega foi aprimorado.
* A lista de países disponíveis ao definir o endereço de um perfil foi enriquecida. (CAMP-26707)
* Uma mensagem de erro agora é exibida ao tentar importar um fluxo de trabalho integrado.

**Email Designer**

* Correção de um problema que ativava o recurso de unidade geográfica em um modelo de email ou fragmento de conteúdo criado com o Designer de email, mesmo que esse recurso estivesse desativado no Adobe Campaign, o que tornava o modelo ou fragmento indisponível ao tentar acessá-lo novamente. (CAMP-28174)
* Correção de um problema que impedia que as condições de conteúdo dinâmico fossem salvas ao editar conteúdo com o Designer de email. (CAMP-27905)
* Correção de um problema que removia a versão de HTML do conteúdo de email após editar a versão de texto sem formatação de uma mensagem e romper a sincronização de HTML no Designer de email. (CAMP-28507)
* Correção de um problema que impedia a abertura da interface do Designer de email ao usar o Internet Explorer 11. (CAMP-28273)
* Correção de um problema que distorcia a renderização de configurações de estilo do Microsoft Outlook aplicada a botões com o Email Designer.
* Correção de um problema no Designer de email que tornava editável um URL de um fragmento de conteúdo usado em um email, o que não era esperado, pois o fragmento estava bloqueado por padrão.
* Correção de um problema que impedia que o componente divisor do Email Designer fosse exibido no Microsoft Office.
* Correção de um problema que causava o congelamento de uma página em determinados navegadores da Internet ao visualizar um conteúdo sincronizado do AEM usando o editor herdado de conteúdo de email. (CAMP-29068)
* Correção de um erro que ocorria ao clicar em qualquer imagem em um email ao usar o editor herdado de conteúdo de email. (CAMP-30424)
* Correção de um problema que impedia que os fragmentos recém-criados fossem exibidos ao editar um email com o Designer de email. (CAMP-29928)
* Correção de um problema que impedia que o texto do botão fosse exibido corretamente em emails criados com o Designer de email e recebidos usando o cliente de webmail do Outlook.
* Agora é possível criar mensagens transacionais de perfil usando o Designer de email. (CAMP-28900)
* Correção de um erro no Email Designer que tornava o conteúdo editável ao recuperar conteúdo de um URL automaticamente no momento da preparação, enquanto deveria ser bloqueado.

**Correções**

* Correção de um problema que mostrava logs de entrega incorretos em Relatórios dinâmicos. (CAMP-23446)
* Correção de um problema que poderia afetar os números no relatório de Resumo da rejeição (CAMP-28703)
* Correção de um problema com a integração do Campaign e do Serviço principal de ativos que podia impedir a exibição de ativos ao selecionar **[!UICONTROL Image shared from Adobe Experience Cloud]** em um email (CAMP-28732).
* Correção de um problema que impedia o envio de mensagens SMS contendo o caractere &quot;oe&quot;, mesmo que a transliteração fosse autorizada na conta externa SMPP. (CAMP-29041)
* Correção de um problema que poderia exibir registros duplicados ao usar uma atividade de Segmentação em workflows. (CAMP-28743)
* Correção de um problema que impedia a exclusão de um dos mapeamentos de valores em uma coluna em uma atividade de workflow. (CAMP-28708)
* Correção de um problema na atividade Transferência de arquivo, ao usar curingas com a opção &quot;Testar para ver se o arquivo existe&quot;. (CAMP-28977)
* Correção de um problema na atividade Transferência de arquivo que poderia ocorrer ao atualizar as configurações da conta externa. (CAMP-28894)
* Correção de um problema com filtros personalizados no editor de consultas ao usar a condição &quot;Email não está vazio&quot;. (CAMP-28741)
* Correção de um problema que poderia ocorrer ao exportar tabelas de recursos personalizadas com mais de 100k registros. (CAMP-28150)
* Correção de um problema que impedia a exclusão de mensagens transacionais vinculadas a acionadores. (CAMP-28385)
* Senhas removidas que foram exibidas sem segurança em alguns logs SMS.
* Correção de um problema que causava a falha das conexões com o simulador SMPP devido a senha vazia enviada pelo Adobe Campaign.
* Correção de um problema que impedia o envio de campanhas quando as conexões SMS estavam instáveis.
* Correção de um problema que exibia deliveries excluídos em Dynamic Reporting.
* Correção de um problema que poderia impedir a recuperação de dados adicionais de logs do delivery, logs de rastreamento e tabelas de logs de exclusão ao usar uma atividade de Enriquecimento em um workflow.
* Correção de um problema com solicitações de exclusão do GDPR que poderia ocorrer ao usar um tipo de link &quot;Link de coleção de cardinalidade N&quot; e a opção &quot;Excluir o registro de destino implica excluir referências de registros pelo link&quot;.
* Correção de um problema com o compartilhamento de relatórios.
* Correção de um problema que poderia levar a problemas de taxa de transferência ao enviar uma notificação por push.
* Correção de um problema com campos ausentes nos arquivos de saída de correspondência direta.
* Correção de um problema que permitia aos usuários modificar workflows incorporados.
* Correção de um problema ao criar uma campanha com base em um template de campanha incluindo um workflow com uma atividade de extração configurada. (CAMP-29198)
* Correção de um problema com a atividade File extraction que impedia de usar a mesma expressão para vários elementos. (CAMP-29182)
* Correção de um problema no Editor de consultas com a condição de associação entre broadlog e o log de rastreamento para rtEvent. (CAMP-28780)
* Correção de um problema que impedia que modificações na opção de página de aterrissagem &quot;Ação específica&quot; fossem salvas. (CAMP-29422)
* Correção de um problema que impedia a exportação da carga de um evento em um workflow. (CAMP-29029)
* Correção de um problema que impedia que os números SMS na inclui na lista de bloqueios fossem excluídos em uma mensagem SMS. (CAMP-28898)
* Correção de um problema que impedia que provedores SMPP fossem notificados em caso de erro ao processar mensagens de entrada. (CAMP-29804)
* Correção de um problema que permitia que contas externas com entregas associadas fossem excluídas. (CAMP-29738)
* A taxa de transferência de envio foi aprimorada e estabilizada para mensagens SMS.
* Correção de um problema que impedia que o caractere &quot;~&quot; fosse usado em uma mensagem SMS. (CAMP-29172)
* Correção de um problema nos deliveries com a opção Send time otimization. (CAMP-29231)
