---
title: Versão mais recente
description: Esta página detalha o conteúdo da versão mais recente do Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 7066cf1d8454ffdefa29bff5092ba2c3e1bac705
workflow-type: tm+mt
source-wordcount: '1766'
ht-degree: 99%

---


# Versão mais recente{#latest-release}

## Versão 22.1 - Fevereiro de 2022 {#feb-2022}

**Novidades**

<table> 
<thead> 
<tr> 
<th> <strong>Atualização de segurança para vulnerabilidades de segurança do Apache Log4j</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>O Apache log4j corrigiu as vulnerabilidades relatadas na versão Apache log4j v2.17.1. O Adobe Campaign Standard usa o Apache log4j e, nesta versão, inclui o Apache log4j v2.17.1 mais recente </p>
</td> 
</tr> 
</tbody> 
</table>

**Correções de segurança**

* Novo mecanismo de assinatura de URL para rastreamento incluído nesta versão. O mecanismo anterior foi desabilitado para evitar um problema que fazia com que alguns links de rastreamento válidos e assinados fossem bloqueados incorretamente após serem modificados por ferramentas de segurança de terceiros. (CAMP-48983)

**Aprimoramentos**

* Processamento de dados de relatório aprimorado para evitar sobrecarga do sistema. (CAMP-47578)
* Depois de enviar mensagens no aplicativo, é possível optar por desativar o delivery. Isso permite excluir o delivery sem perder nenhum dado de relatório. (CAMP-48469)
* Para evitar qualquer problema, os usuários não podem mais usar o mesmo nome da Chave primária automática no banco de dados em uma coluna de tabela personalizada, `"<dataType><resourceName>Id"`. (CAMP-49358)
* Agora é possível monitorar o delivery e rastrear logs de trabalhos com o novo menu suspenso de **Histórico de tarefas** no painel de suas mensagens. (CAMP-49840)
* Aprimoramento da estabilidade e integridade do banco de dados, ao reduzir tuplas inativas quando um grande número de mensagens são enviadas por todos os canais ao longo do tempo. (CAMP-49755, CAMP-49792, CAMP-49849)
* Para garantir que as conexões do banco de dados sejam atualizadas automaticamente em caso de falha ou reinicialização do banco de dados, foram implementadas melhorias no Mail Transfer Agent (MTA) do Campaign. (CAMP-48063)


**Correções**

* Correção de um problema com a opção **Enviar relatório agora** em Relatórios dinâmicos: os trabalhos de geração de PDF falhavam com os deliveries, incluindo várias variantes. (CAMP-49120)
* Correção de um problema que impedia os usuários de atualizar ou desvincular o conteúdo do Adobe Experience Manager (AEM) dos deliveries do Adobe Campaign Standard quando um conteúdo duplicado no AEM compartilhava a mesma chave (cq:uuid). (CAMP-49161)
* Correção de um erro ao acessar uma instância em que as páginas não estavam carregando, os deliveries não podiam ser abertos ou as modificações pendentes não podiam ser salvas. (CAMP-50195)
* Correção de um problema que impedia a abertura dos critérios de alerta de Delivery se o campo **Filtro de delivery** aplicado por este critério não fosse preenchido. (CAMP-49093)
* Correção de um problema ao editar o botão **Secundário**, nos deliveries no aplicativo, que impedia que as alterações fossem consideradas. (CAMP-50250)
* Correção de um erro em instâncias japonesas que impedia os usuários de escolher Várias vezes por dia, como **Frequência de execução** na atividade **Scheduler**. (CAMP-50247)
* Correção de um problema ao trabalhar em uma interface de usuário japonesa que exibia uma mensagem de erro ao selecionar um horário em uma atividade do Scheduler. (CAMP-49289)
* Correção de um erro com relatórios de notificação por push que exibiam notificações por push rejeitadas como **Abrir**, em vez de **Impressão**. (CAMP-45980)
* Correção de um problema que poderia resultar em erros ao abrir um relatório. (CAMP-49222)
* Correção de um problema que poderia resultar na falha da preparação do email após a exclusão de um link para conteúdo AEM. (CAMP-49877)
* Para resolver vários problemas, o mecanismo de repetição foi aprimorado para deliveries, incluindo conteúdo importado de um URL. [Saiba mais](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time) (CAMP-48888)
* Correção de um problema que ocorria após a criação de um novo filtro em um recurso personalizado, ao usá-lo como uma chave de reconciliação em uma página de aterrissagem. Se o recurso personalizado fosse publicado novamente, o filtro era removido da lista de chaves de reconciliação disponíveis para a página de aterrissagem. (CAMP-49516)
* Correção de um problema nas páginas de aterrissagem ao usar condições dinâmicas com caixas de seleção. (CAMP-48604)
* Correção de um problema que ocorria em uma atividade de **Consulta** ao usar a condição de filtro &quot;Em ou antes de outubro&quot;. Ao trabalhar de uma instância definida para um fuso horário europeu, o mês selecionado para o filtro mostrava setembro em vez de outubro, devido a um problema na conversão do fuso horário. (CAMP-48602)
* Para otimizar a entregabilidade, o Adobe Campaign agora envia emails usando codificação de 7 bits em vez de 8 bits. Isso impede que retransmissões intermediárias invalidem a assinatura DKIM, o que pode afetar a autenticidade das mensagens. (CAMP-49016)
* Os desempenhos ao duplicar públicos foram aprimorados para evitar problemas ao trabalhar com públicos grandes. (CAMP-49639)
* Correção de um problema que impedia que um filtro personalizado exibisse os resultados corretos quando usado em uma atividade de **Consulta**. (CAMP-49417)
* Correção de um erro que exibia uma mensagem de erro ao tentar usar um fragmento em um delivery com uma vírgula em seu nome. O problema foi resolvido e agora as vírgulas podem ser usadas nos nomes dos fragmentos. (CAMP-49216)


