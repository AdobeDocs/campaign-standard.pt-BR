---
title: Notas de versão 2017
seo-title: Notas de versão 2017
description: Notas de versão 2017
seo-description: Esta página lista todas as versões 2017 do Adobe Campaign Standard.
page-status-flag: nunca ativado
uuid: d 73 f 8186-e 309-441 b -769 d -71 d 0 a 1 c 33 cf 4
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: versões padrão da campanha
discoiquuid: 1 cfd 9 b 3 b -9 b 3 e -4587-9 c 46-b 6 fb 02131654
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Release Notes 2017{#release-notes}

Procurando uma versão específica do Adobe Campaign Standard 2017?

Cada versão traz novos recursos e correções. Clique em uma versão para exibir seu conteúdo.

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a newer release, consult this [page](../../rn/using/release-notes.md).

## Release 17.10 - October 2017 {#release-17-10---october-2017}

### New capabilities {#new-capabilities}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Fatigue Management<br /> </td> 
   <td> O Gerenciamento de esgotamentos permite que você crie regras de esgotamento para gerenciar a comunicação com perfis. As regras de esgotamento são facilmente criadas, mas extremamente flexíveis com recursos como a contagem de mensagens em vários canais (incluindo mensagens transacionais), contagem somente de entregas específicas ou aplicação de regras a perfis específicos.<br /> Para obter mais informações, consulte a <a href="../../administration/using/fatigue-rules.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Content creation: Import from a URL<br /> </td> 
   <td> A importação de um URL permite recuperar rapidamente o conteúdo criativo de um site para criar emails para qualquer entrega. Além disso, você pode simplificar seu processo criativo permitindo que terceiros compartilhem conteúdo diretamente por meio de um URL. O conteúdo importado pode ser usado de forma flexível como parte de uma única entrega ou no nível de modelo, garantindo a consistência da marca para todas as campanhas relacionadas, independentemente de serem mensagens transacionais ou baseadas em fluxo de trabalho, e incluir testes A/B ou multivariados. A importação de um URL converte e rastreia automaticamente todos os links para monitorar o desempenho de e-mail por meio dos Relatórios dinâmicos.<br /> Para obter mais informações, consulte a <a href="../../designing/using/importing-content-from-a-url.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches}

#### Platform {#platform}

* Correção de um problema que impedia que arquivos compactados grandes fossem descompactados corretamente.
* A segurança no gerenciamento de marca foi aprimorada. Modificar o nome de uma marca e o endereço do remetente agora é reservado para administradores técnicos da Adobe.
* Para aprimorar a segurança, o conteúdo gerado pelo usuário (imagens, páginas espelhadas, páginas de aterrissagem, etc.) não pode ser mais veiculado pelo adobe.com. Agora é obrigatório usar seu próprio domínio para lidar com esses recursos, usando a marca de uso.
* Corrigido um problema de interface ao exibir e filtrar atividades de marketing.
* Correção de um problema que impedia que os campos de data de assinatura fossem atualizados com uma chamada POST Rest API.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail}

* Correção de um problema que podia impedir o direcionamento de um público-alvo de tipo de lista em uma mensagem, fazendo com que a preparação falhasse.
* Idiomas ausentes adicionados nos recursos de entrega de email multilíngues.
* A miniatura do conteúdo, exibida no painel de entrega, agora é atualizada automaticamente quando o usuário modifica o conteúdo e salva.
* Correção de um problema relacionado ao fuso horário que impedia a abertura de uma entrega.

#### Push notifications {#push-notifications}

* When configuring the push notification channel, the push provider platform for iOS should be **apns** and for Android **gcm**.
* Correção de um erro que impedia o aplicativo móvel iOS de ser adicionado na interface do Adobe Campaign.
* Agora, as notificações por push são compatíveis com aplicativos móveis habilitados para GCM e FCM para Android.
* Corrigido um erro que impedia que o conteúdo fosse salvo ao duplicar um modelo de notificação por push.
* Agora é possível criar ou atualizar um perfil do banco de dados do Adobe Campaign ao reconciliar os dados dos usuários do aplicativo móvel.
* O Adobe Campaign agora prioriza o processamento das notificações por push transacionais em notificações por push padrão.

#### Reports {#reports}

* Correção de um problema que impedia a exibição das porcentagens de cliques em hot click no conteúdo de email.
* Correção de um problema com a métrica da lista negra que era contada como uma rejeição em vez de uma rejeição.
* Correção de um problema que fazia com que contagens negativas fossem exibidas em dados de resumo.
* Correção de um problema que contava perfis no segmento de idade incorreto.
* As fórmulas de cálculo de rejeição e limpeza foram alteradas.

