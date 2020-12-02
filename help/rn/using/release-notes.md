---
solution: Campaign Standard
product: campaign
title: Versão mais recente
description: Esta página detalha o conteúdo da versão mais recente do Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: tm+mt
source-git-commit: fc755f3176622e1faf08ccfa4236e016110f9a68
workflow-type: tm+mt
source-wordcount: '2412'
ht-degree: 100%

---


# Versão mais recente{#latest-release}

[Planejamento de versão](../../rn/using/release-planning.md) | [Versões do painel de controle do Campaign](https://docs.adobe.com/content/help/pt-BR/control-panel/using/release-notes.html) | [Atualizações da documentação](../../rn/using/documentation-updates.md) | [Notas de versão anteriores](../../rn/using/release-notes-2020.md) | [Recursos descontinuados](../../rn/using/deprecated-features.md)

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

