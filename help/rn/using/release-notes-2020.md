---
title: Notas de versão 2020
description: Esta página lista todas as versões 2020 do Adobe Campaign Standard.
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
source-git-commit: d0dde3a445c7047d97c3612b284b9bad36f71539

---


# Notas de versão 2020{#release-notes-2020}

[Planejamento](https://helpx.adobe.com/br/campaign/kb/acs-release-planning.html) da versão| Versões [do Painel](https://docs.adobe.com/content/help/pt-BR/control-panel/using/release-notes.html) de controle| Atualizações [da](../../rn/using/documentation-updates.md) documentação| Notas [de versão](../../rn/using/release-notes-2019.md) anteriores| Recursos [obsoletos](https://helpx.adobe.com/br/campaign/kb/acs-deprecated-and-removed-features.html)

## Versão 20.2 - abril de 2020 {#release-20-2---april-2020}

**Novidades**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integração do Blob do Azure</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>O conector do armazenamento Blob do Azure agora pode ser usado para importar ou exportar dados para o Adobe Campaign usando uma atividade de fluxo de trabalho de arquivo <strong></strong> Transferir. </p>
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
   <td> <p>Além de testar perfis, agora você pode testar seus e-mails em perfis direcionados reais. Isso permite obter uma representação exata da mensagem que o perfil receberá: campos personalizados, informações dinâmicas e personalizadas, incluindo dados adicionais de workflows etc. </p>
    <p>Para obter mais informações, consulte a <a href="../../sending/using/testing-messages-using-target.md">documentação detalhada</a> e o <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">vídeo tutorial</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Novos recursos serão lançados no Painel de Controle de Campanha em abril, incluindo o gerenciamento de registros do Google TXT, monitoramento de espaço do banco de dados e alerta de email. Para obter mais informações sobre esses recursos, consulte a Nota [de versão do Painel de](https://docs.adobe.com/content/help/pt-BR/control-panel/using/release-notes.html)controle.

**Aprimoramentos**

* A experiência do usuário de mensagens transacionais foi aprimorada e a consistência da interface foi aprimorada. [Leia mais](../../channels/using/about-transactional-messaging.md)
* O Campaign Standard agora permite enviar provas para o Teste de perfis usando dados adicionais de workflows.
* As garantias para a atividade de API externa foram atualizadas. [Leia mais](../../automating/using/external-api.md)

**Aprimoramentos do Designer de email**

* Correção de um problema que afetava a fuga ao clicar várias vezes em uma imagem personalizada.
* Correção de um problema ao duplicar componentes de texto dinâmicos que resultava na duplicação da linha errada. (CAMP-41249)
* Correção de um problema com o preenchimento no Outlook ao definir o preenchimento no nível da tabela em vez do nível div.
* Correção de um problema que fazia com que a largura de uma imagem fosse modificada ao alternar para o modo HTML. (CAMP-41116)
* Corrigido um problema que impedia que o componente de mídia social ficasse acessível ao fornecer texto alternativo aos ícones. (CAMP-41345)
* Correção de um problema que fazia com que `<br>` as tags visíveis fossem exibidas ao usar a colagem de cópia no Designer de email.
* Correção de um problema que fazia com que tags HTML fossem exibidas no email após alternar de conteúdo HTML para Texto simples. (CAMP-41138)
* Correção de um problema que impedia a renderização de botões com apenas uma borda definida.
* Corrigido um problema no recuo HTML que fazia com que o rodapé dos emails se movesse para a esquerda no Microsoft Outlook. (CAMP-40987)
* Correção de um problema que fazia com que campos de personalização direcionados a um atributo de coleção definido em HTML fossem copiados no conteúdo de texto simples ao alternar para o modo de texto sem formatação. (CAMP-40365)
* Correção de um problema que impedia a inserção de links em um segmento de texto selecionado. (CAMP-41406)
* Correção de um problema que fazia com que a data fosse alterada ao selecionar um fuso horário no editor de query. (CAMP-38277)

**Outras alterações**

* A Reconciliação de **KPIs com o fluxo de trabalho predefinido do Adobe Analytics** agora é executada até a data atual, em vez de ser executada por um único dia.
* O MCPNS não suporta a adição de APNS e APNS-SANDBOX como plataformas em um aplicativo. Depois de adicionar o certificado com êxito no Adobe Campaign Standard, você não poderá mais alterar suas configurações novamente, pois apenas uma plataforma APNS (produção ou caixa de proteção) pode ser adicionada ao aplicativo MCPNS.

**Integrações da plataforma Experience**

>[!NOTE]
>
>Os recursos da plataforma Adobe Experience no Campaign Standard estão atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Consulte a documentação detalhada: Conector [de dados da plataforma](../../administration/using/aep-about-data-connector.md)Experience, destinos [de Audiência](../../audiences/using/aep-about-audience-destinations-service.md)

* Nos logs de fluxo de trabalho, a cada 10 minutos, a Campanha agora exibe o número de registros já processados pelo trabalho que está sendo executado no momento.
* Correção de um problema que ocorria ao importar um perfil da plataforma Adobe Experience que havia sido excluído do banco de dados.
* Correção de um problema nos logs de fluxo de trabalho, que poderia exibir um resultado incorreto para o número total de registros importados.

**Correções**

* Correção de um problema com a atividade do fluxo de trabalho do **Enriquecimento** que poderia ocorrer ao adicionar espaços no campo **Alias** , que criava um novo item de linha. (CAMP-39229)
* Correção de um problema em que cada perfil de teste podia ser direcionado ao enviar uma mensagem de prova.
* Correção de um problema que ocorria após a despublicação e exclusão de uma configuração de evento. [Leia mais](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* Correção de um problema em que o botão **Salvar** desaparecia ao fazer alterações em workflows.
* Correção de um problema ao excluir uma solicitação de privacidade manualmente na Campanha depois de ela ter sido processada, o que impedia que os dados associados à solicitação fossem excluídos mesmo após a limpeza.
* Correção de um problema que ocorria ao visualizar ou enviar mensagens que incluíam caracteres especiais do Adobe Experience Manager.
* Correção de um problema que ocorria em workflows ao executar uma atividade com várias transições de entrada.
* Correção de um problema que impedia usuários padrão de usar &quot;Subscrições para um aplicativo&quot; como dimensão de público alvo em um query de fluxo de trabalho ou delivery. (CAMP-37618)

## Versão 20.1.4 - fevereiro de 2020 {#release-20-1-4---february-2020}

* Correção de um problema ao abrir uma atividade de Audiência **de** leitura em workflows existentes. (CAMP-41002)

## Versão 20.1.3 - fevereiro de 2020 {#release-20-1-3---february-2020}

* Correção de um problema de regressão apresentado em 20.1 pelo CAMP-39273 para clientes que usam a falha. CAMP-39273 foi revertido.

## Versão 20.1.2 - fevereiro de 2020 {#release-20-1-2---february-2020}

**Aprimoramentos do Designer de email**

* Correção de um problema que adicionava um elemento de tag HTML em um fragmento desatualizado ao corrigir e salvar o conteúdo. (CAMP-40685)
* Correção de um problema que adicionava um espaço ao usar conteúdo dinâmico. (CAMP-40605)
* Correção de um problema ao configurar um modelo de email transacional. (CAMP-40604)

## Versão 20.1 - fevereiro de 2020 {#release-20-1---february-2020}

**Novidades**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Adobe Experience Platform Data Connector (beta)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>O Adobe Experience Platform Data Connector agora é integrado ao Adobe Campaign Standard. Você pode disponibilizar seus dados de Campanha na Adobe Experience Platform mapeando dados XTK (dados ingeridos na Campanha) para o Adobe Experience Platform Data Model (XDM). </p>
    <p>Observe que esse recurso só está disponível para clientes hospedados no Azure. Para obter mais informações sobre esse recurso e as condições para ativá-lo, consulte a documentação <a href="../../administration/using/aep-about-data-connector.md"></a> detalhada e o vídeo <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">de</a>instruções.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Destinos da Audiência (beta) </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Os Destinos da Audiência permitem que você compartilhe segmentos da Adobe Experience Platform para o Adobe Campaign.</p>
    <p>Observe que esse recurso só está disponível para clientes hospedados no Azure. Para obter mais informações sobre esse recurso e as condições para ativá-lo, consulte a documentação <a href="../../audiences/using/aep-about-audience-destinations-service.md"></a> detalhada e o vídeo <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">de</a>instruções. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**Aprimoramentos**

* Disponibilidade global da MTA aprimorada: as mensagens (incluindo mensagens transacionais) agora são enviadas pela MTA aprimorada do Adobe Campaign, que fornece uma infraestrutura de envio atualizada que permite melhor entrega, throughput e tratamento de rejeição. [Leia mais](https://helpx.adobe.com/br/campaign/kb/campaign-enhanced-mta.html)

* O gerenciamento de fuso horário foi aprimorado. Agora você pode definir um fuso horário [](../../automating/using/building-a-workflow.md) específico para um fluxo de trabalho inteiro. O fuso horário selecionado será aplicado a todas as atividades do fluxo de trabalho. As informações sobre o fuso horário que foi configurado para o operador ou o servidor agora são exibidas na interface (em logs e depois de selecionar um fuso horário). (CAMP-37672)

* As APIs de Campaign Standard agora permitem que você execute a paginação ao usar tabelas grandes, adicionando o `_forcePagination=true` parâmetro ao URL da sua chamada. [Leia mais](../../api/using/pagination.md)

* A ID do log de Delivery (que é um identificador exclusivo para cada log) agora está disponível nos recursos de Logs do delivery e Logs de rastreamento para todos os targeting dimension. Isso permite identificar logs de rastreamento ou envios ao exportar, por exemplo. [Leia mais](../../automating/using/exporting-logs.md)

**Aprimoramentos do Designer de email**

* Foram adicionadas instruções de texto obrigatórias ausentes ao criar uma Audiência.
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

* O filtro &quot;Delivery com falha na preparação&quot; agora leva em conta a data de criação dos delivery em vez da data da última modificação.
* A unidade organizacional do grupo de segurança Administradores não pode mais ser alterada.
* Ao criar um perfil, o campo Unidade organizacional deve ser preenchido.
* Um Acionador da Experience Cloud agora só pode ser excluído se o evento e o modelo transacional vinculados forem excluídos.
* O Adobe Creative SDK foi descontinuado. Agora está obsoleto no Campaign Standard. Consulte a página Recursos [](https://helpx.adobe.com/br/campaign/kb/acs-deprecated-and-removed-features.html)obsoletos e removidos.


**Correções**

* Correção de um problema ao executar uma solicitação de privacidade de exclusão que impedia que os dados do usuário fossem excluídos nos logs de exclusão. (CAMP-39003)
* Correção de um problema que resultava em problemas de acessibilidade ao redimensionar o texto em um elemento de container.
* Correção de um problema que impedia os usuários de descartarem o pop-up Calendário exibido ao passar o mouse nas atividades de marketing.
* Correção de um problema na **[!UICONTROL External API]** atividade que exibia o **[!UICONTROL Confirm]** botão mesmo quando nenhum dado era modificado.
* Correção de um problema ao usar uma **[!UICONTROL Union]** atividade em query com diferentes dimensões de público alvo. Os dados de transição mostravam apenas registros do targeting dimension do conjunto principal. (CAMP-36831)
* Correção de um problema que resultava em erro ao usar uma **[!UICONTROL Reconciliation]** atividade em contextos específicos, por exemplo, com duas atividades de entrada, uma delas sendo uma atividade de exclusão. (CAMP-37490)
* Correção de problemas de desempenho que podem ocorrer ao selecionar e atualizar perfis de teste. (CAMP-37976)
* Correção de um problema que podia exibir páginas de erro ao assinar ou cancelar a inscrição via landing page. (CAMP-37771)
* Correção de um problema que ocorria ao carregar conteúdo no formato zip, com arquivos PNG referenciados no HTML com sua extensão em letras maiúsculas. (CAMP-37913)
* Correção de um problema que impedia o envio de mensagens no aplicativo ao adicionar um perfil de teste ao delivery.
* Correção de um erro com a atividade de fluxo de trabalho da API externa que falhava quando vinculada ao enriquecimento atividade.
* Correção de um problema que resultava na exibição incorreta do status das mensagens SMS.
* Correção de um problema com recursos personalizados que fazia com que entradas de duplicado fossem exibidas em diferentes pontos de extremidade da API.
* Correção de um problema que impedia que landings page ficassem disponíveis após a publicação. (CAMP-38695)
* Correção de um erro que ocorria ao exibir dados de uma transição de Intersecção provenientes de dois recursos diferentes. (CAMP-38974)
* Correção de um problema que fazia com que o valor de lista discriminada em um template do delivery fosse definido incorretamente. (CAMP-38388)
* Correção de um erro com delivery em massa de email que exibiam o estado dos delivery como Pendente e o status Enviado como Concluído. (CAMP-35355)
* Correção de um erro que exibia o domínio do remetente incorretamente no relatórios dinâmico. (CAMP-33123)
* Correção de um problema que causava discrepância na contagem de Unsubscription no relatórios dinâmico. (CAMP-39949)
* Correção de um problema que impedia a exibição de endereços na tela Enviar registros ao enviar mensagens no aplicativo.
* Correção de um problema que impedia que o SMS enviasse logs fosse atualizado com o número correto de rejeições. (CAMP-38395)
* Corrigida uma falha que permitia que as chamadas de postagem de subscrição do aplicativo atualizassem os tokens de notificação por push. (CAMP-39273)