#### Workflows {#workflows}

* Fixed an issue in the **[!UICONTROL Load file]** activity that could lead to errors after manually adding and removing columns in the activity.
* The **[!UICONTROL deliverabilityUpdate]** technical workflow is now scheduled to run at 2am, server time.
* Correção de um problema de segurança que permitia a execução de uma lista de exportação sem a função de exportação.
* Fixed an issue with the **[!UICONTROL Reconciliation]** activity.
* Fixed an issue with the use of wildcard characters in the **[!UICONTROL File Transfer]** activity.

#### Profiles and audiences {#profiles-and-audiences}

* Correção de um problema que podia impedir que uma condição de uma consulta fosse levada em consideração em alguns casos específicos, resultando em resultados errôneos.
* Correção de um problema que podia impedir que perfis fossem acessados se fossem direcionados a uma mensagem preparada, mas nunca enviada e expirada.

#### Integrations {#integrations}

* Correção de um problema que podia impedir que algumas Fontes de dados criadas para Acionadores fossem exibidas corretamente e fossem selecionadas.

#### Custom resources {#custom-resources}

* Correção de um problema que ocorria nas telas de lista nas quais as linhas de recurso personalizadas podiam ser exibidas sem dados.
* Correção de um problema que impedia que campos de tipo booleano com valor "Falso" fossem exibidos em recursos personalizados.

## Release 17.9 - September 2017 {#release-17-9---september-2017}

### New capabilities {#new-capabilities-1}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Library of Email templates<br /> </td> 
   <td> Apresentando dezoito novos modelos responsivos projetados em dois lindos temas - Astro e Feather. Esses modelos personalizáveis são agnósticos do setor e prontos para serem usados imediatamente. Os modelos incluem conteúdo para uma variedade de casos de uso para que suas campanhas de marketing por email sejam projetadas e entregues de forma mais rápida, eficiente e bonita do que nunca.<br /> Para obter mais informações, consulte a <a href="../../start/using/about-templates.md#content-templates">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamic Reporting with Profile Data<br /> </td> 
   <td> Relatórios dinâmicos fornecem relatórios comerciais totalmente personalizáveis e em tempo real. Com esta versão, um aprimoramento poderoso para Relatórios dinâmicos adiciona acesso a dados de perfil, permitindo a análise demográfica por dimensões de perfil, como gênero, cidade, código postal e idade, além de dados funcionais da campanha por email, como abrir e clicar. Com a mesma interface de arrastar e soltar fácil de usar, determinar como sua campanha de email foi executada em relação aos segmentos de clientes mais importantes ficou mais fácil do que nunca.<br /> Para obter mais informações, consulte a <a href="../../reporting/using/about-dynamic-reports.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mass Subscription with Origin &amp; Date<br /> </td> 
   <td> Com esta melhoria na assinatura em massa, agora você pode armazenar informações de assinatura (origem e data) diretamente no banco de dados do Adobe Campaign Standard por meio da atividade dos Serviços de assinatura em um fluxo de trabalho.<br /> Para obter mais informações, consulte a <a href="../../automating/using/subscription-services.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-1}

#### Platform {#platform-1}

* Alguns clientes precisam aproveitar uma ID vindo do Adobe Campaign Standard, pois eles não gerenciam uma chave exclusiva para identificar seus próprios registros. This ID (**ACS ID**) can be exported as well as used as a reconciliation key while updating the data. For more information, refer to the [detailed documentation](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).
* O protocolo FTP está sendo descontinuado. Agora você deve usar o SFTP. Para não bloquear implementações existentes, as configurações existentes no FTP ainda funcionarão como antes, mas a opção não será exibida para novas atividades.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-1}

