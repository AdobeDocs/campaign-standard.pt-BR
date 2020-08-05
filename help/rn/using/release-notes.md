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
source-git-commit: f45985c030c3d5059bfef444287c10b842298f49
workflow-type: tm+mt
source-wordcount: '1160'
ht-degree: 90%

---


# Versão mais recente{#latest-release}

[Planejamento de versão](../../rn/using/release-planning.md) | [Versões do painel de controle do Campaign](https://docs.adobe.com/content/help/pt-BR/control-panel/using/release-notes.html) | [Atualizações da documentação](../../rn/using/documentation-updates.md) | [Notas de versão anteriores](../../rn/using/release-notes-2020.md) | [Recursos descontinuados](../../rn/using/deprecated-features.md)

![](assets/do-not-localize/cp-icon.png) **Nova versão de junho do Painel de controle do Campaign** com monitoramento de perfis ativos, auditoria de entregabilidade de subdomínio e gerenciamento de chaves GPG. [Saiba mais](https://docs.adobe.com/content/help/pt-BR/control-panel/using/release-notes.html).

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

**Recursos** adicionais (a partir de 13 de julho)

* **Otimização do tempo de envio com recursos de AI e pontuação** do perfil - agora você pode otimizar o design e o delivery das viagens do cliente para prever a preferência de envolvimento de cada indivíduo. Com a tecnologia Journey AI, a Adobe Campaign pode analisar e prever taxas abertas, tempos de envio ideais e probabilidade de taxa com base em métricas de envolvimento do histórico. [Saiba mais](../../sending/using/predictive.md)
* **Nova regulamentação** de privacidade do Brasil - Além das capacidades de privacidade já disponíveis na Campanha, a Adobe ajuda a facilitar a disposição para a Lei Geral de Proteçao de Datos (LGPD) no Brasil. Ao criar uma solicitação de privacidade, o regulamento LGPD foi adicionado ao Adobe Privacy Core Service. [Saiba mais](https://helpx.adobe.com/br/campaign/kb/campaign-privacy-overview.html)

**Aprimoramentos**

* O número de caracteres que podem ser usados no campo **Prefix** para [testar mensagens usando perfis direcionados](../../sending/using/testing-messages-using-target.md) aumentou de 32 para 500.
* O número máximo de eventos em tempo real que podem ser publicados em uma instância aumentou de 350 para 2000. (CAMP-41608)
* A sincronização entre o Adobe Launch e o Campaign Standard foi aprimorada usando o fluxo de trabalho técnico syncWithLaunch. Esse fluxo de trabalho permite a importação automática de todas as propriedades móveis do Adobe Launch para o Adobe Campaign Standard. Para saber mais, consulte [esta página](../../administration/using/technical-workflows.md).

   Você precisará enviar um tíquete ao Atendimento ao cliente da Adobe (diretamente ou por meio de seu contato da Adobe) para habilitar o fluxo de trabalho técnico syncWithLaunch na instância do Campaign. (CAMP-40082)

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

* A ativação dos [públicos-alvo da Adobe Experience Platform](../../automating/using/aep-targeting-audiences.md) da atividade **Read audience** foi aprimorada para oferecer melhor desempenho e estabilidade. Além disso, os logs de fluxo de trabalho ficaram mais claros e detalhados em relação aos trabalhos de ativação, facilitando o monitoramento e a solução de problemas durante a leitura dos públicos-alvo da Adobe Experience Platform.

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
* Correção de um problema que impedia que a função charIndex funcionasse com uma atividade **End** ou **File transfer** em um fluxo de trabalho.
* Correção de um problema nos fluxos de trabalho que poderia ocorrer durante uma atividade **Enriquecimento** com duas atividades de entrada, inclusive direcionamento de recursos com um link entre elas. (CAMP-42133)
* Correção de um problema que poderia impedir a execução de um fluxo de trabalho ao usar funções desconhecidas. (CAMP-41873)
* Correção de um problema nos fluxos de trabalho que poderia ocorrer durante a criação de públicos-alvo usando várias atividades **Save audience** com transições complementares de saída. (CAMP-39992)
* Correção de um problema que causava discrepância de dados ao usar personalização em emails transacionais. (CAMP-41842)
* Correção de problemas que ocorriam ao excluir campos personalizados em deliveries de notificação por push. (CAMP-37586)
* Correção de um erro que impedia que os usuários fizessem alterações nos relatórios. (CAMP-42505)


![](assets/do-not-localize/cp-icon.png) **O novo Painel de controle do Campaign pode ser lançado** com a renovação do certificado para subdomínios CNAME. [Saiba mais](https://docs.adobe.com/content/help/pt-BR/control-panel/using/release-notes.html).
