---
title: Versão mais recente
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
source-git-commit: 422f5eb7011dfcc1d923079e7346394a64934a9a
workflow-type: tm+mt
source-wordcount: '1007'
ht-degree: 4%

---


# Versão mais recente{#latest-release}

[Planejamento de versão](../../rn/using/release-planning.md) | Versões [do Painel de controle](https://docs.adobe.com/content/help/pt-BR/control-panel/using/release-notes.html) | Atualizações [da documentação](../../rn/using/documentation-updates.md) | Notas de versão [anteriores](../../rn/using/release-notes-2020.md) | Recursos [obsoletos](../../rn/using/deprecated-features.md)

## Versão 20.3 - maio de 2020 {#release-20-3---may-2020}

**Novidades**

<table> 
<thead> 
<tr> 
<th> <strong>PDPA (Personal Data Protection Act) da Tailândia</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>A Lei de Proteção de Dados Pessoais (PDPA) da Tailândia é a nova lei de privacidade que harmoniza e moderniza os requisitos de proteção de dados para a Tailândia. Este regulamento aplica-se aos clientes Adobe Campaign que detêm dados para pessoas a quem residem neste país.</p>
<p>Além dos recursos de privacidade já disponíveis no Adobe Campaign (incluindo gerenciamento de consentimento, configurações de retenção de dados e funções de usuário), estamos aproveitando esta oportunidade para incluir recursos adicionais, para ajudar a facilitar sua preparação para o PDPA:</p>
<ul>
<li>Direito de acesso e direito de exclusão: estamos aproveitando as capacidades que foram adicionadas ao RGPD e CCPA. <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#righttoaccess">Saiba mais</a> </li>
<li><p>Ao criar uma solicitação de privacidade, o tipo de regulamento PDPA foi adicionado ao Privacy Core Service. Este método é o que você deve usar para todas as solicitações de acesso e exclusão. O uso da API de Campanha e da interface para acessar e excluir solicitações está obsoleto.  Consulte o artigo <a href="../../rn/using/deprecated-features.md">Recursos removidos e</a>obsoletos.</p></li>
</ul>
<p>Consulte o vídeo <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">como fazer</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Atividade de API externa (GA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>A atividade da API <strong></strong> externa está sendo transferida do beta para o GA. Esta versão oferece flexibilidade adicional ao analisador de corpo de resposta JSON. Agora você pode:</p>
<ul>
<li>analise um JSON aninhado com uma profundidade máxima de 10 níveis. </li>
<li>analise as propriedades selecionadas como nós de folha de um JSON e nivele-as em uma única linha de tabela.</li>
<li>selecione e use um objeto de matriz de um JSON sem precisar nomear o objeto como "dados" ou deixá-lo no nível superior.</li>
</ul>
<p><strong>Cuidado:</strong> Os clientes precisarão <strong>substituir todas as atividades</strong> beta de API externa por atividades de API externas GA em seus workflows.  Os Workflows que usam a versão beta da API externa pararão de funcionar na versão 20.3.</p>
<p>Para obter mais informações, consulte a <a href="../../automating/using/external-api.md">documentação detalhada</a> e o <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">vídeo de instruções</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Aprimoramentos**

* O número de caracteres que podem ser usados no campo **Prefixo** para [testar mensagens usando perfis](../../sending/using/testing-messages-using-target.md) direcionados aumentou de 32 para 500 caracteres.
* O número máximo de eventos em tempo real que podem ser publicados em uma instância foi aumentado de 350 para 2000. (CAMP-41608)
* A sincronização entre o Adobe Launch e o Campaign Standard foi aprimorada usando o fluxo de trabalho técnico syncWithLaunch. Esse fluxo de trabalho permite a importação automática de todas as propriedades móveis do Adobe Launch para o Adobe Campaign Standard. Para obter mais informações, consulte [esta página](../../administration/using/technical-workflows.md).

   Você precisará enviar um ticket para o Atendimento ao cliente da Adobe (diretamente ou por meio de seu contato da Adobe) para habilitar o fluxo de trabalho técnico syncWithLaunch na instância da Campanha. (CAMP-40082)

**Aprimoramentos do Designer de email**

* O Designer de e-mail agora pode lidar com uma formatação HTML mais flexível do que com W3C estrito. (CAMP-42529)
* Correção de um problema com imagens [](../../designing/using/links.md#inserting-a-link) clicáveis para impedir que os links sejam exibidos ao lado da imagem nos blocos de conteúdo. (CAMP-41586)
* Correção de um problema que impedia o redirecionamento para uma landing page quando o URL [](../../designing/using/links.md#about-tracked-urls) rastreado tinha uma categoria adicionada ao modelo. (CAMP-41537)
* Correção de um problema com o preenchimento de botões no Outlook.
* Corrigido um problema que fazia com que as tags HTML fossem exibidas em texto sem formatação.
* A pesquisa de blocos de conteúdo agora exibe os resultados de pesquisa do servidor, bem como os resultados pré-carregados. (CAMP-41870)

**Outras alterações**

* A interface de publicação de recursos personalizados foi aprimorada com mensagens de erro mais claras.
* Os mapeamentos de delivery não utilizados foram removidos da interface.
* As funções de administrador desnecessárias foram removidas da interface.
* As caixas de seleção agora podem ser obrigatórias em uma landing page.
* Ao baixar o arquivo CSV de um relatório dinâmico, o limite de 200 linhas foi removido. Agora você pode incluir cada linha do seu relatório. (CAMP-40810)
* Adicionado o idioma ES-US na lista de idiomas prontos para uso para emails multilíngues. (CAMP-42279)
* Os arquivos baixados com uma atividade Transferir arquivo serão excluídos depois de X dias, onde X é determinado pelo campo **Histórico em dias** no menu **Execução** nas propriedades Fluxo de trabalho. [Leia mais](../../automating/using/managing-execution-options.md)

**Integrações da plataforma Experience**

* A Ativação das Audiências [da plataforma Adobe](../../automating/using/aep-targeting-audiences.md) Experience da atividade **Read audiência** foi aprimorada para oferecer melhor desempenho e estabilidade. Além disso, os registros de fluxo de trabalho foram tornados mais claros e detalhados em relação aos trabalhos de ativação, permitindo um monitoramento e solução de problemas mais fáceis ao ler as audiências da plataforma Adobe Experience.

**Correções**

* Correção de um erro que resultava na criação de um recurso fantasma durante o trabalho de publicação de um recurso personalizado.
* Correção de um problema que impedia que o Histórico de marketing do perfil fosse exibido se o recurso do Perfil fosse estendido com um recurso personalizado. (CAMP-41009)
* Correção de um problema com modelos de landing page predefinidos que exibiam seu conteúdo em francês ao abrir o editor. (CAMP-41639)
* Correção de um problema nas notificações por push com conteúdo dinâmico que impedia a exibição de emojis. (CAMP-40715)
* Correção de um problema na atividade **Desduplicação-duplicada** que resultava na atribuição de um código de segmento incorreto a uma das transições complementares de saída. (CAMP-41400)
* Correção de um erro que impedia a exclusão de relatórios agendados. (CAMP-41302)
* Correção de um problema que causava discrepância entre o painel do delivery e o relatório Resumo **do** Delivery. (CAMP-41145)
* Correção de um problema que resultava em um problema de exibição de sobreposição de caracteres em relatórios baixados.
* Correção de um problema que impedia que a pré-visualização de um delivery funcionasse para substituição de prova.
* Corrigido um erro ao excluir campos personalizados de uma notificação local no aplicativo.
* Correção de um problema que impedia que a função charIndex funcionasse com uma atividade de transferência **** End **ou** File em um fluxo de trabalho.
* Correção de um problema em workflows que ocorria ao usar uma atividade de **Enriquecimento** com duas atividades de entrada, incluindo recursos de público alvo com um link entre elas. (CAMP-42133)
* Correção de um problema que impedia a execução de um fluxo de trabalho ao usar funções desconhecidas. (CAMP-41873)
* Correção de um problema em workflows que ocorria ao criar audiências usando várias atividades **Salvar audiência** com transições de saída complementares. (CAMP-39992)
* Correção de um problema que causava discrepância de dados ao usar personalização em emails transacionais. (CAMP-41842)
* Correção de problemas que ocorriam ao excluir campos personalizados em delivery de notificação por push. (CAMP-37586)
* Correção de um erro que impedia que os usuários fizessem alterações nos relatórios. (CAMP-42505)
