---
title: Notas de versão
seo-title: Notas de versão
description: Notas de versão
seo-description: Esta página lista todas as versões recentes do Adobe Campaign Standard.
page-status-flag: nunca ativado
uuid: 1 cf 2 e 40 c-beca -43 db -8261-a 1820 ee 86 ad 3
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: versões padrão da campanha
discoiquuid: 5 c 7 bfb 74-4002-4 ffe -87 e 8-bddb 41 d 34 b 41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8c1e17942d03250bbe863b2b57a0c810eaec6fa3

---


# Release Notes{#release-notes}

Procurando uma versão específica do Adobe Campaign Standard?

Cada versão traz novos recursos e correções. Clique em uma versão para exibir seu conteúdo. Consult the [Release Planning](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) to find out when the next release will happen.

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a previous release, consult these pages: [2018 Release Notes](../../rn/using/release-notes-2018.md), [2017 Release Notes](../../rn/using/release-notes-2017.md), [2015-2016 Release Notes](../../rn/using/release-notes-2015-2016.md). Also consult the list of [Deprecated and Removed Features](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html).

## Release 19.3 - July 2019 {#release-19-3---july-2019}

### What's new? {#what-s-new-3}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> External API Activity (Public Beta)<br /> </td> 
   <td> <p>Para personalização mais profunda, a Atividade de API externa permite que você coloque dados de sistemas externos em um fluxo de trabalho por meio de uma chamada REST API. Os pontos finais REST podem ser um sistema de gerenciamento de cliente, Adobe I/O Runpoint ou terminal REST da Adobe Experience Cloud (por exemplo, Plataforma de dados, Target, Analytics, Campanha).</p><p>No momento, esse recurso está em beta público.</p><p>For more information, refer to the <a href="../../automating/using/external-api.html">detailed documentation</a> and the <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">how-to video</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Report on workflow segment<br /> </td> 
   <td> <p>Esse recurso permite que os profissionais de marketing analisem o desempenho de entrega por código de segmento. Quando você cria um fluxo de trabalho e usa uma atividade de segmentação para atribuir segmentos à população de entrega, esses segmentos agora podem entrar na mesma entrega. Isso permite exibir as estatísticas de aberturas/cliques com base em vários segmentos em uma única entrega.</p><p>For more information, refer to the <a href="../../reporting/using/creating-a-report-workflow-segment.md">detailed documentation</a> and the <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">how-to video</a>.</p></td>
  </tr> 
 </tbody> 
</table>

### Security enhancements {#security-enhancements-2}

* Correção de um problema de segurança para impedir ataques de negação de serviço (DoS) em solicitações inválidas para obter imagens. (CAMP -33454)

### Email Designer enhancements {#email-designer-enhancements-3}

* Correção de um problema que adicionava tags de estilo HTML adicionais a um modelo HTML sempre que um componente era adicionado, o que poderia aumentar consideravelmente o tamanho do modelo. (CAMP -34694)
* Correção de um problema que poderia impedir que algumas opções de menu da barra de ferramentas à direita fossem disponibilizadas. (CAMP -34577)
* Correção de um problema que ocorria quando o bloco de conteúdo de URL da página Espelho era inserido em um conteúdo de email. (CAMP -34779)
* Correção de um problema que ocorria ao usar o código JSPP em um email, dificultando a edição do conteúdo. (CAMP -34574)
* Correção de um problema que resultava em imagens truncadas na parte superior quando um hiperlink era adicionado a eles. (CAMP -34382)
* Correção de um problema de exibição ao usar o Designer Designer com Firefox. (CAMP -34364)
* Corrigidos vários problemas que ocorria com o modo Avançado ao definir o conteúdo dinâmico em um email. (CAMP -34351, CAMP -34333, CAMP -34331)
* Corrigidos vários problemas que ocorria com o editor de regras de conteúdo dinâmico (CAMP -34304, CAMP -34303).
* Correção de um problema que podia impedir a exibição do campo Link no painel Configurações do Designer de email (CAMP -33749).
* Correção de um problema com o ícone do youtube que era muito grande em emails enviados. (CAMP -33726)
* Correção de um problema de segurança que fazia com que o conteúdo da página espelhada fosse editável. (CAMP -33691)
* Correção de um problema que quebrava a saída HTML ao usar o símbolo maior do que o símbolo dinâmico. (CAMP -33688)
* Correção de um problema que ocorria ao usar a opção Desfazer ao editar texto no Designer de email. (CAMP -32565)
* Correção de um problema que criava tags extras ao desfazer estilos em vez de removê-los. (CAMP -32359)
* Agora você pode definir se cada componente usado em um email será exibido apenas em dispositivos de desktop ou apenas em dispositivos móveis.
* Agora é possível definir a largura e a altura de um componente de conteúdo do Social.
* Correção de um problema que impedia a remoção do código fonte antigo do conteúdo dinâmico após a exclusão desse conteúdo dinâmico.
* Correção de um problema que podia impedir que o assunto de um email fosse atualizado após a modificação.
* Correção de um problema que impedia um n: a estrutura da coluna n de ser selecionada uma vez solta na área de trabalho.
* Correção de um problema que fazia com que a miniatura da mensagem aparecesse desfocada no painel de e-mail.
* Correção de um problema que impedia a exibição correta do plano de fundo para emails recebidos no Outlook.
* Correção de alguns problemas de classificação na página inicial do Designer de email.
* Correção de um problema que ocorria na duplicação de variantes ao usar conteúdo dinâmico.
* Alguns campos indesejados foram removidos do painel Configurações do Designer de email.

### Other improvements {#other-improvements-3}