* Agora é possível criar novos critérios de alertas para usá-los em notificações de alertas de entrega. For more information, refer to the [detailed documentation](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* As notificações de alertas de entrega têm um novo design e a experiência de alertas de entrega do painel foi aprimorada.
* Now when a routing external account is disabled, a warning is displayed in the impacted deliveries (email, SMS and push) and the **Preview** button is hidden in these deliveries.
* Correção de um problema que causava um erro na visualização de um teste A/B no conteúdo de email quando o texto dinâmico era ativado na linha de assunto.

#### Transactional messages {#transactional-messages}

* Agora é possível definir quando você deseja enviar uma mensagem de acompanhamento, por exemplo 3 dias depois de uma mensagem transacional ser enviada. For more information, refer to the [detailed documentation](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).
* Agora é possível definir a data em que as mensagens transacionais vinculadas a um evento devem ser enviadas.
* Correção de um problema que causava um erro de SQL durante a execução de um fluxo de trabalho que continha uma mensagem de acompanhamento após a exclusão de perfis vinculados a eventos recebidos e processados.
* Corrigido um erro que impedia a exclusão de um perfil vinculado a um evento.
* Correção de um problema que podia impedir que a redirecionamento de links rastreados funcionasse.
* Correção de um problema que impedia o rastreamento de rastreamento para certos links em um email ou mensagem SMS.

#### Reports {#reports-1}

* The **Hot clicks** report has been improved. Além disso, agora é possível exibir cliques de acordo com cada conteúdo condicional definido em uma entrega e exibir cliques para cada execução de entregas recorrentes ou mensagens transacionais. For more information, refer to the [detailed documentation](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Correção de um problema que impedia a métrica de quarentena de recuperar os dados corretos.
* Um novo período predefinido foi adicionado ao widget do calendário.
* The [dynamic report metrics](../../reporting/using/indicator-calculation.md) and the [campaigns' KPIs](../../sending/using/confirming-the-send.md) (displayed on the dashboard of sent messages) have been aligned for more coherence.
* Correção de um problema que fazia com que o pipeltravasse em debian 7.

#### Workflows {#workflows-1}

* Correção de um problema que podia impedir que a retenção de arquivos importada funcionasse.

#### Integrations {#integrations-1}

* Evars e eventos agora são compatíveis com a integração do Analytics e campanha.
* Ao enviar um email com o conteúdo do carrinho abandonado, o parâmetro de carga para elementos removidos do carrinho agora é opcional.

#### Profiles and audiences {#profiles-and-audiences-1}

* O Adobe Campaign agora fornece um relatório que exibe o número de perfis ativos. Este relatório é apenas informativo, não afeta diretamente o faturamento. For more information, refer to the [detailed documentation](../../audiences/using/active-profiles.md).
* Correção de um problema que impedia que perfis fossem inscritos em um serviço ao usar a API de perfis e serviços.

## Release 17.7 - July 2017 {#release-17-7---july-2017}

### New capabilities {#new-capabilities-2}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Multilingual email and SMS deliveries<br /> </td> 
   <td> Defina e execute entregas de email e SMS multilíngues por meio de uma única entrega com base no idioma preferencial do cliente segmentado automaticamente. Informe o desempenho de cada entrega para o idioma e níveis individuais.<br /> Cada vez mais empresas enfrentam o desafio de entregar conteúdo em vários idiomas à medida que crescem em casa e no exterior. Dessa forma, a simplificação do fornecimento de mensagens traduzidas é uma parte essencial de uma estratégia eficiente de comunicação do cliente para empresas multinacionais; empresas em países com vários idiomas; e empresas que desejam personalizar ainda mais seu conteúdo a nível de idioma, não importa onde os clientes residem. For more information, refer to the <a href="../../channels/using/creating-a-multilingual-email.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Campaign Notifications<br /> </td> 
   <td> Receba notificações sobre atividades importantes do sistema diretamente no Adobe Campaign Standard. Você será notificado, por exemplo, sobre o progresso de suas entregas em andamento ou quando um fluxo de trabalho estiver incorreto.<br /> As notificações em tempo real mantêm os participantes informados e fornecem aos usuários a capacidade de agir imediatamente e diretamente em notificações de atividades dentro do aplicativo. O resultado para as equipes é agilidade avançada, eficiência e execução mais simplificada de campanhas. For more information, refer to the <a href="../../administration/using/sending-internal-notifications.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery Alerting<br /> </td> 
   <td> Além de exibir notificações diretamente no Adobe Campaign Standard, o Adobe Campaign agora também fornece um sistema de envio de alertas por email para acionar alertas de email a usuários ou participantes externos de atividades importantes do sistema. Crie, gerencie e receba alertas e painéis personalizáveis para acompanhar sucessos ou falhas de entrega.<br /> O Alerta de entrega do Adobe Campaign aumentam a eficiência, mantendo todos os usuários do Adobe Campaign envolvidos em uma empresa informados automaticamente sobre o status da execução de entrega, por email e painel. For more information, refer to the <a href="../../sending/using/receiving-alerts-when-failures-happen.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Encrypted Declared ID in Datasources<br /> </td> 
   <td> Envie acionadores de email e de SMS sem precisar de um perfil existente no Campaign usando informações de contato criptografadas (endereço de email ou número de telefone) como uma ID declarada. Como IDs declaradas criptografadas podem ser decodificadas pelo Adobe Campaign Standard, a Campanha agora pode criar novos perfis comercializáveis ao receber públicos-alvo de outras soluções da Experience Cloud contendo contatos anteriormente desconhecidos.<br /> Direcione clientes e prospetos desconhecidos em tempo real por meio de email e SMS para melhorar a confiabilidade na base de clientes existente e adquirir novos clientes respectivamente. Aproveite ao máximo os dados de cookies originais (do Adobe Audience Manager *) uma vez que os prospetos autenticarem e potencializarem esses insights no Adobe Campaign. <br /> * O Adobe Audience Manager é necessário. For more information, refer to the <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> KPI sharing from Campaign to Analytics<br /> </td> 
   <td> Compartilhe dados de campanha com o Adobe Analytics para medir métricas de marketing por email do Campaign junto com outros esforços de marketing e publicidade por meio da conversão, unindo o comportamento anterior e posterior ao clique.<br /> Acompanhe o desempenho geral diretamente e descubra sinergias com programas externos no Analytics. Aplique seu aprendizado a partir dessa exibição consolidada para suas campanhas; aprimorando as taxas abertas, de click-through e de conversão, melhorando a receita e o desempenho geral da campanha. <br /> O Adobe Analytics é necessário. For more information, refer to the <a href="../../integrating/using/about-campaign-analytics-integration.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Direct Mail Channel - Return To Sender<br /> </td> 
   <td> Agora há suporte para trocas de arquivos simples com fornecedores de Correspondência direta incorporando Retornar às informações do remetente. Esse aprimoramento no canal de Mala direta permite que endereços postais correspondentes sejam excluídos de comunicações futuras.<br /> Isso permite que os comerciantes sejam notificados sobre um endereço incorreto e participem com o cliente por meio de outros canais ou para incentivá-lo a atualizar seu endereço postal. Isso também reduz o número de dólares de marketing perdidos, pois os profissionais de marketing evitam enviar e-mail para endereços incorretos. <br /> O Mala direta está disponível como um canal de suplemento. For more information, refer to the <a href="../../channels/using/return-to-sender.md">detailed documentation</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-2}

#### General {#general}

* Correção de um problema que permitia que qualquer usuário exportasse listas. Now only users with the **[!UICONTROL Export]** role are allowed to.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-2}

* Fixed an issue with the **updateDeliveryExecInfo** workflow that set the **To deliver** indicator to 0 for SMS deliveries.
* In the **Advanced parameters** of the delivery template’s properties, the **Routing** drop-down list now only displays external accounts corresponding to the template message type. Por exemplo, um modelo de entrega de email só exibe contas externas por email.
* Fixed an issue with the **[!UICONTROL Text]** preferred email format defined for test profiles.
* Correção de um problema que resultava em erro de Javascript na seleção do fuso horário padrão na tela Definição de programação de uma entrega.
* Correção de um problema que impedia que os trappings fossem exibidos nos registros de envio.
* Na tela de seleção de modelo do assistente de criação de entrega, os modelos de teste de acompanhamento e A/B estão agora ocultos por padrão. For more information, refer to the [detailed documention](../../channels/using/creating-an-email.md).
* Correção de um problema que permitia que qualquer usuário enviasse entregas. Now only users with the **[!UICONTROL Start deliveries]** role are allowed to. For more information, refer to the [detailed documention](../../sending/using/confirming-the-send.md).

#### Push notifications {#push-notifications-1}

* Fixed an issue with the **Campaign Tracking Endpoint** URL that prevented reporting.
* Correção de um problema que impedia que o título da notificação por push fosse exibido em dispositivos Android.
* Correção de um problema que impedia a exibição da notificação por push em dispositivos iOS quando a notificação por push continha apenas um título (e nada no corpo da mensagem).
* Correção de um problema que fazia com que urls de anexo de mídia em uma entrega fossem rastreados, o que impedia a incorporação de vídeos e imagens na entrega. O rastreamento de urls do tipo mediaattachmenturl agora é desativado por padrão para notificações por push.

#### Reports {#reports-2}

* Correção de um problema em que os valores apareciam diferentes entre gráficos e tabelas.
* Correção de um problema que exibia valores de notificação por push como valores de email.
* Correção de um problema que exibia valores como desconhecidos quando uma entrega era criada fora de uma campanha.
* Correção de um problema que mostrava dados do relatório SMS como dados de aplicativos móveis.

#### Workflows {#workflows-2}

* Agora é possível filtrar logs de fluxo de trabalho (período de tempo e pesquisa de texto). For more information, refer to the [detailed documention](../../automating/using/executing-a-workflow.md#monitoring).
* Uma opção agora está disponível nas entregas do fluxo de trabalho para desativar a confirmação antes do envio.
* Correção de um problema que impedia a configuração de uma transição de saída no assistente de criação de entregas recorrentes.
* Foi corrigido um problema que ocorria ao usar uma atividade de consulta de fluxo de trabalho com base em um campo de recursos personalizado com uma enumeração que tinha vários valores.

## Release 17.5 - May 2017 {#release-17-5---may-2017}

### New capabilities {#new-capabilities-3}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Direct mail<br /> </td> 
   <td> Divida a barreira digital e conecte-se ao mundo físico com o primeiro canal offline do Adobe Campaign Standard, Mala direta. Esse recurso permite personalizar e gerar o arquivo exigido por provedores de mala direta como parte de suas campanhas entre canais. Utilize a Mala direta para envolver os clientes novamente ou para aprimorar a experiência do cliente com um ponto de contato atraente e tátil direcionando os clientes para seu aplicativo, site ou loja.<br /> Para obter mais informações, consulte a <a href="../../channels/using/about-direct-mail.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email BCC<br /> </td> 
   <td> O CCO de email permite salvar mensagens de email únicas enviadas para destinatários individuais, permitindo que a marca arquive essas mensagens. Ao adicionar um endereço de email Cco a todos os emails, os clientes do Adobe Campaign Standard podem manter uma cópia exata de cada email com este recurso. Este é um requisito legal comum para o setor de serviços financeiros e é útil para auxiliar os centros de atendimento ao cliente a resolver conflitos em tempo real.<br /> Para obter mais informações, consulte a <a href="../../administration/using/configuring-email-channel.md#archiving-emails">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-3}

#### Interface updates {#interface-updates}

* In the top bar, the **[!UICONTROL Timeline]** link has been removed and replaced with a link to **[!UICONTROL Programs & Campaigns]** .

#### Emails and SMS messages {#emails-and-sms-messages}

* Fixed an issue which displayed the wrong color for the **[!UICONTROL Retry in progress]** delivery status. A cor era cinza e não azul.

#### Workflows {#workflows-3}

* Fixed an issue that occurred when changing the action to perform in a **[!UICONTROL Transfer file]** activity.

#### Reports {#reports-3}

* The **[!UICONTROL Spam]** and **[!UICONTROL Spam rate]** indicator calculations have been changed.
* The **[!UICONTROL Bounce]** metrics have been improved for a more accurate result.

#### Push notifications {#push-notifications-2}

* Correção de um problema que impedia o clique em um evento de push no histórico de marketing de um perfil.
* O uso das notificações por push nos fluxos de trabalho foi aprimorado.

## Release 17.4 - April 2017 {#release-17-4---april-2017}

### New capabilities {#new-capabilities-4}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Enhanced Image edition capabilities with the Creative SDK<br /> </td> 
   <td> Agora você tem acesso a um conjunto completo de recursos desenvolvidos pelo Creative SDK para aprimorar suas imagens diretamente no editor de conteúdo ao editar emails ou páginas de aterrissagem.<br /> Esse recurso não exige a aquisição de soluções adicionais da Creative Cloud.<br /> Para obter mais informações, consulte a <a href="../../designing/using/modifying-images-with-the-adobe-creative-sdk.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional push notifications<br /> </td> 
   <td> O canal do aplicativo móvel foi adicionado aos recursos transacionais de mensagem do Adobe Campaign. Três canais agora são compatíveis com mensagens transacionais: email, SMS e notificações por push.<br /> Para obter mais informações, consulte a <a href="../../channels/using/transactional-push-notifications.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Recurring push notifications<br /> </td> 
   <td> Agora você pode configurar notificações por push recorrentes em um fluxo de trabalho. Você pode usar notificações por push recorrentes em situações em que seus clientes esperam atualizações periódicas, como lembretes semanais, para dar baixa em novos conteúdos ou promoções.<br /> Para obter mais informações, consulte a <a href="../../automating/using/push-notification-delivery.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Amazon Simple Storage Service (S3) connector<br /> </td> 
   <td> O conector do Amazon Simple Storage Service (S 3) agora pode ser usado para importar ou exportar dados para o Adobe Campaign. Ele pode ser configurado em uma atividade de fluxo de trabalho. A configuração é feita em uma conta externa.<br /> Para obter mais informações, consulte a <a href="../../administration/using/external-accounts.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver integration live<br /> </td> 
   <td> A integração entre o Adobe Campaign e o Dreamweaver agora está disponível. Agora funciona com a última versão oficial lançada do Dreamweaver (17.0.2).<br /> Isso requer a instalação da extensão de integração do Adobe Campaign aqui: <a href="http://adobe.ly/acdw_addon">http://adobe.ly/acdw_addon</a><br /> para obter mais informações, consulte este <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">vídeo</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-4}

#### Platform {#platform-2}

* Correção de um problema de consumo de memória.

#### Emails and SMS messages {#emails-and-sms-messages-1}

* Correção de um problema em que o conteúdo não podia ser sincronizado corretamente com as alterações mais recentes ao visualizar uma mensagem.
* Correção de um problema que impedia a criação ou exclusão de uma regra de processamento de email MX ou Domínio.
* Correção de um problema que podia impedir o envio de emails com vários alias.
* Correção de um problema que impedia que registros de entrega de trapping fossem exibidos nos registros de envio do envio.
* Correção de um problema que resultava em erro ao exibir os urls rastreados de uma entrega sem URL em seu conteúdo.
* Correção de um problema que impedia que os atributos de tamanho de uma imagem fossem aplicados corretamente na mensagem enviada.

#### Transactional messages {#transactional-messages-1}

* O campo rteventhistoid não é mais exposto como um campo de personalização em um modelo de mensagem transacional.

#### Landing pages {#landing-pages}

* We have optimized the **[!UICONTROL by email]** filter used in landing pages to reconcile new subscribers with database profiles.
* Correção de um problema que exibia entradas de texto gratuito em vez de caixas de seleção ao usar campos booleanos em uma configuração de formulário.
* Correção de um problema que impedia a geração de miniaturas da página inicial.

#### Workflows {#workflows-4}

* Fixed a display error when editing an **[!UICONTROL End]** or **[!UICONTROL External Signal]** activity (on Safari only).
* Improved the error message displayed when editing a **[!UICONTROL Read Audience]** activity containing an erroneous audience.
* Solucionado o problema que gerava um erro de SQL ao executar uma atividade de assinatura.

#### Integrations {#integrations-2}

* Dados de Pontos de interesse: correção de um erro que ocorria ao contar assinantes de localização.

#### Audiences and queries {#audiences-and-queries}

* Correção de um problema que impedia o uso de agregados e média de agregados em uma coleção no editor de consultas.
* Correção de um problema que podia impedir o recarregamento do editor de consultas após a alteração do recurso do filtro.

#### Reports {#reports-4}

* Correção de um problema que impedia que as métricas de Taxa de abertura fossem calculadas corretamente ao selecionar várias linhas em uma tabela.
* Correção de um erro que exibia somente métricas como valores inteiros. Agora, as métricas podem ser exibidas com decimais.

#### Push notifications {#push-notifications-3}

* Correção de um problema em que uma mensagem de erro não era exibida ao criar um aplicativo Android vinculado a um aplicativo para dispositivos móveis que falhava em ser criado no MCPNS.
* Correção de um problema que permitia que um usuário adicionasse sons a uma notificação silenciosa.

## Release 17.2 - March 2017 {#release-17-2---march-2017}

### New capabilities {#new-capabilities-5}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Dynamic reporting<br /> </td> 
   <td> O Relatório dinâmico fornece uma nova geração de relatórios comerciais totalmente personalizáveis e em tempo real. Com base em tabelas e gráficos dinâmicos e dinâmicas, esse recurso permite arrastar e soltar variáveis e dimensões para analisar a eficiência e eficiência de suas campanhas de marketing. Os relatórios dinâmicos também permitem que você crie relatórios comerciais do zero e os salve para uso posterior.<br /> Para obter mais informações, consulte a <a href="../../reporting/using/about-dynamic-reports.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver integration (Labs)<br /> </td> 
   <td> Com a integração do Adobe Campaign e Dreamweaver, você agora tem um processo integrado para criar campanhas de email com soluções da Adobe.<br /> Você pode editar emails do Adobe Campaign no Dreamweaver e fazer com que o conteúdo seja sincronizado automaticamente entre ambas as soluções.<br /> Para a versão inicial, a integração está disponível como um recurso "Labs" e funciona somente com o Dreamweaver Pre Release Beta. Se quiser ativá-la, entre em contato com o AC-DW-integration@adobe.com.<br /> Para obter mais informações, consulte este <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">vídeo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Manual send time optimization<br /> </td> 
   <td> Agora é possível definir manualmente um tempo de envio personalizado por destinatário - no nível de entrega ou usando um fluxo de trabalho. <br /> Duas novas opções estão disponíveis: <br /> 
    <ul> 
     <li> Todos os destinatários recebem a mensagem levando em conta o fuso horário. </li> 
     <li> Cada destinatário recebe a mensagem em uma data e hora computadas definidas por uma fórmula. </li> 
    </ul> For more information, refer to the <a href="../../sending/using/optimizing-the-sending-time.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push notifications New capabilities<br /> </td> 
   <td> The push notification channel has been enhanced with several new capabilities:<br /> 
    <ul> 
     <li> Nova interface de criação </li> 
     <li> Notificações silenciosas </li> 
     <li> Push interativo </li> 
     <li> Suporte a conteúdo avançado </li> 
     <li> Calculadora de tamanho de carga </li> 
    </ul> For more information, refer to the <a href="../../channels/using/about-push-notifications.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: new Signal activity<br /> </td> 
   <td> Trigger a workflow from another workflow using the new <span class="uicontrol">Signal</span> activity.<br /> Com a capacidade de iniciar um fluxo de trabalho a partir de outro, agora é possível oferecer suporte a jornadas mais complexas do cliente. Você pode monitorar melhor as jornadas do cliente e reagir no caso de problemas.<br /> Várias atividades de fluxo de trabalho foram atualizadas:<br /> 
    <ul> 
     <li> <span class="uicontrol">Atividade final</span> : uma nova guia permite que você especifique um fluxo de trabalho para acionar depois que esta atividade for executada. </li> 
     <li> <span class="uicontrol">Atualizar</span> atividade de dados: use a nova transição de saída vazia para adicionar uma <strong>atividade final</strong> que aciona outro fluxo de trabalho. Transições de saída vazias não transportam dados e não consomem espaço desnecessário no sistema </li> 
    </ul> For more information, refer to the <a href="../../automating/using/external-signal.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: new Read audience activity<br /> </td> 
   <td> Inicie o processo de definição de metas com um público-alvo existente que você pode selecionar e refinar facilmente em uma atividade.<br /> Para obter mais informações, consulte a <a href="../../automating/using/read-audience.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Points of Interest data<br /> </td> 
   <td> Os dados de Pontos de interesse integram o Adobe Campaign com o Adobe Analytics para dispositivos móveis. A brand can collect data from users' mobile locations - called <strong>Points of Interest</strong> - when users open the brand's app. Isso permite que a marca aproveite os fluxos de trabalho do Adobe Campaign para enviar mensagens personalizadas com base nos locais dos usuários. Este canal utiliza o SDK do serviço principal do Mobile.<br /> Observe que o uso desse recurso requer o Analytics para dispositivos móveis, que é uma solução paga.<br /> Para obter mais informações, consulte a <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> REST APIs<br /> </td> 
   <td> Os recursos vinculados em qualquer nível aos perfis ou aos recursos de serviços estão disponíveis na API.<br /> Para obter mais informações, consulte a <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-5}

