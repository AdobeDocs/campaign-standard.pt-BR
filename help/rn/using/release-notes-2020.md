---
title: Notas de versão 2020
description: Essa página lista todas as versões 2020 do Adobe Campaign Standard.
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
source-git-commit: 5b99fb9fbf8bdac506aeb8a35f30a7ef33aaa7e6
workflow-type: tm+mt
source-wordcount: '2948'
ht-degree: 95%

---


# Notas de versão 2020{#release-notes-2020}

[Planejamento de versão](https://helpx.adobe.com/br/campaign/kb/acs-release-planning.html) | [Versões do painel de controle do Campaign](https://docs.adobe.com/content/help/pt-BR/control-panel/using/release-notes.html) | [Atualizações da documentação](../../rn/using/documentation-updates.md) | [Notas de versão anteriores](../../rn/using/release-notes-2019.md) | [Recursos descontinuados](https://helpx.adobe.com/br/campaign/kb/acs-deprecated-and-removed-features.html)

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
>Novos recursos serão lançados no Painel de controle do Campaign em abril, incluindo o gerenciamento de registros do Google TXT, monitoramento de espaço do banco de dados e alertas de email. Para obter mais informações sobre esses recursos, consulte a [Nota de versão do Painel de controle do Campaign](https://docs.adobe.com/content/help/pt-BR/control-panel/using/release-notes.html).

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
>Os recursos da Adobe Experience Platform no Campaign Standard estão atualmente em versão beta, que pode estar sujeita a atualizações frequentes sem aviso prévio. Consulte a documentação detalhada: [Conector de dados da Experience Platform](../../developing/using/aep-about-data-connector.md), [Audience Destinations](../../audiences/using/aep-about-audience-destinations-service.md)

* Em logs de workflow, a cada 10 minutos, o Campaign agora exibe o número de registros já processados pelo trabalho que está sendo executado no momento.
* Correção de um problema que ocorria ao importar um perfil da Adobe Experience Platform que havia sido excluído do banco de dados.
* Correção de um problema em logs de workflow que poderia exibir um resultado incorreto para o número total de registros importados.

**Correções**

* Correção de um problema com a atividade de workflow **Enriquecimento** que poderia ocorrer ao adicionar espaços no campo **Alias**, o que então criava um novo item de linha. (CAMP-39229)
* Correção de um problema em que cada perfil de teste podia ser direcionado ao enviar uma mensagem de prova.
* Correção de um problema que ocorria após a remoção da publicação e exclusão de uma configuração de evento. [Leia mais](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
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
    <p>Observe que esse recurso só está disponível para clientes hospedados no Azure. Para obter mais informações sobre esse recurso e as condições para ativá-lo, consulte a <a href="../../developing/using/aep-about-data-connector.md">documentação detalhada</a> e o <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">vídeo de instruções</a>.</p>
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
    <p> Observe que esse recurso só está disponível para clientes hospedados no Azure. Para obter mais informações sobre esse recurso e as condições para ativá-lo, consulte a <a href="../../audiences/using/aep-about-audience-destinations-service.md">documentação detalhada</a> e o <a href="https://docs.adobe.com/content/help/pt-BR/campaign-standard-learn/tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.translate.html">vídeo de instruções</a>. </p>
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
* [!DNL Adobe Creative SDK] foi desativada. Ele agora está obsoleto no Campaign Standard. Consulte a página [Recursos descontinuados e removidos](https://helpx.adobe.com/br/campaign/kb/acs-deprecated-and-removed-features.html).


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