## Versão 21.3 - Setembro de 2021 {#release-21-3---sept-2021}

Os novos recursos, melhorias e correções incluídos na versão mais recente do Campaign Standard estão listados abaixo.

**Novidades**

<table> 
<thead> 
<tr> 
<th> <strong>Interface unificada da Experience Cloud</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>A barra de cabeçalho do Adobe Campaign foi alterada para unificar e melhorar sua experiência em todos os produtos e serviços da Experience Cloud. Essas alterações foram projetadas para facilitar sua vida, inclusive:</p>
<ul>
<li>É mais fácil alternar entre suas organizações ou mudar de aplicativo.</li>
<li>Ajuda do usuário aprimorada: com a inclusão da Experience League no produto, os resultados da pesquisa também abrangem resultados de fóruns da comunidade e mais conteúdo de vídeo, facilitando o acesso a mais conteúdo para aproveitar ao máximo o aplicativo. Também adicionamos um mecanismo de feedback diretamente no menu Ajuda, facilitando o relato de problemas ou o compartilhamento de suas ideias.</li>
<li>Notificações aprimoradas: o menu suspenso Notificações agora tem duas guias, uma para suas próprias notificações de produtos e uma para anúncios de produtos mais globais.</li>
</ul>
<p>Para obter mais informações consulte a <a href="../../start/using/interface-description.md#top-bar">documentação detalhada</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Trilha de auditoria</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>A nova trilha de auditoria captura em tempo real uma lista abrangente de ações e eventos que ocorrem no Adobe Campaign. Ela inclui uma forma de autoatendimento a fim de acessar um histórico de dados para ajudar a responder a perguntas como:</p>
<ul>
<li>O que aconteceu com esse fluxo de trabalho e quem o atualizou pela última vez?</li>
<li>Quem fez as últimas mudanças?</li>
<li>Qual era o estado anterior?</li>
</ul>
<p>O Adobe Campaign agora audita ações de criação, edição e exclusão para: workflows, opções e recursos personalizados. As modificações desses itens também são rastreadas.</p>
<p>Para obter mais informações, consulte a <a href="../../administration/using/audit.md">documentação detalhada</a>.</p>
</td> 
</tr> 
</tbody> 
</table>


<table> 
<thead> 
<tr> 
<th> <strong>Modo de diagnóstico do fluxo de trabalho</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Agora você pode executar workflows da campanha no modo de diagnóstico. Esse modo registra informações para ajudar a solucionar problemas de execução. Todo o plano de execução é registrado se uma consulta de fluxo de trabalho levar, por padrão, mais de um minuto.</p>
<p>Para obter mais informações consulte a <a href="../../automating/using/managing-execution-options.md">documentação detalhada</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Melhorias de segurança**

* A segurança foi aprimorada para proteção contra ataques de SSRF. (CAMP-47836)
* A lista de usuários agora está restrita apenas a administradores. (CAMP-47260)
* As variáveis de ambiente não podem mais ser usadas como parte da expansão de parâmetros em um URL. (CAMP-47268)

**Melhorias**

* Ao ser criada uma entrega recorrente em um fluxo de trabalho, vinculado a um conteúdo do Adobe Experience Manager, o status de aprovação do conteúdo agora é verificado antes do envio.
* O limite de conexão de banco de dados agora está alinhado ao pacote do Campaign para evitar erros de conexão.
* Uma nova verificação de consistência na publicação de recursos personalizados impede que os usuários criem índices duplicados, o que faz com que a publicação falhe. Uma mensagem de erro aprimorada solicita que o usuário renomeie o índice, se necessário. [Saiba mais](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)

**Outras alterações**

