---
solution: Campaign Standard
product: campaign
title: Notas de versão anteriores
description: Notas de versão anteriores
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: ac129fd21382d1d89263acae2fdbe280709f5946
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 43%

---

# Notas de versão anteriores {#new-release}

Esta página descreve novos recursos, melhorias e correções incluídos na próxima versão do Campaign Standard.

>[!CAUTION]
>
> Esse conteúdo está sujeito a alterações sem aviso prévio até a data de atualização dos ambientes de estágio. Saiba mais na [página de planejamento de versão](../../rn/using/release-planning.md).

## Versão 21.3 - Setembro de 2021 {#release-21-3---sept-2021}

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
* Adição de uma verificação de consistência ao criar índices em recursos personalizados e melhoria das mensagens de erro.

**Outras alterações**

* O serviço Adobe Experience Platform Data Connector e Audience Destinations agora está obsoleto no Campaign Standard. Se estiver usando esses recursos, será necessário migrar para Fontes e Destinos do Adobe e adaptar sua implementação. [Saiba mais](../../integrating/using/get-started-sources-destinations.md)
* Os recursos obsoletos e removidos são listados em [this page](deprecated-features.md).
* Uma nova função de agregação &quot;StringAgg&quot; foi introduzida para concatenar os valores de uma coluna do tipo string. (CAMP-47077)
* O workflow técnico **Update delivery indicators** (updateDeliveryIndicators) foi aprimorado para melhorar o desempenho.
* Os modelos de mensagens no aplicativo agora estão disponíveis para todos os idiomas suportados no Campaign Standard.
* O tempo de preparação de delivery foi otimizado para mensagens transacionais, reduzindo o número de chamadas para o servidor de rastreamento durante a análise de delivery.
* Uma nova mensagem de alerta informa aos usuários uma alta taxa de rejeição.
* Mensagens e avisos de erro de log aprimorados para facilitar a depuração quando os logs de rastreamento falharam ao serem recuperados corretamente. (CAMP-48939, CAMP-47360)
* Agora é possível personalizar totalmente as URLs, incluindo o nome do domínio. [Saiba mais](../../designing/using/personalization.md#personalizing-urls)

**Correções**

* Correção de um erro de tempo limite ao importar conteúdo de email de um URL. (CAMP-49054)
* Correção de um erro (-69) causado por um fim de sessão, ao acessar um URL marcado ou atualizar uma página do navegador. (CAMP-49003, CAMP-48930, CAMP-48894)
* Correção de um problema ao sincronizar regras do servidor de capacidade de entrega herdado para o novo servidor de capacidade de entrega. (CAMP-48923)
* Correção de um problema ao carregar um modelo de email com tags HTML no Designer de email. (CAMP-48243)
* Correção de um erro em que o conteúdo do Adobe Experience Manager não era carregado ao criar mensagens transacionais com o Designer de email. (CAMP-49075)
* Correção de um problema na interface em que um preenchimento excessivo era adicionado entre a barra superior e o conteúdo.
* Correção de um problema com mensagens transacionais que poderia levar a um erro de publicação ao usar blocos de conteúdo do Campaign no conteúdo do Adobe Experience Manager. (CAMP-49233)
* Correção de um problema que poderia resultar em uma mensagem de erro quando a autenticação falhava. O usuário agora é redirecionado para a página de logon.
* Correção de um problema de exibição de token que impedia os usuários de editar ou compartilhar um relatório.
* Correção de um problema durante a publicação de um recurso personalizado usando uma expressão de filtro com relações de tabela 1-n. (CAMP-48740)
* Correção de um problema de formatação de data que impedia que as datas de contato do delivery fossem recuperadas em transições de workflow. (CAMP-48871)
* Correção de um problema que impedia a extensão de logs de envio durante a criação de uma dimensão de perfil personalizada.
* Correção de um problema que resultava em falha de deliveries com várias variantes de idioma. A partir de agora, se um usuário excluir a variante de idioma padrão, outra variante de idioma deverá ser definida como padrão antes da criação de cópias de idiomas. (CAMP-48235)
* Correção de um problema que fazia com que as mensagens de email mostrassem espaços em branco extras no Outlook se o usuário tivesse selecionado a opção **Mostrar somente em dispositivos móveis** ao projetar a mensagem. (CAMP-48902)
* Correção de um problema que fazia com que a data da última execução do campo de atividade de query incremental ficasse ausente na guia **Dados processados** após a execução do workflow de query incremental. (CAMP-48879)
* Correção de um problema que impedia a definição adequada de um código de segmento dinâmico na atividade de workflow de **Segmentação**. (CAMP-48727)
* Correção de um erro que ocorria aleatoriamente ao tentar salvar um workflow após editá-lo. (CAMP-48695)
* Correção de um problema que impedia a publicação de recursos personalizados devido à permanência de um esquema de dados do acionador mesmo após a exclusão do acionador. (CAMP-48523)
* Correção de um problema que impedia que as solicitações do loop de comentários fossem atendidas, pois o processo do InMail não podia recuperar os logs do delivery para atualizar. (CAMP-48705)
* Correção de um problema que impedia definir corretamente as opções de exclusão na atividade de workflow **Exclusion** .(CAMP-48355)
* Correção de um problema que ocorria quando atividades de enriquecimento em workflows envolviam assinaturas ou unsubscriptions de um serviço. Esse problema causou falha.
* Correção de um problema que impedia a execução de workflows.
* Correção de um problema que impedia os usuários de renomear ou excluir grupos de segurança predefinidos da interface do usuário.
* Correção de um problema que impedia usuários de excluir um trabalho de publicação de evento incompleto.
* Correção de um problema em que o workflow de limpeza do banco de dados falhava com um erro. (CAMP-49097)
