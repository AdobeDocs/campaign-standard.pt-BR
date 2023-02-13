---
title: Notas de versão de 2021
description: Essa página lista todas as versões de 2021 do Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: 225c65cc-2964-4b71-84a9-30fcd22d75bf
source-git-commit: 1a2b2ab8b6d23ca021d196909dc3ebdc02fe4e9e
workflow-type: tm+mt
source-wordcount: '4569'
ht-degree: 100%

---

# Notas de versão de 2021{#release-notes-2021}

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
* Os perfis de prova e captura foram excluídos do cálculo de desempenho de delivery nos Relatórios dinâmicos. (CAMP-47338)

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
* Correção de um problema que fazia com que a data da última execução do campo de atividade de consulta incremental não fosse exibida na guia **Dados processados** após a execução do fluxo de trabalho de query incremental. (CAMP-48879)
* Correção de um problema que impedia a definição adequada de um código de segmento dinâmico na atividade de fluxo de trabalho **Segmentação**. (CAMP-48727)
* Correção de um erro que ocorria aleatoriamente ao tentar salvar um fluxo de trabalho após editá-lo. (CAMP-48695)
* Correção de um problema que impedia a publicação de recursos personalizados devido à permanência de um esquema de dados do acionador mesmo após a exclusão do acionador. (CAMP-48523)
* Correção de um problema que impedia que as solicitações do loop de comentários fossem atendidas, pois o processo do InMail não podia recuperar os logs do delivery para atualização. (CAMP-48705)
* Correção de um problema que impedia a definição correta das opções de exclusão na atividade de fluxo de trabalho **Exclusão**.(CAMP-48355)
* Correção de um problema que ocorria quando atividades de enriquecimento em workflows envolviam assinaturas ou cancelamentos de assinaturas de um serviço. Esse problema causou uma falha.
* Correção de um problema que impedia a execução de workflows.
* Correção de um problema que impedia os usuários de renomear ou excluir grupos de segurança predefinidos da interface do usuário.
* Correção de um problema que impedia usuários de excluir um processo de publicação de evento incompleto.
* Correção de um problema em que o fluxo de trabalho de limpeza do banco de dados falhava com um erro. (CAMP-49097)


## Versão 21.2 - Junho de 2021 {#release-21-2---june-2021}

Os novos recursos, melhorias e correções incluídos na próxima versão do Campaign Standard estão listados abaixo. Os novos recursos, as melhorias e as correções incluídos nesta versão do Campaign Standard estão listados abaixo.

**Melhorias**

* Ao criar uma página de destino, agora é possível adicionar uma caixa de seleção obrigatória que os perfis devem marcar antes de enviar o formulário. Para obter mais informações consulte a [documentação detalhada](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox).

* Para a integração do Triggers, a mensagem de erro exibida quando o conteúdo do acionador não recebe dados de reconciliação foi aprimorada: “Dados de alias ausentes no conteúdo”.

* O desempenho para recuperar notificações por push da fila foi aprimorado.

**Outras alterações**

* O mecanismo de assinatura do URL para links de rastreamento foi desabilitado para evitar um problema que fazia com que alguns links de rastreamento válidos e assinados fossem bloqueados incorretamente após serem modificados por ferramentas de segurança de terceiros.

* Em entregas com muitas variantes, os usuários não poderão mais criar cópias de idioma se a variante padrão tiver sido excluída. Uma mensagem agora é exibida durante a criação da cópia de idioma. (CAMP-48235)

* O processo de exclusão de perfil de duas etapas (descontinuado a partir da versão 19.4 do Campaign) agora está desativado por padrão. Anteriormente, era necessário desativá-lo manualmente na interface do Campaign antes de usar o Serviço principal de privacidade. Não fazer isso levava as solicitações de exclusão a permanecerem no estado pendente sem conclusão.

* Em Relatórios dinâmicos, o segmento **Excluir prova** foi removido. (CAMP-46161)

* Uma nova mensagem de aviso foi adicionada para informar ao usuário quando um certificado iOS é carregado sem o valor platformPrincipal no aplicativo Campaign.