#### General {#general-1}

* Agora é possível adicionar dados de perfil ao exportar logs de entrega.

#### Emails and SMS messages {#emails-and-sms-messages-2}

* Fixed an issue causing the **[!UICONTROL Request confirmation before sending messages]** option to remain selected even after unchecking it and saving the delivery.
* Correção de um problema que podia impedir a publicação de emails transacionais de publicação.
* Correção de um problema em que o conteúdo não podia ser sincronizado corretamente com as alterações mais recentes antes da visualização de uma entrega.

#### Landing pages {#landing-pages-1}

* Corrigido um erro que impedia que um usuário editasse ao clicar no conteúdo de uma página de aterrissagem.

#### Workflows {#workflows-5}

* Fixed an issue that could prevent from reading the content of the reject transition of a **[!UICONTROL Load file]** activity.
* Fixed an issue that prevented swapped columns to be properly taken into account when configuring a **[!UICONTROL Load file]** activity.

## Release 17.1 - January 2017 {#release-17-1---january-2017}

### New capabilities {#new-capabilities-6}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Log export for external reporting<br /> </td> 
   <td> Exporte logs como logs de entrega e rastreamento para processá-los em seus relatórios preferidos ou ferramentas BI. Você pode usar fluxos de trabalho simples com consultas incrementais para automatizar exportações regulares de novos logs.<br /> Além da disponibilidade de recursos de log do seletor de recursos, foram feitos aprimoramentos nas atividades de consulta <a href="../../automating/using/incremental-query.md">Incremental</a> e <a href="../../automating/using/extract-file.md">Extrair arquivos</a> :<br /> 
    <ul> 
     <li> <span class="uicontrol">A consulta incremental</span> agora permite usar um campo de data para recuperar dados novos ou atualizados. Anteriormente, todos os resultados de execuções anteriores eram excluídos automaticamente, mesmo se fossem atualizados desde a última execução. </li> 
     <li> <span class="uicontrol">O arquivo</span> de extração agora pode exportar rótulos para valores de enumeração em vez de IDs. </li> 
    </ul> Essas atividades estão disponíveis para administradores com acesso a todas as unidades geográficas e org.<br /> Para obter mais informações sobre como exportar logs, consulte a documentação <a href="../../automating/using/exporting-logs.md">detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Marketing capabilities for transactional messages<br /> </td> 
   <td> Agora, os profissionais de marketing podem enviar mensagens transacionais com base em perfis de marketing do cliente. This allows them to:<br /> 
    <ul> 
     <li> Apply marketing typology rules such as <span class="uicontrol">Blacklisted address</span> . </li> 
     <li> Inclua o link de cancelamento de assinatura nas mensagens. </li> 
     <li> Adicione as mensagens transacionais ao relatório de entrega global. </li> 
     <li> Aproveite as mensagens transacionais na jornada do cliente. </li> 
    </ul> For more information, refer to the <a href="../../channels/using/profile-transactional-messages.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional Messaging API<br /> </td> 
   <td> The Transactional Messaging API is now available through <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>, making it easier to use and to monitor:<br /> 
    <ul> 
     <li> Você pode se beneficiar do relatório da plataforma adobe. io e de capas de monitoramento. </li> 
     <li> A autenticação agora é realizada usando a autenticação de token adobe. io em vez de uma lista de permissões de IP, tornando o processo de segurança mais simples. </li> 
     <li> Todas as apis agora estão integradas em uma única plataforma, tornando mais simples do que nunca adicionar recursos transacionais de mensagens à integração caso você já ofereça suporte à API de perfil e de serviços. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-6}