* Por meio da integração com os Serviços de localização da Adobe Experience Platform, o Adobe Campaign agora é compatível com enviar mensagens de marketing baseadas na localização aos assinantes do aplicativo móvel por meio do SDK da plataforma de experiência. For more information, refer to the [detailed documentation](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md).
* O recurso de relatório foi aprimorado para obter uma melhor experiência. Para usar esse recurso, você precisa aceitar o Contrato de uso de relatórios dinâmicos. For more on this, refer to the [detailed documentation](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* Nos fluxos de trabalho, uma nova opção foi adicionada para visualizar as próximas dez execuções de um fluxo de trabalho. For more on this, refer to the [detailed documentation](../../automating/using/scheduler.md).
* Na atividade do Agendador, uma nova opção permite selecionar um dia específico de uma semana específica para entregas mensais. For more on this, refer to the [detailed documentation](../../automating/using/scheduler.md).
* Ao criar entregas recorrentes sem período de agregação, o painel de entrega agora permite que você solicite confirmação antes que a entrega seja enviada. For more on this, refer to the [detailed documentation](../../sending/using/confirming-the-send.md).
* Agora é possível personalizar o rótulo de uma entrega com variáveis de evento declaradas na atividade de sinal externo do fluxo de trabalho. For more on this, refer to the [detailed documentation](../../automating/using/calling-a-workflow-with-external-parameters.md).
* A consulta de exclusão do RGPD foi aprimorada para melhorar o desempenho. (CAMP -33504)
* A opção «ftp» foi removida da interface de configuração da conta externa. (CAMP -34472)
* Agora você pode ativar e desativar a opção do modo de teste SMTP para cada mensagem de email. For more on this, refer to the [detailed documentation](../../administration/using/configuring-email-channel.md#smtp-test-mode). (CAMP -34602)

### Other changes {#other-changes-2}

* Um aviso foi adicionado na interface de propriedades de entrega. Ele especifica que as entregas são preparadas com base no período de agregação e se descobrem para chamar o fluxo de trabalho várias vezes por dia, caso não tenham um período. (CAMP -34393)
* Um aviso foi adicionado nas telas de configuração de recurso personalizadas. Recomendamos usar 30 caracteres para IDs de recurso personalizadas. Isso também se aplica a campos de recursos personalizados, chaves, índices e links.
* Uma mensagem agora aparece ao tentar excluir uma mensagem transacional usada por uma página de aterrissagem como uma mensagem de confirmação.
* Um aviso agora aparece nos registros de fluxos de trabalho quando uma atividade está sendo executada por mais de 6 horas. Isso não se aplica às atividades de Notificação por push, Entrega, Sinal de início, Início, Fim, Fork, Conexão e Espera.
* Um aviso agora aparece nos registros de fluxos de trabalho quando você atinge o número máximo de fluxos de trabalho que estão sendo executados simultaneamente.
* Os fluxos de trabalho que foram pausados ou reprovados por mais de 7 dias agora são interrompidos para consumir menos espaço em disco. A tarefa de limpeza é exibida nos registros de fluxo de trabalho.
* Ao usar uma atividade de «Transferir arquivo», um erro agora é registrado se o tamanho do arquivo exceder o espaço disponível em disco.
* A ação Redirecionar para URL de destino não pode mais ser selecionada para o botão secundário nas mensagens no aplicativo.

### Patches {#patches-3}

* Correção de um problema que fazia com que as solicitações de acesso do RGPD falhassem.
* Corrigido um problema que fazia com que disparadores fossem descartados quando vários disparadores eram recebidos para um perfil único.
* Correção de um problema que resultava em uma mensagem de erro de publicação de recurso personalizado incorreta após o login.
* Correção de um problema que exibia uma página em branco ao criar ou estender um recurso personalizado.
* Correção de um problema que impedia que um público com appsubscriptionrcp como a dimensão de definição de metas ficasse disponível para direcionamento em uma entrega móvel.
* Correção de um erro que impedia que os endereços de e-mail de retorno fossem colocados em quarentena. (CAMP -24587)
* Correção de um problema que ocorria ao adicionar uma regra de tipologia e depois excluí-la antes de salvar a tipologia. (CAMP -32789)
* Correção de um problema que podia impedir a exibição do conteúdo da página de aterrissagem ao desativar o conteúdo dinâmico. (CAMP -32924)
* Correção de um problema com entregas recorrentes que ocorria ao usar a personalização nos atributos de uma entrega mestre. (CAMP -32983)
* Correção de um problema em fluxos de trabalho que impossibilitava a leitura de resultados de uma transição contendo dados de mensagens SMS recebidas. (CAMP -33134)
* Correção de um problema em fluxos de trabalho que ocorria ao combinar atividades de fork e exclusão para criar públicos-alvo. (CAMP -33401)
* Correção de um problema que impedia que o conteúdo da página espelhada fosse exibido e que as mensagens de prova fossem enviadas para entregas recorrentes. (CAMP -33413)
* Correção de um problema que resultava em erro ao usar uma atividade da União entre perfis e públicos-alvo. Esse problema foi causado por uma incompatibilidade das teclas de identificação nas transições de entrada. (CAMP -33713)
* Correção de um problema nas atividades Testar que impedia a expressão "reccount" de usar a sintaxe correta ao clicar duas vezes nele. (CAMP -33756)
* Correção de um problema que resultava em uma mensagem de erro ao abrir os logs de fluxo de trabalho técnico Faturamento. (CAMP -34313)
* Correção de um problema em páginas de aterrissagem que ocorria ao configurar campos da caixa de seleção com assinaturas. (CAMP -34369)
* Correção de um problema que ocorria ao configurar uma lista e adicionar o campo "ícone" a ele. (CAMP -34585)
* Correção de um problema que impedia o uso de|símbolos "e" % "como separadores de data ou hora em carregar atividades do fluxo de trabalho de arquivo. (CAMP -34706)
* Correção de um problema que ocorria ao usar condições de visibilidade com caixas de seleção em páginas de destino. (CAMP -34802)
* Correção de um problema na atividade de Enriquecimento que impedia a exibição dos campos na guia «Dados adicionais», se a dimensão de filtragem fosse definida para rastrear logs e a dimensão de destino ao perfil.
* Correção de um problema que resultava em uma mensagem de erro ao exportar um recurso "workflowtemplate".
* Correção de um problema ao criar um novo perfil, que impedia que o campo "Código/região do código" fosse salvo se fosse selecionado na caixa de diálogo.
* Corrigidos vários problemas que ocorria ao usar o modelo de importação de Correspondência direta (updatequarantinesdeliverylogsmail).
* Correção de um problema relacionado à integração de Ativos sob demanda.
* Correção de um problema que ocorria ao ampliar na exibição Linha do tempo. (CAMP -33628)
* Correção de um problema que impedia que os testes fossem enviados instantaneamente para mensagens de email com uma data e hora programadas. (CAMP -33723)
* Correção de um problema relacionado à mensagem transacional que gerava registros de erro quando um usuário era desconectado. (CAMP -31698)
* Correção de um erro que ocorria em ambientes específicos ao agendar uma mensagem de email.
* Correção de um problema que causava a falha do fluxo de trabalho da execução da entrega Atualizar.
* Correção de um problema de segurança que quebrou o conteúdo de email quando o assunto continha várias linhas.


## Release 19.2.7 - July 2019 {#release-19-2-7---july-2019}

### Improvements {#improvements-2}

* A consulta de exclusão do RGPD foi aprimorada para melhorar o desempenho.
* Correção de um problema que causava falhas na Web após a atualização 19.2. (CAMP -34862)
* Correção de um problema que podia impedir que usuários não administradores salvassem ou agendassem relatórios. (CAMP -31133)
* Corrigido um problema ao usar "|" como separador de data na atividade do fluxo de trabalho do arquivo Carregar. (CAMP -34706)

## Release 19.2.4 - June 2019 {#release-19-2-4---june-2019}

### Email Designer {#email-designer-2}

* Correção de um problema que impedia os usuários de editar fragmentos quando tags de estilo vazias eram usadas no HTML. Esta é uma correção de acompanhamento para o CAMP CAMP 778 in em 19.2.3.

## Release 19.2.3 - June 2019 {#release-19-2-3---june-2019}

### Email Designer {#email-designer-1}

Introduziu uma série de aprimoramentos e correções para otimizar fragmentos na versão 19.2. Os fragmentos recém-criados funcionarão perfeitamente. Os fragmentos criados anteriormente ficaram esmaecidos e precisam ser migrados para o novo formato. Para fazer isso, clique em cada fragmento e valide sua migração para o novo formato. Recomendamos que você teste alguns fragmentos antes de migrar todos os fragmentos.

* Correção de um problema que impedia os usuários de editar um fragmento depois de desbloquear. Isso afetava fragmentos existentes ao atualizar para 19.2. (CAMP -33778)
* Correção de um problema ao usar conteúdo dinâmico. Espaços extras foram adicionados ao HTML.

### Other improvements {#other-improvements-2}

* Correção de um problema que podia impedir que o envio de SMS fosse retomado após uma desconexão do conector SMS.
* Correção de um problema que podia fechar conexões SMPP quando TLS estava ativado.
* Correção de um problema que podia fechar conexões SMPP quando TLS estava ativado.
* A opção «Launch_ URL_ Campaign» foi adicionada no Campaign para gerenciar propriedades de aplicativos móveis criados com o SDK da Adobe Experience Platform Mobile.
* Corrigido um erro que fazia com que a opção de ambiente da Caixa de proteção fosse desmarcada após o upload do certificado de uma propriedade móvel recém-criada e sair da página de propriedade do aplicativo móvel.
* Correção de um problema que impedia o enriquecimento de um conteúdo de mensagem transacional com informações do recurso Serviço. (CAMP -33707)
* Correção de um problema nas páginas de aterrissagem da Lista negra que ocorria ao cancelar a inscrição de perfis de um serviço.

## Release 19.2 - May 2019 {#release-19-2---may-2019}

### What's new? {#what-s-new-}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Control Panel<br /> </td> 
   <td> <p>Para ajudar a aumentar a eficiência do seu trabalho como usuário administrador, você pode monitorar facilmente a capacidade e gerenciar as configurações de suas instâncias (começando pelo gerenciamento de servidores SFTP).</p><p>For more information, refer to the <a href="https://helpx.adobe.com/campaign/kb/control-panel.html">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-control-panel-video-use.html">how-to video</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Local notifications<br /> </td> 
   <td> <p>As mensagens de notificação local permitem informar os usuários quando os novos dados tornam-se disponíveis em seus aplicativos móveis, mesmo sem ter acesso à Internet ou ao aplicativo móvel em execução em primeiro plano. As notificações locais são acionadas por um aplicativo móvel em um determinado momento e dependendo de um evento.</p><p>For more information, refer to the <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">detailed documentation</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Workflow enhancement - Add a payload to external signal activity<br /> </td> 
   <td> <p>Inicie um fluxo de trabalho com uma carga quando as condições definidas forem cumpridas com êxito de outro fluxo de trabalho ou uma chamada REST API para integrar com seus sistemas externos. This also includes a new <strong>test</strong> activity where you can run tests on this functionality.</p><p>For more information, refer to the <a href="../../automating/using/calling-a-workflow-with-external-parameters.md">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-external-signal-activity-feature-video-use.html">how-to video</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Landing Pages enhancement - Google reCAPTCHA<br /> </td> 
   <td> <p>Aproveite o Google recaptcha para evitar spam em suas páginas de aterrissagem sem nenhuma ação de seus clientes.</p><p>For more information, refer to the <a href="../../channels/using/designing-a-landing-page.md#setting-google-recaptcha">detailed documentation</a>.</p></td> 
  </tr> 
 </tbody> 
</table>

### Security enhancements {#security-enhancements}

* Correção de um possível problema de segurança de clickjacking na área de trabalho do relatório.

### Email Designer enhancements {#email-designer-enhancements}

* Correção de um problema que ocorria ao duplicar fragmentos e tentar usá-los no Designer de email. (CAMP -33193)
* Correção de um problema que criava espaços indesejados ao usar elementos em linha na interface do Designer de email. (CAMP -32163)
* Correção de um problema que excluía alguns atributos de tag HTML adicionais adicionados pelo usuário depois de salvar o conteúdo de email no Designer de email. (CAMP -32162)
* Correção de um problema que exibia uma tag do Microsoft Office no modo HTML do Designer de email mesmo depois de removê-lo. (CAMP -32141)
* Se você criou um email usando uma versão anterior do Designer de email, ao abrir este conteúdo de email, uma janela pop-up solicita que o usuário atualize para a versão mais recente. (CAMP -31529)
* Correção de um problema que poderia distorcer imagens de um email criado com o Designer de email quando fornecido para alguns clientes de mensagens. (CAMP -31407)
* Correção de um problema que impedia que alguns elementos, como listas ou botões, fossem exibidos corretamente no modo de texto simples quando criado no modo HTML. (CAMP -32582, CAMP -32542)
* Correção de um problema que impedia a exibição de mais de 50 unidades organizacionais em um modelo de conteúdo ou propriedades do fragmento. (CAMP -32932)
* Correção de um problema com a cor de fundo do visor ao receber um e-mail criado com o Designer do email no Outlook. (CAMP -31402)
* Correção de um problema que podia impedir que conteúdo de email criado com o Designer de e-mail fosse responsivo quando aberto no Outlook. (CAMP -31400)
* Correção de um problema que impedia o funcionamento correto do conteúdo dinâmico quando usado em um assunto de email. (CAMP -32837)
* Correção de um problema relacionado ao assunto do email que não era devidamente ignorado.
* Correção de um problema que impedia o carregamento de fragmentos na paleta esquerda do Designer de email.
* Correção de um problema que impedia que fragmentos criados durante a edição de conteúdo por email fossem exibidos na paleta esquerda do Designer ao atualizar a lista de fragmentos.
* Corrigidos vários problemas que ocorria ao usar o conteúdo dinâmico em um email.
* Correção de um problema que ocorria com o seletor de cores ao tentar definir uma cor usando valores RGB.
* Correção de um problema que impedia que a página espelhada fosse responsiva ao receber o e-mail em um dispositivo móvel.

### Transactional Messaging enhancements {#transactional-messaging-enhancements}

Várias melhorias foram adicionadas ao canal de mensagens transacionais para otimizar operações e desempenho.

* A duração da mensagem transacional foi estendida para garantir que todas as mensagens sejam enviadas antes que expirem, especialmente quando as tentativas são realizadas.
* O desempenho transacional de mensagens foi aumentado distribuindo a carga em diferentes threads de envio.
* O processo transacional de mensagem foi otimizado para ser iniciado em paralelo múltiplas análises da mesma mensagem.
* Solucionado o problema que gerava uma latência e latência inconsistentes para notificações por push transacionais.
* Correção de um problema que exibia um público-alvo incorreto para entregas de execução de mensagem transacionais.
* Correção de um problema que ocorria ao importar um pacote com uma configuração de evento e a mensagem transacional associada. For more on this, refer to the [detailed documentation](../../channels/using/about-transactional-messaging.md#exporting-and-importing-transactional-messages).
* Correção de um problema que excluía os dados da coleção dos perfis de teste criados para uma mensagem transacional contendo listagens de produtos.

### Other changes {#other-changes}

* Uma nova opção foi adicionada à conta externa SMS. Ele permite limitar o número máximo de processos MTA que enviam SMS para controlar melhor o número de conexões paralelas. For more information, refer to the [SMS connector protocol and settings](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html) technote.
* Ao publicar um recurso com a extensão da API, se a API já tiver sido publicada, ela será automaticamente atualizada sempre que for publicada novamente. Anteriormente, essa ação era manual e a atualização da API podia quebrar o perfil ou o recurso de serviço dessa API. For more on this, refer to the [detailed documentation](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* A dimensão de código postal foi removida de Relatórios dinâmicos. Em vez disso, recomendamos usar as dimensões Cidade, País, Estado.
* O acionador do evento «Primeira inicialização» do evento de ciclo de vida para mensagens no aplicativo foi removido.
* Ao exportar um pacote com grupos de segurança, ele agora contém as funções atribuídas a cada grupo. (CAMP -32960)
* Na atividade do arquivo Carregar, uma nova opção permite verificar se as colunas do arquivo que você está carregando correspondem à definição da coluna. For more information, refer to the [detailed documentation](../../automating/using/load-file.md). (CAMP -32229)
* Os fluxos de trabalho agora podem ser iniciados com uma carga, permitindo usar e compartilhar parâmetros externos entre as atividades dentro do fluxo de trabalho. For more information, refer to the [detailed documentation](../../automating/using/calling-a-workflow-with-external-parameters.md). (CAMP -29412 e CAMP -29413)
* As apis do Campaign Standard agora permitem atualizar unidades geográficas e organizacionais de perfis usando uma carga. For more information, refer to the [detailed documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).
* Mensagens de erro quando um objeto do banco de dados não puder ser acessado ficou mais claro para ser entendido.
* Na atividade de arquivo Extrair, os recursos do Javascript foram atualizados ao definir o nome de um arquivo a ser exportado. Apenas a função formatdate agora está disponível para uso no campo Saída. For more information, refer to the [detailed documentation](../../automating/using/extract-file.md).
* A geração da ID de sequência automática foi aprimorada para recursos personalizados. Chaves primárias para novos recursos personalizados agora estão em 64 bits por padrão.
* O modo de teste de publicação de recurso personalizado foi aprimorado. Uma mensagem de aviso agora é exibida aos usuários se a última publicação de recursos personalizados falhar e não for fixa. Após uma falha de publicação de recursos personalizados, você pode reverter para a última versão de trabalho. For more information, refer to the [detailed documentation](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
* Uma nova opção foi adicionada na atividade de arquivo Transferir. Isso permite que você classifique os arquivos ao usar a ação de download de Arquivo no modo SFTP. For more information, refer to the [detailed documentation](../../automating/using/transfer-file.md). (CAMP -33109)

### Patches {#patches}

* Correção de um problema que causava o vazamento de memória para a MTA quando as configurações de SMS eram recarregadas.
* Correção de um problema que podia impedir a publicação de atualizações de banco de dados em modo de reparo.
* Correção de um problema que causava a discrepância entre Relatórios do Adobe Analytics e Relatórios dinâmicos do Adobe Campaign. (CAMP -25393)
* Corrigido um erro que causava a falha do fluxo de trabalho de compartilhamento de relatório.
* Correção de um erro que impedia os usuários de enviarem mensagens no aplicativo com apenas o URL de mídia.
* Correção de um problema que exibia um aplicativo móvel mesmo que seu certificado não fosse carregado na instância.
* Fixed an error that prevented personalization fields from working when using the **Target all users of a Mobile app** template.
* Novas instâncias do Campaign Standard foram fornecidas. (CAMP -32635 e CAMP -32344)
* Correção de um erro que impedia a personalização da fórmula de data em um fluxo de trabalho. (CAMP -30336)
* Correção de um problema ao definir uma fórmula de data personalizada que podia impedir que os campos "Dados adicionais" e "Código do segmento" ficassem disponíveis na lista suspensa. (CAMP -32383)
* Correção de um problema que podia impedir que as atividades "Transferir arquivo" e "Extrair arquivo" localizassem os arquivos se estivessem criptografadas. (CAMP -32377)
* Correção de um problema em apis que podia impedir que o filtro linecount fizesse a renderização da contagem total exata. (CAMP -31424)
* Correção de um problema em páginas de aterrissagem que podia impedir que campos de entrada mostrassem o valor atualizado após a modificação. (CAMP -31401)
* Correção de um problema que fazia com que uma atividade de sinal fosse ativada de forma inesperada.
* Correção de um problema que impedia a exibição de visualização de email quando o público-alvo estava vazio.
* Correção de um problema na atividade «Extract file» que podia gerar um arquivo enquanto a opção «Não gerar um arquivo se a transição de entrada estava vazia» foi ativada.
* Correção de um problema que fazia com que o fluxo de trabalho de Entrega desativasse se não fosse concluído com sucesso.
* Correção de um problema que podia impedir que usuários salvassem ou agendassem relatórios. (CAMP -31133)

## Release 19.1.3 - March 2019 {#release-19-1-3---march-2019}

### Email Designer enhancements {#email-designer-enhancements-1}

* Correção de um problema que impedia a modificação de um modelo após salvar.
* Correção de vários problemas ao usar um modelo criado anteriormente em um e-mail.
* Correção de um problema que impedia que os componentes ficassem ocultos nos modelos importados.

### Other improvements {#other-improvements}

* Correção de um erro ao exibir regras de tipologia. (CAMP -32059 e CAMP -31849)
* Correção de um problema que impedia que as regras de tipologia fossem editadas. (CAMP -31750)
* Correção de um problema com o processo do inmail que podia parar de forma inesperada. (CAMP -31238)

## Release 19.1 - February 2019 {#release-19-1---february-2019}

### What's new? {#what-s-new--1}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Push channel Reporting improvements<br /> </td> 
   <td> <p>Vários aprimoramentos foram adicionados ao relatório de Canal de push para permitir medir a participação do usuário de forma mais intuitiva. Com esta versão, expandiremos a lista de métricas de Canal de push para três métricas diferentes: Impressões, cliques, aberturas (Abp Open) para ajudar a medir e analisar a interação dos usuários com as Notificações por push com mais eficiência. Além disso, estamos padronizando a definição e implementação dessas métricas. O relatório de notificação por push incorporado também foi aprimorado com visualizações e métricas comumente usadas.</p><p> For more information, refer to the <a href="../../reporting/using/push-notification-report.md">detailed documentation</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Launch integration for Mobile App<br /> </td> 
   <td> <p>Esta versão contém a integração do Adobe Campaign com as versões GA das extensões Android e iOS para o Adobe Campaign Standard nos Adobe Campaign Platform Launch e Mobile sdks. Essas extensões oferecem suporte para mensagens de push, mensagens no aplicativo e atualizações de perfil do aplicativo móvel.</p><p> For more information, refer to the <a href="../../administration/using/about-typology-rules.md#typology-rules">detailed documentation</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mobile In-App Messaging<br /> </td> 
   <td> <p>Esta versão contém a versão GA do canal Dentro do aplicativo no Campaign. De um ponto de vista funcional, as adições mais importantes à versão Beta são relatórios Dinâmicos para canal no aplicativo e handshake seguro entre o SDK móvel e o MASU (Marketing Cloud In-App Service que serve as regras Dentro do aplicativo para o SDK). O handshake seguro garante que os dados de PII dos usuários não se encaixam em mãos maliciosas e permitem manter a privacidade dos usuários em um dispositivo compartilhado limpando o cache da mensagem toda vez que o usuário fizer logout.</p><p>For more information, refer to the <a href="../../channels/using/about-in-app-messaging.md">detailed documentation</a> and the dedicated <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-in-app-message-tutorial.html">In-App tutorial</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Workflow enhancements<br /> </td> 
   <td> <p>Os seguintes recursos do fluxo de trabalho foram adicionados:</p> 
    <ul> 
     <li> Agora é possível copiar as atividades dentro de um fluxo de trabalho ou outro fluxo de trabalho da mesma instância Campanha. Dessa forma, é possível duplicar facilmente um fluxo de trabalho inteiro ou atividades específicas, além de manter as configurações definidas inicialmente. For more information, refer to the <a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">detailed documentation</a>. (CAMP -20014) </li> 
     <li> When using the <strong>Load file</strong> activity, you can now add a timestamp to the name of the file containing the rejected records. For more information, refer to the <a href="../../automating/using/load-file.md#configuration">detailed documentation</a>. </li> 
     <li> <strong>As atividades de consulta</strong> e <strong>segmentação</strong> agora permitem ativar uma transição de saída se as atividades não recuperarem dados. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Security enhancements {#security-enhancements-1}

* O código HTML da página de aterrissagem gerada foi atualizado para impedir a indexação do mecanismo de pesquisa.

### Email Designer enhancements {#email-designer-enhancements-2}

* Um conjunto de quatro melhores modelos de e-mail responsivos da classe projetados pelos artistas do Behance agora está disponível.

   For more information, refer to the [detailed documentation](../../start/using/about-templates.md#content-templates).

* Nossa nova experiência de acompanhamento ajudará você a iniciar a criação de emails mais rapidamente e facilitar o acesso à documentação e aos tutoriais.

   For more information, refer to the [detailed documentation](../../designing/using/about-email-content-design.md#email-designer-home-page).

* Agora você tem a flexibilidade de configurar o número de colunas e largura com base em suas necessidades.

   For more information, refer to the [detailed documentation](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

* Ao editar na exibição móvel, você pode ocultar determinados componentes apenas em dispositivos móveis para uso eficaz do espaço.

   For more information, refer to the [detailed documentation](../../designing/using/about-email-content-design.md#switching-to-mobile-view).

* Agora você pode adicionar canais sociais personalizados ao seu modelo de e-mail sobre os que já estão disponíveis.
* Correção de um problema que impedia a rolagem do menu de estrutura ao usar mais de 18 estruturas. (CAMP -31173)
* Correção de um problema que exibia o precabeçalho sobre o conteúdo ao encaminhar um e-mail contendo um pré-cabeçalho enviado com o Adobe Campaign. (CAMP -30736)
* Fixed an issue that prevented the subject line from being updated when clicking the **Refresh AEM content** option after modifying the subject in Adobe Experience Manager. (CAMP -29984)
* Correção de vários problemas que impedia o uso de imagens dinâmicas do Adobe Target.
* Correção de um problema que impedia a atualização da visualização ao recuperar o conteúdo no tempo de preparação se o conteúdo tivesse sido importado anteriormente de um URL.
* The YouTube icon has been added to the **Social** content component.
* The **List** view has been added for content components and fragments displayed in the Email Designer palette.

### Other improvements {#other-improvements-1}

* O Adobe Campaign agora é compatível totalmente com o FCM para aplicativos SDK V 4 e AEP SDK.
* O Adobe Campaign oferece suporte para notificações por push no Desgaste OS pelo Android, bem como para watchos pela Apple.
* As mensagens de aviso e de erro que podem ser exibidas ao navegar na interface foram mais claras e fáceis de entender.
* Agora você pode adicionar a colunas de lista de perfis relacionadas a aceitar e rejeitar («Não entrar mais em contato…»).
* A lista suspensa Fuso horário na tela de criação de perfil foi movida da seção Endereço para a seção superior da interface.
* Agora você pode adicionar separadores ao configurar telas de recursos personalizadas, permitindo que você organize seus campos em categorias.

   For more information, refer to the [detailed documentation](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration).

### Other changes {#other-changes-1}

* O Adobe Campaign e a Adobe Experience Cloud soltam o suporte para o Microsoft Internet Explorer 11, iniciando o segundo trimestre de 2019, e a versão Campaign Standard 19.2. Alterne para Microsoft Edge ou outro navegador compatível. See [Deprecated and removed features](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html) page.
* The **Country code** field from the Profile resource has been renamed to **Country/Region code**.

### Patches {#patches-1}

* Correção de um problema que impedia o envio da mensagem ao adicionar um perfil de teste a uma mensagem transacional por email. (CAMP -29854)
* Correção de um problema que diminuía a mensagem enviando de outros canais se o envio fosse baixo para um canal quando a mensagem enviando de todos os canais era acionada simultaneamente.
* Correção de um problema que fazia com que o MTA começasse a enviar mensagens SMS quando a conexão de conta externa ainda não tinha sido estabelecida.
* Correção de um problema que ocorria com frequência de execução de atividade do programador e hora de início. (CAMP -30745)
* Correção de um problema que ocorria com a geração de PKEY ao usar recursos de perfil estendidos. (CAMP -30285)
* Correção de um problema que ocorria com regras de esgotamento de fadiga baseadas no calendário. (CAMP -30136)
* Correção de um problema que ocorria ao tentar acessar recursos personalizados com nomes terminados com "Base". (CAMP -30109)
* Correção de um problema que impedia o uso de uma chamada de PATCH para assinar um perfil a um serviço. (CAMP -29728)
* Correção de um problema que poderia corromper um fluxo de trabalho ao importar um arquivo XML por meio da atividade Carregar arquivo. (CAMP -29208 e CAMP -28205)
* Correção de um problema ao vincular recursos personalizados, que podia impedir a geração de links de cardinalidade reversa. (CAMP -30476)
* Correção de um problema que impedia a ampliação dos logs de entrega ao usar apenas o código do segmento.
* Correção de um problema que poderia duplicar linhas ao usar a atividade de transferência de arquivo nos fluxos de trabalho.
* Correção de um problema que impedia que relatórios agendados fossem enviados no horário escolhido.
* Correção de um problema que causava a discrepância entre os kpis "Para entrega" e "Enviado" para uma entrega no aplicativo em um fluxo de trabalho.
* Correção de um problema que impedia o rastreamento de funcionar para uma mensagem no aplicativo criado com um HTML personalizado.
* Correção de um problema que impedia que o conteúdo de entrega no aplicativo fosse salvo quando usado em um fluxo de trabalho.
* Correção de um problema que impedia a exibição de aplicativos móveis para administradores.
* Correção de um problema que causava a falha do fluxo de trabalho técnico Atualização de capacidade. (CAMP -26387)
* Correção de um problema que causava a discrepância entre os perfis direcionados ao criar uma entrega no aplicativo e os exibidos no painel de entrega. (CAMP -28722)
* Correção de um problema com a integração de Campanha e Ativos principais, que podia impedir a seleção de um ativo compartilhado por email.

## Release 19.0 - January 2019 {#release-19-0---january-2019}

### What's new? {#what-s-new--2}

<table> 
 <colgroup><col style="width: 30%"><col style="width: 70%"></colgroup>
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Email Designer General Availability<br /> </td> 
   <td> <p>O novo Designer de email intuitivo (antigo Creative Designer) foi movido para GA. Agora, é compatível com todos os recursos do editor de conteúdo herdado, incluindo:</p> 
    <ul> 
     <li> The use of <a href="../../integrating/using/adding-target-dynamic-content.md">dynamic images from Adobe Target</a> </li> 
     <li> The ability to <a href="../../designing/using/importing-content-from-a-url.md#retrieving-content-from-a-url-automatically-at-preparation-time">retrieve content from a URL automatically at preparation time</a> </li> 
     <li> Fully compliant <a href="../../start/using/about-templates.md#content-templates">out-of-the box content templates</a>. </li> 
    </ul> 
    <p>For more information, refer to the <a href="../../designing/using/about-email-content-design.md">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html">how-to video</a>. As melhorias e correções estão listadas abaixo.</p><p>Como consequência, o editor de conteúdo de email herdado agora está obsoleto. For more information, refer to this <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">page</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Product Listings in Transactional Emails<br /> </td> 
   <td> <p>Agora é possível fazer referência a uma ou mais coleções de produtos em uma mensagem de email transacional. Por exemplo, você pode enviar automaticamente um e-mail de abandono de carrinho listando todos os produtos que estavam no carrinho do usuário com uma imagem, preço e link para cada produto.</p><p>For more information, refer to the <a href="../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-product-listings-in-transactional-emails-feature-video-setup.html">how-to video</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mobile View in the Email Designer<br /> </td> 
   <td> <p>Agora você pode alternar para uma exibição móvel dedicada ao editar o conteúdo de email. Isso permite ajustar o design responsivo de um email editando separadamente todas as opções de estilo para exibição móvel, como adaptar margens, tamanho de fonte menor, cor de plano de fundo diferente e assim por diante.</p><p> For more information, refer to the <a href="../../designing/using/about-email-content-design.md#switching-to-mobile-view">detailed documentation</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> In-App Messaging Beta Improvements<br /> </td> 
   <td> <p>O recurso Beta de mensagens no aplicativo foi aprimorado com os seguintes recursos:</p> 
    <ul> 
     <li> O canal beta no aplicativo é compatível com o RGPD </li> 
     <li> Integração com as apis do Analytics para preencher os acionadores de acionadores </li> 
     <li> Aparência e descrição intuitivas dos modelos de entrega </li> 
     <li> Aprimoramentos na interface de criação do ponto de vista de utilização </li> 
    </ul> <p>For more information, refer to the <a href="../../channels/using/about-in-app-messaging.md">detailed documentation</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements}

* Uma nova opção na atividade de dados Carregar agora permite aplicar uma etapa de pós-processamento ao arquivo que contém os registros rejeitados (ex. Compactação de formato zip). (CAMP -24521)
* Uma nova opção na atividade de atualização de dados agora permite configurar o tamanho máximo do lote para os dados serem carregados. (CAMP -28400)
* Melhoria na seleção de estado de endereço dos perfis. Ao selecionar um país, a lista suspensa «Estado» agora é atualizada automaticamente com valores de estados relevantes. (CAMP -28874)
* Uma nova opção na atividade de arquivo Extrair agora impede a geração de um arquivo se a transição de entrada estiver vazia. Isso evita criar e carregar arquivos vazios em servidores SFTP.
* O relatório de resumo de entrega foi aprimorado.
* A lista de países disponíveis ao definir o endereço de um perfil foi aprimorada. (CAMP -26707)
* Uma mensagem de erro agora é exibida ao tentar importar um fluxo de trabalho incorporado.

### Email Designer {#email-designer}

* Correção de um problema que ativava o recurso de unidade geográfica em um modelo de e-mail ou um fragmento de conteúdo criado com o Designer de email, mesmo que esse recurso fosse desativado no Adobe Campaign, o que fazia com que o modelo ou fragmento não disponível ao tentar acessá-lo novamente. (CAMP -28174)
* Correção de um problema que impedia que as condições de conteúdo dinâmico fossem salvas durante a edição de conteúdo com o Designer de email. (CAMP -27905)
* Correção de um problema que removia a versão HTML do conteúdo de email após editar a versão de texto simples de uma mensagem e quebrar a sincronização HTML no Designer de emails. (CAMP -28507)
* Correção de um problema que impedia a abertura da interface de email do Designer ao usar o Internet Explorer 11. (CAMP -28273)
* Correção de um problema que distorcia a renderização do Microsoft Outlook das configurações de estilo aplicadas aos botões com o Designer de email.
* Correção de um problema no Designer de email que editava um URL de um fragmento do conteúdo usado em um email, o que não era esperado, pois o fragmento estava bloqueado por padrão.
* Correção de um problema que impedia que o componente de divididor do Designer de email fosse exibido no Microsoft Office.
* Correção de um problema que causava o congelamento de uma página em determinados navegadores da Internet ao exibir um conteúdo sincronizado com o AEM usando o editor de conteúdo de email herdado. (CAMP -29068)
* Correção de um erro que ocorria ao clicar em qualquer imagem de um email ao usar o editor de conteúdo de email herdado. (CAMP -30424)
* Correção de um problema que impedia que os fragmentos recém criados fossem exibidos ao editar um email com o Designer de email. (CAMP -29928)
* Correção de um problema que impedia a exibição correta do texto do botão em emails criados com o Designer de email e recebido usando o cliente de email do Outlook.
* Agora é possível criar mensagens transacionais de perfil usando o Designer de email. (CAMP -28900)
* Correção de um erro no Designer de email que tornava o conteúdo editável ao recuperar o conteúdo de um URL automaticamente no tempo de preparação, ao passo que deveria ser bloqueado.

### Patches {#patches-2}

* Correção de um problema que exibia registros de entrega incorretos no relatório dinâmico. (CAMP -23446)
* Correção de um problema que poderia afetar os números no relatório de Resumo de rejeição (CAMP -28703)
* Fixed an issue with the Campaign and Assets Core Service integration which could prevent assets from being displayed when selecting **[!UICONTROL Image shared from Adobe Experience Cloud]** in an email (CAMP-28732).
* Correção de um problema que impedia que mensagens SMS contendo o caractere'œ'fossem enviadas mesmo que a transliteração fosse autorizada na conta externa SMPP. (CAMP -29041)
* Correção de um problema que exibia registros duplicados ao usar uma atividade de Segmentação nos fluxos de trabalho. (CAMP -28743)
* Correção de um problema que impedia a exclusão de um dos mapeamentos de valor em uma coluna em uma atividade de fluxo de trabalho. (CAMP -28708)
* Correção de um problema na atividade de transferência de Arquivo ao usar curingas com o "Teste para verificar se existe um arquivo". (CAMP -28977)
* Correção de um problema na atividade Transferência de arquivos que ocorria ao atualizar configurações de conta externas. (CAMP -28894)
* Correção de um problema com filtros personalizados no editor de consultas ao usar a condição "Email não está vazia". (CAMP -28741)
* Correção de um problema que ocorria ao exportar tabelas de recursos personalizados com mais de 100 mil registros. (CAMP -28150)
* Correção de um problema que impedia a exclusão de mensagens transacionais vinculadas a disparadores. (CAMP -28385)
* Removidas as senhas que eram exibidas de forma insecita em alguns logs do SMS.
* Correção de um problema que fazia com que as conexões com o simulador SMPP falhassem devido à senha vazia enviada pelo Adobe Campaign.
* Correção de um problema que impedia o envio de campanhas quando as conexões SMS ficavam instáveis.
* Correção de um problema que exibia entregas excluídas no relatório dinâmico.
* Correção de um problema que podia impedir a recuperação de dados adicionais de registros de entrega, registros de rastreamento e exclusão de tabelas de registros, ao usar uma atividade de Enriquecimento em um fluxo de trabalho.
* Correção de um problema com solicitações de exclusão do RGPD que ocorria ao usar um tipo de link "Link de coleção de cardinalidade N" e "Excluir o registro de metas implica a exclusão de registros de referências por link".
* Correção de um problema com o compartilhamento de relatórios.
* Correção de um problema que resultava em problemas de produção ao enviar uma notificação por push.
* Correção de um problema com arquivos de saída de mala direta que estavam faltando.
* Correção de um problema que permitia que os usuários modificassem fluxos de trabalho incorporados.
* Correção de um problema ao criar uma campanha com base em um modelo de campanha que inclui um fluxo de trabalho com uma atividade de extração configurada. (CAMP -29198)
* Correção de um problema com a atividade de extração de arquivo que impedia o uso da mesma expressão para vários elementos. (CAMP -29182)
* Correção de um problema, no editor de consultas, com a condição ingressar entre o log de log broade o log de rastreamento para rtevent. (CAMP -28780)
* Correção de um problema que impedia que as modificações na opção de página inicial "Ação específica" fossem salvas. (CAMP -29422)
* Correção de um problema que impedia a exportação de carga de um evento em um fluxo de trabalho. (CAMP -29029)
* Correção de um problema que impedia que números de SMS da lista negra fossem excluídos em uma mensagem SMS. (CAMP -28898)
* Correção de um problema que podia impedir que provedores SMPP fossem notificados no caso de um erro durante o processamento de mensagens de entrada. (CAMP -29804)
* Correção de um problema que permitia que contas externas com entregas associadas fossem excluídas. (CAMP -29738)
* O envio foi aprimorado e estabilizado para mensagens SMS.
* Correção de um problema que impedia o uso do caractere «~» em uma mensagem SMS. (CAMP -29172)
* Correção de um problema em entregas com a opção de otimização de tempo Enviar. (CAMP -29231)