* O tamanho máximo de um email agora é definido como 100 MB por padrão. Esse limite permite evitar qualquer erro que possa aumentar indefinidamente o tamanho de um email, o que pode causar uma falha do sistema. (CAMP-47445) [Saiba mais](../../sending/using/design-and-personalize.md#email-size)

* A integração do Serviço principal de ativos com o Designer de email agora pode ser usada por usuários padrão.

* Uma nova mensagem foi adicionada para confirmar uma migração bem-sucedida de um aplicativo de push v4 para um aplicativo de push v5.

* Durante a criação de tokens JSONWeb para autenticar na API do Campaign Standard, os perfis de produto agora são **considerados**. Isso significa que as entidades organizacionais e funções alocadas ao grupo de segurança (que corresponde ao perfil do produto no AdobeIO) serão aplicadas à conta técnica IMS necessária para chamadas de API Rest do Campaign Standard. (CAMP-47479)

**Correções**

* Correção de um problema que impedia que a opção de expiração da tabela de log do processo em lote (**xtkjoblog**) fosse aplicada. Isso impedia que a tabela fosse removida corretamente.

* Correção de um problema que impedia a alteração da ordem dos filtros em uma atividade de fluxo de trabalho de **Segmentação**. (CAMP-48357)

* Correção de uma regressão de 20.4 que podia resultar em falha de entregas com um erro de valor nulo. (CAMP-48591)

* Correção de um problema que impedia o envio de um relatório por meio do menu **Compartilhar** > **Enviar relatório agora** ou **Enviar relatório na programação**. (CAMP-47798)

* Correção de uma regressão introduzida no Campaign que podia gerar taxas de abertura incorretas para o Gmail devido à filtragem de eventos de rastreamento recebidos das contas do Gmail. (CAMP-46504)

* Correção de vários problemas que causavam discrepância de dados entre relatórios no Adobe Campaign Standard e relatórios no Adobe Analytics. (CAMP-47671, CAMP-47296)

* Correção de um problema que impedia o acesso aos logs do delivery após a falha da preparação. (CAMP-48296)

* Correção de um problema que podia exibir uma mensagem de erro ao ser feita uma tentativa de editar, excluir ou enviar um relatório personalizado. (CAMP-47789, CAMP-47798)

* Correção de um problema que resultava em falha nas chamadas de APIs ao criar um novo recurso personalizado e ativar a opção **Não sincronizar**. (CAMP-48014)

* Correção de um problema em que os recursos personalizados com a opção **Não sincronizar** ativada podiam fazer referência a um esquema que tinha sido reformulado ou excluído. Esse problema causava um erro durante a publicação dos recursos personalizados.

* Correção de um problema de recusa de SMS ao serem usados vários códigos curtos na mesma conta externa.

* Correção de um problema que impedia o acesso a um novo critério de alerta de entrega (&quot;o recurso que você está tentando acessar está inacessível&quot;) após a publicação do banco de dados. (CAMP-48221)

* Correção de um problema em que os logs de rastreamento estavam ausentes em algumas instâncias do Campaign com relatórios dinâmicos. Um novo [fluxo de trabalho técnico](../../administration/using/technical-workflows.md) foi adicionado para restaurar esses logs de rastreamento. (CAMP-47885)

* Correção de um problema em que nenhum dado da entrega era exibido em Relatórios dinâmicos. Os relatórios eram definidos como 0. (CAMP-47480)

* Correção de um problema que impedia o Cliente HTTP JavaScript do servidor de se conectar ao URL externo.

* Correção de um problema que redefinia uma atividade **Consulta incremental** após a alteração do nome interno do fluxo de trabalho. Isso ocorria quando um campo de data era usado como modo incremental. (CAMP-47674)

* Correção de um problema que impedia a pré-visualização da miniatura no resumo da entrega ao ser criado um email multilíngue com a integração do Adobe Experience Manager. Esse problema ocorria ao ser usado o botão **Criação de cópia de idioma** para criar as variantes de email. (CAMP-47810)

* Correção de um problema que impedia os usuários de acessar a entrega principal por meio da entrega secundária de email ou SMS. (CAMP-47986)

* Correção de um problema que podia causar consumo excessivo de CPU e memória ao serem enviadas mensagens transacionais por meio da API REST com um evento personalizado ausente. (CAMP-47147)

* Correção de um erro na API de mensagens transacionais que, ocasionalmente, impedia o envio de mensagens em tempo real.

* Correção de um problema em que os relatórios não eram recebidos após o uso da opção **Enviar relatório na programação**. (CAMP-48583, CAMP-47786)

* Correção de um problema em que os relatórios recebidos após o uso da opção **Enviar relatório agora** estavam incompletos e com dados faltando. (CAMP-48583)

* Correção de um problema no Designer de email, em que as dimensões de uma imagem eram reduzidas ao ser carregada uma imagem. (CAMP-47017)

* Correção de um problema que impedia que cada modelo do Experience Manager disponível fosse exibido ao ser criada uma entrega. (CAMP-48132)

* Correção de um erro que impedia que o link Campanha na página Resumo de uma entrega enviada de redirecionar os usuários para a campanha relacionada. (CAMP-48012)

* Correção de um problema no Designer de email em que a integração do Serviço principal de ativos continuava falhando ao ser feita a tentativa de selecionar um ativo. (CAMP-47446)

* Correção de um problema que bloqueava algumas entregas do Journey Orchestration porque o Campaign não aceitava carimbos de data e hora com um valor exato (ou seja, terminando em 00) enviados por eventos do Journey Orchestration.

## Versão 21.1 - Fevereiro de 2021 {#release-21-1---february-2021}

**Novidades**

<table> 
<thead> 
<tr> 
<th> <strong>Serviço de feedback por email</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>O EFS (Email Feedback Service, Serviço de feedback por email) é um serviço escalável que captura diretamente o feedback do MTA aprimorado, melhorando assim a precisão dos relatórios. Esse recurso está sendo lançado como um beta privado e estará progressivamente disponível para todos os clientes em versões futuras.</p>
<ul>
<li>Agora todas as categorias de feedback são capturadas, para oferecer relatórios completos e precisos.</li>
<li>O cálculo do indicador <b>Entregue</b> agora se baseia no feedback em tempo real do MTA aprimorado para melhorar a precisão e a reatividade.</li>
<li>O EFS soluciona o problema de atrasos de relatórios síncronos de devoluções temporárias.</li>
</ul>
<p>Para obter mais informações consulte a <a href="../../sending/using/confirming-the-send.md">documentação detalhada</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Melhorias na integração do Adobe Experience Manager</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>A integração do Campaign com o Adobe Experience Manager foi aprimorada: agora você pode importar conteúdo multilíngue com mais facilidade do Adobe Experience Manager. <p>
<p>O Adobe Campaign Standard agora detecta automaticamente as variantes de idioma do conteúdo do Adobe Experience Manager e permite a importação e a criação de variantes em massa, simplificando significativamente o número de etapas que um profissional precisa seguir para criar uma campanha multilíngue com base no conteúdo do Adobe Experience Manager.</p>
<p>Para obter mais informações consulte a <a href="../../integrating/using/creating-multilingual-email-aem.md">documentação detalhada</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<!--
<table> 
<thead> 
<tr> 
<th> <strong>Unified Experience Cloud interface</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Adobe Campaign header bar has been changed to unify and improve your experience across all Experience Cloud products and services. These changes are designed to make your life easier, including:</p>
<ul>
<li>Easier switching between your organizations or to a different application.</li>
<li>Improved User Help – Bringing the Experience League into the product, search results also include results from community forums and more video content, giving you easier access to more content to help get the most out of the application. We've also added a feedback mechanism right in the Help menu, making it easier to report issues or share your ideas.</li>
<li>Improved Notifications – Notifications drop-down now has two tabs: one for your own product notifications, and one for more global product announcements.</li>
</ul>
<p>For more information refer to the <a href="../../start/using/interface-description.md#top-bar">detailed documentation</a>.
</p>
<p>NOTE: This change will be progressively rolled out to all customer environments between Feb 10 and March 1st.
</p>
</td> 
</tr> 
</tbody> 
</table>
-->

**Aprimoramentos**

* **A integração do Microsoft Dynamics 365** foi aperfeiçoada com um aplicativo de integração de autoatendimento dedicado e um processo de implementação aprimorado. [Saiba mais](../../integrating/using/d365-acs-get-started.md)

* Foi feito um aprimoramento para facilitar a solução de problemas ao serem encontrados problemas no processo de mensagens transacionais. Os administradores técnicos da Adobe agora podem usar o rastreamento em qualquer processo sem reiniciá-lo.

* A lista **Perfis** agora permite que você pesquise por registros com base em um destes campos: email, nome, sobrenome ou campos personalizados que foram adicionados à filtragem avançada ao estender o recurso de perfil. Esse recurso também está disponível em APIs do Campaign Standard usando o parâmetro filterType. [Saiba mais](../../audiences/using/integrated-customer-profile.md)

* Um parâmetro foi ajustado para o número de containers que executam o processo de pooling do banco de dados de mensagens transacionais. Isso permite que a carga seja distribuída uniformemente em todos os containers usados e alcance o desempenho ideal.

* Uma nova função **GetOption** agora está disponível em atividades usando variáveis de evento depois de chamar um fluxo de trabalho com parâmetros externos. Permite retornar o valor de uma função especificada. [Saiba mais](../../automating/using/customizing-workflow-external-parameters.md)

* Uma nova opção permite que o Campaign Standard **verifique a memória física** disponível no sistema antes de iniciar um fluxo de trabalho. Se a quantidade de memória for muito baixa, a execução do workflow será atrasada até que a memória do sistema atinja esse limite. Isso evita uma maior degradação do desempenho e reduz o risco de uma interrupção. O workflow será retomado automaticamente quando a carga no servidor diminuir e a memória aumentar. Observe que essa opção é somente leitura e não pode ser modificada. [Saiba mais](../../automating/using/best-practices-workflows.md#execution)

* No Adobe Campaign Standard, está disponível um novo processo que permite migrar mais facilmente do aplicativo para dispositivos móveis herdado SDK v4 para o **SDK móvel da Adobe Experience Platform**. Consulte [esta página](../../administration/using/sdkv4-migration.md).

**Outras alterações**

* Alteração de um erro para um aviso durante a preparação da mensagem, quando o limite de 100 downloads de conteúdo por hora variável é atingido. Um aviso agora é exibido quando o limite é atingido, o que permite continuar com a entrega.

* Ao enriquecer um conteúdo de mensagem transacional, os links não são mais recuperados ao buscar dados da tabela do Perfil, o que reduz a latência durante a preparação da mensagem e evita dados vazios do perfil devido a uma relação incorreta definida com a tabela do perfil.

* A configuração técnica da instância foi otimizada para garantir a estabilidade. (CAMP-45681)

* O gerenciamento de sessões foi aprimorado para otimizar a memória. (CAMP-45901, CAMP-46767)

* A atividade **Transferir arquivo** agora gera uma variável adicional (filesCount) que contém o número de arquivos carregados ou baixados. (CAMP-45842) [Saiba mais](../../automating/using/transfer-file.md#output-variables)

* O conector SMS agora pode enviar vários parâmetros opcionais com cada mensagem. [Saiba mais](../../administration/using/sms-protocol.md)

* Os usuários com a função DATAMODEL agora podem publicar extensões de log de entrega. (CAMP-46604)

* A mensagem de erro exibida ao tentar publicar um recurso que direciona um recurso personalizado que não existe mais foi esclarecida para melhor compreensão. (CAMP-46893)

* Os seguintes idiomas foram adicionados à lista **Idioma preferencial**: Indonésio - Indonésia (in-id), Inglês - Suécia (en-se), Inglês - Ásia Pacífico (en-ap), Inglês - Japão (en-jp), Espanhol - América Latina (es-la). (CAMP-46351)

* Ao testar uma página de destino, o seletor de perfis agora usará o recurso profilBase em vez do perfil para evitar atingir o tempo limite.

* O formato de log SMPP foi aprimorado.

* Parâmetros opcionais para as funções cryptString e decryptString JS foram adicionados para corresponder às APIs do Adobe Campaign Classic.

* Mensagens de aviso ou erro aprimoradas nos logs de preparação de entrega.

* Logs de erros aprimorados ao tentar se conectar ao Adobe Identity Management Service (IMS).

* Agora você pode filtrar ainda mais as dimensões **Entrega** e **Campanha** usando a barra de pesquisa nos relatórios dinâmicos.

* A data de validade da mensagem SMS transacional agora pode ser definida pelo valor definido para o parâmetro de expiração na API de Mensagens transacionais. (CAMP-36600)

* Nos relatórios dinâmicos, o relatório integrado **Resumo da entrega** mostrava dados incorretos para a métrica de taxa não assinada. Uma nova métrica chamada **Unsubscription única** foi adicionada para corrigir isso. (CAMP-46445)

**Correções**

* Correção de um problema que fazia com que as entregas fossem executadas muito lentamente devido a determinados processos. Isso acontecia porque unidades incorretas estavam definidas para vários parâmetros (milissegundos em vez de segundos, por exemplo).

* Correção de um problema quando o SDK móvel enviava uma solicitação de rastreamento aberta com base na condição de que deliveryId/MessageID não fosse nulo. Isso resultava em erros 404 para entregas com rastreamento desativado. Uma variável adicional (acsDeliveryTracking) com informações sobre o status de rastreamento da entrega agora é enviada junto com o conteúdo. Essa variável pode ter dois valores ativados ou desativados dependendo do status de rastreamento definido. [Saiba mais](../../administration/using/push-tracking.md).

* Correção de um problema em workflows que ocorria ao copiar e colar uma atividade **Desduplicação** executada uma vez e que aproveitava um recurso temporário. Depois de duplicado, o recurso de atividade era automaticamente definido como vazio, resultando em problemas em outras atividades do workflow. Depois de colado, o recurso de atividade permanecerá o mesmo, para que o erro seja acionado o mais rápido possível, em vez de posteriormente, no workflow. (CAMP-46903)

* Correção de problemas que faziam com que a análise de entrega falhasse ao enviar perfis de direcionamento de notificação push transacional, introduzindo um novo [target mapping](../../administration/using/target-mappings-in-campaign.md): **Perfil — Evento em tempo real para push** (*mapRtEventAppSubRcp*). Os logs de entrega, exclusão e rastreamento para [notificações por push transacionais baseadas em perfil](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile) agora serão armazenado nas tabelas *broadLogAppSubRcp*, *excludeLogAppSubRcp* e *trackingLogAppSubRcp*.

   >[!IMPORTANT]
   >
   >Devido a essa alteração, se você está usando uma notificação transacional por push baseada em perfil (criada antes da atualização para o Adobe Campaign 21.1), é recomendável atualizar o target mapping para o novo e publicar a mensagem novamente. Veja as etapas detalhadas [aqui](../../channels/using/transactional-push-notifications.md#change-target-mapping). Usar o target mapping anterior **Perfil — Evento em tempo real** (*mapRtEventRcp*) pode resultar em tempos de preparação de entrega mais longos e diminuição de desempenho.

* Correção de um problema que impedia a execução de relatórios do delivery quando 5000 linhas eram exibidas.
* Correção de um problema com o teste AB que impedia que o conteúdo da variante B fosse atualizado após a modificação do template do delivery. (CAMP-45235)
* Correção de um problema que causava a interrupção do processo de mensagens transacionais, impedindo o envio de mensagens.
* Correção de um problema que resultava em problemas de navegação após clicar em um link interno (por exemplo, ao acessar a entrega pai de uma tela de resumo de prova).
* Correção de um problema que impedia que todos os modelos de conteúdo do Experience Manager disponíveis fossem exibidos ao criar uma entrega. (CAMP-45990)
* Correção de um problema em workflows que impedia a exibição de mensagens de falha nos logs do delivery após a adição da coluna **Motivo** à guia de dados adicional. (CAMP-45139)
* Correção de um problema que ocorria quando duas chamadas de assinatura do aplicativo tinham a mesma ID da Marketing Cloud (erro &quot;o valor de chave duplicado viola a restrição única&quot;).
* Correção de um problema que resultava em problemas de lentidão ao arrastar e soltar atividades em um fluxo de trabalho contendo uma grande quantidade de atividades **Consulta** e **Ler público**. (CAMP-44511)
* Correção de um erro que ocorria ao final da preparação da mensagem transacional, impedindo que as informações de redirecionamento fossem carregadas nos servidores de rastreamento.
* Correção de um problema que podia exibir mensagens de erro ao tentar abrir modelos de importação ou processos de importação anteriores após a personalização do recurso de fluxo de trabalho. (CAMP-46183)
* Correção de um problema que impedia a execução de uma atividade **Ler público** se ela estivesse configurada com um nome de público dinâmico. (CAMP-46047)
* Correção de um problema que impedia a exibição do botão **Exportar lista**
* Correção de um problema que resultava na falha do fluxo de trabalho **Relatórios agregados**. (CAMP-45979)
* Correção de um problema ao criar um recurso personalizado com uma chave composta personalizada (conteúdo dinâmico de texto/data).
* Correção de um problema que impedia a exibição dos dados de transição de consulta. (CAMP-45669)
* Correção de problemas de consumo de memória relacionados à publicação de recursos personalizados.
* Correção de um problema que ocorria ao configurar uma entrega para ser enviada em uma data específica. Se a entrega tivesse sido definida para ser enviada imediatamente depois de confirmada, a preparação da entrega falhava e a data inicialmente especificada ainda era levada em conta. (CAMP-44107)
* Correção de um problema que impedia a abertura de modelos transacionais. (CAMP-47181)
* Correção de um problema no processo de publicação de mensagens transacionais que podia resultar em tipologias duplicadas e regras de tipologia com nomes que excediam o tamanho de sequência permitido. (CAMP-47104)
* Correção de um problema na atividade **API externa** que ocorria quando um parâmetro de entrada retornava um registro que não existia. (CAMP-47023)
* Correção de um problema que impedia a reconexão do conector SMPP.
* Correção de um problema que ocorria na atividade **Transferência de arquivo** ao baixar um arquivo contendo um ponto em seu nome. Os caracteres após o ponto eram considerados como a extensão do arquivo. (CAMP-46624)
* Correção de um problema que impedia a execução do pool do banco de dados, o que fazia com que mensagens transacionais ficassem presas na fila do roteador.
* Correção de um erro que não impedia o envio de logs do delivery cancelados.
* Correção de um problema que causava a falha de um fluxo de trabalho ao usar uma atividade **AND-join**. A atividade alterava automaticamente o conjunto Principal para a última transição conectada a ela, mesmo se mostrasse visualmente a primeira transição conectada. (CAMP-46900)
* Correção de um problema que fazia com que endereços colocados em quarentena com êxito tivessem seu status definido incorretamente como Válido, removendo-os da quarentena.
* Correção de um problema que impedia que campos personalizados fossem exibidos se contivessem caracteres especiais. (CAMP-46805)
* Correção de um problema que impedia a exibição de uma visualização detalhada específica para um perfil. Isso ocorria se o recurso de perfil tivesse sido estendido com campos personalizados com a opção **Adicionar uma seção de campos personalizados** ativada.
* Correção de um problema que retornava um código de erro 500 ao enviar eventos transacionais. (CAMP-46811)
* Correção de um problema que poderia impedir o recebimento de relatórios agendados por email. (CAMP-46891)
* Correção de um problema que ocorria ao vincular um recurso personalizado ao recurso do perfil com um link simples de cardinalidade 1. Ao acessar um perfil com o campo de recurso personalizado vazio, agora uma mensagem de erro é exibida em vez de uma lista vazia.
* Correção de um problema ao usar substituição de perfil em um fluxo de trabalho em que a página não carregava os perfis de entrega ao selecionar o perfil a ser substituído. (CAMP-46522)
* Correção de uma regressão em que o fluxo de trabalho técnico **Limpeza de banco de dados** tentava eliminar as tabelas de trabalho de entrega expiradas, resultando nos seguintes erros: (CAMP-46536)

```
   PGS-220000 PostgreSQL error: ERROR: table ""wkdlv_24439460_data"" does not exist and WDB-200001 SQL statement 'DROP TABLE wkdlv_24448131_data' could not be executed.
```

* Correção do seguinte erro que ocorria em alguns casos ao usar o filtro personalizado em recursos personalizados: (CAMP-46509)

```
   The 'profile/xxxx' field used in the filter 'xxxxx' does not exist in custom resource 'xxx'
```

* Correção de um problema em que a **Preparação da notificação por push** demorava muito para ser concluída. Isso era causado pela falta de um índice nas tabelas de trabalho transitórias.
* Correção de um erro que podia ocorrer ao ser usada a opção **Dimensão para reconciliar** em uma atividade **Reconciliação** em um fluxo de trabalho se uma relação já estivesse definida entre um recurso personalizado e um recurso de perfil.
* Correção de um problema que ocorria ao adicionar links por meio de uma atividade de **Reconciliação** ou **Enriquecimento**. Os links selecionados não eram exibidos na transição de saída.
* Correção de um problema ao usar uma atividade **Segmentação** com entregas recorrentes em um fluxo de trabalho que fazia com que a entrega fosse enviada para o público errado. (CAMP-46275, CAMP-46470)
* Correção de um erro em que a publicação de recursos personalizados falhava ao tentar estender o recurso de Perfil para criar dimensões de perfil personalizadas para relatórios dinâmicos. (CAMP-46266)
* Correção de um erro que ocorria ao adicionar um link a uma tabela de importação de arquivo. Depois de adicionar uma atividade **Enriquecimento** à atividade **Importação de arquivos**, o link configurado anteriormente desaparecia. (CAMP-46557)
* Correção de um problema ao usar recursos personalizados vinculados aos dados do Perfil em que a ordem de exibição na tela de configuração **Detalhes** era alterada ao salvar. (CAMP-46312)
* Correção de um problema que impedia a exibição de dados em relatórios dinâmicos devido a entregas com base em um mapeamento de entrega personalizado.
* Correção de um erro que podia impedir a seleção de uma coleção com um público alvo de recurso incorreto em uma atividade de fluxo de trabalho **Consulta**.
* Correção de um problema que fazia com que o processo InMail validasse as devoluções definitivas incorretamente.
* Correção de um erro que ocorria ao abrir uma tela de perfil devido a um erro de link.
* Correção de um problema que impedia a exclusão de dados do GDPR do fluxo de trabalho de limpeza.
* Correção de um erro que ocorria quando a configuração de programação era atualizada manualmente com o teclado nos parâmetros de programação da entrega de email.
* Correção de um problema que podia impedir a edição de um perfil devido a parâmetros incorretos na entidade organizacional.
* Correção de um problema que deixava o campo de extensão **Serviço** vazio e impossível de ser definido nas **Propriedades de email**, mesmo que estivesse definido no template do delivery.
* Correção de um problema que podia fazer as provas demorarem mais para serem processadas. (CAMP-45048)
* Correção de um problema que impedia a classificação de colunas em uma tela de visão geral do perfil.
* Correção de um problema de geração de miniaturas que podia ocorrer no Azure em variantes de email contendo caracteres chineses. (CAMP-47152)
* Correção de uma regressão introduzida no Campaign 20.4 que podia gerar taxas de abertura incorretas para o Gmail devido à filtragem de eventos de rastreamento recebidos das contas do Gmail. (CAMP-46504)
* Correção de um problema que impedia a importação de conteúdo HTML em um template de mensagem transacional. (CAMP-47318)
* Correção de um problema que podia retardar a exibição das renderizações no **Relatório de renderização de email**. (CAMP-46226)
* Correção de um problema que podia impedir a publicação de recursos personalizados configurados com um elemento do tipo Lista na definição da tela. (CAMP-47217)
* Correção de um problema no Email Designer que impedia que os divisores de linha fossem renderizados corretamente no **Microsoft Outlook** quando colocados na parte superior do conteúdo de email. (CAMP-46294)
* Correção de um problema que causava o travamento da reconciliação de KPIs com o fluxo de trabalho técnico do **Adobe Analytics**. (CAMP-46576)
* Correção de um problema no **Email Designer** que impedia a exibição automática de fragmentos em caixas de pesquisa ao inserir blocos de conteúdo. (CAMP-44205)
* Correção de um problema no **Email Designer** que fazia com que caracteres indesejados fossem exibidos em emails enviados ao usar emojis em fragmentos. (CAMP-46621)
* Correção da regressão introduzida na versão 20.4 no **Email Designer** que afetava o componente Divider, o que resultava em mais alturas de linha e distorções de imagem no conteúdo. (CAMP-46663)
* Correção de um problema que fazia com que os botões predefinidos permanecessem centralizados quando a mensagem era enviada para uma caixa de correio do Outlook, mesmo que esses botões estivessem alinhados à direita ou à esquerda no **Email Designer**. (CAMP-46466)
* Correção de um problema que impedia que a lista de perfis de teste fosse atualizada ao pesquisar perfis na pré-visualização do **Email Designer**. (CAMP-45265)
* Correção de um problema que impedia que perfis de teste personalizados fossem exibidos na lista ao pesquisar perfis na pré-visualização do **Email Designer**. (CAMP-45589)
* Correção de um problema que fazia com que datas não correspondentes fossem exibidas ao gerar gráficos de tendência do **Relatório de resumo da entrega**. (CAMP-45521)
