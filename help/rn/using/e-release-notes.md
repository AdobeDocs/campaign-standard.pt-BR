---
title: Notas de versão anteriores
description: Notas de versão anteriores
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 5435e1dbfbe08399c488322320ac5bb8e681a79d
workflow-type: ht
source-wordcount: '734'
ht-degree: 100%

---

# Notas de versão anteriores {#new-release}

Esta página descreve novos recursos, melhorias e correções incluídos na próxima versão do Campaign Standard.

>[!CAUTION]
>
> Esse conteúdo está sujeito a alterações sem aviso prévio até a data de atualização dos ambientes de estágio. Saiba mais na [página de planejamento de versão](../../rn/using/release-planning.md).

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
* Para resolver vários problemas, o mecanismo de repetição foi aprimorado para deliveries, incluindo conteúdo importado de um URL. (CAMP-48888)
* Correção de um problema que ocorria após a criação de um novo filtro em um recurso personalizado, ao usá-lo como uma chave de reconciliação em uma página de aterrissagem. Se o recurso personalizado fosse publicado novamente, o filtro era removido da lista de chaves de reconciliação disponíveis para a página de aterrissagem. (CAMP-49516)
* Correção de um problema nas páginas de aterrissagem ao usar condições dinâmicas com caixas de seleção. (CAMP-48604)
* Correção de um problema que ocorria em uma atividade de **Consulta** ao usar a condição de filtro &quot;Em ou antes de outubro&quot;. Ao trabalhar de uma instância definida para um fuso horário europeu, o mês selecionado para o filtro mostrava setembro em vez de outubro, devido a um problema na conversão do fuso horário. (CAMP-48602)
* Para otimizar a entregabilidade, o Adobe Campaign agora envia emails usando codificação de 7 bits em vez de 8 bits. Isso impede que retransmissões intermediárias invalidem a assinatura DKIM, o que pode afetar a autenticidade das mensagens. (CAMP-49016)
* Os desempenhos ao duplicar públicos foram aprimorados para evitar problemas ao trabalhar com públicos grandes. (CAMP-49639)
* Correção de um problema que impedia que um filtro personalizado exibisse os resultados corretos quando usado em uma atividade de **Consulta**. (CAMP-49417)
* Correção de um erro que exibia uma mensagem de erro ao tentar usar um fragmento em um delivery com uma vírgula em seu nome. O problema foi resolvido e agora as vírgulas podem ser usadas nos nomes dos fragmentos. (CAMP-49216)