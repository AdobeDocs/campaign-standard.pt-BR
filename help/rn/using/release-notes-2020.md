---
solution: Campaign Standard
product: campaign
title: Notas de versão 2020
description: Essa página lista todas as versões 2020 do Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Visão geral
role: Profissional
level: Iniciante
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '5327'
ht-degree: 99%

---


# Notas de versão 2020{#release-notes-2020}

[Planejamento de versão](https://helpx.adobe.com/br/campaign/kb/acs-release-planning.html) | [Versões do painel de controle do Campaign](https://docs.adobe.com/content/help/pt-BR/control-panel/using/release-notes.html) | [Atualizações da documentação](../../rn/using/documentation-updates.md) | [Notas de versão anteriores](../../rn/using/release-notes-2019.md) | [Recursos descontinuados](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=pt-BR#release-notes)

![](assets/do-not-localize/cp-icon.png) **Nova versão de junho do Painel de controle do Campaign** com monitoramento de perfis ativos, auditoria de entregabilidade de subdomínio e gerenciamento de chaves GPG. [Saiba mais](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html).

![](assets/do-not-localize/cp-icon.png) **Nova versão de outubro do Painel de controle do Campaign** com configuração de domínio usando CNAMEs e novos recursos de monitoramento de banco de dados. [Saiba mais](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html).

## Versão 20.4 - Outubro de 2020 {#release-20-4---october-2020}

**Novidades**

<table> 
<thead> 
<tr> 
<th> <strong>Grupos de controle</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Agora você pode usar <strong>Grupos de controle</strong> para medir o impacto das campanhas excluindo parte de seus públicos. Portanto você poderá comparar o comportamento do público-alvo que recebeu a mensagem com o comportamento dos contatos não atingidos. Com base nos logs de envio, você também poderá se concentrar em um grupo de controle em campanhas futuras.
</p>
<p>Para obter mais informações consulte a <a href="../../sending/using/control-group.md">documentação detalhada</a> e o <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html?lang=pt-BR#communication-channels">vídeo de instruções</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>API externa – Suporte ao OAuth</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Agora o Adobe Campaign oferece suporte ao OAuth para autenticação na atividade de workflow da <strong>API externa</strong>. Esse novo recurso abre a capacidade de essa atividade se comunicar com sistemas que exigem suporte para o OAuth.
</p>
<p>Para obter mais informações consulte a <a href="../../automating/using/external-api.md">documentação detalhada</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Integração com a Journey AI</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Temos o prazer de anunciar a Journey AI para todos os clientes do Adobe Campaign Standard.</p>
  <p>A Journey AI usa o Advanced Machine Learning (ML) para permitir que as empresas otimizem o design e o delivery das jornadas do cliente, prevendo a preferência de engajamento de cada pessoa.</p>
  <P>A Journey AI consiste em dois elementos de ML:</p>
<ul> 
     <li> <strong>Pontuação preditiva de engajamento</strong> – identifica de forma inteligente o nível de engajamento preferencial dos clientes para oferecer uma melhor definição do público-alvo e personaliza as mensagens para aumentar as conversões e a retenção. Assista ao <a href="https://docs.adobe.com/content/help/pt-BR/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html">vídeo de instruções</a>.</li> 
     <li> <strong>Otimização preditiva do tempo de envio</strong> – prevê o melhor momento para enviar emails para cada indivíduo em uma campanha para maximizar as taxas de engajamento e melhorar o ROI da campanha de email. Assista ao <a href="https://docs.adobe.com/content/help/pt-BR/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html">vídeo de instruções</a>.</li>
    </ul>
  <p>Se quiser saber como começar a usar a Journey AI, reveja a <a href="../../sending/using/predictive.md">documentação detalhada</a> e entre em contato com o seu Executivo de contas. A Journey AI está disponível gratuitamente para os clientes atuais do Campaign, enquanto que para os outros o custo de implementação é de aproximadamente 50 horas.</p>
    </td> 
</tr> 
</tbody> 
</table>

**Aprimoramentos**

* **Gerenciamento de privacidade**: o campo **recusa do CCPA**, que estava disponível por meio da interface do Campaign e da API, agora também é compatível com o Serviço principal de privacidade. Esse campo permite que os usuários do Adobe Campaign façam o rastreamento caso um consumidor tenha optado pela venda de informações pessoais. [Saiba mais](https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#ccpa)
* **Melhorias na execução do workflow** (beta): no contexto de uma iniciativa global em torno dos workflows, foram desenvolvidas algumas melhorias importantes para estabilizar o gerenciamento da memória, reduzir a latência e otimizar a memória consumida pelos workflows durante a execução. Esses aprimoramentos estão atualmente na versão beta e só estão disponíveis para um conjunto de clientes. A disponibilidade geral está prevista para o início de 2021.
* Para melhorar a segurança, o Campaign agora usa um **mecanismo de assinatura** para rastrear links em emails.
* A configuração do aplicativo móvel foi aprimorada com **mensagens de erro mais claras** ao carregar certificados do iOS ou chaves do Android.
* **O gerenciamento de erros de SMS** foi aprimorado para evitar a adição de muitos perfis à lista de quarentena. Por padrão, os erros de SMS agora são configurados como erros leves ao invés de erros graves. Consulte [esta página](https://helpx.adobe.com/br/campaign/kb/sms-connector-protocol-and-settings.html).

**Aprimoramentos do Email Designer**

* Melhoramos a experiência do usuário no Designer de email com a **nova ajuda contextual dinâmica** que conecta totalmente a interface do usuário e a documentação, fornecendo acesso fácil ao conteúdo de ajuda mais recente.
* Correção de um problema que removia quebras de linha em uma mensagem ao editar sua versão de texto. (CAMP-44483)
* Correção de um problema que impedia que a versão em texto simples de um modelo HTML fosse gerada e sincronizada automaticamente. (CAMP-44195)
* Correção de um problema que ocorria ao redimensionar imagens. Depois que as mensagens eram enviadas, as imagens não eram exibidas corretamente no Microsoft Outlook. (CAMP-44656)
* Correção de um problema que ocorria ao inserir um botão e definir sua largura como &quot;auto&quot;. Depois que a mensagem era enviada, o conteúdo do botão não era exibido totalmente. (CAMP-44560)
* Correção de um problema que ocorria ao carregar conteúdo de um arquivo HTML anexado. Depois que a mensagem era enviada para um endereço Gmail, o CSS não era aplicado, causando um problema de renderização. (CAMP-44085)
* Correção de um problema que impedia que fragmentos de conteúdo usados anteriormente em uma mensagem fossem atualizados quando modificados diretamente no modelo de conteúdo. (CAMP-43973)
* Correção de um problema com a barra de pesquisa **Fragmentos**. Ao pesquisar por um fragmento existente, a barra de pesquisa não apresentava nenhum resultado. (CAMP-44223)
* Correção de um problema com as barras de pesquisa **Blocos de conteúdo** e **Fragmentos**. Ao usar uma das barras de pesquisa, os resultados só eram exibidos se você clicasse em **Mostrar mais resultados...**. (CAMP-44205)
* Correção de um problema que impedia que o preenchimento entre texto e imagens fosse aplicado no Microsoft Outlook. (CAMP-45370)
* Correção de um problema ao duplicar um fragmento. Após a duplicação do fragmento, faltavam linhas HTML no fragmento original. (CAMP-45207)
* Correção de um erro que causava problemas de renderização no Microsoft Outlook. (CAMP-44749)
* Correção de um erro que ocorria ao modificar o preenchimento do **Componente de estrutura** em um template do delivery. As guias CSS não carregavam as alterações feitas no preenchimento, causando um problema de renderização. (CAMP-45381)
* Correção de um problema ao carregar uma imagem. A altura da imagem era automaticamente definida como 0, causando um problema de renderização. (CAMP-45366)

**Outras alterações**

* Os mecanismos de repetição foram adicionados em caso de erro ao tentar importar um público da Experience Platform usando uma atividade **Ler público**. (CAMP-43947, CAMP-43366)
* As unidades organizacionais agora são automaticamente definidas para corresponder à unidade organizacional do usuário que está criando o perfil ou a entidade. As unidades organizacionais não podem mais ser removidas e deixadas vazias.
* Ao publicar um recurso personalizado, uma mensagem pop-up de confirmação é exibida após a preparação.
* A mensagem pop-up que aparece quando um recurso personalizado apresenta falha foi melhorada para oferecer mais clareza.
* O editor de expressão em workflows foi aprimorado para evitar erros de execução. [Novas funções](../../automating/using/customizing-workflow-external-parameters.md) estão disponíveis: elas podem ser usadas em todas as atividades que permitem usar variáveis de evento depois de chamar um workflow com parâmetros externos. Além disso, uma dica de ferramenta agora é exibida no editor de expressão com a descrição da função.
* [Foram adicionados novos filtros à lista de eventos transacionais. ](../../channels/using/configuring-transactional-event.md#searching-transactional-events) Eles permitem que você filtre as configurações do evento de acordo com seu status, bem como a última vez que um evento foi recebido.
* Os logs exibidos ao exportar pacotes se tornaram mais específicos e detalhados quanto aos erros encontrados em caso de falha.
* Agora é possível pesquisar, filtrar e exportar a lista de [URLs rastreados](../../sending/using/tracking-messages.md) após o envio de uma mensagem.
* A [sincronização automática entre o Launch e o Campaign](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow) agora está ativada por padrão na disponibilidade geral.
* O tamanho dos pacotes de exportação de workflow foi otimizado com a remoção da exportação de prova de envio.
* Uma nova mensagem foi adicionada para exibir o tamanho do arquivo baixado na atividade de **transferência de arquivo**.
* Foram aprimoradas as mensagens de erro para tokens de sessão inválidos.
* Um novo mecanismo agora impede que eventos de rastreamento de proxies sejam adicionados a logs de rastreamento e relatórios.
* Uma nova mensagem de aviso foi adicionada para ajudar a depurar atividades de gerenciamento de dados conectadas a uma atividade de delivery.
* Foram aprimoradas as etiquetas no espaço de trabalho de relatórios.
* Uma nova etapa de validação foi adicionada para impedir a exclusão de objetos técnicos em mensagens transacionais.
* Um novo filtro sobre o status do delivery foi adicionado na guia **Lista de execução** de uma mensagem transacional para melhorar a solução de problemas.
* Para melhorar o desempenho e otimizar o tempo de execução, os índices não utilizados foram removidos com base nas estatísticas de uso das tabelas identificadas na análise preliminar para mais de 350 clientes. As tabelas afetadas são: nmsaddressStatus, nmscampaign, nmsdelivery, nmslandingpage, nmsprogram, nmsrecipient, nmsseedmember, nmsservice, nmssubhistorcp, nmsaudience, xtkworkflow

**Correções**

* Correção de um problema que impedia o uso de um link de destino para notificações de push ou mensagens no aplicativo quando o rastreamento era ativado.
* Correção de um problema em que a alta prioridade em mensagens transacionais não era respeitada no caso de deliveries significativos em massa.
* Correção de um problema que impedia a atribuição de marcas a um email transacional. Várias mensagens de erro poderiam ser exibidas durante a etapa de publicação. (CAMP-44988)
* Correção de um problema na interface do usuário do workflow que podia impedir que as informações fossem salvas em campos que solicitavam valores numéricos. (CAMP-44025)
* Correção de um problema que poderia exibir uma mensagem de erro ao usar uma atividade **de teste** em um workflow de template de importação. (CAMP-42910)
* Correção de um problema que ocorria ao usar uma atividade **Ler público** contendo um campo do tipo lista discriminada e conectado às atividades **União** ou **Enriquecimento**. (CAMP-42795)
* Correção de um problema nos relatórios dinâmicos ao usar os segmentos predefinidos para filtrar dados nos relatórios. (CAMP-42627)
* Correção de um problema que impedia a configuração de uma atividade do **Scheduler** para a meia-noite. (CAMP-42674)
* Correção de um problema que poderia interromper o envio de mensagens SMS quando a conexão SMPP estava instável. (CAMP-42789)
* Correção de um problema que impedia a exibição do botão **Parar preparação** após a atualização da página. (CAMP-42721)
* Correção de um problema que impedia a exibição de porcentagens de relatórios de cliques ativos ao importar conteúdo de um URL. (CAMP-44468)
* Correção de um problema que poderia exibir um erro de tempo de espera ao selecionar um perfil a ser usado no contexto da substituição do perfil. (CAMP-44746)
* Correção de um problema que impedia que instâncias funcionassem após a implantação de recursos personalizados contendo definições de links incorretas. (CAMP-44406)
* Correção de um problema que criava entidades vinculadas vazias (tipologias, marcas, etc.) após copiar e colar um delivery em um template de campanha. (CAMP-44765)
* Correção de um problema que impedia o envio de provas devido a um tratamento incorreto de tabelas de preparação de delivery em caso de falha de um banco de dados ou uma simples reinicialização do banco de dados no Azure.
* Correção de um problema que impedia a exclusão de links com conteúdo do Experience Manager em um delivery configurado com conteúdo multilíngue. (CAMP-44029)
* Correção de um problema em relatórios dinâmicos que podia exibir uma mensagem de erro ao tentar filtrar dimensões.  (CAMP-43097)
* Correção de um problema que podia exibir uma tela em branco ao tentar acessar perfis em uma instância configurada com recursos personalizados que continham definições específicas de links. (CAMP-41009)
* Correção de um problema em workflows que ocorria ao usar uma atividade de **Enriquecimento** com duas atividades de entrada com ambos os recursos de público-alvo vinculados. (CAMP-42133)
* Correção de um problema que fazia com que workflows de importação fossem repetidos ao usar uma atividade de **Transferência de arquivo**. (CAMP-43754)
* Correção de um problema que fazia com que duplicações não fossem considerados ao criar um perfil com logs exportados. (CAMP-45031)
* Correção de um problema que causava a discrepância de dados entre relatórios no Adobe Campaign e relatórios exportados em arquivos PDF. (CAMP-43010)
* Correção de um erro que causava a falha do workflow do delivery de correspondência direta ao usar campos de dados existentes em funções. (CAMP-42737)
* Correção de um problema ao importar pacotes, incluindo eventos transacionais e modelos de mensagem. O processo de importação parava em 5%. (CAMP-42544)
* Correção de um problema que causava um erro (Uncaught TypeError) após modificar a atividade de **Enriquecimento** e adicionar outros dados em um workflow. (CAMP-41877)
* Correção de um erro que impedia a exclusão do workflow. Os logs tinham que ser removidos para a exclusão do workflow. (CAMP-44144)
* Correção de um erro ao criar uma landing page com código HTML. As caixas de seleção obrigatórias não eram reconhecidas no Campaign e não estavam disponíveis na landing page publicada. (CAMP-44181)
* Correção de um problema que resultava no loop de workflows ao usar a atividade **Esperar** . (CAMP-43981)
* Correção de um problema ao enviar mensagens transacionais que resultava no direcionamento de vários endereços de email várias vezes em um mesmo delivery. (CAMP-44202)
* Correção de um erro ao usar substituição de perfil com personalização targetData. (CAMP-44996)
* Correção de um problema que causava a falha da pré-visualização do delivery ao exportar um template do delivery em um pacote. (CAMP-44084)
* Correção de um problema que impedia o envio de provas para perfis de teste ao usar mapeamentos de público-alvo personalizados. (CAMP-43701)
* Correção de um erro que ocorria em workflows ao usar a atividade **Ler público** e direcionar um público configurado com um targeting dimension diferente de **Perfil**.  (CAMP-41885)
* Correção de um problema que resultava em erros quando o workflow técnico **updateEventsStatus** demorava muito para recuperar o histórico de eventos (quando o workflow era interrompido). O campo de agregação &quot;sumQueueTime&quot; não utilizado foi removido do workflow para resolver o problema. (CAMP-43920)
* Correção de um problema de memória ao implantar recursos personalizados. (CAMP-42909)
* Correção de um problema nas mensagens transacionais quando os atributos estavam ausentes nas coleções. Agora, todos os atributos ausentes são definidos com um valor padrão e incluídos no payload. (CAMP-42882)
* Correção de um problema que poderia afetar o desempenho ao consultar logs do delivery de eventos em tempo real. (CAMP-42759)
* Correção de um erro que ocorria ao usar extensões de arquivo em maiúsculas com ativos compartilhados. (CAMP-44159)
* Correção de um problema que exibia uma mensagem de erro ao testar a conexão com uma conta externa antes de sua criação. O botão **Testar conexão** agora é exibido somente depois que a conta externa é criada.
* Correção de um problema que deixava mensagens pendentes após o MTA aprimorado ser reiniciado em instâncias configuradas com o compartilhamento.
* Correção de um problema que resultava na incompatibilidade da contagem de perfis ativos com o número efetivo de deliveries enviados.
* Correção de um problema que resultava em latência ao procurar recursos no editor de query em um workflow.
* Correção de um problema ao selecionar a opção **Especificar os campos a serem considerados na pesquisa de texto** em um recurso personalizado. Se a lista de campos foi deixada vazia, a publicação do recurso personalizado falhou.
* Correção de um problema de desempenho ao exibir a visão geral dos recursos personalizados com um grande volume de dados.
* Correção de um problema que impedia a importação de um delivery usando substituições de perfil.
* Correção de um problema ao usar substituição de perfil que impedia o envio imediato de provas se o delivery fosse programado.
* Correção de um problema que ocorria ao carregar uma chave do Android para um aplicativo móvel. A mensagem que aparecia depois de carregar a chave com êxito exibia o valor da chave anterior.
* Correção de um problema que impedia a criação de perfis de teste a partir de mensagens transacionais após a criação de uma configuração de evento com uma coleção sem atributo.
* Correção de um problema que poderia impedir a publicação de recursos personalizados após a criação de um novo filtro usando uma agregação.
* Correção de um problema causado pelo proxy de imagem do Gmail que ocasionava uma taxa de abertura de rastreamento incorreta para recipients do Gmail.
* Correção de um problema que causava erros de falta de memória ao importar um pacote.
* Correção de um problema que causava a falha da ação de desvinculação do Experience Manager quando o seu conteúdo incluía um caminho com um caractere &quot;%20&quot;.
* Correção de um erro nos rótulos ao duplicar atividades de workflow.
* Correção de um problema com o seletor de mensagens transacionais em uma landing page quando a opção **Iniciar envio de mensagem** era selecionada.
* Correção de um problema com mensagens transacionais ou deliveries recorrentes que impedia que o status do delivery fosse inicializado com o valor padrão correto. Os logs de erros também foram aprimorados.
* Correção de um problema ao estender o esquema **Assinatura para um aplicativo** (appSubscriptionRcp) com um link de perfil usando um campo personalizado. O índice não era criado automaticamente, o que poderia afetar o tempo de envio de push. (CAMP-41120)



## Versão 20.3 - maio de 2020 {#release-20-3---may-2020}

**Novidades**

<table> 
<thead> 
<tr> 
<th> <strong>Lei de Proteção de Dados Pessoais (PDPA) da Tailândia</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>A Lei de Proteção de Dados Pessoais (PDPA) da Tailândia é a nova lei de privacidade que harmoniza e moderniza os requisitos de proteção de dados para a Tailândia. Esse regulamento aplica-se aos clientes do Adobe Campaign que mantêm dados de residentes desse país.</p>
<p>Além dos recursos de privacidade disponíveis no Adobe Campaign (inclusive gestão do consentimento, configurações de retenção de dados e funções do usuário), estamos aproveitando esta oportunidade para incluir mais recursos facilitando sua preparação para o PDPA:</p>
<ul>
<li>Direito de acesso e direito de exclusão: estamos usando os recursos que foram adicionados ao GDPR e CCPA. <a href="https://helpx.adobe.com/content/help/br/campaign/kb/acs-privacy.html#righttoaccess">Saiba mais</a> </li>
<li><p>Durante a criação de uma solicitação de acesso a dados pessoais, o tipo de regulamento PDPA foi adicionado ao serviço principal Privacidade. Esse é método que você deve usar para todas as solicitações de acesso e exclusão. O uso da API e da interface do Campaign para solicitações de acesso e exclusão ficará obsoleto.  Consulte o <a href="../../rn/using/deprecated-features.md">artigo Recursos obsoletos e removidos</a>.</p></li>
</ul>
<p>Consulte o <a href="https://docs.adobe.com/content/help/pt-BR/campaign-standard-learn/tutorials/privacy/privacy-overview.translate.html">vídeo de instruções</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Atividade API externa (GA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>A atividade <strong>API externa</strong> está passando de beta para GA. Nessa versão, o analisador do corpo de resposta JSON tem flexibilidade adicional. Agora você pode:</p>
<ul>
<li>analisar um JSON aninhado com uma profundidade máxima de 10 níveis. </li>
<li>analisar as propriedades selecionadas como nós de folha de um JSON e nivelá-las em uma única linha de tabela.</li>
<li>selecionar e usar um objeto de matriz de um JSON sem precisar nomear o objeto como “dados” ou deixá-lo no nível superior.</li>
</ul>
<p><strong>Cuidado:</strong> os clientes precisarão <strong>substituir todas as atividades beta da API externa</strong> por atividades GA da API externa nos fluxos de trabalho.  Os fluxos de trabalho que usam a versão beta da API externa não funcionarão mais na versão 20.3.</p>
<p>Para saber mais, consulte a <a href="../../automating/using/external-api.md">documentação detalhada</a> e o <a href="https://docs.adobe.com/content/help/pt-BR/campaign-standard-learn/tutorials/managing-processes-and-data/data-management-activities/external-api-activity.translate.html">vídeo de instruções</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Recursos adicionais** (a partir de 13 de julho)

* **Otimização do tempo de envio com recursos de IA e pontuação do perfil** – agora você pode otimizar o design e o delivery das jornadas do cliente para prever a preferência de envolvimento de cada indivíduo. Com a tecnologia Journey AI, o Adobe Campaign pode analisar e prever taxas abertas, tempos de envio ideais e probabilidade de churn com base em métricas históricas de engajamento. [Saiba mais](../../sending/using/predictive.md)
* **Nova regulamentação de privacidade do Brasil** – além das características de privacidade já disponíveis no Campaign, a Adobe ajuda a facilitar o preparo para a Lei Geral de Proteção de Dados (LGPD) do Brasil. Durante a criação de uma solicitação de acesso a dados pessoais, o regulamento LGPD foi adicionado ao Serviço Principal de Privacidade da Adobe. [Saiba mais](https://helpx.adobe.com/br/campaign/kb/campaign-privacy-overview.html)

**Aprimoramentos**

* O número de caracteres que podem ser usados no campo **Prefix** para [testar mensagens usando perfis direcionados](../../sending/using/testing-messages-using-target.md) aumentou de 32 para 500.
* O número máximo de eventos em tempo real que podem ser publicados em uma instância aumentou de 350 para 2000. (CAMP-41608)
* A sincronização entre o Adobe Launch e o Campaign Standard foi aprimorada usando o workflow técnico syncWithLaunch. Esse workflow permite a importação automática de todas as propriedades móveis do Adobe Launch para o Adobe Campaign Standard. Para saber mais, consulte [esta página](../../administration/using/technical-workflows.md).

   Você precisará enviar um tíquete ao Atendimento ao cliente da Adobe (diretamente ou por meio de seu contato da Adobe) para habilitar o workflow técnico syncWithLaunch na instância do Campaign. (CAMP-40082)

**Aprimoramentos do Email Designer**

* O Email Designer agora pode lidar com uma formatação HTML mais flexível do que o W3C estrito. (CAMP-42529)
* Correção de um problema com as [imagens clicáveis](../../designing/using/links.md#inserting-a-link) para impedir a exibição dos links ao lado da imagem nos blocos de conteúdo. (CAMP-41586)
* Correção de um problema que impedia o redirecionamento para uma landing page quando o [URL rastreado](../../designing/using/links.md#about-tracked-urls) tinha uma categoria adicionada ao template. (CAMP-41537)
* Correção de um problema com o preenchimento de botões no Outlook.
* Correção de um problema que fazia com que as tags HTML fossem exibidas em texto sem formatação.
* A pesquisa de blocos de conteúdo agora exibe resultados de pesquisa do servidor e resultados pré-carregados. (CAMP-41870)

**Outras alterações**

* A interface personalizada de publicação de recursos foi aprimorada com mensagens de erro mais claras.
* Os mapeamentos dos deliveries não utilizados foram removidos da interface.
* As funções de administrador desnecessárias foram removidas da interface.
* As caixas de seleção agora podem ser obrigatórias em uma landing page.
* Ao baixar o arquivo CSV de um relatório dinâmico, o limite de 200 linhas foi removido. Agora você pode incluir cada linha do seu relatório. (CAMP-40810)
* Adição do idioma ES-US à lista de idiomas prontos para uso para emails multilíngues. (CAMP-42279)
* Os arquivos baixados com uma atividade Transfer File agora serão excluídos depois de X dias, em que X é determinado pelo campo **History in days** no menu **Execution** nas propriedades Workflow. [Leia mais](../../automating/using/managing-execution-options.md)

**Integrações da Experience Platform**

* A ativação dos [públicos-alvo da Adobe Experience Platform](../../integrating/using/aep-targeting-audiences.md) da atividade **Read audience** foi aprimorada para oferecer melhor desempenho e estabilidade. Além disso, os logs de workflow ficaram mais claros e detalhados em relação aos trabalhos de ativação, facilitando o monitoramento e a solução de problemas durante a leitura dos públicos-alvo da Adobe Experience Platform.

**Correções**

* Correção de um erro que criava um recurso fantasma durante o trabalho de publicação de um recurso personalizado.
* Correção de um problema que impedia que o histórico de marketing do perfil fosse exibido se o recurso de perfil fosse estendido com um recurso personalizado. (CAMP-41009)
* Correção de um problema com templates de landing page prontos para uso que exibiam o conteúdo em francês ao abrir o editor. (CAMP-41639)
* Correção de um problema nas notificações por push com conteúdo dinâmico que podia impedir a exibição de emojis. (CAMP-40715)
* Correção de um problema na atividade **Desduplicação** que atribuía um código de segmento incorreto a uma das transições complementares de saída. (CAMP-41400)
* Correção de um erro que impedia a exclusão de relatórios programados. (CAMP-41302)
* Correção de um problema que causava discrepância entre o painel do delivery e o relatório **Delivery Summary**. (CAMP-41145)
* Correção de um problema que causava um problema de exibição de sobreposição de caracteres nos relatórios baixados.
* Correção de um problema que impedia que a pré-visualização de um delivery funcionasse para substituição da prova.
* Correção de um erro durante a exclusão de campos personalizados de uma notificação local no aplicativo.
* Correção de um problema que impedia que a função charIndex funcionasse com uma atividade **End** ou **File transfer** em um workflow.
* Correção de um problema nos fluxos de trabalho que poderia ocorrer durante uma atividade **Enriquecimento** com duas atividades de entrada, inclusive direcionamento de recursos com um link entre elas. (CAMP-42133)
* Correção de um problema que poderia impedir a execução de um workflow ao usar funções desconhecidas. (CAMP-41873)
* Correção de um problema nos fluxos de trabalho que poderia ocorrer durante a criação de públicos-alvo usando várias atividades **Save audience** com transições complementares de saída. (CAMP-39992)
* Correção de um problema que causava discrepância de dados ao usar personalização em emails transacionais. (CAMP-41842)
* Correção de problemas que ocorriam ao excluir campos personalizados em deliveries de notificação por push. (CAMP-37586)
* Correção de um erro que impedia que os usuários fizessem alterações nos relatórios. (CAMP-42505)


![](assets/do-not-localize/cp-icon.png) **O novo Painel de controle do Campaign pode ser lançado** com a renovação do certificado para subdomínios CNAME. [Saiba mais](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html).

## Versão 20.2 - Abril de 2020 {#release-20-2---april-2020}

**Novidades**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integração com o Azure Blob</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>O conector de armazenamento do Azure Blob agora pode ser usado para importar ou exportar dados para o Adobe Campaign usando uma atividade de workflow <strong>Transferir arquivo</strong>. </p>
    <p>Para obter mais informações, consulte a <a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">documentação detalhada</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Teste de email usando perfis direcionados</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Além de testar perfis, agora você pode testar seus emails em perfis direcionados reais. Você pode obter uma representação exata da mensagem que o perfil receberá: campos personalizados, informações dinâmicas e personalizadas, incluindo dados adicionais de workflows etc. </p>
    <p>Para obter mais informações, consulte a <a href="../../sending/using/testing-messages-using-target.md">documentação detalhada</a> e o <a href="https://docs.adobe.com/content/help/pt-BR/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.translate.html">vídeo tutorial</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Novos recursos serão lançados no Painel de controle do Campaign em abril, incluindo o gerenciamento de registros do Google TXT, monitoramento de espaço do banco de dados e alertas de email. Para obter mais informações sobre esses recursos, consulte a [Nota de versão do Painel de controle do Campaign](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html).

**Aprimoramentos**

* A experiência do usuário de mensagens transacionais foi aprimorada, e a consistência da interface foi aprimorada. [Leia mais](../../channels/using/getting-started-with-transactional-msg.md)
* O Campaign Standard agora permite enviar provas para perfis de Teste usando dados adicionais de workflows.
* As garantias para a atividade API externa foram atualizadas. [Leia mais](../../automating/using/external-api.md)

**Aprimoramentos do Email Designer**

* Correção de um problema que afetava o escape ao clicar várias vezes em uma imagem personalizada.
* Correção de um problema ao duplicar componentes de texto dinâmicos que poderia resultar na duplicação da linha errada. (CAMP-41249)
* Correção de um problema com o preenchimento no Outlook ao definir o preenchimento no nível da tabela em vez de no nível div.
* Correção de um problema que fazia com que a largura de uma imagem fosse modificada ao alternar para o modo HTML. (CAMP-41116)
* Correção de um problema que impedia que o componente de mídia social ficasse acessível ao fornecer texto alternativo aos ícones. (CAMP-41345)
* Correção de um problema que fazia com que as tags `<br>` visíveis fossem exibidas ao usar as funções Copiar e Colar no Email Designer.
* Correção de um problema que fazia com que tags HTML fossem exibidas no email após alternar do conteúdo HTML para Texto simples. (CAMP-41138)
* Correção de um problema que impedia a renderização de botões com apenas uma borda definida.
* Correção de um problema no recuo HTML que fazia com que o rodapé de emails se movesse para a esquerda no Microsoft Outlook. (CAMP-40987)
* Correção de um problema que fazia com que campos de personalização direcionados a um atributo de coleção definido em HTML fossem copiados no conteúdo de texto simples ao alternar para o modo de texto sem formatação. (CAMP-40365)
* Correção de um problema que impedia a inserção de links em um segmento de texto selecionado. (CAMP-41406)
* Correção de um problema que fazia com que a data fosse alterada ao selecionar um fuso horário no Editor de consultas. (CAMP-38277)

**Outras alterações**

* A **Reconciliação de KPIs com o workflow predefinido do Adobe Analytics** agora é executada até a data atual, em vez de ser executada por um único dia.
* O MCPNS não oferece suporte para a adição de APNS e APNS-SANDBOX como plataformas em um aplicativo. Depois de adicionar o certificado com êxito no Adobe Campaign Standard, você não poderá mais alterar as configurações novamente, pois apenas uma plataforma APNS (produção ou caixa de proteção) pode ser adicionada ao aplicativo MCPNS.

**Integrações da Experience Platform**

>[!NOTE]
>
>Os recursos da Adobe Experience Platform no Campaign Standard estão atualmente em versão beta, que pode estar sujeita a atualizações frequentes sem aviso prévio. Consulte a documentação detalhada: [Conector de dados da Experience Platform](../../integrating/using/aep-about-data-connector.md), [Audience Destinations](../../integrating/using/aep-about-audience-destinations-service.md)

* Em logs de workflow, a cada 10 minutos, o Campaign agora exibe o número de registros já processados pelo trabalho que está sendo executado no momento.
* Correção de um problema que ocorria ao importar um perfil da Adobe Experience Platform que havia sido excluído do banco de dados.
* Correção de um problema em logs de workflow que poderia exibir um resultado incorreto para o número total de registros importados.

**Correções**

* Correção de um problema com a atividade de workflow **Enriquecimento** que poderia ocorrer ao adicionar espaços no campo **Alias**, o que então criava um novo item de linha. (CAMP-39229)
* Correção de um problema em que cada perfil de teste podia ser direcionado ao enviar uma mensagem de prova.
* Correção de um problema que ocorria após a remoção da publicação e exclusão de uma configuração de evento. [Leia mais](../../channels/using/publishing-transactional-event.md#deleting-an-event)
* Correção de um problema em que o botão **Save** desaparecia ao fazer alterações em workflows.
* Correção de um problema ao excluir uma solicitação de acesso a dados pessoais manualmente no Campaign depois de ela ter sido processada, o que impedia que os dados associados à solicitação fossem excluídos mesmo após a limpeza.
* Correção de um problema que podia ocorrer ao pré-visualizar ou enviar mensagens que incluíam caracteres especiais do Adobe Experience Manager.
* Correção de um problema que ocorria em workflows ao executar uma atividade com várias transições de entrada.
* Correção de um problema que impedia os usuários padrão de usar &quot;Assinaturas de um aplicativo&quot; como dimensão de destino em uma query de workflow ou delivery. (CAMP-37618)

## Versão 20.1.4 - Fevereiro de 2020 {#release-20-1-4---february-2020}

* Correção de um problema ao abrir uma atividade **Read Audience** em workflows existentes. (CAMP-41002)

## Versão 20.1.3 - Fevereiro de 2020 {#release-20-1-3---february-2020}

* Correção de um problema de regressão apresentado na versão 20.1 por CAMP-39273 para clientes que usam a abertura. CAMP-39273 foi revertido.

## Versão 20.1.2 - Fevereiro de 2020 {#release-20-1-2---february-2020}

**Aprimoramentos do Email Designer**

* Correção de um problema que adicionava um elemento de tag HTML em um fragmento desatualizado ao corrigir e salvar o conteúdo. (CAMP-40685)
* Correção de um problema que adicionava um espaço ao usar conteúdo dinâmico. (CAMP-40605)
* Correção de um problema ao configurar um template de email transacional. (CAMP-40604)

## Versão 20.1 - Fevereiro de 2020 {#release-20-1---february-2020}

**Novidades**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Conector de dados da Adobe Experience Platform (beta)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>O Conector de dados da Adobe Experience Platform agora está integrado ao Adobe Campaign Standard. Você pode disponibilizar seus dados do Campaign na Adobe Experience Platform, mapeando dados XTK (dados assimilados no Campaign) para o Modelo de dados da Adobe Experience Platform (XDM). </p>
    <p>Observe que esse recurso só está disponível para clientes hospedados no Azure. Para obter mais informações sobre esse recurso e as condições para ativá-lo, consulte a <a href="../../integrating/using/aep-about-data-connector.md">documentação detalhada</a> e o <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html?lang=pt-BR#administrating">vídeo de instruções</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Audience Destinations (beta) </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>O serviço Audience Destinations permite compartilhar segmentos da Adobe Experience Platform com o Adobe Campaign.</p>
    <p> Observe que esse recurso só está disponível para clientes hospedados no Azure. Para obter mais informações sobre esse recurso e as condições para ativá-lo, consulte a <a href="../../integrating/using/aep-about-audience-destinations-service.md">documentação detalhada</a> e o <a href="https://docs.adobe.com/content/help/pt-BR/campaign-standard-learn/tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.translate.html">vídeo de instruções</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**Aprimoramentos**

* Disponibilidade global do MTA aprimorado: as mensagens (incluindo mensagens transacionais) agora são enviadas pelo MTA aprimorado do Adobe Campaign, que fornece uma infraestrutura de envio atualizada que possibilita melhorar a entrega, a taxa de rendimento e o tratamento de rejeições. [Leia mais](https://helpx.adobe.com/br/campaign/kb/campaign-enhanced-mta.html)

* O gerenciamento do fuso horário foi aprimorado. Agora, você pode definir um [fuso horário](../../automating/using/building-a-workflow.md) específico para um workflow inteiro. O fuso horário selecionado será aplicado a todas as atividades do workflow. As informações sobre o fuso horário que foi configurado para o operador ou o servidor agora são exibidas na interface (em logs e depois de selecionar um fuso horário). (CAMP-37672)

* Agora, as APIs do Campaign Standard permitem fazer a paginação ao usar tabelas grandes, adicionando o parâmetro `_forcePagination=true` ao URL da chamada. [Leia mais](../../api/using/pagination.md)

* A ID de log de delivery (que é um identificador exclusivo de cada log) agora está disponível nos recursos Logs de delivery e Logs de rastreamento para todas as dimensões de direcionamento. Você pode identificar logs de rastreamento ou envios ao exportar, por exemplo. [Leia mais](../../automating/using/exporting-logs.md)

**Aprimoramentos do Email Designer**

* Foram adicionadas instruções de texto obrigatórias que estavam ausentes ao criar um público-alvo.
* Correção de um problema ao clicar no botão **Change content** no assistente do editor de email herdado.
* Correção de um problema que impedia que os cabeçalhos fossem alinhados ao conteúdo no relatório Service Summary. (CAMP-38103)
* Correção de um problema que impedia que variantes de conteúdo dinâmico fossem excluídas sem afetar o restante da linha de assunto. (CAMP-40096)
* Correção de um problema de teste A/B ao usar a variante B na linha de assunto. (CAMP-40327)
* Correção de um problema que impedia arrastar e soltar arquivos ao usar o recurso de importação Upload HTML. (CAMP-39326)
* Correção de um problema que impedia copiar e colar texto de um editor de texto. (CAMP-39028)
* Correção de um problema que impedia a exibição de sugestões de palavras. (CAMP-38970)
* Correção de um problema que impedia os usuários de salvar fragmentos. (ATU-2447)
* Correção de um problema que impedia a duplicação de estruturas dinâmicas. (CAMP-38367)
* Correção de um problema que impedia que o conteúdo dinâmico mantivesse condições ao duplicar. (CAMP-39051)

**Outras alterações**

* O filtro &quot;Deliveries with preparation failed&quot; agora leva em conta a data de criação dos deliveries em vez da data da última modificação.
* A unidade organizacional do grupo de segurança Administrators não pode mais ser alterada.
* Ao criar um perfil, o campo Organizational Unit deve ser preenchido.
* Um Acionador da Experience Cloud agora só poderá ser excluído se o evento e o template transacional vinculados a ele forem excluídos.
* [!DNL Adobe Creative SDK] foi desativado. Ele agora está obsoleto no Campaign Standard. Consulte a página [Recursos descontinuados e removidos](../../rn/using/deprecated-features.md).


**Correções**

* Correção de um problema ao executar uma exclusão de solicitação de acesso a dados pessoais que impedia que os dados do usuário fossem excluídos em logs de exclusão. (CAMP-39003)
* Correção de um problema que resultava em problemas de acessibilidade ao redimensionar o texto em um elemento de container.
* Correção de um problema que impedia os usuários de descartarem o pop-up Calendar exibido ao focalizar o mouse em atividades de marketing.
* Correção de um problema na atividade **[!UICONTROL External API]** que exibia o botão **[!UICONTROL Confirm]**, mesmo quando nenhum dado era modificado.
* Correção de um problema ao usar uma atividade **[!UICONTROL Union]** em consultas com diferentes dimensões de destino. Os dados de transição mostravam apenas registros da dimensão de direcionamento do conjunto principal. (CAMP-36831)
* Correção de um problema que resultava em erro ao usar uma atividade **[!UICONTROL Reconciliation]** em contextos específicos, por exemplo, com duas atividades de entrada, uma delas sendo uma atividade de exclusão. (CAMP-37490)
* Correção de problemas de desempenho que podem ocorrer ao selecionar e atualizar perfis de teste. (CAMP-37976)
* Correção de um problema que podia exibir páginas de erro ao assinar ou cancelar a assinatura via landing pages. (CAMP-37771)
* Correção de um problema que ocorria ao carregar conteúdo no formato zip, com arquivos PNG referenciados no HTML com sua extensão em letras maiúsculas. (CAMP-37913)
* Correção de um problema que impedia o envio de mensagens no aplicativo ao adicionar um perfil de teste ao delivery.
* Correção de um erro com a atividade de workflow API externa que falhava quando vinculada a atividades de enriquecimento.
* Correção de um problema que resultava na exibição incorreta do status de mensagens SMS.
* Correção de um problema com recursos personalizados que fazia com que entradas duplicadas fossem exibidas em diferentes pontos de extremidade de API.
* Correção de um problema que impedia que landing pages ficassem disponíveis após a publicação. (CAMP-38695)
* Correção de um erro que ocorria ao exibir dados de uma transição de Intersecção proveniente de dois recursos diferentes. (CAMP-38974)
* Correção de um problema que fazia com que o valor de lista discriminada em um template do delivery fosse definido incorretamente. (CAMP-38388)
* Correção de um erro com deliveries de email em massa que exibiam o estado dos deliveries como Pending e o status Sent como Finished. (CAMP-35355)
* Correção de um erro que exibia o domínio do remetente incorretamente em Dynamic Reporting. (CAMP-33123)
* Correção de um problema que causava discrepância em contagens de cancelamentos de assinatura em Dynamic Reporting. (CAMP-39949)
* Correção de um problema que impedia a exibição de endereços na tela Sending logs ao enviar mensagens no aplicativo.
* Correção de um problema que impedia que logs de envio de SMS fossem atualizados com o número correto de rejeições. (CAMP-38395)
* Correção de uma abertura que permitia que as chamadas de publicação de assinaturas do aplicativo atualizassem os tokens de notificação por push. (CAMP-39273)
