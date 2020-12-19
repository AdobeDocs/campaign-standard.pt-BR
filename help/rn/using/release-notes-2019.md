---
solution: Campaign Standard
product: campaign
title: Notas de versão 2019
description: Essa página lista todas as versões 2019 do Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: tm+mt
source-git-commit: a51943e4da04f5d19aaecdfcf956f5c4f3d804c8
workflow-type: tm+mt
source-wordcount: '7623'
ht-degree: 9%

---


# Notas de versão 2019{#release-notes-2019}

[Planejamento](https://helpx.adobe.com/br/campaign/kb/acs-release-planning.html)  de lançamento| Versões [ de ](https://docs.adobe.com/content/help/pt-BR/control-panel/using/release-notes.html) Painel de controle do Campaign| Atualizações [ de ](../../rn/using/documentation-updates.md) documentação| Notas [ de versão ](../../rn/using/release-notes.md) mais recentes| Recursos  [obsoletos](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=pt-BR#release-notes)

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
   <td> <p>A CCPA é a nova lei de privacidade do estado da Califórnia que harmoniza e moderniza os requisitos de proteção de dados que entram em vigor em 1° de janeiro de 2020. O CCPA se aplica aos clientes do Adobe Campaign que coletam dados de residentes da Califórnia.</p>
   <p>Além dos recursos de privacidade já disponíveis na Adobe Campaign (incluindo gerenciamento de consentimento, configurações de retenção de dados e funções de usuário), estamos aproveitando esta oportunidade para incluir recursos adicionais, para ajudar a facilitar sua preparação para CCPA:</p>
   <ul>
    <li>Direito de acesso e direito de exclusão: estamos nos beneficiando dos recursos que foram adicionadas ao GDPR. <a href="https://helpx.adobe.com/content/help/br/campaign/kb/acs-privacy.html#righttoaccess">Saiba mais</a> </li>
    <li><p>Ao criar uma solicitação de privacidade, o tipo de regulamento (RGPD ou CCPA) foi adicionado ao Privacy Core Service. Esse é método que você deve usar para todas as solicitações de acesso e exclusão. O uso da API e da interface do Campaign para solicitações de acesso e exclusão ficará obsoleto.  Consulte o <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html">artigo Recursos obsoletos e removidos</a>.</p></li>
    <li>Um campo <strong>Recusa CCPA</strong> foi adicionado ao recurso Perfis para permitir que os usuários do Adobe Campaign rastreiem se um consumidor optou pela venda de Informações Pessoais. <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#ccpa">Saiba mais</a>.</li>
  </ul>
    <p>Consulte o <a href="https://docs.adobe.com/content/help/pt-BR/campaign-standard-learn/tutorials/privacy/privacy-overview.translate.html">vídeo de instruções</a>.</p>
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
    <p>A integração entre o Adobe Campaign Standard e o Microsoft Dynamics 365 está disponível. Você poderá transferir seus registros de contato e de entidade personalizada do Dynamics 365 para a Campanha e obter dados de evento de email da Campanha para o Dynamics 365 para melhor alinhamento de vendas/marketing.</p>
    <p>Consulte a <a href="../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md">documentação detalhada</a> para configurar esta integração e visualização o <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/integrating-with-adobe-cloud/campaign-and-microsoft-dynamics-365/working-with-campaign-standard-and-microsoft-dynamics-365.html">vídeo de instruções</a>.</p>
  </td>
  </tr> 
 </tbody> 
</table>

**Aprimoramentos**

* O pop-up de consentimento do relatórios dinâmico foi atualizado para incluir a integração do Adobe Campaign Standard e do Microsoft Dynamics 365. Ao aceitar os termos, os dados do perfil serão incluídos ao usar a integração Adobe Campaign Standard / Microsoft Dynamics 365 e o Relatórios dinâmico. [Leia mais](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)  (CAMP-29766)
* Correção de um problema que exibia datas de contato incorretas ao receber alertas de delivery.
* Quando um evento de mensagen transacional é enviado com um parâmetro de contexto desconhecido, a Campanha agora retorna uma mensagem de erro &quot;400&quot; em vez de &quot;500&quot;. (CAMP-28632)
* Um novo segmento **Excluir prova** foi adicionado no relatórios dinâmico. Esse segmento agora é selecionado por padrão para filtrar seus relatórios. [Leia mais](../../reporting/using/list-of-components-.md#segments)
* A opção **Expiração da mensagem** foi adicionada à notificação por push. Permite que você especifique uma data de expiração na qual a mensagem não será mais enviada pela Apple (APNS) ou Android (FCM). [Leia mais](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* Foram feitas melhorias na atividade **Carregar arquivo**: os logs de fluxo de trabalho foram tornados mais claros e detalhados sobre o erro que ocorre quando um arquivo falha ao carregar. A transição de saída gerada ao ativar a opção **Manter os rejeitos em um arquivo** foi renomeada como **Rejeições**. [Leia mais](../../automating/using/load-file.md)
* Registros relacionados multilíngues foram adicionados aos logs de envio para entender melhor as falhas de envio devido aos idiomas ausentes nos arquivos CSV carregados.

**Aprimoramentos de segurança**

* Correção de um problema ao excluir informações de perfis quantificados por meio de uma solicitação de privacidade, que removia todos os dados, exceto o endereço de email na lista da quarentena.
* A segurança foi aprimorada para proteção contra injeções em cabeçalhos de email.
* A segurança foi aprimorada para proteção contra ataques SSRF nos quais expressões xtk podem ser usadas (HTML de email, conteúdo e assunto de texto, SMS e conteúdo de notificação por push).

**Aprimoramentos do Email Designer**

* Correção de um problema que impedia que links de unsubscription, subscrição e landing page fossem rastreados quando inseridos em um email. (CAMP-37809)
* Correção de um problema que resultava em erros ao criar um novo email e selecionar um modelo. (CAMP-38000)
* Ao editar um link usando o Designer de email, agora você pode usar a opção **Link sublinhado**. Além disso, uma propriedade **Público alvo** foi adicionada com o valor padrão definido como **None**. [Leia mais](../../designing/using/styles.md#about-styling-links)
* Correção de um problema de cor em links em componentes de texto no corpo de um email. (CAMP-37330)
* Correção de um problema que impedia a remoção de links associados ao excluir uma imagem. (CAMP-37234)
* Correção de um problema que impedia salvar modificações nas configurações **Order** do conteúdo dinâmico em uma condição. (CAMP-36883)
* Correção de um problema ao pesquisar landings page. A pesquisa foi estendida dos 50 primeiros criados para todos os bancos de dados. (CAMP-36839)
* Correção de um problema ao salvar modificações no remetente de email em **De: campo Name**. (CAMP-36606)
* O aviso de compatibilidade do componente de carrossel foi modificado para refletir os clientes de email suportados.
* Correção de um problema de exibição em dispositivos móveis. O atributo height agora está sempre definido como &quot;height: auto&quot; ao adicionar ou carregar uma nova imagem em um email. (CAMP-35497)
* Correção de um problema que deixava estilo e tags meta no HTML ao excluir um fragmento de um componente de estrutura. (CAMP-35390)
* Correção de um problema com fragmentos ao atualizar conteúdo reutilizável. (CAMP-35186)
* Correção de um problema ao exibir somente conteúdo condicional móvel em emails. (CAMP-35155)
* Correção de um problema que exibia aleatoriamente espaços sem quebra de largura zero. (CAMP-35116)
* Correção de um problema com a posição dos botões na caixa de diálogo **Salvar como fragmento**.
* Correção de um problema de pré-visualização ao adicionar uma tag HTML em um título de imagem e texto alternativo.
* Correção de um problema ao editar, no designer de email, links criados em emails do editor herdado.
* Correção de um problema que deixava marcas de estilo duplicadas no conteúdo.
* Correção de um problema com o formato de data ao inserir um campo de personalização em um email.
* Correção de um problema de salvamento ao alternar do modo HTML para texto sem formatação.
* Correção de um problema ao clicar na opção Bloquear e desbloquear que adicionava valores de margem no painel de propriedades de estilo incorporado.
* Correção de um problema com o tamanho da pré-visualização móvel para melhor renderização.
* Correção de um problema com o tamanho dos botões em modelos e fragmentos.
* Correção de um problema com o tamanho das imagens quando inseridas em um componente de botão.

**Outras alterações**

* O intervalo de tempo padrão para o qual os dados são exibidos nas páginas KPI do delivery e na página Relatórios dinâmico foi alinhado para evitar discrepâncias nos resultados do relatórios. (CAMP-35148)
* Uma mensagem de erro foi adicionada nos registros quando o certificado do aplicativo expira.
* A pré-visualização de cálculo de carga agora inclui o tamanho do campo personalizado para evitar falhas de notificação por push. (CAMP-35303)
* O nome do arquivo **Rejeita** na atividade **Carregar arquivo** agora pode ser personalizado da mesma forma que na atividade **Exportação de arquivo**.
* Todas as entidades personalizadas que não estão vinculadas a nenhuma entidade predefinida agora podem ser acessadas por meio da API.
* Desempenho de banco de dados aprimorado em grandes recursos.
* As descrições de alguns erros que ocorrem ao enviar mensagens SMS foram clarificadas. (CAMP-36558)
* Uma mensagem de erro agora é exibida ao executar uma atividade **Scheduler** do fluxo de trabalho que está conectada a si mesma, diretamente ou por meio de várias atividades, pois isso pode levar a que o servidor de fluxo de trabalho da instância fique travado.
* Foram feitas melhorias para ajudar a solucionar problemas de mensagens transacionais: o link &quot;Dados&quot; foi renomeado como &quot;Últimos eventos transacionais&quot; na tela de configuração do evento, agora ele lista os eventos recebidos classificados em ordem decrescente. Além disso, um novo status de evento transacional foi criado: &quot;targetingFailed&quot;. Quando o módulo de mensagens transacionais falha ao enriquecer um link que é usado para direcionamento de mensagem, o evento transacional agora estará nesse novo estado (em vez do status &quot;roteamentoFailed&quot;).
* Foram introduzidas melhorias na interface ao restringir o acesso da landing page a unidades geográficas ou organizacionais específicas. O objetivo é avisar que a landing page pode estar sujeita a condições de visibilidade: a seleção de uma unidade geográfica e organizacional ao criar uma landing page agora é obrigatória. Um banner com informações relacionadas agora é exibido assim que uma unidade é selecionada. A mensagem de erro que é exibida ao testar a landing page ficou mais clara.
* Nas APIs do Campaign Standard, as chaves personalizadas não podem ser modificadas usando uma operação PATCH se o valor da chave for diferente da chave de origem, ou se você estiver usando sua própria chave de negócio como URI em vez da fornecida pelo Adobe.
* O idioma &quot;albanês - Macedônia&quot; foi adicionado à lista suspensa de idioma preferencial. (CAMP-35396)

**Correções**

* Correção de um problema que impedia relatórios agendados de serem classificados ou pesquisados.
* Correção de um problema com regras de Acionadores que fazia com que as regras E e OU fossem misturadas.
* Correção de um problema que exibia a propriedade Mobile como Excluído no Launch. (CAMP-35382)
* Correção de um problema que impedia a sincronização das propriedades do Adobe Launch para dispositivos móveis no Adobe Campaign. (CAMP-35411, CAMP-35089, CAMP-35014, CAMP-35487)
* Correção de um problema em que as mensagens de push transacionais falhavam quando os eventos eram enriquecidos com dados de perfil. (CAMP-34385)
* Correção de um problema em que as propriedades móveis não eram sincronizadas em vários ambientes. (CAMP-37060)
* Correção de um problema ao selecionar, em uma notificação por push, um modelo usando uma fórmula de data de contato. (CAMP-35300)
* Correção de um problema que resultava em falha do serviço de envio de mensagens. (CAMP-35287)
* Correção de um problema com emails diretos recorrentes, todos definidos com a data do primeiro evento. (CAMP-35139)
* Correção de um problema com recursos personalizados **Perfis** recentemente estendidos que não estavam disponíveis para query. (CAMP-35119)
* Correção do modo **Reparar estrutura do banco de dados** para instâncias com a configuração Compartilhamento ativada. (CAMP-35118)
* Correção de um problema que resultava em um erro de log SQL ao adicionar dados de agregação em logs. (CAMP-35034)
* Correção de um problema com o transição ao criar uma atividade **Segmentação**. (CAMP-35033)
* Correção de um problema na atividade **Query** que impedia que a função **encrysescbcDecrypt** descriptografasse a função **encryad_aescbcEncrypt**. (CAMP-34952)
* Correção de um problema que impedia que **Logs de rastreamento** fossem exibidos em delivery. (CAMP-34855)
* Correção de um problema ao usar uma fórmula de data personalizada **Enviar otimização de tempo**, que poderia impedir o envio de notificações por push devido a erros nos dados adicionais do fluxo de trabalho. (CAMP-30336)
* Correção de um problema que impedia a publicação de recursos personalizados. (CAMP-37425)
* Correção de um problema que impedia que usuários administradores modificassem pacotes de importação.  (CAMP-37176)
* Correção de um problema em workflows que impedia o envio de provas, se a atividade do delivery estivesse conectada a uma atividade vazia **Ler audiência**. (CAMP-37164)
* Correção de um problema que impedia a importação de recursos personalizados para um novo ambiente. (CAMP-36506)
* Correção de um problema em relatórios de cliques ativos que resultava em porcentagens ocultas por imagens (CAMP-36407)
* Correção de um problema que ocorria ao tentar exportar um campo de descrição do delivery. (CAMP-35467)
* Correção de um problema que podia deixar o estado de um delivery como &quot;Start pendente&quot;, embora o delivery tivesse sido concluído. (CAMP-35355)
* Correção de um problema que impedia a exibição de logs de fluxo de trabalho após a ativação e, em seguida, a desativação de logs SQL.

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
   <td> <p>Para personalização mais profunda, a Atividade de API externa permite que você coloque dados de sistemas externos em um fluxo de trabalho por meio de uma chamada REST API. Os pontos finais REST podem ser um sistema de gerenciamento de clientes, um terminal REST da Adobe I/O Runtime ou da Adobe Experience Cloud (por exemplo, Plataforma de dados, Público alvo, Analytics, Campanha).</p><p>Esse recurso está atualmente em beta público.</p><p>Para saber mais, consulte a <a href="../../automating/using/external-api.md">documentação detalhada</a> e o <a href="https://docs.adobe.com/content/help/pt-BR/campaign-standard-learn/tutorials/managing-processes-and-data/data-management-activities/external-api-activity.translate.html">vídeo de instruções</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Relatório sobre o segmento do fluxo de trabalho<br /> </td> 
   <td> <p>Esse recurso permite que os comerciantes detalhem o desempenho do delivery por código de segmento. Quando você cria um fluxo de trabalho e usa uma atividade de segmentação para atribuir segmentos à população do delivery, esses segmentos agora podem entrar no mesmo delivery. Isso permite exibir as estatísticas de abertura/cliques com base em vários segmentos em um único delivery.</p><p>Para saber mais, consulte a <a href="../../reporting/using/creating-a-report-workflow-segment.md">documentação detalhada</a> e o <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">vídeo de instruções</a>.</p></td>
  </tr> 
 </tbody> 
</table>

**Aprimoramentos de segurança**

* Correção de um problema de segurança para impedir ataques de negação de serviço (DoS) em solicitações inválidas para obter imagens. (CAMP-33454)

**Aprimoramentos do Email Designer**

* Correção de um problema que adicionava tags de estilo HTML adicionais a um modelo HTML sempre que um componente era adicionado, o que poderia aumentar drasticamente o tamanho do modelo. (CAMP-34694)
* Correção de um problema que impedia que algumas opções de menu da barra de ferramentas superior direita ficassem disponíveis. (CAMP-34577)
* Correção de um problema que ocorria quando o bloco de conteúdo do URL do Mirror page era inserido em um conteúdo de email. (CAMP-34779)
* Correção de um problema que ocorria ao usar o código JSPP em um email, dificultando a edição do conteúdo. (CAMP-34574)
* Correção de um problema que resultava em imagens truncadas na parte superior quando um hiperlink era adicionado a elas. (CAMP-34382)
* Correção de um problema de exibição ao usar o Designer de email com o Firefox. (CAMP-34364)
* Correção de vários problemas que ocorriam no modo Avançado ao definir o conteúdo dinâmico em um email. (CAMP-34351, CAMP-34333, CAMP-34331)
* Correção de vários problemas que ocorriam com o editor de regras de conteúdo dinâmico (CAMP-34304, CAMP-34303).
* Correção de um problema que impedia a exibição do campo Link no painel Configurações do Designer de email (CAMP-33749).
* Correção de um problema com o ícone do YouTube que era superdimensionado em emails enviados. (CAMP-33726)
* Correção de um problema de segurança que tornava o conteúdo do mirror page editável. (CAMP-33691)
* Correção de um problema que quebrou a saída HTML ao usar o símbolo maior que no conteúdo dinâmico. (CAMP-33688)
* Correção de um problema que ocorria ao usar a opção Desfazer ao editar texto no Designer de email. (CAMP-32565)
* Correção de um problema que criava tags extras ao desfazer estilos em vez de removê-los. (CAMP-32359)
* Agora você pode definir se cada componente usado em um email será exibido somente em dispositivos desktop ou somente em dispositivos móveis.
* Agora é possível definir a largura e a altura de um componente de conteúdo do Social.
* Correção de um problema que impedia que o código de origem antigo do conteúdo dinâmico fosse removido após a exclusão desse conteúdo dinâmico.
* Correção de um problema que impedia que o assunto de um email fosse atualizado após sua modificação.
* Correção de um problema que impedia que uma estrutura de coluna n:n fosse selecionada uma vez solta no espaço de trabalho.
* Correção de um problema que fazia com que a miniatura da mensagem fosse exibida desfocada no painel de email.
* Correção de um problema que impedia que o plano de fundo fosse exibido corretamente em emails recebidos no Outlook.
* Correção de alguns problemas de classificação no home page do Designer de email.
* Correção de um problema que ocorria ao duplicar variantes ao usar conteúdo dinâmico.
* Alguns campos indesejados foram removidos do painel Configurações do Designer de email.

**Outras melhorias**

* Por meio da integração com o Adobe Experience Platform Location Services, a Adobe Campaign agora é compatível para enviar mensagens de marketing baseadas em localização aos assinantes do aplicativo móvel por meio do Experience Platform SDK. Para obter mais informações, consulte a [documentação detalhada](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md).
* O recurso de relatórios foi aprimorado para proporcionar uma experiência melhor. Para usar esse recurso, é necessário aceitar o Contrato de uso dinâmico de Relatórios. Para obter mais informações, consulte a [documentação detalhada](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* Em workflows, uma nova opção foi adicionada à pré-visualização das próximas dez execuções de um fluxo de trabalho. Para obter mais informações, consulte a [documentação detalhada](../../automating/using/scheduler.md).
* Na atividade do Scheduler, uma nova opção permite selecionar um dia específico de uma semana específica para delivery mensais. Para obter mais informações, consulte a [documentação detalhada](../../automating/using/scheduler.md).
* Ao criar delivery recorrentes sem período de agregação, o painel do delivery agora permite que você solicite a confirmação antes do envio do delivery. Para obter mais informações, consulte a [documentação detalhada](../../sending/using/confirming-the-send.md).
* Agora você pode personalizar o rótulo de um delivery com variáveis de evento que foram declaradas na atividade de sinal externo do fluxo de trabalho. Para obter mais informações, consulte a [documentação detalhada](../../automating/using/calling-a-workflow-with-external-parameters.md).
* O query de exclusão do RGPD foi aprimorado para melhorar o desempenho. (CAMP-33504)
* A opção &quot;ftp&quot; foi removida da interface de configuração da conta externa. (CAMP-34472)
* Agora você pode ativar e desativar a opção de modo de teste SMTP para cada mensagem de email. Para obter mais informações, consulte a [documentação detalhada](../../administration/using/configuring-email-channel.md#smtp-test-mode). (CAMP-34602)

**Outras alterações**

* Um aviso foi adicionado na interface de propriedades do delivery. Ela especifica que os delivery são preparados com base em seu período de agregação e não chamam o fluxo de trabalho várias vezes por dia. Verifique se eles não têm nenhum período. (CAMP-34393)
* Um aviso foi adicionado nas telas de configuração de recursos personalizados. Recomendamos o uso de no máximo 30 caracteres para IDs de recursos personalizados. Isso também se aplica a campos de recursos personalizados, chaves, índices e links.
* Agora, uma mensagem é exibida ao tentar excluir um mensagen transacional que é usado por uma landing page como uma mensagem de confirmação.
* Um aviso agora aparece nos registros de workflows quando uma atividade está em execução há mais de 6 horas. Isso não se aplica às atividades de notificação por push, Delivery, Sinal, Start, Fim, Fork, AND-joint, Agendamento e Espera.
* Um aviso agora aparece nos registros de workflows quando você atinge o número máximo de workflows que estão sendo executados simultaneamente.
* Workflows que estão em estado de pausa ou de falha há mais de 7 dias agora são parados para consumir menos espaço em disco. A tarefa de limpeza é exibida nos logs do fluxo de trabalho.
* Ao usar uma atividade &quot;Transferir arquivo&quot;, um erro será registrado se o tamanho do arquivo exceder o espaço em disco disponível.
* A ação Redirecionar para URL de destino não pode mais ser selecionada para o botão secundário nas mensagens no aplicativo.

**Correções**

* Correção de um problema que resultava em falha de solicitações de acesso ao RGPD.
* Correção de um problema que resultava no descarte de acionadores quando vários acionadores eram recebidos por um perfil único.
* Correção de um problema que resultava em uma mensagem de erro de publicação de recursos personalizados incorreta após o logon.
* Correção de um problema que exibia uma página em branco ao criar ou estender um recurso personalizado.
* Correção de um problema que impedia que uma audiência com appSubscriptionrcp como targeting dimension ficasse disponível para definição de metas em um delivery móvel.
* Correção de um erro que impedia que endereços de email de rejeição em disco fossem colocados na quarentena. (CAMP-24587)
* Correção de um problema que ocorria ao adicionar uma regra de tipologia e, em seguida, excluí-la antes de salvar a tipologia. (CAMP-32789)
* Correção de um problema que impedia a exibição do conteúdo da landing page ao desativar o conteúdo dinâmico. (CAMP-32924)
* Correção de um problema com delivery recorrentes que ocorria ao usar a personalização em atributos de delivery primário. (CAMP-32983)
* Correção de um problema em workflows que impedia a leitura de resultados de uma transição que continha dados de mensagens SMS recebidas. (CAMP-33134)
* Correção de um problema em workflows que ocorria ao combinar atividades de bifurcação e exclusão para criar audiências. (CAMP-33401)
* Correção de um problema que impedia a exibição do conteúdo do mirror page e o envio de mensagens de prova para delivery recorrentes. (CAMP-33413)
* Correção de um problema que resultava em erro ao usar uma atividade de União entre perfis e audiências. Esse problema foi causado por uma incompatibilidade das chaves de identificação nas transições de entrada. (CAMP-33713)
* Corrigido um problema nas atividades de teste que impedia que a expressão &quot;recCount&quot; usasse a sintaxe correta ao clicar no duplo. (CAMP-33756)
* Correção de um problema que resultava em uma mensagem de erro ao abrir os logs técnicos do fluxo de trabalho de cobrança. (CAMP-34313)
* Correção de um problema no landing page que poderia ocorrer ao configurar campos de caixa de seleção com o subscrição. (CAMP-34369)
* Correção de um problema que ocorria ao configurar uma lista e adicionar o campo &quot;ícone&quot; a ela. (CAMP-34585)
* Correção de um problema que impedia o uso dos símbolos &quot;|&quot; e &quot;%&quot; como separadores de data ou hora em atividades de fluxo de trabalho de arquivo de carregamento. (CAMP-34706)
* Correção de um problema que ocorria ao usar condições de visibilidade com caixas de seleção no landing page. (CAMP-34802)
* Correção de um problema na atividade do Enriquecimento que impedia que os campos fossem exibidos na guia &quot;Dados adicionais&quot;, se a dimensão do filtro fosse definida como logs de rastreamento e a dimensão do público alvo como perfil.
* Correção de um problema que resultava em uma mensagem de erro ao exportar um recurso &quot;workflowTemplate&quot;.
* Correção de um problema ao criar um novo perfil, que impedia que o campo &quot;Código do país/região&quot; fosse salvo se fosse selecionado na caixa de diálogo.
* Correção de vários problemas que ocorriam ao usar o template de importação de Mala direta (updateQuarantinesDeliveryLogsDirectMail).
* Correção de um problema relacionado à integração dos Ativos sob demanda.
* Correção de um problema que ocorria ao aumentar o zoom na visualização da Linha do tempo. (CAMP-33628)
* Correção de um problema que impedia o envio instantâneo de provas para mensagens de email com data e hora agendadas. (CAMP-33723)
* Correção de um problema relacionado a mensagens transacionais que geravam registros de erros quando um usuário logout. (CAMP-31698)
* Corrigido um erro que ocorria em ambientes específicos ao agendar uma mensagem de email.
* Correção de um problema que causava a falha do fluxo de trabalho de execução do delivery Update.
* Correção de um problema de segurança que quebrava o conteúdo do email quando o assunto continha várias linhas.


## Versão 19.2.7 - Julho de 2019 {#release-19-2-7---july-2019}

**Aprimoramentos**

* O query de exclusão do RGPD foi aprimorado para melhorar o desempenho.
* Corrigido um problema que causava falhas na Web após a atualização 19.2. (CAMP-34862)
* Correção de um problema que impedia que usuários que não fossem administradores salvassem ou agendassem relatórios. (CAMP-31133)
* Correção de um problema ao usar &quot;|&quot; como separador de datas na atividade de fluxo de trabalho Carregar arquivo. (CAMP-34706)

## Versão 19.2.4 - Junho de 2019 {#release-19-2-4---june-2019}

**Email Designer**

* Correção de um problema que impedia os usuários de editar fragmentos quando tags de estilo vazias eram usadas no HTML. Esta é uma correção de acompanhamento para CAMP-33778 em 19.2.3.

## Versão 19.2.3 - Junho de 2019 {#release-19-2-3---june-2019}

**Designer de email**

Introduziu uma série de melhorias e correções para otimizar fragmentos na versão 19.2. Os fragmentos recém-criados funcionarão perfeitamente. Os fragmentos criados anteriormente ficaram esmaecidos e precisam ser migrados para o novo formato. Para fazer isso, clique em cada fragmento e valide sua migração para o novo formato. Recomendamos que você teste alguns fragmentos antes de migrar todos eles.

* Correção de um problema que impedia os usuários de editar um fragmento após desbloqueá-lo. Isso afetava os fragmentos existentes ao atualizar para a versão 19.2. (CAMP-33778)
* Correção de um problema ao usar conteúdo dinâmico. Espaços adicionais foram adicionados no HTML.

**Outras melhorias**

* Correção de um problema que impedia que o envio de SMS retomasse após uma desconexão do conector SMS.
* Correção de um problema que poderia fechar conexões SMPP quando TLS era ativado.
* Correção de um problema que poderia fechar conexões SMPP quando TLS era ativado.
* A opção &quot;Launch_URL_Campanha&quot; foi adicionada na Campanha para gerenciar propriedades de aplicativos móveis criados com o Adobe Experience Platform Mobile SDK.
* Corrigido um erro que fazia com que a opção ambiente Sandbox ficasse desmarcada depois de fazer upload do certificado de uma propriedade móvel recém-criada e sair da página de propriedades do aplicativo móvel.
* Correção de um problema que impedia o enriquecimento de um conteúdo de mensagen transacional com informações do recurso Serviço. (CAMP-33707)
* Correção de um problema nas landings page de lista de bloqueios que ocorria ao tentar cancelar a inscrição de perfis de um serviço.

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
   <td> <p>Para ajudar a aumentar a eficiência do seu trabalho como usuário administrador, você pode monitorar facilmente a capacidade e gerenciar as configurações de suas instâncias (começando pelo gerenciamento de servidores SFTP).</p><p>Para saber mais, consulte a <a href="https://docs.adobe.com/content/help/pt-BR/control-panel/using/control-panel-home.translate.html">documentação detalhada</a> e o <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/control-panel-overview.html?lang=en">vídeo de instruções</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Notificações locais<br /> </td> 
   <td> <p>As mensagens de notificação locais permitem que você informe seus usuários quando novos dados estiverem disponíveis em seus aplicativos móveis, mesmo sem ter acesso à Internet ou ao aplicativo móvel em execução em primeiro plano. As notificações locais são acionadas por um aplicativo móvel em um horário específico e dependendo de um evento.</p><p>Para obter mais informações, consulte a <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">documentação detalhada</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Aprimoramento do fluxo de trabalho - Adicione uma carga à atividade de sinal externo<br /> </td> 
   <td> <p>Start um fluxo de trabalho com uma carga quando as condições definidas forem atendidas com êxito a partir de outro fluxo de trabalho ou de uma chamada REST API para integração com seus sistemas externos. Isso também inclui uma nova atividade <strong>test</strong> na qual você pode executar testes nesta funcionalidade.</p><p>Para saber mais, consulte a <a href="../../automating/using/calling-a-workflow-with-external-parameters.md">documentação detalhada</a> e o <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/execution-activities/external-signal-activity.html">vídeo de instruções</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Aprimoramento do Landing page - Google reCAPTCHA<br /> </td> 
   <td> <p>Aproveite o Google reCAPTCHA para evitar spam em suas landings page sem exigir qualquer ação de seus clientes.</p><p>Para obter mais informações, consulte a <a href="../../channels/using/configuring-landing-page.md#setting-google-recaptcha">documentação detalhada</a>.</p></td> 
  </tr> 
 </tbody> 
</table>

**Aprimoramentos de segurança**

* Corrigido um problema de segurança de cliques em potencial na área de trabalho do relatórios.

**Aprimoramentos do Email Designer**

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
* Correção de um problema que impedia que fragmentos criados durante a edição de conteúdo de email fossem exibidos na paleta esquerda do Email Designer ao atualizar a lista do fragmento.
* Correção de vários problemas que ocorriam ao usar conteúdo dinâmico em um email.
* Correção de um problema que ocorria com o seletor de cores ao tentar definir uma cor usando valores RGB.
* Correção de um problema que impedia o mirror page de responder ao receber o email em um dispositivo móvel.

**Aprimoramentos de mensagens transacionais**

Várias melhorias foram adicionadas ao canal de mensagens transacionais para otimizar a operação e o desempenho.

* A duração do mensagen transacional foi estendida para garantir que todas as mensagens sejam enviadas antes de expirarem, especialmente quando o tentativas for executado.
* O desempenho de mensagens transacionais foi aumentado pela distribuição da carga em diferentes threads de envio.
* O processo de mensagens transacionais foi otimizado para ser capaz de start em paralelo com várias análises da mesma mensagem.
* Correção de um problema que resultava em throughput e latência inconsistentes para notificações por push transacionais.
* Correção de um problema que exibia uma audiência de público alvo incorreta para delivery de execução de mensagens transacionais.
* Correção de um problema que ocorria ao importar um pacote com uma configuração de evento e o mensagen transacional associado. Para obter mais informações, consulte a [documentação detalhada](../../channels/using/getting-started-with-transactional-msg.md#exporting-and-importing-transactional-messages).
* Correção de um problema que excluía os dados de coleta dos perfis de teste criados para um mensagen transacional que continha listagens de produtos.

**Outras alterações**

* Uma nova opção foi adicionada à conta externa SMS. Ela permite limitar o número máximo de processos MTA que enviam SMS para melhor controlar o número de conexões paralelas. Para obter mais informações, consulte a nota técnica [protocolo e configurações do conector SMS](https://helpx.adobe.com/br/campaign/kb/sms-connector-protocol-and-settings.html).
* Ao publicar um recurso com extensão de API, se a API já tiver sido publicada, ela será atualizada automaticamente toda vez que for publicada novamente. Anteriormente, essa ação era manual e a falha ao atualizar a API poderia quebrar o perfil ou o recurso de serviço dessa API. Para obter mais informações, consulte a [documentação detalhada](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* A dimensão do CEP foi removida do Relatórios dinâmico. Em vez disso, recomendamos usar as dimensões Cidade, País, Estado.
* O acionador do evento de ciclo de vida &quot;Primeira inicialização&quot; para mensagens no aplicativo foi removido.
* Ao exportar um pacote com grupos de segurança, ele agora contém as funções atribuídas a cada grupo. (CAMP-32960)
* Na atividade Carregar arquivo, uma nova opção permite verificar se as colunas do arquivo que você está carregando correspondem à definição da coluna. Para obter mais informações, consulte a [documentação detalhada](../../automating/using/load-file.md). (CAMP-32229)
* Os workflows agora podem ser iniciados com uma carga, permitindo que você use e compartilhe parâmetros externos entre atividades dentro do fluxo de trabalho. Para obter mais informações, consulte a [documentação detalhada](../../automating/using/calling-a-workflow-with-external-parameters.md). (CAMP-29412 e CAMP-29413)
* As APIs de Campaign Standard agora permitem atualizar as unidades geográficas e organizacionais dos perfis usando uma carga. Para obter mais informações, consulte a [documentação detalhada](../../api/using/get-started-apis.md).
* As mensagens de erro quando um objeto do banco de dados não está acessível foram tornadas mais claras para entender.
* Na atividade Extract file, os recursos do Javascript foram atualizados ao definir o nome de um arquivo a ser exportado. Somente a função formatDate está disponível para uso no campo Saída. Para obter mais informações, consulte a [documentação detalhada](../../automating/using/extract-file.md).
* A geração de ID de sequência automática foi aprimorada para recursos personalizados. As chaves primárias para novos recursos personalizados agora estão em 64 bits por padrão.
* O modo de teste de publicação de recursos personalizados foi aprimorado. Agora, uma mensagem de aviso é exibida aos usuários se a última publicação de recursos personalizados falhar e não for corrigida. Após uma falha de publicação de recursos personalizados, é possível reverter para a última versão em funcionamento. Para obter mais informações, consulte a [documentação detalhada](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
* Uma nova opção foi adicionada na atividade Transferir arquivo. Permite que você classifique os arquivos ao usar a ação de download de Arquivo, no modo SFTP. Para obter mais informações, consulte a [documentação detalhada](../../automating/using/transfer-file.md). (CAMP-33109)

**Correções**

* Correção de um problema que resultava em vazamento de memória para o MTA quando as configurações de SMS eram recarregadas.
* Correção de um problema que impedia a publicação de atualizações do banco de dados no modo de reparo.
* Correção de um problema que causava discrepância entre o Adobe Analytics Reports e o Adobe Campaign Dynamic Relatórios. (CAMP-25393)
* Correção de um erro que causava a falha do fluxo de trabalho de compartilhamento de relatórios.
* Correção de um erro que impedia os usuários de enviarem mensagens no aplicativo com apenas o URL da mídia.
* Correção de um problema que exibia um aplicativo móvel mesmo se seu certificado não tivesse sido carregado para a instância.
* Correção de um erro que impedia que os campos de personalização funcionassem ao usar o Público alvo **para todos os usuários de um modelo de aplicativo móvel**.
* Novas instâncias do Campaign Standard foram provisionadas. (CAMP-32635 e CAMP-32344)
* Correção de um erro que impedia a personalização da fórmula de data em um fluxo de trabalho. (CAMP-30336)
* Correção de um problema ao definir uma fórmula de data personalizada que poderia impedir que os campos &quot;Dados adicionais&quot; e &quot;Código de segmento&quot; ficassem disponíveis na lista suspensa. (CAMP-32383)
* Correção de um problema que impedia que as atividades &quot;Transferir arquivo&quot; e &quot;Extrair arquivo&quot; localizassem os arquivos rejeitados se eles fossem criptografados. (CAMP-32377)
* Correção de um problema nas APIs que podia impedir que o filtro lineCount renderizasse a contagem total exata. (CAMP-31424)
* Correção de um problema no landing page que impedia que os campos de entrada exibissem o valor atualizado depois de modificado. (CAMP-31401)
* Corrigido um problema que fazia com que uma atividade de sinal fosse ativada inesperadamente.
* Correção de um problema que impedia a exibição da pré-visualização de email quando a audiência estava vazia.
* Correção de um problema na atividade &quot;Extrair arquivo&quot; que gerava um arquivo enquanto a opção &quot;Não gerar um arquivo se a transição de entrada estiver vazia&quot; estava ativada.
* Correção de um problema que resultava na desativação do fluxo de trabalho de Disponibilidade se ele não fosse concluído com êxito.
* Correção de um problema que impedia que os usuários salvassem ou agendassem relatórios. (CAMP-31133)

## Versão 19.1.3 - março de 2019 {#release-19-1-3---march-2019}

**Aprimoramentos do Email Designer**

* Correção de um problema que impedia a modificação de um modelo após salvá-lo.
* Correção de vários problemas ao usar um modelo criado anteriormente em um email.
* Correção de um problema que impedia que os componentes ficassem ocultos em modelos importados.

**Outras melhorias**

* Correção de um erro ao exibir o regra de tipologia. (CAMP-32059 e CAMP-31849)
* Correção de um problema que impedia a edição de regras de tipologia. (CAMP-31750)
* Correção de um problema com o processo do InMail que podia ser interrompido inesperadamente. (CAMP-31238)

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
   <td> Melhorias no Relatórios do canal de push<br /> </td> 
   <td> <p>Vários aprimoramentos foram adicionados ao relatórios de canal de push para permitir que você avalie o envolvimento do usuário de forma mais intuitiva. Com esta versão, estamos expandindo a lista de métricas de canal de push para três métricas diferentes: Impressões, cliques, aberturas (abertura do aplicativo) para ajudar a medir e analisar a interação dos usuários com as notificações por push com mais eficiência. Juntamente com isso, também estamos padronizando a definição e implementação dessas métricas. O relatório incorporado de notificação por push também foi aprimorado com visualizações e métricas comumente usadas.</p><p> Para obter mais informações, consulte a <a href="../../reporting/using/push-notification-report.md">documentação detalhada</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Iniciar integração para o aplicativo móvel<br /> </td> 
   <td> <p>Esta versão contém a integração do Adobe Campaign com as versões GA das extensões Android e iOS para Adobe Campaign Standard nos SDKs Adobe Experience Platform Launch e Mobile. Essas extensões suportam mensagens de push, mensagens no aplicativo e atualizações de perfis de aplicativos móveis.</p><p> Para obter mais informações, consulte a <a href="https://helpx.adobe.com/br/campaign/kb/configuring-app-sdk.html">documentação detalhada</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mensagens no aplicativo móvel<br /> </td> 
   <td> <p>Esta versão contém a versão GA do canal no aplicativo no Campaign. De um ponto de vista funcional, as adições mais notáveis à versão Beta são Relatórios dinâmicos para o canal no aplicativo e handshake seguro entre o SDK móvel e o Mias (Marketing Cloud In-App Messaging Service que serve as regras no aplicativo para o SDK). O handshake seguro garante que os dados de PII de seus usuários não caiam em mãos mal-intencionadas, assim como permite manter a privacidade dos usuários em um dispositivo compartilhado, limpando o cache de mensagens sempre que o usuário fizer logoff.</p><p>Para obter mais informações, consulte a <a href="../../channels/using/about-in-app-messaging.md">documentação detalhada</a> e o <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/in-app/in-app-message-overview.html">tutorial no aplicativo</a> dedicado.</p> </td> 
  </tr> 
  <tr> 
   <td> Melhorias no fluxo de trabalho<br /> </td> 
   <td> <p>Os seguintes recursos de fluxo de trabalho foram adicionados:</p> 
    <ul> 
     <li> Agora é possível copiar e colar atividades em um fluxo de trabalho ou em outro fluxo de trabalho da mesma instância de Campanha. Dessa forma, você pode duplicado facilmente um fluxo de trabalho inteiro ou atividades específicas e manter as configurações definidas inicialmente. Para obter mais informações, consulte a <a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">documentação detalhada</a>. (CAMP-20014) </li> 
     <li> Ao usar a atividade <strong>Carregar arquivo</strong>, agora é possível adicionar um carimbo de data e hora ao nome do arquivo que contém os registros rejeitados. Para obter mais informações, consulte a <a href="../../automating/using/load-file.md#configuration">documentação detalhada</a>. </li> 
     <li> <strong>As atividades </strong> de consulta e  <strong></strong> segmentação agora permitem ativar uma transição de saída se o atividade não recuperar dados. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Aprimoramentos de segurança**

* O código HTML de landing page gerado foi atualizado para impedir a indexação do mecanismo de pesquisa.

**Aprimoramentos do Email Designer**

* Um conjunto dos quatro melhores modelos de e-mail responsivos da classe criados por artistas da Behance está disponível.

   Para obter mais informações, consulte a [documentação detalhada](../../designing/using/using-reusable-content.md#content-templates).

* Nossa nova experiência de integração o ajudará a criar e-mails de start mais rapidamente e a facilitar o acesso à documentação e aos tutoriais.

   Para obter mais informações, consulte a [documentação detalhada](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page).

* Agora você tem a flexibilidade de configurar o número de colunas e a largura com base em suas necessidades.

   Para obter mais informações, consulte a [documentação detalhada](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

* Ao editar na visualização móvel, você pode ocultar determinados componentes apenas na exibição móvel para obter um uso eficaz do espaço.

   Para obter mais informações, consulte a [documentação detalhada](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

* Agora você pode adicionar canais sociais personalizados ao seu modelo de e-mail sobre os que já estão disponíveis.
* Correção de um problema que impedia a rolagem para baixo no menu de estrutura ao usar mais de 18 estruturas. (CAMP-31173)
* Correção de um problema que exibia o precabeçalho na parte superior do conteúdo ao encaminhar um email contendo um precabeçalho enviado com o Adobe Campaign. (CAMP-30736)
* Correção de um problema que impedia que a linha de assunto fosse atualizada ao clicar na opção **Atualizar conteúdo AEM** depois de modificar o assunto no Adobe Experience Manager. (CAMP-29984)
* Correção de vários problemas que impedia o uso de imagens dinâmicas do Adobe Target.
* Correção de um problema que impedia que a pré-visualização fosse atualizada ao recuperar conteúdo no momento da preparação se o conteúdo tivesse sido importado anteriormente de um URL.
* O ícone do YouTube foi adicionado ao componente de conteúdo **Social**.
* A visualização **Lista** foi adicionada para componentes de conteúdo e fragmentos exibidos na paleta Designer de email.

**Outras melhorias**

* A Adobe Campaign agora é totalmente compatível com o FCM para aplicativos SDK V4 e AEP SDK.
* A Adobe Campaign oferece suporte a notificações por push no Wear OS pelo Android e a watchOS pela Apple.
* As mensagens de aviso e de erro que podem ser exibidas ao navegar na interface ficaram mais claras e mais fáceis de entender.
* Agora você pode adicionar às colunas de lista de perfis relacionadas à aceitação e à recusa (&quot;Campos &quot;Não entre em contato ...&quot;).
* A lista suspensa Fuso horário na tela de criação do Perfil foi movida da seção Endereço para a seção superior da interface.
* Agora você pode adicionar separadores ao configurar telas de recursos personalizadas, permitindo que você organize seus campos no categoria.

   Para obter mais informações, consulte a [documentação detalhada](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration).

**Outras alterações**

* A Adobe Campaign e a Adobe Experience Cloud deixarão de oferecer suporte ao Microsoft Internet Explorer 11 a partir do primeiro trimestre de 2019 e da versão Campaign Standard 19.2. Use o Microsoft Edge ou outro navegador compatível. Consulte a página [Recursos obsoletos e removidos](../../rn/using/deprecated-features.md).
* O campo **Código do país** do recurso de Perfil foi renomeado para **Código do país/região**.

**Correções**

* Correção de um problema que impedia o envio da mensagem ao adicionar um perfil de teste a um mensagen transacional de email. (CAMP-29854)
* Correção de um problema que atrasava o envio de mensagens de outros canais se o envio fosse baixo para um canal quando o envio de mensagens de todos os canais era acionado simultaneamente.
* Correção de um problema que fazia com que o MTA start enviasse mensagens SMS quando a conexão de conta externa ainda não era estabelecida.
* Correção de um problema que ocorria com a frequência de execução da atividade do Scheduler e o tempo do start. (CAMP-30745)
* Correção de um problema que ocorria com a geração de PKEY ao usar recursos de perfil estendidos. (CAMP-30285)
* Correção de um problema que ocorria com regras de Fadiga baseadas no dia do calendário. (CAMP-30136)
* Correção de um problema que ocorria ao tentar acessar recursos personalizados com nomes terminados com &quot;Base&quot;. (CAMP-30109)
* Correção de um problema que impedia o uso de uma chamada de PATCH para assinar um perfil para um serviço. (CAMP-29728)
* Correção de um problema que corrompia um fluxo de trabalho ao importar um arquivo XML por meio da atividade Carregar arquivo. (CAMP-29208 e CAMP-28205)
* Correção de um problema ao vincular recursos personalizados que poderia impedir a geração de links de cardinalidade reversa. (CAMP-30476)
* Correção de um problema que impedia estender logs do delivery ao usar apenas o código de segmento.
* Correção de um problema que poderia duplicado linhas ao usar a atividade de transferência de Arquivo em workflows.
* Correção de um problema que impedia o envio de relatórios agendados no horário escolhido.
* Correção de um problema que causava discrepância entre os KPIs &quot;Enviar&quot; e &quot;Enviar&quot; para um delivery no aplicativo em um fluxo de trabalho.
* Correção de um problema que impedia que o rastreamento funcionasse para uma mensagem no aplicativo criada com um HTML personalizado.
* Correção de um problema que impedia que o conteúdo de delivery no aplicativo fosse salvo quando usado em um fluxo de trabalho.
* Correção de um problema que impedia que aplicativos móveis fossem exibidos para administradores.
* Correção de um problema que causava a falha do fluxo de trabalho técnico da Atualização de entregabilidade. (CAMP-26387)
* Correção de um problema que causava discrepância entre os perfis direcionados ao criar um delivery no aplicativo e os exibidos no painel do delivery. (CAMP-28722)
* Correção de um problema com a integração do Serviço principal de Campanha e Ativos que poderia impedir a seleção de um ativo compartilhado em um email.

## Versão 19.0 - Janeiro de 2019 {#release-19-0---january-2019}

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
   <td> Disponibilidade Geral do Designer de Email<br /> </td> 
   <td> <p>O novo e-mail Designer intuitivo (anteriormente conhecido como Creative Designer) foi movido para GA. Agora, ele oferece suporte a todos os recursos do editor de conteúdo legado, incluindo:</p> 
    <ul> 
     <li> O uso de <a href="../../integrating/using/adding-target-dynamic-content.md">imagens dinâmicas do Adobe Target</a> </li> 
     <li> A capacidade de <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">recuperar conteúdo de um URL automaticamente no momento da preparação</a> </li> 
     <li> Compatível totalmente com <a href="../../designing/using/using-reusable-content.md#content-templates">modelos de conteúdo prontos para uso</a>. </li> 
    </ul> 
    <p>Para saber mais, consulte a <a href="../../designing/using/designing-content-in-adobe-campaign.md">documentação detalhada</a> e o <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html">vídeo de instruções</a>. Os aprimoramentos e correções estão listados abaixo.</p><p>Como consequência, o editor de conteúdo de e-mail herdado agora está obsoleto. Para obter mais informações, consulte esta <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html">página</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Listas de produtos em emails transacionais<br /> </td> 
   <td> <p>Agora você pode fazer referência a uma ou mais coleções de produtos em uma mensagem de email transacional. Por exemplo, você pode enviar automaticamente um email de abandono de carrinho listando todos os produtos que estavam no carrinho do usuário com uma imagem, preço e link para cada produto.</p><p>Para saber mais, consulte a <a href="../../channels/using/editing-transactional-message.md#using-product-listings-in-a-transactional-message">documentação detalhada</a> e o <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html">vídeo de instruções</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Visualização móvel no Designer de email<br /> </td> 
   <td> <p>Agora você pode alternar para uma visualização para dispositivos móveis dedicada ao editar conteúdo de email. Isso permite ajustar o design responsivo de um email editando separadamente todas as opções de estilo para exibição móvel, como ajustar margens, tamanho de fonte menor, cor de fundo diferente e assim por diante.</p><p> Para obter mais informações, consulte a <a href="../../designing/using/plain-text-html-modes.md#switching-to-mobile-view">documentação detalhada</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Melhorias beta nas mensagens no aplicativo<br /> </td> 
   <td> <p>O recurso Beta de mensagens no aplicativo foi aprimorado com os seguintes recursos:</p> 
    <ul> 
     <li> O canal Beta no aplicativo é compatível com o GDPR </li> 
     <li> Integração com as APIs do Analytics para preencher os detalhes de Triggers </li> 
     <li> Aparência intuitiva e descrição dos templates do delivery </li> 
     <li> Melhorias na interface de criação do ponto de vista de usabilidade </li> 
    </ul> <p>Para obter mais informações, consulte a <a href="../../channels/using/about-in-app-messaging.md">documentação detalhada</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

**Aprimoramentos**

* Uma nova opção na atividade Carregar dados agora permite aplicar uma etapa de pós-processamento ao arquivo que contém os registros rejeitados (por exemplo, compactação no formato Zip). (CAMP-24521)
* Uma nova opção na atividade de dados Atualizar agora permite que você configure o tamanho máximo do lote para que os dados sejam carregados. (CAMP-28400)
* Seleção de estado de endereço de perfis aprimorada. Ao selecionar um país, a lista suspensa &quot;Estado&quot; agora é atualizada automaticamente com valores de estados relevantes. (CAMP-28874)
* Uma nova opção na atividade de arquivos Extract agora impede a geração de um arquivo se a transição de entrada estiver vazia. Isso evita criar e carregar arquivos vazios em servidores SFTP.
* O relatório de resumo do Delivery foi aprimorado.
* A lista dos países disponíveis ao definir um endereço de perfil foi enriquecida. (CAMP-26707)
* Uma mensagem de erro agora é exibida ao tentar importar um fluxo de trabalho incorporado.

**Designer de email**

* Correção de um problema que ativava o recurso de unidade geográfica em um modelo de e-mail ou em um fragmento de conteúdo criado com o Designer de e-mail, mesmo que esse recurso estivesse desabilitado no Adobe Campaign, o que tornava o modelo ou fragmento indisponível ao tentar acessá-lo novamente. (CAMP-28174)
* Correção de um problema que impedia que condições de conteúdo dinâmico fossem salvas ao editar conteúdo com o Designer de email. (CAMP-27905)
* Correção de um problema que removia a versão HTML do conteúdo de email após a edição da versão em texto simples de uma mensagem e a quebra da sincronização em HTML no Designer de email. (CAMP-28507)
* Correção de um problema que impedia a abertura da interface do Email Designer ao usar o Internet Explorer 11. (CAMP-28273)
* Correção de um problema que distorcia a renderização de configurações de estilo do Microsoft Outlook aplicadas a botões com o Designer de email.
* Correção de um problema no Designer de email que tornava editável um URL de um fragmento de conteúdo usado em um email, o que não era esperado, pois o fragmento era bloqueado por padrão.
* Correção de um problema que impedia a exibição do componente divisor do Email Designer no Microsoft Office.
* Correção de um problema que causava o congelamento de uma página em determinados navegadores da Internet ao visualizar um conteúdo sincronizado de AEM usando o editor de conteúdo de email herdado. (CAMP-29068)
* Correção de um erro que ocorria ao clicar em qualquer imagem em um email ao usar o editor de conteúdo de email herdado. (CAMP-30424)
* Correção de um problema que impedia que os fragmentos recém-criados fossem exibidos ao editar um email com o Designer de email. (CAMP-29928)
* Correção de um problema que impedia que o texto do botão fosse exibido corretamente em emails criados com o Designer de email e recebidos usando o cliente do Outlook Web mail.
* Agora é possível criar mensagens transacionais de perfil usando o Designer de e-mail. (CAMP-28900)
* Correção de um erro no Designer de email que tornava o conteúdo editável ao recuperar o conteúdo de um URL automaticamente no momento da preparação, enquanto deveria ser bloqueado.

**Correções**

* Correção de um problema que mostrava logs do delivery incorretos no relatórios dinâmico. (CAMP-23446)
* Correção de um problema que poderia afetar os números no relatório Resumo da rejeição (CAMP-28703)
* Correção de um problema com a integração do Serviço principal de Campanha e ativos que poderia impedir a exibição de ativos ao selecionar **[!UICONTROL Image shared from Adobe Experience Cloud]** em um email (CAMP-28732).
* Correção de um problema que impedia o envio de mensagens SMS contendo o caractere &quot;um&quot;, mesmo que a transliteração fosse autorizada na conta externa SMPP. (CAMP-29041)
* Correção de um problema que podia exibir registros de duplicados ao usar uma atividade de Segmentação em workflows. (CAMP-28743)
* Correção de um problema que impedia a exclusão de um dos mapeamentos de valor em uma coluna em uma atividade de fluxo de trabalho. (CAMP-28708)
* Correção de um problema na atividade de transferência de Arquivo, ao usar curingas com a opção &quot;Testar para ver se o arquivo existe&quot;. (CAMP-28977)
* Correção de um problema na atividade Transferência de arquivos que poderia ocorrer ao atualizar as configurações de conta externa. (CAMP-28894)
* Correção de um problema com filtros personalizados no editor de query ao usar a condição &quot;E-mail não está vazio&quot;. (CAMP-28741)
* Correção de um problema que ocorria ao exportar tabelas de recursos personalizadas com mais de 100 mil registros. (CAMP-28150)
* Correção de um problema que impedia a exclusão de mensagens transacionais vinculados a acionadores. (CAMP-28385)
* Senhas removidas que foram exibidas sem segurança em alguns logs SMS.
* Correção de um problema que causava a falha das conexões com o simulador SMPP devido à senha vazia enviada pela Adobe Campaign.
* Correção de um problema que impedia o envio de campanhas quando as conexões SMS estavam instáveis.
* Correção de um problema que exibia delivery excluídos no relatórios dinâmico.
* Correção de um problema que impedia a recuperação de dados adicionais de logs do delivery, logs de rastreamento e tabelas de registros de exclusão ao usar uma atividade de Enriquecimento em um fluxo de trabalho.
* Correção de um problema com solicitações de exclusão do RGPD que poderia ocorrer ao usar um tipo de link &quot;N de coleção de cardinalidade&quot; e a opção &quot;Excluir o registro de público alvo implica excluir referências de registro pelo link&quot;.
* Correção de um problema com o compartilhamento de relatórios.
* Correção de um problema que resultava em problemas de throughput ao enviar uma notificação por push.
* Correção de um problema que causava a falta de campos nos arquivos de saída de mala direta.
* Correção de um problema que permitia aos usuários modificar workflows incorporados.
* Correção de um problema ao criar uma campanha com base em um template de campanha, incluindo um fluxo de trabalho com uma atividade de extração configurada. (CAMP-29198)
* Correção de um problema com a atividade extração Arquivo que impedia o uso da mesma expressão para vários elementos. (CAMP-29182)
* Correção de um problema, no editor de query, com a condição de junção entre o log de fluxo e o log de rastreamento para rtEvent. (CAMP-28780)
* Correção de um problema que impedia que modificações na opção de landing page &quot;Ação específica&quot; fossem salvas. (CAMP-29422)
* Correção de um problema que impedia a exportação de uma carga de evento em um fluxo de trabalho. (CAMP-29029)
* Correção de um problema que impedia que números de SMS na  lista de bloqueios fossem excluídos em uma mensagem SMS. (CAMP-28898)
* Correção de um problema que impedia que os provedores SMPP fossem notificados em caso de erro ao processar mensagens recebidas. (CAMP-29804)
* Correção de um problema que permitia a exclusão de contas externas com delivery associados. (CAMP-29738)
* A taxa de transferência de envio foi melhorada e estabilizada para mensagens SMS.
* Correção de um problema que impedia o caractere &quot;~&quot; de ser usado em uma mensagem SMS. (CAMP-29172)
* Correção de um problema em delivery com a opção de otimização de tempo de envio. (CAMP-29231)