#### General {#general-2}

* **[!UICONTROL Access authorization]** As opções retornaram às propriedades da página de aterrissagem.
* Solucionado o problema que fazia com que uma imagem antiga fosse renderizada em vez da imagem correta. Isso ocorria se a imagem de origem fosse atualizada na definição de conteúdo de uma entrega ou página de aterrissagem.
* Correção de um problema que impedia os usuários de editar determinados campos em uma conta externa SFTP existente.
* Correção de vários problemas de UI. Por exemplo, agora os usuários podem editar atributos de perfil e salvar modificações sem problemas com a interface do usuário.

#### Emails and SMS messages {#emails-and-sms-messages-3}

* Corrigido um problema pertencendo aos modelos de entrega com conteúdo HTML que contém um

#### Push notifications {#push-notifications-4}

* Corrigido um problema que podia ter impedido postback de um aplicativo para o servidor do Adobe Campaign.
* Fixed an issue that may have prevented **[!UICONTROL Play a sound]** and **[!UICONTROL Custom fields]** to be taken into account for Android.
* Corrigido um problema que fazia com que um caractere de escape extra fosse adicionado aos caracteres Unicode usados para Emojis.
* Quando o token de registro de um assinante se torna lista negra, o status correspondente agora é atualizado imediatamente na lista de assinantes do aplicativo no Adobe Campaign.

