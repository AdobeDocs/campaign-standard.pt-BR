---
title: Versão mais recente
description: Esta página detalha o conteúdo da versão mais recente do Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 199a40da4ae168fced2bada7d0515839bfe38c15
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---


# Versão mais recente{#latest-release}

![Painel de controle do Campaign](assets/do-not-localize/cp-icon.png) **Nova versão do Painel de controle do Campaign**. [Saiba mais](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=pt-BR){target=&quot;_blank&quot;}.


## Versão 22.2 - junho de 2022 {#june-2022}

**Aprimoramentos**

* **Serviço de notificação da Adobe** - o Campaign vem com o Serviço de notificação da Adobe, que permite que as soluções da Experience Cloud alertem os usuários sobre atividades que são importantes para eles. A experiência do usuário foi aprimorada a partir da versão 22.2: as notificações foram priorizadas e as notificações geradas por produtos foram separadas dos avisos de status da Adobe. Além disso, quando a notificação se refere a um fluxo de trabalho específico, agora é possível acessar o fluxo de trabalho correspondente diretamente do email ou da notificação no produto.  Para obter mais informações sobre notificações do Adobe Campaign, consulte [Notificações do Adobe Campaign](../../administration/using/sending-internal-notifications.md).

* **Otimização na inicialização do fluxo de trabalho** - A Adobe adicionou um novo recurso que pode ajustar o número de workflows que começam ao mesmo tempo. Isso ajudaria a evitar picos da CPU que poderiam levar a interrupções do serviço ou tempo de inatividade. A Adobe o ativaria após a versão 22.2. Não há mais nenhum item de ação no cliente em relação a isso.

* **Acessibilidade** - a Adobe fez muitas correções de acessibilidade para melhorar a facilidade geral de uso do aplicativo. No momento, esses recursos estão habilitados apenas para alguns participantes iniciais e serão implantados para todos os clientes na versão 22.3 do ACS. Exemplos de melhorias de acessibilidade:

   * Garantia de que haja um indicador de foco visível para elementos focalizáveis em cada tela
   * Criação de pontos de referência de página para facilitar a navegação
   * Adição de nome, função, valor e estado para diversos controles
   * Correção de problemas relacionados à ordem de foco dinâmico nas telas principais


**Correções**

* Correção de um problema no fluxo de trabalho técnico de faturamento devido a um erro de chave duplicada. (CAMP-51029)
* Adição da categoria ausente do navegador Microsoft Edge em Relatórios de rastreamento. Eles eram categorizados anteriormente como aberturas do Microsoft e Chrome. (CAMP-51165)
* Correção de um problema com solicitações do GDPR que não excluíam dados de tabelas secundárias. (CAMP-48276)
* Correção de um problema no Designer de email que fazia com que a condição de visibilidade de um fragmento não fosse salva em um template de mensagem transacional. (CAMP-50338)
* Correção de um problema nos Relatórios de campanha que fazia com que o intervalo de datas não fosse considerado. (CAMP-50991)
* Correção de um erro que causava a falha de emails agendados: a análise de entrega não podia ser iniciada, pois a entrega ainda estava no status “Nova tentativa pendente”. (CAMP-50302)
* Correção de um problema no Designer de email ao visualizar um email com uma substituição de perfil. (CAMP-49312)
* Correção de um problema com listas discriminadas personalizadas de valor vazio: ao criar um recurso personalizado com um campo que é uma lista discriminada de texto e contém apenas um valor, esse valor agora é definido por padrão, para que você possa criar uma consulta nesse campo como uma solicitação simples. (CAMP-50606)



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
* Agora é possível monitorar o delivery e rastrear logs de trabalhos com o novo menu suspenso de **Histórico de tarefas** no painel de suas mensagens. [Saiba mais](../../sending/using/monitoring-a-delivery.md) (CAMP-49840)
* Aprimoramento da estabilidade e integridade do banco de dados, ao reduzir tuplas inativas quando um grande número de mensagens são enviadas por todos os canais ao longo do tempo. (CAMP-49755, CAMP-49792, CAMP-49849)
* Para garantir que as conexões do banco de dados sejam atualizadas automaticamente em caso de falha ou reinicialização do banco de dados, foram implementadas melhorias no Mail Transfer Agent (MTA) do Campaign. (CAMP-48063)
* Uma nova opção de rastreamento para **Usar o pixel de rastreamento na parte superior do email** foi adicionada às propriedades de email, permitindo mover o pixel de rastreamento na parte superior do email, em vez de na parte inferior. (CAMP-49672)

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

