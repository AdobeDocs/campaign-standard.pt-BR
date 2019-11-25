---
title: Notas de versão
description: Esta página lista todas as versões recentes do Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b06edadfa963881403328c4ab37d25d701bc8237

---


# Notas de versão{#release-notes}

Todas as versões de 2019, com seus novos recursos e patches, estão listadas nesta página. As atualizações do Painel de controle também estão incluídas.

Recursos adicionais:

* [Planejamento de lançamento da campanha](https://helpx.adobe.com/campaign/kb/acs-release-planning.html)
* [Atualizações mais recentes da documentação](../../rn/using/documentation-updates.md)
* [Recursos descontinuados e removidos](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)
* [Painel de controle](https://helpx.adobe.com/campaign/kb/control-panel.html)
* Notas de versão anteriores: [2018](../../rn/using/release-notes-2018.md), [2017](../../rn/using/release-notes-2017.md), [2015-2016](../../rn/using/release-notes-2015-2016.md)

## Versão 19.4 - outubro de 2019 {#release-19-4---october-2019}

### What's new? {#what-s-new-5}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> California Consumer Privacy Act (CCPA)<br /> </td> 
   <td> <p>A CCPA é a nova lei de privacidade do estado da Califórnia que harmoniza e moderniza os requisitos de proteção de dados que entram em vigor em 1° de janeiro de 2020. O CCPA se aplica aos clientes do Adobe Campaign que detêm dados para pessoas de dados residentes na Califórnia.</p>
   <p>Além dos recursos de privacidade já disponíveis no Adobe Campaign (incluindo gerenciamento de consentimento, configurações de retenção de dados e funções de usuário), estamos aproveitando esta oportunidade para incluir recursos adicionais, para ajudar a facilitar sua preparação para CCPA:</p>
   <ul>
    <li>Direito de acesso e direito de exclusão: estamos aproveitando as capacidades que foram adicionadas ao RGPD. <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#righttoaccess">Saiba mais</a> </li>
    <li><p>Ao criar uma solicitação de privacidade, o tipo de regulamento (RGPD ou CCPA) foi adicionado ao Privacy Core Service. Este método é o que você deve usar para todas as solicitações de acesso e exclusão. O uso da API de campanha e da interface para acessar e excluir solicitações está obsoleto.  Consulte o artigo <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">Recursos removidos e</a>obsoletos.</p></li>
    <li>Um campo <strong>CCPA Opt-Out</strong> foi adicionado ao recurso Perfis para permitir que os usuários do Adobe Campaign rastreiem se um consumidor optou pela venda de Informações pessoais. <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#ccpa">Saiba mais</a>.</li>
  </ul>
    <p>Consulte o vídeo <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">como fazer</a>.</p>
</td> 
  </tr> 
  <tr> 
   <td> Integração do Microsoft Dynamics 365 (GA)<br /> </td> 
   <td> 
    <p>A integração entre o Adobe Campaign Standard e o Microsoft Dynamics 365 está disponível. Você poderá transferir seus registros de contato e entidade personalizados do Dynamics 365 para o Campaign e obter dados de eventos de email do Campaign para o Dynamics 365 para melhorar o alinhamento de vendas/marketing.</p>
    <p>Consulte a documentação <a href="https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html"></a> detalhada para configurar essa integração e exibir o vídeo <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/integrating/microsoft-dynamics365-connector/introduction.html">de</a>instruções.</p>
  </td>
  </tr> 
 </tbody> 
</table>

### Aprimoramentos {#improvements-3}

* O pop-up de consentimento para relatórios dinâmicos foi atualizado para incluir a integração entre o Adobe Campaign Standard e o Microsoft Dynamics 365. Ao aceitar os termos, os dados do perfil serão incluídos ao usar a integração do Adobe Campaign Standard / Microsoft Dynamics 365 e o Relatório dinâmico. [Leia mais](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) (CAMP-29766)
* Correção de um problema que exibia datas de contato incorretas ao receber alertas de entrega.
* Quando um evento de mensagem transacional é enviado com um parâmetro de contexto desconhecido, o Campaign agora retorna uma mensagem de erro "400" em vez de "500". (CAMP-28632)
* Um novo segmento de prova **de** exclusão foi adicionado nos relatórios dinâmicos. Esse segmento agora é selecionado por padrão para filtrar seus relatórios. [Leia mais](../../reporting/using/list-of-components-.md#segments)
* A opção de expiração **da** mensagem foi adicionada à notificação por push. Ela permite especificar uma data de expiração na qual a mensagem não será mais enviada pela Apple (APNS) ou Android (FCM). [Leia mais](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* Foram feitas melhorias na atividade de arquivo **** Load: os logs de fluxo de trabalho foram tornados mais claros e detalhados sobre o erro que ocorre quando um arquivo falha ao carregar. A transição de saída gerada ao ativar a opção **Manter os rejeitos em um arquivo** foi renomeada como **Rejeitos**. [Leia mais](../../automating/using/load-file.md#load-files)
* Vários registros relacionados foram adicionados aos logs de envio para entender melhor as falhas de envio devido aos idiomas ausentes nos arquivos CSV carregados.

### Aprimoramentos de segurança {#security-enhancements-3}

* Correção de um problema ao excluir as informações de um perfil quantificado por meio de uma solicitação de privacidade, que removia todos os dados, exceto o endereço de email na lista de quarentena.
* A segurança foi aprimorada para proteção contra injeções em cabeçalhos de email.
* A segurança foi aprimorada para proteção contra ataques SSRF nos quais as expressões xtk podem ser usadas (HTML de email, conteúdo e assunto de texto, SMS e conteúdo de notificação por push).

### Aprimoramentos do Designer de email {#email-designer-enhancements-4}

* Ao editar um link usando o designer de email, agora é possível usar a opção de link **** Sublinhado. Além disso, uma propriedade **Target** foi adicionada com o valor padrão definido como **Nenhum**. [Leia mais](../../designing/using/styles.md#about-styling-links)
* Correção de um problema de cor em links em componentes de texto no corpo de um email. (CAMP-37330)
* Correção de um problema que impedia a remoção de links associados ao excluir uma imagem. (CAMP-37234)
* Correção de um problema que impedia salvar modificações nas configurações de **Ordem** do conteúdo dinâmico em uma condição. (CAMP-36883)
* Correção de um problema ao pesquisar páginas iniciais. A pesquisa foi estendida dos 50 primeiros criados para todos os bancos de dados. (CAMP-36839)
* Corrigido um problema ao salvar modificações no remetente de email em **De: Campo Nome** . (CAMP-36606)
* O aviso de compatibilidade do componente de carrossel foi modificado para refletir os clientes de email suportados.
* Correção de um problema de exibição em dispositivos móveis. O atributo height agora está sempre definido como "height: auto" ao adicionar ou carregar uma nova imagem em um email. (CAMP-35497)
* Correção de um problema que deixava estilo e tags meta no HTML ao excluir um fragmento de um componente de estrutura. (CAMP-35390)
* Correção de um problema com fragmentos ao atualizar conteúdo reutilizável. (CAMP-35186)
* Correção de um problema ao exibir somente conteúdo condicional móvel em emails. (CAMP-35155)
* Correção de um problema que exibia aleatoriamente espaços sem quebra de largura zero. (CAMP-35116)
* Correção de um problema com a posição dos botões na caixa de diálogo **Salvar como fragmento** .
* Correção de um problema de visualização ao adicionar uma tag HTML em um título de imagem e texto alternativo.
* Correção de um problema ao editar, no designer Email, links criados em emails do editor legado.
* Correção de um problema que deixava marcas de estilo duplicadas no conteúdo.
* Correção de um problema com o formato de data ao inserir um campo de personalização em um email.
* Correção de um problema de salvamento ao alternar do modo HTML para texto sem formatação.
* Correção de um problema ao clicar na opção Bloquear e desbloquear que adicionava valores de margem no painel de propriedades de estilo incorporado.
* Correção de um problema com o tamanho da visualização móvel para melhor renderização.
* Correção de um problema com o tamanho dos botões em modelos e fragmentos.
* Correção de um problema com o tamanho das imagens quando inseridas em um componente de botão.

### Outras alterações {#other-changes-3}

* O intervalo de tempo padrão para o qual os dados são mostrados nas páginas de KPI de entrega e na página Relatório dinâmico foi alinhado para evitar discrepâncias nos resultados do relatório. (CAMP-35148)
* Uma mensagem de erro foi adicionada nos registros quando o certificado do aplicativo expira.
* A visualização do cálculo de carga agora inclui o tamanho do campo personalizado para evitar falhas de notificação por push. (CAMP-35303)
* O nome do arquivo **** Rejeitado na atividade de arquivo **** Carregar agora pode ser personalizado da mesma forma que na atividade de exportação **de** Arquivo.
* Todas as entidades personalizadas que não estão vinculadas a nenhuma entidade predefinida podem ser acessadas por meio da API.
* Desempenho de banco de dados aprimorado em grandes recursos.
* As descrições de alguns erros que ocorrem ao enviar mensagens SMS foram clarificadas. (CAMP-36558)
* Uma mensagem de erro agora é exibida ao executar uma atividade do **Agendador** do fluxo de trabalho que está conectada a si mesmo, diretamente ou por meio de várias atividades, pois isso pode levar a que o servidor de fluxo de trabalho da instância fique travado.
* Foram feitas melhorias para ajudar a solucionar problemas de mensagens transacionais: o link "Dados" foi renomeado como "Últimos eventos transacionais" na tela de configuração do evento, agora ele lista os eventos recebidos classificados em ordem decrescente. Além disso, um novo status de evento transacional foi criado: "targetingFailed". Quando o módulo de mensagens transacionais falha ao enriquecer um link que é usado para direcionamento de mensagem, o evento transacional agora estará nesse novo estado (em vez do status "roteamentoFailed").
* Foram feitas melhorias na interface ao restringir o acesso da página de aterrissagem a unidades geográficas ou organizacionais específicas. O objetivo é avisar que a página de aterrissagem pode estar sujeita a condições de visibilidade: a seleção de uma unidade geográfica e organizacional ao criar uma página de aterrissagem é agora obrigatória. Um banner com informações relacionadas agora é exibido assim que uma unidade é selecionada. A mensagem de erro que é exibida ao testar a página inicial ficou mais clara.
* Nas APIs do Campaign Standard, as chaves personalizadas não podem ser modificadas usando uma operação PATCH se o valor da chave for diferente da chave de origem ou se você estiver usando sua própria chave comercial como URI em vez da fornecida pela Adobe.
* O idioma "Albanês - Macedônia" foi adicionado à lista suspensa de idiomas preferenciais. (CAMP-35396)

### Correções {#patches-4}

* Correção de um problema que impedia relatórios agendados de serem classificados ou pesquisados.
* Correção de um problema com regras de Acionadores que fazia com que as regras E e OU fossem misturadas.
* Correção de um problema que exibia a propriedade Mobile como Excluído no Launch. (CAMP-35382)
* Correção de um problema que impedia a sincronização das propriedades móveis do Adobe Launch no Adobe Campaign. (CAMP-35411, CAMP-35089, CAMP-35014, CAMP-35487)
* Correção de um problema em que as mensagens de push transacionais falhavam quando os eventos eram enriquecidos com dados de perfil. (CAMP-34385)
* Correção de um problema em que as propriedades móveis não eram sincronizadas em vários ambientes. (CAMP-37060)
* Correção de um problema ao selecionar, em uma notificação por push, um modelo usando uma fórmula de data de contato. (CAMP-35300)
* Correção de um problema que resultava em falha do serviço de envio de mensagens. (CAMP-35287)
* Correção de um problema com emails diretos recorrentes, todos definidos com a data do primeiro evento. (CAMP-35139)
* Correção de um problema com os recursos personalizados **Perfis** estendidos recentemente que não estavam disponíveis para consultas. (CAMP-35119)
* Correção do modo de estrutura **do banco de dados de** Reparo para instâncias com configuração de Compartilhamento ativada. (CAMP-35118)
* Correção de um problema que resultava em um erro de log SQL ao adicionar dados agregados em logs. (CAMP-35034)
* Correção de um problema com transições ao criar uma atividade de **Segmentação** . (CAMP-35033)
* Correção de um problema na atividade **Query** que impedia que a função **encrypt_aescbcDecrypt** descriptografasse a função **encrypt_aescbcEncrypt** . (CAMP-34952)
* Correção de um problema que impedia que os logs **de** rastreamento fossem exibidos em entregas. (CAMP-34855)
* Correção de um problema ao usar uma fórmula de data personalizada de otimização **de tempo de** envio, que poderia impedir o envio de notificações por push devido a erros nos dados adicionais do fluxo de trabalho. (CAMP-30336)
* Correção de um problema que impedia a publicação de recursos personalizados. (CAMP-37425)
* Correção de um problema que impedia que usuários administradores modificassem pacotes de importação.  (CAMP-37176)
* Correção de um problema em fluxos de trabalho que impedia o envio de provas, se a atividade de entrega estivesse conectada a uma atividade vazia de público-alvo **de** Leitura. (CAMP-37164)
* Correção de um problema que impedia a importação de recursos personalizados para um novo ambiente. (CAMP-36506)
* Correção de um problema em relatórios de cliques ativos que resultava em porcentagens ocultas por imagens (CAMP-36407)
* Correção de um problema que ocorria ao tentar exportar um campo de descrição de entrega. (CAMP-35467)
* Correção de um problema que podia deixar o estado de uma entrega como "Iniciar pendente", embora a entrega estivesse concluída. (CAMP-35355)
* Correção de um problema que impedia a exibição de logs de fluxo de trabalho após a ativação e, em seguida, a desativação de logs SQL.

## Atualização do Painel de Controle - agosto de 2019 {#controlpanel-update---august-2019}

### What's new? {#what-s-new-4}

Adicionamos novos recursos para que os usuários administradores recebam notificações antes que os certificados SSL de seus domínios expirem. Para obter mais informações, consulte a [documentação detalhada](https://helpx.adobe.com/campaign/kb/control-panel-subdomains-certificates.html).

Além disso, agora os usuários administradores podem excluir chaves SSH que foram adicionadas para acessar os servidores SFTP.

Observe que o Painel de controle está disponível apenas para clientes hospedados no AWS. Essas atualizações estarão disponíveis em 26 de agosto.

## Versão 19.3 - julho de 2019 {#release-19-3---july-2019}

### What's new? {#what-s-new-3}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Atividade de API externa (beta público)<br /> </td> 
   <td> <p>Para personalização mais profunda, a Atividade de API externa permite que você coloque dados de sistemas externos em um fluxo de trabalho por meio de uma chamada de API REST. Os pontos de extremidade REST podem ser um sistema de gerenciamento de clientes, o Adobe I/O Runtime ou o terminal REST da Adobe Experience Cloud (por exemplo, Plataforma de dados, Target, Analytics, Campaign).</p><p>Esse recurso está atualmente em beta público.</p><p>Para obter mais informações, consulte a <a href="../../automating/using/external-api.md">documentação detalhada</a> e o <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">vídeo de instruções</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Relatório no segmento de fluxo de trabalho<br /> </td> 
   <td> <p>Esse recurso permite que os profissionais de marketing detalhem seu desempenho de entrega por código de segmento. Quando você cria um fluxo de trabalho e usa uma atividade de segmentação para atribuir segmentos ao preenchimento da entrega, esses segmentos agora podem entrar na mesma entrega. Isso permite exibir as estatísticas de abertura/cliques com base em vários segmentos em uma única entrega.</p><p>Para obter mais informações, consulte a <a href="../../reporting/using/creating-a-report-workflow-segment.md">documentação detalhada</a> e o <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">vídeo de instruções</a>.</p></td>
  </tr> 
 </tbody> 
</table>

### Aprimoramentos de segurança {#security-enhancements-2}

* Correção de um problema de segurança para impedir ataques de negação de serviço (DoS) em solicitações inválidas para obter imagens. (CAMP-33454)

### Aprimoramentos do Designer de email {#email-designer-enhancements-3}

* Correção de um problema que adicionava tags de estilo HTML adicionais a um modelo HTML sempre que um componente era adicionado, o que poderia aumentar drasticamente o tamanho do modelo. (CAMP-34694)
* Corrigido um problema que impedia que algumas opções de menu da barra de ferramentas superior direita ficassem disponíveis. (CAMP-34577)
* Correção de um problema que ocorria quando o bloco de conteúdo do URL da página Espelho era inserido em um conteúdo de email. (CAMP-34779)
* Correção de um problema que ocorria ao usar o código JSPP em um email, dificultando a edição do conteúdo. (CAMP-34574)
* Correção de um problema que resultava em imagens truncadas na parte superior quando um hiperlink era adicionado a elas. (CAMP-34382)
* Correção de um problema de exibição ao usar o Designer de email com o Firefox. (CAMP-34364)
* Correção de vários problemas que ocorriam no modo Avançado ao definir o conteúdo dinâmico em um email. (CAMP-34351, CAMP-34333, CAMP-34331)
* Correção de vários problemas que ocorriam com o editor de regras de conteúdo dinâmico (CAMP-34304, CAMP-34303).
* Correção de um problema que impedia a exibição do campo Link no painel Configurações do Designer de email (CAMP-33749).
* Correção de um problema com o ícone do YouTube que era superdimensionado em emails enviados. (CAMP-33726)
* Correção de um problema de segurança que tornava o conteúdo da página espelhada editável. (CAMP-33691)
* Correção de um problema que quebrou a saída HTML ao usar o símbolo maior que no conteúdo dinâmico. (CAMP-33688)
* Correção de um problema que ocorria ao usar a opção Desfazer ao editar texto no Designer de email. (CAMP-32565)
* Correção de um problema que criava tags extras ao desfazer estilos em vez de removê-los. (CAMP-32359)
* Agora você pode definir se cada componente usado em um email será exibido somente em dispositivos desktop ou somente em dispositivos móveis.
* Agora é possível definir a largura e a altura de um componente de conteúdo do Social.
* Correção de um problema que impedia a remoção do código de origem antigo do conteúdo dinâmico após a exclusão desse conteúdo dinâmico.
* Correção de um problema que impedia que o assunto de um email fosse atualizado após sua modificação.
* Correção de um problema que impedia que uma estrutura de coluna n:n fosse selecionada uma vez solta no espaço de trabalho.
* Correção de um problema que fazia com que a miniatura da mensagem fosse exibida desfocada no painel de email.
* Correção de um problema que impedia que o plano de fundo fosse exibido corretamente em emails recebidos no Outlook.
* Correção de alguns problemas de classificação na página inicial do Email Designer.
* Correção de um problema que ocorria ao duplicar variantes ao usar conteúdo dinâmico.
* Alguns campos indesejados foram removidos do painel Configurações do Designer de email.

### Outras melhorias {#other-improvements-3}

* Por meio da integração com o Adobe Experience Platform Location Services, o Adobe Campaign agora é compatível para enviar mensagens de marketing baseadas em localização aos assinantes do aplicativo móvel por meio do Experience Platform SDK. Para obter mais informações, consulte a [documentação detalhada](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md).
* O recurso de relatório foi aprimorado para uma melhor experiência. Para usar esse recurso, é necessário aceitar o Contrato de uso de relatórios dinâmicos. For more on this, refer to the [detailed documentation](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* Em fluxos de trabalho, uma nova opção foi adicionada para visualizar as próximas dez execuções de um fluxo de trabalho. For more on this, refer to the [detailed documentation](../../automating/using/scheduler.md).
* Na atividade do Agendador, uma nova opção permite selecionar um dia específico de uma semana específica para entregas mensais. For more on this, refer to the [detailed documentation](../../automating/using/scheduler.md).
* Ao criar entregas recorrentes sem período de agregação, o painel de entrega agora permite solicitar confirmação antes de a entrega ser enviada. For more on this, refer to the [detailed documentation](../../sending/using/confirming-the-send.md).
* Agora você pode personalizar um rótulo de entrega com variáveis de evento que foram declaradas na atividade de sinal externo do fluxo de trabalho. For more on this, refer to the [detailed documentation](../../automating/using/calling-a-workflow-with-external-parameters.md).
* A consulta de exclusão do RGPD foi aprimorada para melhorar o desempenho. (CAMP-33504)
* A opção "ftp" foi removida da interface de configuração de conta externa. (CAMP-34472)
* Agora você pode ativar e desativar a opção de modo de teste SMTP para cada mensagem de email. For more on this, refer to the [detailed documentation](../../administration/using/configuring-email-channel.md#smtp-test-mode). (CAMP-34602)

### Outras alterações {#other-changes-2}

* Um aviso foi adicionado na interface de propriedades de entrega. Ela especifica que as entregas são preparadas com base em seu período de agregação e não para chamar o fluxo de trabalho várias vezes por dia, verifique se elas não têm nenhum período. (CAMP-34393)
* Um aviso foi adicionado nas telas de configuração de recursos personalizados. Recomendamos o uso do máximo de 30 caracteres para IDs de recursos personalizados. Isso também se aplica a campos de recursos personalizados, chaves, índices e links.
* Agora, uma mensagem é exibida ao tentar excluir uma mensagem transacional usada por uma página de aterrissagem como mensagem de confirmação.
* Um aviso agora aparece nos logs de fluxos de trabalho quando uma atividade está sendo executada por mais de 6 horas. Isso não se aplica às atividades de notificação por push, entrega, sinal, início, fim, bifurcação, junção E, agendamento e espera.
* Um aviso agora aparece nos logs de fluxos de trabalho quando você atinge o número máximo de fluxos de trabalho que estão sendo executados simultaneamente.
* Os fluxos de trabalho que estão em estado de pausa ou de falha há mais de 7 dias são agora interrompidos para consumir menos espaço em disco. A tarefa de limpeza é exibida nos registros do fluxo de trabalho.
* Ao usar uma atividade "Transferir arquivo", um erro será registrado se o tamanho do arquivo exceder o espaço em disco disponível.
* A ação Redirecionar para URL de destino não pode mais ser selecionada para o botão secundário nas mensagens no aplicativo.

### Correções {#patches-3}

* Correção de um problema que resultava em falha de solicitações de acesso ao RGPD.
* Correção de um problema que resultava no descarte de acionadores quando vários acionadores eram recebidos para um perfil exclusivo.
* Correção de um problema que resultava em uma mensagem de erro de publicação de recursos personalizados incorreta após o logon.
* Correção de um problema que exibia uma página em branco ao criar ou estender um recurso personalizado.
* Correção de um problema que impedia que um público-alvo com appSubscriptionrcp como a dimensão de definição de metas estivesse disponível para definição de metas em uma entrega móvel.
* Correção de um erro que impedia que endereços de email de rejeição em disco fossem colocados em quarentena. (CAMP-24587)
* Correção de um problema que ocorria ao adicionar uma regra de tipologia e, em seguida, excluí-la antes de salvar a tipologia. (CAMP-32789)
* Correção de um problema que impedia a exibição do conteúdo da página inicial ao desativar o conteúdo dinâmico. (CAMP-32924)
* Correção de um problema com entregas recorrentes que ocorria ao usar a personalização nos atributos de uma entrega mestre. (CAMP-32983)
* Correção de um problema nos fluxos de trabalho que impedia a leitura dos resultados de uma transição que contém dados de mensagens SMS recebidas. (CAMP-33134)
* Correção de um problema nos fluxos de trabalho que ocorria ao combinar atividades de bifurcação e exclusão para criar públicos-alvo. (CAMP-33401)
* Correção de um problema que impedia a exibição do conteúdo da página espelhada e o envio de mensagens de prova para entregas recorrentes. (CAMP-33413)
* Correção de um problema que resultava em erro ao usar uma atividade da União entre perfis e públicos. Esse problema foi causado por uma incompatibilidade das chaves de identificação nas transições de entrada. (CAMP-33713)
* Corrigido um problema nas atividades de Teste que impedia que a expressão "recCount" usasse a sintaxe correta ao clicar duas vezes. (CAMP-33756)
* Correção de um problema que resultava em uma mensagem de erro ao abrir os logs técnicos do fluxo de trabalho de cobrança. (CAMP-34313)
* Corrigido um problema nas páginas iniciais que ocorria ao configurar campos de caixa de seleção com assinaturas. (CAMP-34369)
* Correção de um problema que ocorria ao configurar uma lista e adicionar o campo "ícone" a ela. (CAMP-34585)
* Correção de um problema que impedia o uso dos símbolos "|" e "%" como separadores de data ou hora em atividades de fluxo de trabalho de arquivo de carregamento. (CAMP-34706)
* Correção de um problema que ocorria ao usar condições de visibilidade com caixas de seleção em páginas iniciais. (CAMP-34802)
* Correção de um problema na atividade Enriquecimento que impedia a exibição de campos na guia "Dados adicionais", se a dimensão de filtragem estivesse definida como logs de rastreamento e a dimensão de destino para perfil.
* Correção de um problema que resultava em uma mensagem de erro ao exportar um recurso "workflowTemplate".
* Correção de um problema ao criar um novo perfil, que impedia que o campo "Código do país/região" fosse salvo se fosse selecionado na caixa de diálogo.
* Correção de vários problemas que ocorriam ao usar o modelo de importação de Mala direta (updateQuarantinesDeliveryLogsDirectMail).
* Correção de um problema relacionado à integração dos Ativos sob demanda.
* Correção de um problema que ocorria ao ampliar na exibição da Linha do tempo. (CAMP-33628)
* Correção de um problema que impedia que provas fossem enviadas instantaneamente para mensagens de email com data e hora agendadas. (CAMP-33723)
* Correção de um problema relacionado a mensagens transacionais que geravam registros de erros quando um usuário logout. (CAMP-31698)
* Corrigido um erro que ocorria em ambientes específicos ao agendar uma mensagem de email.
* Correção de um problema que causava a falha do fluxo de trabalho de execução de entrega de Atualização.
* Correção de um problema de segurança que quebrava o conteúdo do email quando o assunto continha várias linhas.


## Versão 19.2.7 - julho de 2019 {#release-19-2-7---july-2019}

### Aprimoramentos {#improvements-2}

* A consulta de exclusão do RGPD foi aprimorada para melhorar o desempenho.
* Corrigido um problema que causava falhas na Web após a atualização 19.2. (CAMP-34862)
* Corrigido um problema que impedia que usuários que não fossem administradores salvassem ou agendassem relatórios. (CAMP-31133)
* Correção de um problema ao usar "|" como separador de datas na atividade de fluxo de trabalho Carregar arquivo. (CAMP-34706)

## Versão 19.2.4 - junho de 2019 {#release-19-2-4---june-2019}

### Email Designer {#email-designer-2}

* Correção de um problema que impedia os usuários de editar fragmentos quando tags de estilo vazias eram usadas no HTML. Esta é uma correção de acompanhamento para CAMP-33778 em 19.2.3.

## Versão 19.2.3 - junho de 2019 {#release-19-2-3---june-2019}

### Email Designer {#email-designer-1}

Introduziu uma série de melhorias e correções para otimizar fragmentos na versão 19.2. Os fragmentos recém-criados funcionarão perfeitamente. Os fragmentos criados anteriormente ficaram esmaecidos e precisam ser migrados para o novo formato. Para fazer isso, clique em cada fragmento e valide sua migração para o novo formato. Recomendamos que você teste alguns fragmentos antes de migrar todos eles.

* Correção de um problema que impedia os usuários de editar um fragmento após desbloqueá-lo. Isso afetava os fragmentos existentes ao atualizar para a versão 19.2. (CAMP-33778)
* Correção de um problema ao usar conteúdo dinâmico. Espaços adicionais foram adicionados no HTML.

### Outras melhorias {#other-improvements-2}

* Correção de um problema que impedia que o envio de SMS retomasse após uma desconexão do conector SMS.
* Correção de um problema que poderia fechar conexões SMPP quando TLS era ativado.
* Correção de um problema que poderia fechar conexões SMPP quando TLS era ativado.
* A opção "Launch_URL_Campaign" foi adicionada ao Campaign para gerenciar propriedades de aplicativos móveis criados com o SDK do Adobe Experience Platform Mobile.
* Corrigido um erro que fazia com que a opção de ambiente do Sandbox ficasse desmarcada depois de fazer upload do certificado de uma propriedade móvel recém-criada e sair da página de propriedades do aplicativo móvel.
* Correção de um problema que impedia o enriquecimento de um conteúdo de mensagem transacional com informações do recurso Serviço. (CAMP-33707)
* Correção de um problema nas páginas de aterrissagem da lista negra que ocorria ao tentar cancelar a assinatura de perfis de um serviço.

## Versão 19.2 - maio de 2019 {#release-19-2---may-2019}

### What's new? {#what-s-new-}

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
   <td> <p>Para ajudar a aumentar a eficiência do seu trabalho como usuário administrador, você pode monitorar facilmente a capacidade e gerenciar as configurações de suas instâncias (começando pelo gerenciamento de servidores SFTP).</p><p>Para obter mais informações, consulte a <a href="https://helpx.adobe.com/campaign/kb/control-panel.html">documentação detalhada</a> e o <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-control-panel-video-use.html">vídeo de instruções</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Notificações locais<br /> </td> 
   <td> <p>As mensagens de notificação locais permitem que você informe seus usuários quando novos dados estiverem disponíveis em seus aplicativos móveis, mesmo sem ter acesso à Internet ou ao aplicativo móvel em execução em primeiro plano. As notificações locais são acionadas por um aplicativo móvel em um horário específico e dependendo de um evento.</p><p>Para obter mais informações, consulte a <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">documentação detalhada</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Aprimoramento do fluxo de trabalho - Adicionar uma carga à atividade do sinal externo<br /> </td> 
   <td> <p>Inicie um fluxo de trabalho com uma carga quando as condições definidas forem atendidas com êxito a partir de outro fluxo de trabalho ou de uma chamada REST API para integração com seus sistemas externos. Isso também inclui uma nova atividade de <strong>teste</strong> na qual você pode executar testes nesta funcionalidade.</p><p>Para obter mais informações, consulte a <a href="../../automating/using/calling-a-workflow-with-external-parameters.md">documentação detalhada</a> e o <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-external-signal-activity-feature-video-use.html">vídeo de instruções</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Aprimoramento de páginas iniciais - Google reCAPTCHA<br /> </td> 
   <td> <p>Aproveite o Google reCAPTCHA para evitar spam em suas páginas de aterrissagem sem exigir qualquer ação dos clientes.</p><p>Para obter mais informações, consulte a <a href="../../channels/using/designing-a-landing-page.md#setting-google-recaptcha">documentação detalhada</a>.</p></td> 
  </tr> 
 </tbody> 
</table>

### Aprimoramentos de segurança {#security-enhancements}

* Corrigido um problema de segurança de cliques em potencial na área de trabalho de relatórios.

### Aprimoramentos do Designer de email {#email-designer-enhancements}

* Correção de um problema que ocorria ao duplicar fragmentos e tentar usá-los no Designer de email. (CAMP-33193)
* Correção de um problema que criava espaços indesejados ao usar elementos em linha na interface do Email Designer. (CAMP-32163)
* Correção de um problema que excluía alguns atributos adicionais de tag HTML adicionados pelo usuário após salvar o conteúdo do email no Designer de email. (CAMP-32162)
* Correção de um problema que exibia uma tag do Microsoft Office no modo HTML do Email Designer mesmo após a remoção. (CAMP-32141)
* Se você tiver criado um email usando uma versão anterior do Email Designer, ao abrir esse conteúdo, uma janela pop-up solicitará que o usuário atualize para a versão mais recente. (CAMP-31529)
* Correção de um problema que poderia distorcer imagens de um email criado com o Email Designer quando entregue a alguns clientes de mensagens. (CAMP-31407)
* Correção de um problema que impedia que alguns elementos, como listas ou botões, fossem exibidos corretamente no modo de texto simples quando criados no modo HTML. (CAMP-32582, CAMP-32542)
* Correção de um problema que impedia a exibição de mais de 50 unidades organizacionais em um modelo de conteúdo ou propriedades de fragmento. (CAMP-32932)
* Correção de um problema com a cor de fundo do visor ao receber um email criado com o Designer de email no Outlook. (CAMP-31402)
* Correção de um problema que impedia que o conteúdo de email criado com o Designer de email fosse responsivo quando aberto no Outlook. (CAMP-31400)
* Correção de um problema que impedia que o conteúdo dinâmico funcionasse corretamente quando usado em um assunto de email. (CAMP-32837)
* Correção de um problema relacionado ao assunto do email que não foi escapado corretamente.
* Correção de um problema que impedia o carregamento de fragmentos na paleta esquerda do Email Designer.
* Correção de um problema que impedia que fragmentos criados durante a edição de conteúdo de email fossem exibidos na paleta esquerda do Email Designer ao atualizar a lista de fragmentos.
* Correção de vários problemas que ocorriam ao usar conteúdo dinâmico em um email.
* Correção de um problema que ocorria com o seletor de cores ao tentar definir uma cor usando valores RGB.
* Correção de um problema que impedia que a página espelhada respondesse ao receber o email em um dispositivo móvel.

### Aprimoramentos de mensagens transacionais {#transactional-messaging-enhancements}

Vários aprimoramentos foram adicionados ao canal de mensagens transacionais para otimizar a operação e o desempenho.

* A duração da mensagem transacional foi estendida para garantir que todas as mensagens sejam enviadas antes de expirarem, especialmente quando as tentativas forem executadas.
* O desempenho de mensagens transacionais foi aumentado pela distribuição da carga em diferentes threads de envio.
* O processo de mensagens transacionais foi otimizado para ser capaz de iniciar em paralelo várias análises da mesma mensagem.
* Correção de um problema que resultava em throughput e latência inconsistentes para notificações por push transacionais.
* Correção de um problema que exibia um público-alvo incorreto para entregas de execução de mensagem transacional.
* Correção de um problema que ocorria ao importar um pacote com uma configuração de evento e a mensagem transacional associada. For more on this, refer to the [detailed documentation](../../channels/using/about-transactional-messaging.md#exporting-and-importing-transactional-messages).
* Correção de um problema que excluía os dados de coleta dos perfis de teste criados para uma mensagem transacional contendo as listas de produtos.

### Outras alterações {#other-changes}

* Uma nova opção foi adicionada à conta externa do SMS. Ela permite limitar o número máximo de processos MTA que enviam SMS para melhor controlar o número de conexões paralelas. Para obter mais informações, consulte a nota técnica de protocolo e configurações [do conector](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html) SMS.
* Ao publicar um recurso com extensão de API, se a API já tiver sido publicada, ela será atualizada automaticamente sempre que for publicada novamente. Anteriormente, essa ação era manual e a falha ao atualizar a API poderia quebrar o perfil ou o recurso de serviço dessa API. For more on this, refer to the [detailed documentation](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* A dimensão do CEP foi removida do Relatório dinâmico. Recomendamos usar as dimensões Cidade, País, Estado.
* O acionador de evento de ciclo de vida "Primeira inicialização" para mensagens no aplicativo foi removido.
* Ao exportar um pacote com grupos de segurança, ele agora contém as funções atribuídas a cada grupo. (CAMP-32960)
* Na atividade Carregar arquivo, uma nova opção permite verificar se as colunas do arquivo que você está carregando correspondem à definição da coluna. Para obter mais informações, consulte a [documentação detalhada](../../automating/using/load-file.md). (CAMP-32229)
* Os fluxos de trabalho agora podem ser iniciados com uma carga, permitindo que você use e compartilhe parâmetros externos entre atividades dentro do fluxo de trabalho. Para obter mais informações, consulte a [documentação detalhada](../../automating/using/calling-a-workflow-with-external-parameters.md). (CAMP-29412 e CAMP-29413)
* As APIs do Campaign Standard agora permitem que você atualize as unidades geográficas e organizacionais dos perfis usando uma carga. Para obter mais informações, consulte a [documentação detalhada](../../api/using/about-campaign-standard-apis.md).
* As mensagens de erro quando um objeto do banco de dados não está acessível foram tornadas mais claras para entender.
* Na atividade Extrair arquivo, os recursos do Javascript foram atualizados ao definir o nome de um arquivo a ser exportado. Somente a função formatDate está disponível para uso no campo Saída. Para obter mais informações, consulte a [documentação detalhada](../../automating/using/extract-file.md).
* A geração de ID de sequência automática foi aprimorada para recursos personalizados. As chaves primárias para novos recursos personalizados agora estão em 64 bits por padrão.
* O modo de teste de publicação de recursos personalizados foi aprimorado. Agora, uma mensagem de aviso é exibida aos usuários se a última publicação de recursos personalizados falhar e não for corrigida. Após uma falha de publicação de recursos personalizados, é possível reverter para a última versão em funcionamento. Para obter mais informações, consulte a [documentação detalhada](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
* Uma nova opção foi adicionada à atividade Transferir arquivo. Permite que você classifique os arquivos ao usar a ação de download de Arquivo, no modo SFTP. Para obter mais informações, consulte a [documentação detalhada](../../automating/using/transfer-file.md). (CAMP-33109)

### Correções {#patches}

* Correção de um problema que resultava em vazamento de memória para o MTA quando as configurações de SMS eram recarregadas.
* Correção de um problema que impedia a publicação de atualizações do banco de dados no modo de reparo.
* Correção de um problema que causava discrepância entre os Relatórios do Adobe Analytics e os Relatórios dinâmicos do Adobe Campaign. (CAMP-25393)
* Correção de um erro que causava a falha do fluxo de trabalho de compartilhamento de relatórios.
* Correção de um erro que impedia os usuários de enviarem mensagens no aplicativo com apenas o URL da mídia.
* Correção de um problema que exibia um aplicativo móvel mesmo se seu certificado não tivesse sido carregado para a instância.
* Correção de um erro que impedia que campos de personalização funcionassem ao usar o **Target para todos os usuários de um modelo de aplicativo** móvel.
* Novas instâncias do Campaign Standard foram provisionadas. (CAMP-32635 e CAMP-32344)
* Correção de um erro que impedia a personalização da fórmula de data em um fluxo de trabalho. (CAMP-30336)
* Correção de um problema ao definir uma fórmula de data personalizada que poderia impedir que os campos "Dados adicionais" e "Código do segmento" ficassem disponíveis na lista suspensa. (CAMP-32383)
* Correção de um problema que impedia que as atividades "Transferir arquivo" e "Extrair arquivo" localizassem os arquivos rejeitados se eles fossem criptografados. (CAMP-32377)
* Corrigido um problema nas APIs que impedia que o filtro lineCount renderizasse a contagem total exata. (CAMP-31424)
* Correção de um problema nas páginas iniciais que impedia que os campos de entrada exibissem o valor atualizado após sua modificação. (CAMP-31401)
* Correção de um problema que resultava na ativação inesperada de uma atividade de sinal.
* Correção de um problema que impedia a exibição da visualização de email quando o público-alvo estava vazio.
* Corrigido um problema na atividade "Extrair arquivo" que gerava um arquivo enquanto a opção "Não gerar um arquivo se a transição de entrada estiver vazia" estava ativada.
* Correção de um problema que resultava na desativação do fluxo de trabalho de Disponibilidade se ele não fosse concluído com êxito.
* Correção de um problema que impedia os usuários de salvar ou agendar relatórios. (CAMP-31133)

## Versão 19.1.3 - março de 2019 {#release-19-1-3---march-2019}

### Aprimoramentos do Designer de email {#email-designer-enhancements-1}

* Correção de um problema que impedia a modificação de um modelo após salvá-lo.
* Correção de vários problemas ao usar um modelo criado anteriormente em um email.
* Correção de um problema que impedia que os componentes ficassem ocultos em modelos importados.

### Outras melhorias {#other-improvements}

* Corrigido um erro ao exibir regras de tipologia. (CAMP-32059 e CAMP-31849)
* Correção de um problema que impedia a edição de regras de tipologia. (CAMP-31750)
* Correção de um problema com o processo do InMail que podia parar inesperadamente. (CAMP-31238)

## Versão 19.1 - fevereiro de 2019 {#release-19-1---february-2019}

### What's new? {#what-s-new--1}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Melhorias nos relatórios de canal de push<br /> </td> 
   <td> <p>Vários aprimoramentos foram adicionados aos relatórios de Canal de push para permitir que você avalie o envolvimento do usuário de forma mais intuitiva. Com esta versão, estamos expandindo a lista de Métricas de canal de push para três métricas diferentes: Impressões, cliques, aberturas (abertura do aplicativo) para ajudar a medir e analisar a interação dos usuários com as notificações por push com mais eficiência. Juntamente com isso, também estamos padronizando a definição e implementação dessas métricas. O relatório incorporado de notificação por push também foi aprimorado com visualizações e métricas comumente usadas.</p><p> Para obter mais informações, consulte a <a href="../../reporting/using/push-notification-report.md">documentação detalhada</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Iniciar integração para aplicativo móvel<br /> </td> 
   <td> <p>Esta versão contém a integração do Adobe Campaign com as versões GA das extensões Android e iOS para o Adobe Campaign Standard no Adobe Experience Platform Launch e SDKs móveis. Essas extensões suportam mensagens de push, mensagens no aplicativo e atualizações de perfil do aplicativo móvel.</p><p> Para obter mais informações, consulte a <a href="../../administration/using/about-typology-rules.md#typology-rules">documentação detalhada</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mensagens no aplicativo móvel<br /> </td> 
   <td> <p>Esta versão contém a versão GA do canal no aplicativo no Campaign. De um ponto de vista funcional, as adições mais notáveis à versão Beta são Relatórios dinâmicos para canal no aplicativo e handshake seguro entre o SDK móvel e o Mias (Serviço de mensagens no aplicativo da Marketing Cloud que serve as regras no aplicativo para o SDK). O handshake seguro garante que os dados de PII de seus usuários não caem em mãos mal-intencionadas, assim como permite manter a privacidade dos usuários em um dispositivo compartilhado, limpando o cache de mensagens sempre que o usuário fizer logoff.</p><p>For more information, refer to the <a href="../../channels/using/about-in-app-messaging.md">detailed documentation</a> and the dedicated <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-in-app-message-tutorial.html">In-App tutorial</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Melhorias no fluxo de trabalho<br /> </td> 
   <td> <p>Os seguintes recursos de fluxo de trabalho foram adicionados:</p> 
    <ul> 
     <li> Agora é possível copiar e colar atividades em um fluxo de trabalho ou em outro fluxo de trabalho da mesma instância do Campaign. Dessa forma, você pode duplicar facilmente um fluxo de trabalho inteiro ou atividades específicas e manter as configurações definidas inicialmente. Para obter mais informações, consulte a <a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">documentação detalhada</a>. (CAMP-2014) </li> 
     <li> Ao usar a atividade <strong>Carregar arquivo</strong> , agora é possível adicionar um carimbo de data e hora ao nome do arquivo que contém os registros rejeitados. Para obter mais informações, consulte a <a href="../../automating/using/load-file.md#configuration">documentação detalhada</a>. </li> 
     <li> <strong>As atividades de consulta</strong> e <strong>segmentação</strong> agora permitem ativar uma transição de saída se as atividades não recuperarem dados. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Aprimoramentos de segurança {#security-enhancements-1}

* O código HTML da página inicial gerado foi atualizado para impedir a indexação do mecanismo de pesquisa.

### Aprimoramentos do Designer de email {#email-designer-enhancements-2}

* Um conjunto dos quatro melhores modelos de e-mail responsivos da classe criados pelos artistas do Behance está disponível.

   Para obter mais informações, consulte a [documentação detalhada](../../designing/using/using-reusable-content.md#content-templates).

* Nossa nova experiência de integração o ajudará a iniciar a criação de e-mails mais rapidamente e a facilitar o acesso à documentação e aos tutoriais.

   Para obter mais informações, consulte a [documentação detalhada](../../designing/using/overview.md#email-designer-home-page).

* Agora você tem a flexibilidade de configurar o número de colunas e a largura com base em suas necessidades.

   Para obter mais informações, consulte a [documentação detalhada](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

* Ao editar na exibição móvel, você pode ocultar determinados componentes apenas na exibição móvel para um uso eficaz do espaço.

   Para obter mais informações, consulte a [documentação detalhada](../../designing/using/styles.md#switching-to-mobile-view).

* Agora você pode adicionar canais sociais personalizados ao seu modelo de email sobre os que já estão disponíveis.
* Correção de um problema que impedia a rolagem para baixo no menu de estrutura ao usar mais de 18 estruturas. (CAMP-31173)
* Correção de um problema que exibia o precabeçalho na parte superior do conteúdo ao encaminhar um email contendo um precabeçalho enviado com o Adobe Campaign. (CAMP-30736)
* Correção de um problema que impedia a atualização da linha de assunto ao clicar na opção **Atualizar conteúdo** do AEM após modificar o assunto no Adobe Experience Manager. (CAMP-29984)
* Correção de vários problemas que impedia o uso de imagens dinâmicas do Adobe Target.
* Correção de um problema que impedia que a visualização fosse atualizada ao recuperar conteúdo no momento da preparação se o conteúdo tivesse sido importado anteriormente de um URL.
* O ícone do YouTube foi adicionado ao componente de conteúdo do **Social** .
* A exibição **Lista** foi adicionada para componentes de conteúdo e fragmentos exibidos na paleta Designer de email.

### Outras melhorias {#other-improvements-1}

* O Adobe Campaign agora é totalmente compatível com o FCM para aplicativos SDK V4 e AEP SDK.
* O Adobe Campaign oferece suporte a notificações por push no Wear OS pelo Android, bem como a watchOS pela Apple.
* As mensagens de aviso e de erro que podem ser exibidas ao navegar na interface ficaram mais claras e mais fáceis de entender.
* Agora você pode adicionar às colunas da lista de perfis relacionadas à aceitação e à recusa ("Campos "Não entre em contato ...").
* A lista suspensa Fuso horário na tela de criação do perfil foi movida da seção Endereço para a seção superior da interface.
* Agora você pode adicionar separadores ao configurar telas de recursos personalizadas, permitindo que você organize seus campos em categorias.

   Para obter mais informações, consulte a [documentação detalhada](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration).

### Outras alterações {#other-changes-1}

* O Adobe Campaign e a Adobe Experience Cloud reduzirão o suporte ao Microsoft Internet Explorer 11 a partir do primeiro trimestre de 2019 e da versão 19.2 do Campaign Standard. Alterne para o Microsoft Edge ou outro navegador compatível. Consulte [Página de recursos](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html) obsoletos e removidos.
* O campo de código **do** país do recurso Perfil foi renomeado para código **do** país/região.

### Correções {#patches-1}

* Correção de um problema que impedia o envio da mensagem ao adicionar um perfil de teste a uma mensagem de email transacional. (CAMP-29854)
* Correção de um problema que atrasava o envio de mensagens de outros canais se o envio fosse baixo para um canal quando o envio de mensagens de todos os canais era acionado simultaneamente.
* Correção de um problema que fazia com que o MTA começasse a enviar mensagens SMS quando a conexão de conta externa ainda não estava estabelecida.
* Correção de um problema que ocorria com a frequência de execução da atividade do Agendador e a hora de início. (CAMP-30745)
* Correção de um problema que poderia ocorrer com a geração de PKEY ao usar recursos de perfil estendido. (CAMP-30285)
* Correção de um problema que ocorria com regras de Fadiga baseadas no dia do calendário. (CAMP-30136)
* Correção de um problema que ocorria ao tentar acessar recursos personalizados com nomes terminados com "Base". (CAMP-30109)
* Correção de um problema que impedia o uso de uma chamada PATCH para assinar um perfil para um serviço. (CAMP-29728)
* Correção de um problema que corrompia um fluxo de trabalho ao importar um arquivo XML pela atividade Carregar arquivo. (CAMP-29208 e CAMP-28205)
* Correção de um problema ao vincular recursos personalizados que poderia impedir a geração de links de cardinalidade reversa. (CAMP-30476)
* Correção de um problema que impedia estender registros de entrega ao usar somente o código do segmento.
* Correção de um problema que podia duplicar linhas ao usar a atividade de transferência de Arquivo em fluxos de trabalho.
* Correção de um problema que impedia o envio de relatórios agendados no horário escolhido.
* Correção de um problema que causava discrepância entre os KPIs "Enviar" e "Enviado" para uma entrega no aplicativo em um fluxo de trabalho.
* Correção de um problema que impedia que o rastreamento funcionasse para uma mensagem no aplicativo criada com um HTML personalizado.
* Correção de um problema que impedia que o conteúdo de entrega no aplicativo fosse salvo quando usado em um fluxo de trabalho.
* Correção de um problema que impedia que aplicativos móveis fossem exibidos para administradores.
* Correção de um problema que causava a falha do fluxo de trabalho técnico da Atualização de entregabilidade. (CAMP-26387)
* Correção de um problema que causava discrepância entre os perfis direcionados ao criar uma entrega no aplicativo e os exibidos no painel de entrega. (CAMP-28722)
* Correção de um problema com a integração do serviço principal de campanha e ativos que poderia impedir a seleção de um ativo compartilhado em um email.

## Versão 19.0 - Janeiro de 2019 {#release-19-0---january-2019}

### What's new? {#what-s-new--2}

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
   <td> Disponibilidade Geral do Designer de Email<br /> </td> 
   <td> <p>O novo e-mail Designer intuitivo (anteriormente conhecido como Creative Designer) foi movido para GA. Agora, ele suporta todos os recursos do editor de conteúdo legado, incluindo:</p> 
    <ul> 
     <li> O uso de imagens <a href="../../integrating/using/adding-target-dynamic-content.md">dinâmicas do Adobe Target</a> </li> 
     <li> A capacidade de <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">recuperar o conteúdo de um URL automaticamente no momento da preparação</a> </li> 
     <li> Modelos de conteúdo totalmente compatíveis <a href="../../designing/using/using-reusable-content.md#content-templates">prontos para uso</a>. </li> 
    </ul> 
    <p>Para obter mais informações, consulte a <a href="../../designing/using/overview.md">documentação detalhada</a> e o <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html">vídeo de instruções</a>. Os aprimoramentos e correções estão listados abaixo.</p><p>Como consequência, o editor de conteúdo de e-mail herdado agora está obsoleto. Para obter mais informações, consulte esta <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">página</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Listas de produtos em emails transacionais<br /> </td> 
   <td> <p>Agora você pode fazer referência a uma ou mais coleções de produtos em uma mensagem de email transacional. Por exemplo, você pode enviar automaticamente um email de abandono de carrinho listando todos os produtos que estavam no carrinho do usuário com uma imagem, preço e link para cada produto.</p><p>Para obter mais informações, consulte a <a href="../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message">documentação detalhada</a> e o <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-product-listings-in-transactional-emails-feature-video-setup.html">vídeo de instruções</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Exibição móvel no Designer de email<br /> </td> 
   <td> <p>Agora você pode alternar para uma exibição móvel dedicada ao editar conteúdo de email. Isso permite ajustar o design responsivo de um email editando separadamente todas as opções de estilo para exibição móvel, como ajustar margens, tamanho de fonte menor, cor de fundo diferente e assim por diante.</p><p> Para obter mais informações, consulte a <a href="../../designing/using/styles.md#switching-to-mobile-view">documentação detalhada</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Melhorias beta nas mensagens no aplicativo<br /> </td> 
   <td> <p>O recurso Beta de mensagens no aplicativo foi aprimorado com os seguintes recursos:</p> 
    <ul> 
     <li> O canal Beta no aplicativo é compatível com o GDPR </li> 
     <li> Integração com as APIs do Analytics para preencher os detalhes de Triggers </li> 
     <li> Exibição intuitiva e descrição dos modelos de entrega </li> 
     <li> Melhorias na interface de criação do ponto de vista de usabilidade </li> 
    </ul> <p>Para obter mais informações, consulte a <a href="../../channels/using/about-in-app-messaging.md">documentação detalhada</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Aprimoramentos {#improvements}

* Uma nova opção na atividade Carregar dados agora permite aplicar uma etapa de pós-processamento ao arquivo que contém os registros rejeitados (por exemplo, Compactação no formato Zip). (CAMP-24521)
* Uma nova opção na atividade Atualizar dados agora permite que você configure o tamanho máximo do lote para que os dados sejam carregados. (CAMP-28400)
* Melhoria na seleção do estado do endereço dos perfis. Ao selecionar um país, a lista suspensa "Estado" agora é atualizada automaticamente com valores de estados relevantes. (CAMP-28874)
* Uma nova opção na atividade Extrair arquivo agora impede a geração de um arquivo se a transição de entrada estiver vazia. Isso evita criar e carregar arquivos vazios em servidores SFTP.
* O relatório de resumo de Entrega foi aprimorado.
* A lista de países disponíveis ao definir o endereço de um perfil foi aprimorada. (CAMP-26707)
* Uma mensagem de erro agora é exibida ao tentar importar um fluxo de trabalho incorporado.

### Email Designer {#email-designer}

* Correção de um problema que ativava o recurso de unidade geográfica em um modelo de email ou fragmento de conteúdo criado com o Designer de email, mesmo que esse recurso estivesse desabilitado no Adobe Campaign, o que tornava o modelo ou fragmento indisponível ao tentar acessá-lo novamente. (CAMP-28174)
* Correção de um problema que impedia que condições de conteúdo dinâmico fossem salvas ao editar conteúdo com o Designer de email. (CAMP-27905)
* Correção de um problema que removia a versão HTML do conteúdo de email após editar a versão em texto simples de uma mensagem e quebrar a sincronização em HTML no Designer de email. (CAMP-28507)
* Correção de um problema que impedia a abertura da interface do Email Designer ao usar o Internet Explorer 11. (CAMP-28273)
* Correção de um problema que distorcia a renderização de configurações de estilo do Microsoft Outlook aplicadas a botões com o Designer de email.
* Correção de um problema no Designer de email que tornava editável um URL de um fragmento de conteúdo usado em um email, o que não era esperado, pois o fragmento era bloqueado por padrão.
* Correção de um problema que impedia a exibição do componente divisor do Email Designer no Microsoft Office.
* Correção de um problema que causava o congelamento de páginas em determinados navegadores da Internet ao visualizar um conteúdo sincronizado do AEM usando o editor de conteúdo de email herdado. (CAMP-29068)
* Correção de um erro que ocorria ao clicar em qualquer imagem em um email ao usar o editor de conteúdo de email herdado. (CAMP-30424)
* Correção de um problema que impedia que os fragmentos recém-criados fossem exibidos ao editar um email com o Designer de email. (CAMP-29928)
* Correção de um problema que impedia que o texto do botão fosse exibido corretamente em emails criados com o Designer de email e recebidos usando o cliente do Outlook Web mail.
* Agora é possível criar mensagens transacionais de perfil usando o Designer de email. (CAMP-28900)
* Correção de um erro no Designer de email que tornava o conteúdo editável ao recuperar o conteúdo de um URL automaticamente no momento da preparação, enquanto deveria ser bloqueado.

### Correções {#patches-2}

* Correção de um problema que mostrava registros de entrega incorretos no Relatório dinâmico. (CAMP-23446)
* Correção de um problema que poderia afetar os números no relatório Resumo da rejeição (CAMP-28703)
* Correção de um problema com a integração do serviço principal de campanha e ativos que poderia impedir a exibição de ativos ao selecionar **[!UICONTROL Image shared from Adobe Experience Cloud]** um email (CAMP-28732).
* Correção de um problema que impedia o envio de mensagens SMS contendo o caractere "um" mesmo que a transliteração fosse autorizada na conta externa SMPP. (CAMP-29041)
* Correção de um problema que podia exibir registros duplicados ao usar uma atividade de Segmentação em fluxos de trabalho. (CAMP-28743)
* Correção de um problema que impedia a exclusão de um dos mapeamentos de valor em uma coluna em uma atividade de fluxo de trabalho. (CAMP-28708)
* Correção de um problema na atividade de transferência de Arquivo, ao usar curingas com a opção "Testar para ver se o arquivo existe". (CAMP-28977)
* Correção de um problema na atividade Transferência de arquivos que poderia ocorrer ao atualizar configurações de conta externa. (CAMP-28894)
* Correção de um problema com filtros personalizados no editor de consulta ao usar a condição "Email não está vazio". (CAMP-28741)
* Correção de um problema que ocorria ao exportar tabelas de recursos personalizadas com mais de 100 mil registros. (CAMP-28150)
* Correção de um problema que impedia a exclusão de mensagens transacionais vinculadas a acionadores. (CAMP-28385)
* Senhas removidas que foram exibidas sem segurança em alguns logs SMS.
* Correção de um problema que causava a falha das conexões com o simulador SMPP devido à senha vazia enviada pelo Adobe Campaign.
* Correção de um problema que impedia o envio de campanhas quando as conexões SMS estavam instáveis.
* Correção de um problema que exibia entregas excluídas no relatório Dinâmico.
* Correção de um problema que impedia a recuperação de dados adicionais de registros de entrega, registros de rastreamento e tabelas de exclusão de registros ao usar uma atividade Enriquecimento em um fluxo de trabalho.
* Correção de um problema com solicitações de exclusão do RGPD que poderia ocorrer ao usar um tipo de link "N de coleção de cardinalidade" e a opção "Excluir o registro de destino implica excluir referências de registros pelo link".
* Correção de um problema com o compartilhamento de relatórios.
* Correção de um problema que resultava em problemas de throughput ao enviar uma notificação por push.
* Correção de um problema com campos ausentes de arquivos de saída de mala direta.
* Correção de um problema que permitia aos usuários modificar fluxos de trabalho incorporados.
* Correção de um problema ao criar uma campanha com base em um modelo de campanha, incluindo um fluxo de trabalho com uma atividade de extração configurada. (CAMP-29198)
* Correção de um problema com a atividade de extração de Arquivo que impedia o uso da mesma expressão para vários elementos. (CAMP-29182)
* Correção de um problema, no editor de consulta, com a condição de junção entre o log de fluxo e o log de rastreamento para rtEvent. (CAMP-28780)
* Correção de um problema que impedia que modificações na opção da página inicial "Ação específica" fossem salvas. (CAMP-29422)
* Correção de um problema que impedia a exportação da carga de um evento em um fluxo de trabalho. (CAMP-29029)
* Correção de um problema que impedia que números SMS da lista negra fossem excluídos em uma mensagem SMS. (CAMP-28898)
* Corrigido um problema que impedia que os provedores SMPP fossem notificados em caso de erro ao processar mensagens recebidas. (CAMP-29804)
* Correção de um problema que permitia a exclusão de contas externas com entregas associadas. (CAMP-29738)
* A taxa de transferência de envio foi melhorada e estabilizada para mensagens SMS.
* Correção de um problema que impedia o caractere "~" de ser usado em uma mensagem SMS. (CAMP-29172)
* Correção de um problema em entregas com a opção de otimização de tempo de envio. (CAMP-29231)