#### Workflows {#workflows-6}

* Correção de um problema que podia ter evitado visualizações de consultas em recursos do evento (por exemplo, rtevent).
* The reject file generated by a **[!UICONTROL Load file]** activity can now be retrieved in its outbound transition and processed in the next activity. For example, upload the reject file via an SFTP server using **[!UICONTROL Transfer file]** .
* Fixed an issue that may have prevented a user from limiting the population of a segment if **[!UICONTROL Temporary resource]** was selected in the **[!UICONTROL General]** tab of **[!UICONTROL Segmentation]** .
* **[!UICONTROL Scheduler]** não podem mais ser definidas para acionar um fluxo de trabalho mais de uma vez a cada 10 minutos.
* Fixed an issue that may have prevented **[!UICONTROL Use common columns]** from working properly in an **[!UICONTROL Union]** activity.

#### Integrations {#integrations-3}

* Solucionado o problema que gerava um erro ao implantar um acionador de evento no Adobe Campaign. Esse erro ocorria quando os metadados "Probabilidade de retornar em 30 dias" eram adicionados ao acionador Abandono na Adobe Marketing Cloud.
* Correção de um problema que fazia com que o fluxo de trabalho técnico limpe o campo de Dimensão do Target ao importar públicos-alvo de serviços principais de Pessoas. Consultas subsequentes não conseguiam recuperar os públicos importados.
* Fixed an issue that may have caused the **[!UICONTROL Save audience]** activity of a workflow to fail when the option **[!UICONTROL Share in Adobe Marketing Cloud]** was checked.

