---
title: Versão mais recente
description: Esta página detalha o conteúdo da versão mais recente do Campaign Standard
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: vignes
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 97760e8b5fe0eb4905dcae69e8bbbefa837a461f
workflow-type: tm+mt
source-wordcount: '2442'
ht-degree: 4%

---


# Versão mais recente{#latest-release}

[Planejamento de versão](../../rn/using/release-planning.md) | [Versões do painel de controle do Campaign](https://docs.adobe.com/content/help/pt-BR/control-panel/using/release-notes.html) | [Atualizações da documentação](../../rn/using/documentation-updates.md) | [Notas de versão anteriores](../../rn/using/release-notes-2020.md) | [Recursos descontinuados](../../rn/using/deprecated-features.md)

## Versão 20.4 - Outubro de 2020 {#release-20-4---october-2020}

**Novidades**

<table> 
<thead> 
<tr> 
<th> <strong>grupos de controle</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Agora você pode usar <strong>Grupos de controle</strong> para medir o impacto de suas campanhas excluindo uma parte de suas audiências. Poderá então comparar o comportamento da população do público alvo que recebeu a mensagem com o comportamento dos contatos que não foram visados. Com base nos registros de envio, você também pode público alvo um grupo de controle em futuras campanhas.
</p>
<p>For more information refer to the <a href="../../sending/using/control-group.md">detailed documentation</a> and <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html">how-to video</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>API externa - Suporte a OAuth</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>A Adobe Campaign agora oferece suporte ao OAuth para autenticação na atividade de fluxo de trabalho da API <strong></strong> externa. Esse novo recurso abre a capacidade de essa atividade se comunicar com sistemas que exigem suporte a OAuth.
</p>
<p>For more information refer to the <a href="../../automating/using/external-api.md">detailed documentation</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Integração da jornada AI</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Temos o prazer de anunciar a Journey AI para todos os clientes da Adobe Campaign Standard.</p>
  <p>O Journey AI usa o Advanced Machine Learning (ML) para permitir que as empresas otimizem o design e o delivery das jornadas do cliente, predizendo a preferência de envolvimento de cada indivíduo.</p>
  <P>A jornada AI consiste em dois elementos ML:</p>
<ul> 
     <li> <strong>Pontuação</strong> preditiva de envolvimento - identifica de forma inteligente o nível de envolvimento preferencial dos clientes para um melhor público alvo e personaliza as mensagens para aumentar as conversões e a retenção. Assista ao vídeo <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html">de instruções</a>.</li> 
     <li> <strong>Otimização</strong> preditiva do tempo de envio - prevê o melhor momento para enviar emails para cada indivíduo em uma campanha para maximizar as taxas de envolvimento e melhorar o ROI da campanha de email. Assista ao vídeo <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html">de instruções</a>.</li>
    </ul>
  <p>Se quiser saber como começar a usar a Journey AI, reveja a documentação <a href="../../sending/using/predictive.md"></a> detalhada e entre em contato com o Executivo de contas. Observe que, embora a Journey AI esteja disponível gratuitamente para os clientes existentes da Campanha, há um custo de implementação de aproximadamente 50 horas.</p>
    </td> 
</tr> 
</tbody> 
</table>

**Aprimoramentos**

* **Gerenciamento** de privacidade: o campo **CCPA Opt-Out** , que estava disponível por meio da interface de Campanha e da API, agora também é suportado pelo Privacy Core Service. Esse campo permite que os usuários do Adobe Campaign rastreiem se um consumidor optou pela venda de Informações pessoais. [Saiba mais](https://helpx.adobe.com/content/help/br/campaign/kb/acs-privacy.html#ccpa)
* **Melhorias** na execução do fluxo de trabalho (beta): no contexto de uma iniciativa global em torno dos workflows, foram desenvolvidas algumas melhorias importantes para estabilizar o gerenciamento da memória, reduzir a latência e otimizar a memória consumida pelos workflows durante a execução. Esses aprimoramentos estão atualmente na versão beta e só estão disponíveis para um conjunto de clientes. A disponibilidade geral está prevista para o início de 2021.
* Para melhorar a segurança, o Campaign agora usa um mecanismo **de** assinatura para rastrear links em emails.
* A configuração do aplicativo móvel foi aprimorada com mensagens **de erro** mais claras ao carregar certificados do iOS ou chaves do Android.
* Um **novo mapeamento** de delivery (mapRtEventAppSubRcp) agora está disponível para perfis de definição de metas de mensagens de push transacionais. O delivery, a exclusão e os logs de rastreamento desses delivery agora estarão disponíveis nas tabelas wideLogAppSubRcp, excludeLogAppSubRcp e trackingLogAppSubRcp. Isso resolve um problema que causava a falha da análise do delivery ao enviar uma mensagem de push transacional usando a dimensão do público alvo do **Perfil** .
* **O gerenciamento** de erros de SMS foi aprimorado para evitar que muitos perfis sejam adicionados à lista da quarentena. Por padrão, os erros de SMS agora são configurados como erros de software em vez de erros de hardware. Consulte [esta página](https://helpx.adobe.com/br/campaign/kb/sms-connector-protocol-and-settings.html).

**Aprimoramentos do Email Designer**

* Melhoramos a experiência do usuário no Email Designer com a **nova ajuda** contextual dinâmica que conecta totalmente a interface do usuário e a documentação, fornecendo um acesso fácil ao conteúdo de ajuda mais recente.
* Correção de um problema que removia quebras de linha em uma mensagem ao editar sua versão de texto. (CAMP-44483)
* Correção de um problema que impedia que a versão em texto simples de um modelo HTML fosse gerada e sincronizada automaticamente. (CAMP-44195)
* Correção de um problema que ocorria ao redimensionar imagens. Depois que as mensagens foram enviadas, as imagens não eram exibidas corretamente no Microsoft Outlook. (CAMP-44656)
* Correção de um problema que ocorria ao inserir um botão e definir sua largura como &quot;auto&quot;. Depois que a mensagem foi enviada, o conteúdo do botão não era exibido totalmente. (CAMP-44560)
* Correção de um problema que ocorria ao carregar conteúdo de um arquivo HTML anexado. Depois que a mensagem foi enviada para um endereço Gmail, o CSS não foi aplicado, causando um problema de renderização. (CAMP-44085)
* Correção de um problema que impedia que fragmentos de conteúdo usados anteriormente em uma mensagem fossem atualizados quando fossem modificados diretamente no modelo de conteúdo. (CAMP-43973)
* Correção de um problema com a barra de pesquisa **Fragmentos** . Ao pesquisar por um fragmento existente, a barra de pesquisa não apresentou nenhum resultado. (CAMP-44223)
* Correção de um problema com as barras de pesquisa Blocos **de** conteúdo e **Fragmentos** . Ao usar uma das barras de pesquisa, os resultados só serão exibidos se você clicar em **Mostrar mais resultados...**. (CAMP-44205)
* Correção de um problema que impedia que o preenchimento entre texto e imagens fosse aplicado no Microsoft Outlook. (CAMP-45370)
* Correção de um problema ao duplicar um fragmento. Após duplicar o fragmento, havia linhas HTML ausentes no fragmento original. (CAMP-45207)
* Corrigido um erro que causava problemas de renderização no Microsoft Outlook. (CAMP-44749)
* Correção de um erro que ocorria ao modificar o preenchimento do Componente **de** estrutura em um template do delivery. As tags CSS não carregavam as alterações feitas no preenchimento que causavam um problema de renderização. (CAMP-45381)
* Correção de um problema ao carregar uma imagem. A altura da imagem foi automaticamente definida como 0, causando um problema de renderização. (CAMP-45366)

**Outras alterações**

* Os mecanismos de repetição foram adicionados em caso de erro ao tentar importar uma audiência Experience Platform usando uma atividade **Ler audiência** . (CAMP-43947, CAMP-43366)
* As unidades organizacionais agora são automaticamente definidas para corresponder à unidade organizacional do usuário que está criando o perfil ou a entidade. As unidades organizacionais não podem mais ser removidas e deixadas vazias.
* Ao publicar um recurso personalizado, um pop-up de confirmação é exibido depois da preparação.
* A mensagem pop-up que aparece quando um recurso personalizado falha foi melhorada para maior clareza.
* O editor de expressões em workflows foi aprimorado para evitar erros de execução. [Novas funções](../../automating/using/customizing-workflow-external-parameters.md) estão disponíveis: eles podem ser usados em todas as atividades que permitem usar variáveis de evento depois de chamar um fluxo de trabalho com parâmetros externos. Além disso, uma dica de ferramenta agora é exibida no editor de expressões com a descrição da função.
* [Novos filtros](../../administration/using/configuring-transactional-messaging.md#searching-transactional-events) foram adicionados à lista de eventos transacionais. Eles permitem que você filtre as configurações do evento de acordo com seu status, bem como a última vez que um evento foi recebido.
* Os registros exibidos ao exportar pacotes foram tornados mais específicos e detalhados sobre os erros encontrados em caso de falha.
* Depois de enviar uma mensagem, agora é possível pesquisar, filtrar e exportar a lista de URLs [](../../sending/using/tracking-messages.md)rastreados.
* A [sincronização automática entre o Launch e a Campanha](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow) agora está ativada por padrão no GA.
* O tamanho dos pacotes de exportação de fluxo de trabalho foi otimizado com a remoção da exportação de prova de envio.
* Uma nova mensagem foi adicionada para exibir o tamanho do arquivo baixado na atividade de transferência **de** arquivo.
* Mensagens de erro para tokens de sessão inválidos foram aprimoradas.
* Um novo mecanismo agora impede que eventos de rastreamento de proxies sejam adicionados a logs de rastreamento e relatórios.
* Uma nova mensagem de aviso foi adicionada para ajudar a depurar atividades de gestão de dados conectadas a uma atividade de delivery.
* As etiquetas na área de trabalho do relatórios foram aprimoradas.
* Uma nova etapa de validação foi adicionada para impedir a exclusão de objetos técnicos em mensagens transacionais.
* Um novo filtro sobre o status do delivery foi adicionado na guia **Execution lista** de um mensagen transacional para melhorar a solução de problemas.
* Para melhorar o desempenho e otimizar o tempo de execução, os índices não utilizados foram removidos, com base nas estatísticas de uso das tabelas identificadas na análise preliminar para mais de 350 clientes. As tabelas impactadas são: nmsaddressStatus, nmscampaign, nmsdelivery, nmslandingpage, nmsprogram, nmscustomer, nmsseedmember, nmsservice, nmssubhistorcp, nmsaudience, xtkworkflow

**Correções**

* Correção de um problema que impedia o uso de um link de destino para notificações por push ou mensagens no aplicativo quando o rastreamento era ativado.
* Correção de um problema em que a alta prioridade em mensagens transacionais não era respeitada no caso de delivery significativos em massa.
* Correção de um problema que impedia a atribuição de marcas a um email transacional. Várias mensagens de erro podem ser exibidas durante a etapa de publicação. (CAMP-44988)
* Correção de um problema na interface do usuário do fluxo de trabalho que podia impedir que as informações fossem salvas em campos que solicitavam valores numéricos. (CAMP-44025)
* Correção de um problema que poderia exibir uma mensagem de erro ao usar uma atividade **de teste** em um fluxo de trabalho de template de importação. (CAMP-42910)
* Correção de um problema que ocorria ao usar uma atividade **Ler audiência** contendo um campo do tipo lista discriminada e conectado às atividades **União** ou **Enriquecimento** . (CAMP-42795)
* Correção de um problema nos relatórios Dinâmicos ao usar os segmentos predefinidos para filtrar dados nos relatórios. (CAMP-42627)
* Correção de um problema que impedia a configuração de uma atividade de **Scheduler** como 12 AM. (CAMP-42674)
* Correção de um problema que poderia interromper o envio de mensagens SMS quando a conexão SMPP estava instável. (CAMP-42789)
* Correção de um problema que impedia a exibição do botão **Parar preparação** após atualizar a página. (CAMP-42721)
* Correção de um problema que impedia a exibição de porcentagens de relatórios de cliques ativos ao importar conteúdo de um URL. (CAMP-44468)
* Correção de um problema que poderia exibir um erro de tempo limite ao selecionar um perfil a ser usado no contexto da substituição do perfil. (CAMP-44746)
* Correção de um problema que impedia que instâncias funcionassem após a implantação de recursos personalizados contendo definições de links incorretas. (CAMP-44406)
* Correção de um problema que criava entidades vinculadas vazias (tipologias, marcas etc.) após copiar e colar um delivery em um template de campanha. (CAMP-44765)
* Correção de um problema que impedia o envio de provas devido a um tratamento incorreto de tabelas de preparação de delivery em caso de falha de um banco de dados ou uma simples reinicialização do banco de dados no Azure.
* Correção de um problema que impedia a exclusão de links com conteúdo Experience Manager em um delivery configurado com conteúdo multilíngue. (CAMP-44029)
* Correção de um problema em relatórios dinâmicos que podia exibir uma mensagem de erro ao tentar filtrar dimensões.  (CAMP-43097)
* Correção de um problema que podia exibir uma tela em branco ao tentar acessar perfis em uma instância configurada com recursos personalizados que continham definições de links específicas. (CAMP-41009)
* Correção de um problema em workflows que ocorria ao usar uma atividade de **Enriquecimento** com duas atividades de entrada com ambos os recursos de público alvo vinculados. (CAMP-42133)
* Correção de um problema que fazia com que workflows de importação fossem repetidos ao usar uma atividade de transferência **de** arquivo. (CAMP-43754)
* Correção de um problema que fazia com que duplicados não fossem considerados ao criar um perfil com registros exportados. (CAMP-45031)
* Correção de um problema que causava a discrepância de dados entre relatórios no Adobe Campaign e relatórios exportados em arquivos PDF. (CAMP-43010)
* Correção de um erro que causava a falha do fluxo de trabalho do delivery de mala direta ao usar campos de dados existentes em funções. (CAMP-42737)
* Correção de um problema ao importar pacotes, incluindo eventos transacionais e modelos de mensagem. O processo de importação parou em 5%. (CAMP-42544)
* Correção de um problema que causava um erro (TypeError não detectado) após modificar a atividade do **Enriquecimento** e adicionar dados adicionais em um fluxo de trabalho. (CAMP-41877)
* Correção de um erro que impedia a exclusão do fluxo de trabalho. Os registros tinham que ser removidos para excluir o fluxo de trabalho. (CAMP-44144)
* Corrigido um erro ao criar uma landing page com código HTML. As caixas de seleção obrigatórias não eram reconhecidas na Campanha e não estavam disponíveis na landing page publicada. (CAMP-44181)
* Correção de um problema que resultava no loop de workflows ao usar a atividade **Wait** . (CAMP-43981)
* Correção de um problema ao enviar mensagens transacionais que resultava no direcionamento de vários endereços de email várias vezes em um mesmo delivery. (CAMP-44202)
* Correção de um erro ao usar substituição de perfil com personalização targetData. (CAMP-44996)
* Correção de um problema que causava a falha da pré-visualização do delivery ao exportar um template do delivery em um pacote. (CAMP-44084)
* Correção de um problema que impedia o envio de provas para perfis de teste ao usar target mapping personalizados. (CAMP-43701)
* Correção de um erro que ocorria em workflows ao usar a atividade **Ler Audiência** e direcionar uma audiência configurada com um targeting dimension diferente de **Perfil**.  (CAMP-41885)
* Correção de um problema que resultava em erros quando o fluxo de trabalho técnico **updateEventsStatus** demorava muito para recuperar o histórico de eventos (quando o fluxo de trabalho era parado). O campo de agregação &quot;sumQueueTime&quot; não utilizado foi removido do fluxo de trabalho para resolver o problema. (CAMP-43920)
* Correção de um problema de memória ao implantar recursos personalizados. (CAMP-42909)
* Correção de um problema nas mensagens transacionais quando os atributos estavam ausentes nas coleções. Agora, todos os atributos ausentes são definidos com um valor padrão e incluídos na carga. (CAMP-42882)
* Correção de um problema que poderia afetar o desempenho ao consultar logs do delivery de eventos em tempo real. (CAMP-42759)
* Correção de um erro que ocorria ao usar extensões de arquivo em maiúsculas com ativos compartilhados. (CAMP-44159)
* Correção de um problema que exibia uma mensagem de erro ao testar a conexão com uma conta externa antes de ela ser criada. O botão **Testar conexão** agora é exibido somente depois que a conta externa é criada.
* Correção de um problema que deixava mensagens pendentes após o MTA aprimorado ser reiniciado em instâncias configuradas com o compartilhamento.
* Correção de um problema que resultava na incompatibilidade da contagem de perfis ativos com o número efetivo de delivery enviados.
* Correção de um problema que resultava em latência ao procurar recursos no editor de query em um fluxo de trabalho.
* Correção de um problema ao selecionar **Especificar os campos a serem considerados na opção de pesquisa** de texto em um recurso personalizado. Se a lista de campo ficou vazia, a publicação de recursos personalizados falhou.
* Correção de um problema de desempenho ao exibir a visão geral dos recursos personalizados com um grande volume de dados.
* Correção de um problema que impedia a importação de um delivery usando substituições de perfil.
* Correção de um problema ao usar substituição de perfil que impedia o envio imediato de provas se o delivery fosse programado.
* Correção de um problema que ocorria ao carregar uma chave do Android para um aplicativo móvel. A mensagem que apareceu depois de carregar a chave com êxito exibiu o valor da chave anterior.
* Correção de um problema que impedia a criação de perfis de teste a partir de mensagens transacionais após a criação de uma configuração de evento com uma coleção sem atributo.
* Correção de um problema que poderia impedir a publicação de recursos personalizados após a criação de um novo filtro usando uma agregação.
* Correção de um problema que causava uma taxa de abertura de rastreamento incorreta para recipient Gmail causados pelo proxy de imagem Gmail.
* Correção de um problema que causava erros de falta de memória ao importar um pacote.
* Correção de um problema que causava a falha da ação de desvinculação de Experience Manager quando o conteúdo de Experience Manager incluía um caminho com um caractere &quot;%20&quot;.
* Correção de um erro nos rótulos ao duplicar atividades de fluxo de trabalho.
* Correção de um problema com o seletor de mensagens transacionais em uma landing page quando a opção de mensagem **de envio de** Start era selecionada.
* Correção de um problema com mensagens transacionais ou delivery recorrentes que impedia que o status do delivery fosse inicializado com o valor padrão correto. Os registros de erros também foram aprimorados.
* Correção de um problema ao estender a **Subscrição para um schema de aplicativo** (appSubscriptionRcp) com um link de perfil usando um campo personalizado. O índice não foi criado automaticamente, o que pode afetar o tempo de envio de push. (CAMP-41120)