* O serviço Adobe Experience Platform Data Connector e Audience Destinations foi descontinuado no Campaign Standard. Se você estiver usando esses recursos, será necessário migrar para Fontes e Destinos do Adobe e adaptar sua implementação. [Saiba mais](../../integrating/using/get-started-sources-destinations.md)
* Os recursos obsoletos e removidos estão listados [nesta página](deprecated-features.md).
* Uma nova função de agregação &quot;StringAgg&quot; foi introduzida para concatenar os valores de uma coluna do tipo string. (CAMP-47077) [Saiba mais](../../automating/using/list-of-functions.md#aggregates)
* O fluxo de trabalho técnico **Atualizar indicadores de entrega** (updateDeliveryIndicators) foi aprimorado para melhorar o desempenho.
* Os modelos de mensagens no aplicativo agora estão disponíveis para todos os idiomas aceitos no Campaign Standard.
* O tempo de preparo da entrega foi otimizado para mensagens transacionais, reduzindo o número de chamadas para o servidor de rastreamento durante a análise da entrega.
* Uma nova mensagem de alerta informa aos usuários uma alta taxa de rejeição.
* Mensagens e avisos de erro de log aprimorados para facilitar a depuração quando os logs de rastreamento falharam ao serem recuperados corretamente. (CAMP-48939, CAMP-47360)
* Agora é possível personalizar totalmente os URLs, incluindo o nome do domínio. [Saiba mais](../../designing/using/personalization.md#personalizing-urls)

**Correções**

* Correção de um erro de tempo limite ao importar conteúdo de email de um URL. (CAMP-49054)
* Correção de um erro (-69) causado pelo fim da sessão ao acessar um URL marcado ou atualizar uma página do navegador. (CAMP-49003, CAMP-48930, CAMP-48894)
* Correção de um problema ao sincronizar regras do servidor de capacidade de entrega herdado para o novo servidor de capacidade de entrega. (CAMP-48923)
* Correção de um problema ao carregar um modelo de email com tags HTML no Designer de email. (CAMP-48243)
* Correção de um erro em que o conteúdo do Adobe Experience Manager não era carregado ao serem criadas mensagens transacionais com o Designer de email. (CAMP-49075)
* Correção de um problema na interface em que um preenchimento excessivo era adicionado entre a barra superior e o conteúdo.
* Correção de um problema com mensagens transacionais que podia causar um erro de publicação ao serem usados blocos de conteúdo do Campaign no conteúdo do Adobe Experience Manager. (CAMP-49233)
* Correção de um problema que podia resultar em uma mensagem de erro quando a autenticação falhava. O usuário agora é redirecionado para a página de logon.
* Correção de um problema de exibição de token que impedia os usuários de editar ou compartilhar um relatório.
* Correção de um problema durante a publicação de um recurso personalizado usando uma expressão de filtro com relações de tabela 1-n. (CAMP-48740)
* Correção de um problema de formatação de data que impedia que as datas de contato da entrega fossem recuperadas em transições do fluxo de trabalho. (CAMP-48871)
* Correção de um problema que impedia a extensão de logs de envio durante a criação de uma dimensão de perfil personalizada.
* Correção de um problema que resultava em falha de entrega com múltiplas variantes de idioma. A partir de agora, se um usuário excluir a variante de idioma padrão, outra variante de idioma deverá ser definida como padrão antes da criação de cópias de idiomas. (CAMP-48235)
* Correção de um problema que fazia com que as mensagens de email mostrassem espaços em branco extras no Outlook se o usuário selecionasse a opção **Mostrar somente em dispositivos móveis** ao projetar a mensagem. (CAMP-48902)
* Correção de um problema que fazia com que a data da última execução do campo de atividade de query incremental ficasse ausente na guia **Dados processados** após a execução do fluxo de trabalho de query incremental. (CAMP-48879)
* Correção de um problema que impedia a definição adequada de um código de segmento dinâmico na atividade de fluxo de trabalho **Segmentação**. (CAMP-48727)
* Correção de um erro que ocorria aleatoriamente ao tentar salvar um fluxo de trabalho após editá-lo. (CAMP-48695)
* Correção de um problema que impedia a publicação de recursos personalizados devido à permanência de um esquema de dados do acionador mesmo após a exclusão do acionador. (CAMP-48523)
* Correção de um problema que impedia que as solicitações do loop de comentários fossem atendidas, pois o processo do InMail não podia recuperar os logs do delivery para atualização. (CAMP-48705)
* Correção de um problema que impedia a definição correta das opções de exclusão na atividade de fluxo de trabalho **Exclusão**.(CAMP-48355)
* Correção de um problema que ocorria quando atividades de enriquecimento em workflows envolviam assinaturas ou cancelamentos de assinaturas de um serviço. Esse problema causou uma falha.
* Correção de um problema que impedia a execução de workflows.
* Correção de um problema que impedia os usuários de renomear ou excluir grupos de segurança predefinidos da interface do usuário.
* Correção de um problema que impedia usuários de excluir um trabalho de publicação de evento incompleto.
* Correção de um problema em que o fluxo de trabalho de limpeza do banco de dados falhava com um erro. (CAMP-49097)
