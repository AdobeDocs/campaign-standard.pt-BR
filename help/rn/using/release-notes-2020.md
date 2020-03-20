---
title: Notas de versão mais recentes de 2020
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
source-git-commit: a6b0dd550dc0f6815cbf25f03fd199f4105de9c3

---


# Versão mais recente{#latest-release}

[Planejamento](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) da versão| Versões [do Painel](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) de controle| Atualizações [da](../../rn/using/documentation-updates.md) documentação| Notas [de versão](../../rn/using/release-notes-2019.md) anteriores| Recursos [obsoletos](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## Versão 20.1.4 - fevereiro de 2020 {#release-20-1-4---february-2020}

* Correção de um problema ao abrir uma atividade **Ler público** -alvo em fluxos de trabalho existentes. (CAMP-41002)

## Versão 20.1.3 - fevereiro de 2020 {#release-20-1-3---february-2020}

* Correção de um problema de regressão apresentado em 20.1 pelo CAMP-39273 para clientes que usam a falha. CAMP-39273 foi revertido.

## Versão 20.1.2 - fevereiro de 2020 {#release-20-1-2---february-2020}

**Aprimoramentos do Designer de email**

* Correção de um problema que adicionava um elemento de tag HTML em um fragmento desatualizado ao corrigir e salvar o conteúdo. (CAMP-40685)
* Correção de um problema que adicionava um espaço ao usar conteúdo dinâmico. (CAMP-40605)
* Correção de um problema ao configurar um modelo de email transacional. (CAMP-40604)

## Versão 20.1 - fevereiro de 2020 {#release-20-1---february-2020}

**Novidades?**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Adobe Experience Platform Data Connector (beta)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>O Adobe Experience Platform Data Connector agora é integrado ao Adobe Campaign Standard. Você pode disponibilizar os dados do Campaign na Adobe Experience Platform mapeando os dados XTK (dados ingeridos no Campaign) para o Adobe Experience Platform Data Model (XDM). </p>
    <p>Observe que esse recurso só está disponível para clientes hospedados no Azure. Para obter mais informações sobre esse recurso e as condições para ativá-lo, consulte a documentação <a href="../../administration/using/aep-about-data-connector.md"></a> detalhada e o vídeo <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">de</a>instruções.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Destinos do público-alvo (beta) </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Os Destinos de público-alvo permitem que você compartilhe segmentos da Adobe Experience Platform para o Adobe Campaign.</p>
    <p>Observe que esse recurso só está disponível para clientes hospedados no Azure. Para obter mais informações sobre esse recurso e as condições para ativá-lo, consulte a documentação <a href="../../audiences/using/aep-about-audience-destinations-service.md"></a> detalhada e o vídeo <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">de</a>instruções. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**Aprimoramentos**

* Disponibilidade global da MTA aprimorada: mensagens (incluindo mensagens transacionais) agora são enviadas pelo MTA aprimorado do Adobe Campaign, que fornece uma infraestrutura de envio atualizada que permite melhor entrega, throughput e tratamento de rejeição. [Leia mais](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)

* O gerenciamento de fuso horário foi aprimorado. Agora você pode definir um fuso horário [](../../automating/using/building-a-workflow.md) específico para um fluxo de trabalho inteiro. O fuso horário selecionado será aplicado a todas as atividades do fluxo de trabalho. As informações sobre o fuso horário que foi configurado para o operador ou o servidor agora são exibidas na interface (em logs e depois de selecionar um fuso horário). (CAMP-37672)

* As APIs do Campaign Standard agora permitem que você execute a paginação ao usar tabelas grandes, adicionando o `_forcePagination=true` parâmetro ao URL da sua chamada. [Leia mais](../../api/using/pagination.md)

* A ID do log de entrega (que é um identificador exclusivo para cada log) agora está disponível nos recursos de logs de entrega e de rastreamento para todas as dimensões de direcionamento. Isso permite identificar o envio ou o rastreamento de registros ao exportar, por exemplo. [Leia mais](../../automating/using/exporting-logs.md)

**Aprimoramentos do Designer de email**

* Foram adicionadas instruções de texto obrigatórias ausentes ao criar um Público-alvo.
* Correção de um problema ao clicar no botão **Alterar conteúdo** no assistente do editor de email herdado.
* Correção de um problema que impedia que os cabeçalhos fossem alinhados com o conteúdo no relatório Resumo do serviço. (CAMP-38103)
* Correção de um problema que impedia que variantes de conteúdo dinâmico fossem excluídas sem afetar o restante da linha de assunto. (CAMP-40096)
* Correção de um problema de teste A/B ao usar a variante B na linha de assunto. (CAMP-40327)
* Correção de um problema que impedia arrastar e soltar arquivos ao usar o recurso de importação Carregar HTML. (CAMP-39326)
* Correção de um problema que impedia a cópia e colagem de texto de um editor de texto. (CAMP-39028)
* Correção de um problema que impedia a exibição de sugestões de palavras. (CAMP-38970)
* Correção de um problema que impedia os usuários de salvar fragmentos. (ATU-2447)
* Correção de um problema que impedia a duplicação de estruturas dinâmicas. (CAMP-38367)
* Correção de um problema que impedia que o conteúdo dinâmico retivesse condições ao duplicar. (CAMP-39051)

**Outras alterações**

* O filtro &quot;Falha na preparação das entregas&quot; agora leva em conta a data de criação das entregas em vez da última data de modificação.
* A unidade organizacional do grupo de segurança Administradores não pode mais ser alterada.
* Ao criar um perfil, o campo Unidade organizacional deve ser preenchido.
* Um Acionador da Experience Cloud agora só pode ser excluído se o evento e o modelo transacional vinculados forem excluídos.
* O Adobe Creative SDK foi descontinuado. Agora está obsoleto no Campaign Standard. Consulte a página Recursos [](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)obsoletos e removidos.


**Correções**

* Correção de um problema ao executar uma solicitação de privacidade de exclusão que impedia que os dados do usuário fossem excluídos nos logs de exclusão. (CAMP-39003)
* Correção de um problema que resultava em problemas de acessibilidade ao redimensionar o texto em um elemento de contêiner.
* Correção de um problema que impedia os usuários de descartarem o pop-up Calendário exibido ao passar o mouse nas atividades de marketing.
* Correção de um problema na **[!UICONTROL External API]** atividade que exibia o **[!UICONTROL Confirm]** botão mesmo quando nenhum dado era modificado.
* Correção de um problema ao usar uma **[!UICONTROL Union]** atividade em consultas com diferentes dimensões de destino. Os dados de transição exibiam somente registros da dimensão de definição de metas do conjunto principal. (CAMP-36831)
* Correção de um problema que resultava em erro ao usar uma **[!UICONTROL Reconciliation]** atividade em contextos específicos, por exemplo, com duas atividades de entrada, uma delas sendo uma atividade de exclusão. (CAMP-37490)
* Correção de problemas de desempenho que podem ocorrer ao selecionar e atualizar perfis de teste. (CAMP-37976)
* Correção de um problema que podia exibir páginas de erro ao assinar ou cancelar a assinatura por páginas de aterrissagem. (CAMP-37771)
* Correção de um problema que ocorria ao carregar conteúdo no formato zip, com arquivos PNG referenciados no HTML com sua extensão em letras maiúsculas. (CAMP-37913)
* Correção de um problema que impedia o envio de mensagens no aplicativo ao adicionar um perfil de teste à entrega.
* Correção de um erro na atividade de fluxo de trabalho da API externa que falhava quando vinculada a atividades de enriquecimento.
* Correção de um problema que resultava na exibição incorreta do status das mensagens SMS.
* Correção de um problema com recursos personalizados que fazia com que entradas duplicadas aparecessem em diferentes pontos de extremidade da API.
* Correção de um problema que impedia que páginas de aterrissagem ficassem disponíveis após a publicação. (CAMP-38695)
* Correção de um erro que ocorria ao exibir dados de uma transição de Interseção provenientes de dois recursos diferentes. (CAMP-38974)
* Correção de um problema que fazia com que o valor de enumeração em um modelo de entrega fosse definido incorretamente. (CAMP-38388)
* Correção de um erro com entregas em massa de email que exibiam o estado das entregas como Pendente e o status Enviado como Concluído. (CAMP-35355)
* Correção de um erro que exibia o domínio do remetente incorretamente no Relatório dinâmico. (CAMP-33123)
* Correção de um problema que causava discrepância nas contagens de Cancelamento de assinatura nos relatórios dinâmicos. (CAMP-39949)
* Correção de um problema que impedia a exibição de endereços na tela Enviar registros ao enviar mensagens no aplicativo.
* Correção de um problema que impedia que o SMS enviasse logs fosse atualizado com o número correto de rejeições. (CAMP-38395)
* Corrigida uma falha que permitia que as chamadas de postagem de assinatura do aplicativo atualizassem os tokens de notificação por push. (CAMP-39273)
