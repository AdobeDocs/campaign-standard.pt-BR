---
title: Notas de versão de 2017
description: Essa página lista todas as versões de 2017 do Adobe Campaign Standard.
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 73a1ec49-fcbc-406b-9590-1ad20da9e73b
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '4572'
ht-degree: 5%

---

# Notas de versão de 2017{#release-notes}

## Versão 17.10 - Outubro de 2017 {#release-17-10---october-2017}

**Novos recursos**

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Gerenciamento de fadiga<br /> </td> 
   <td> O Gerenciamento de fadiga permite criar regras de fadiga para gerenciar a comunicação excessiva com perfis. As regras de fadiga são facilmente criadas, mas são extremamente flexíveis com recursos como a contagem de mensagens em vários canais (incluindo mensagens transacionais), a contagem apenas de deliveries específicos ou a aplicação de regras a perfis específicos.<br /> Para obter mais informações, consulte <a href="../../sending/using/fatigue-rules.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Criação de conteúdo: Importar de um URL<br /> </td> 
   <td> Importar de um URL permite recuperar rapidamente o conteúdo criativo de um site para criar emails para qualquer entrega. Além disso, você pode simplificar seu processo criativo, permitindo que terceiros compartilhem conteúdo diretamente por meio de um URL. O conteúdo importado pode ser usado de forma flexível como parte de uma única entrega ou no nível do modelo, garantindo a consistência da marca para todas as campanhas relacionadas, sejam elas baseadas em fluxo de trabalho ou mensagens transacionais, e incluindo testes A/B ou multivariados. Importar de um URL converte e rastreia automaticamente todos os links para monitorar o desempenho do email por meio do Dynamic Reporting.<br /> Para obter mais informações, consulte <a href="../../designing/using/using-existing-content.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Platform_

* Correção de um problema que impedia que arquivos compactados grandes fossem descompactados corretamente.
* A segurança no gerenciamento da marca foi aprimorada. A modificação do nome e do endereço do remetente de uma marca agora está reservada para administradores técnicos do Adobe.
* Para melhorar a segurança, conteúdo gerado pelo usuário (imagens, mirror pages, landing pages etc.) não pode mais ser atendido pelo domínio adobe.com. Agora é obrigatório usar seu próprio domínio para lidar com esses recursos, por meio do uso da marca.
* Correção de um problema de interface ao exibir e filtrar atividades de marketing.
* Correção de um problema que impedia que os campos de data da assinatura fossem atualizados com uma chamada à API POST Rest.

_Emails, mensagens SMS e correspondência direta_

* Correção de um problema que impedia o de direcionar um público-alvo do tipo lista em uma mensagem, causando a falha da preparação.
* Idiomas ausentes adicionados nos recursos multilíngues de delivery de email.
* A miniatura do conteúdo, exibida no painel do delivery, agora é atualizada automaticamente quando o usuário modifica o conteúdo e salva.
* Correção de um problema relacionado ao fuso horário que impedia a abertura de uma entrega.

_Notificações por push_

* Ao configurar o canal de notificação por push, a plataforma do provedor de push do iOS deve ser **apns** e para Android **gcm**.
* Correção de um erro que impedia a adição do aplicativo móvel iOS na interface do Adobe Campaign.
* As notificações por push agora são compatíveis com aplicativos móveis Android habilitados para GCM e FCM.
* Correção de um erro que impedia que o conteúdo fosse salvo ao duplicar um template de notificação por push.
* Agora é possível criar ou atualizar um perfil do banco de dados do Adobe Campaign reconciliando os dados dos usuários do aplicativo móvel.
* O Adobe Campaign agora prioriza o processamento das notificações transacionais por push em relação às notificações por push padrão.

_Relatórios_

* Correção de um problema que impedia que as porcentagens de cliques ativos fossem exibidas no conteúdo do email.
* Correção de um problema com a métrica incluir na lista de bloqueios que era contada como uma rejeição permanente em vez de uma rejeição.
* Correção de um problema que resultava na exibição de contagens negativas nos dados de resumo.
* Correção de um problema que contava perfis no segmento de idade errado.
* As fórmulas de cálculo de rejeição temporária e permanente foram alteradas.

_Workflows_

* Correção de um problema no **[!UICONTROL Load file]** atividade que pode levar a erros após adicionar e remover manualmente colunas na atividade.
* A variável **[!UICONTROL deliverabilityUpdate]** o fluxo de trabalho técnico agora está agendado para ser executado às 2:00, hora do servidor.
* Correção de um problema de segurança que permitia executar uma exportação de lista sem a função de exportação.
* Correção de um problema com o **[!UICONTROL Reconciliation]** atividade.
* Correção de um problema com o uso de caracteres curingas no **[!UICONTROL File Transfer]** atividade.

_Perfis e públicos_

* Correção de um problema que impedia que uma condição de um query fosse considerada corretamente em alguns casos específicos, resultando em resultados errôneos.
* Correção de um problema que impedia que perfis fossem acessados se fossem direcionados em uma mensagem preparada, mas nunca enviada e expirada.

_Integrações_

* Correção de um problema que impedia que algumas Fontes de dados criadas para Acionadores fossem exibidas e selecionadas corretamente.

_Recursos personalizados_

* Correção de um problema que ocorria em telas de lista em que as linhas de recursos personalizados podiam ser exibidas sem dados.
* Correção de um problema que impedia que campos do tipo booleano com valor &quot;Falso&quot; fossem exibidos em recursos personalizados.

## Versão 17.9 - Setembro de 2017 {#release-17-9---september-2017}

**Novos recursos**

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Biblioteca de modelos de email<br /> </td> 
   <td> Apresentando dezoito modelos novos e responsivos projetados em dois belos temas - Astro e Feather. Esses modelos personalizáveis são agnósticos do setor e estão prontos para serem usados imediatamente. Os modelos incluem conteúdo para uma variedade de casos de uso para fazer com que suas campanhas de marketing por email sejam projetadas e entregues de forma mais rápida, eficiente e linda do que nunca.<br /> Para obter mais informações, consulte <a href="../../designing/using/using-reusable-content.md#content-templates">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Relatórios dinâmicos com dados de perfil<br /> </td> 
   <td> O Dynamic Reporting fornece relatórios comerciais totalmente personalizáveis e em tempo real. Com esta versão, um aprimoramento poderoso do Dynamic Reporting adiciona acesso aos dados do perfil, permitindo a análise demográfica por dimensões de perfil, como gênero, cidade, código postal e idade, além de dados funcionais de campanha de email, como aberturas e cliques. Com a mesma interface de arrastar e soltar fácil de usar, determinar o desempenho de sua campanha de email em relação aos segmentos de clientes mais importantes está mais fácil do que nunca.<br /> Para obter mais informações, consulte <a href="../../reporting/using/about-dynamic-reports.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Assinatura em Massa com Origem e Data<br /> </td> 
   <td> Com esse aprimoramento de Assinatura em massa, agora é possível armazenar informações de assinatura (origem e data) diretamente no banco de dados do Adobe Campaign Standard por meio da atividade de Serviços de assinatura em um workflow.<br /> Para obter mais informações, consulte <a href="../../automating/using/subscription-services.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Platform_

* Alguns clientes precisam aproveitar uma ID proveniente do Adobe Campaign Standard, pois não gerenciam uma chave exclusiva para identificar seus próprios registros. Essa ID (**ID DO ACS**) podem ser exportadas e usadas como uma chave de reconciliação ao atualizar os dados. Para obter mais informações, consulte a [documentação detalhada](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).
* O protocolo FTP está sendo substituído. Agora você deve usar o SFTP. Para não bloquear as implementações existentes, as configurações existentes no FTP ainda funcionarão como antes, mas a opção não será exibida para novas atividades.

_Emails, mensagens SMS e correspondência direta_

* Agora é possível criar novos critérios de alerta para usá-los nas notificações de alerta do delivery. Para obter mais informações, consulte a [documentação detalhada](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* As notificações de alerta do delivery têm um novo design e a experiência do usuário do painel de alerta do delivery foi aprimorada.
* Agora, quando uma conta externa de roteamento é desativada, um aviso é exibido nos deliveries afetados (email, SMS e push) e na **Visualizar** está oculto nessas entregas.
* Correção de um problema que causava um erro na pré-visualização de um teste A/B no conteúdo de email quando o texto dinâmico era ativado na linha de assunto.

_Mensagens transacionais_

* Agora é possível definir quando você deseja enviar uma mensagem de acompanhamento, por exemplo, 3 dias após o envio de uma mensagem transacional. Para obter mais informações, consulte a [documentação detalhada](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).
* Agora é possível definir a data a partir da qual as mensagens transacionais vinculadas a um evento devem ser enviadas.
* Correção de um problema que causava um erro de SQL ao executar um workflow contendo uma mensagem de acompanhamento após excluir perfis vinculados a eventos recebidos e processados.
* Correção de um erro que impedia a exclusão de um perfil vinculado a um evento.
* Correção de um problema que impedia o funcionamento do redirecionamento de links rastreados.
* Correção de um problema que impedia a desativação do rastreamento de determinados links em uma mensagem de email ou SMS.

_Relatórios_

* A variável **Hot clicks** relatório foi melhorado. Além disso, agora é possível exibir cliques ativos de acordo com cada conteúdo condicional definido em um delivery e exibir cliques ativos para cada execução de deliveries recorrentes ou mensagens transacionais. Para obter mais informações, consulte a [documentação detalhada](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Correção de um problema que impedia a métrica de quarentena de recuperar dados corretos.
* Um novo período predefinido foi adicionado ao widget de calendário.
* A variável [métricas de relatório dinâmicas](../../reporting/using/indicator-calculation.md) e a variável [KPIs de campanhas](../../sending/using/confirming-the-send.md) (exibido no painel de mensagens enviadas) foram alinhados para maior coerência.
* Correção de um problema que resultava no travamento do pipeline no debian 7.

_Workflows_

* Correção de um problema que impedia o funcionamento da retenção do arquivo importado.

_Integrações_

* eVars e eventos agora são compatíveis com a integração do Analytics e do Campaign.
* Ao enviar um email com o conteúdo do carrinho abandonado, o parâmetro de carga para elementos removidos do carrinho agora é opcional.

_Perfis e públicos_

* O Adobe Campaign agora fornece um relatório que exibe o número de perfis ativos. Este relatório é apenas informativo, não tem um impacto direto na cobrança. Para obter mais informações, consulte a [documentação detalhada](../../audiences/using/active-profiles.md).
* Correção de um problema que impedia que os perfis fossem inscritos em um serviço ao usar a API de Perfis e Serviços.

## Versão 17.7 - Julho de 2017 {#release-17-7---july-2017}

**Novos recursos**

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Entregas de email e SMS multilíngues<br /> </td> 
   <td> Defina e execute deliveries de emails e SMS multilíngues em um único delivery com base no idioma preferencial dos clientes segmentados automaticamente. Relate o desempenho de cada entrega até os níveis de idioma e pessoa.<br /> Cada vez mais empresas enfrentam o desafio de fornecer conteúdo em vários idiomas à medida que crescem internamente e no exterior. Dessa forma, a simplificação da entrega localizada de mensagens é uma parte essencial de uma estratégia eficaz de comunicação com o cliente para empresas multinacionais, empresas em países com vários idiomas e empresas que desejam personalizar ainda mais seu conteúdo no nível linguístico, independentemente de onde os clientes residam. Para obter mais informações, consulte a <a href="../../channels/using/creating-a-multilingual-email.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificações do Adobe Campaign<br /> </td> 
   <td> Receba notificações sobre atividades importantes do sistema diretamente no Adobe Campaign Standard. Você será notificado, por exemplo, sobre o progresso de seus deliveries em andamento ou quando um workflow estiver com erro.<br /> As notificações em tempo real mantêm as partes interessadas relevantes informadas e fornecem aos usuários a capacidade de agir de forma imediata e direta nas notificações de atividade a partir do aplicativo. O resultado para as equipes é agilidade avançada, eficiência e execução mais suave de campanhas. Para obter mais informações, consulte a <a href="../../administration/using/sending-internal-notifications.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Alertas de entrega<br /> </td> 
   <td> Além de visualizar notificações diretamente no Adobe Campaign Standard, o Adobe Campaign agora também fornece um sistema de alerta por email para acionar alertas por email para usuários ou participantes externos de atividades importantes do sistema. Crie, gerencie e receba alertas e painéis personalizáveis para rastrear os sucessos ou as falhas do delivery.<br /> Os alertas de entrega do Adobe Campaign aumentam a eficiência, mantendo todos os usuários do Adobe Campaign envolvidos em uma empresa informados automaticamente sobre o status de execução da entrega, por email e pelo painel. Para obter mais informações, consulte a <a href="../../sending/using/receiving-alerts-when-failures-happen.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> ID declarada criptografada em fontes de dados<br /> </td> 
   <td> Enviar acionadores de email e SMS sem a necessidade de um perfil existente no Campaign usando informações de contato criptografadas (endereço de email ou número de telefone) como uma ID declarada. Como as IDs declaradas criptografadas podem ser decodificadas pelo Adobe Campaign Standard, o Campaign agora pode criar novos perfis comercializáveis ao receber públicos-alvo de outras soluções Experience Cloud que contêm contatos anteriormente desconhecidos.<br /> Direcione clientes e clientes potenciais desconhecidos em tempo real, por meio de email e SMS, para melhorar a fidelidade na sua base de clientes existente e adquirir novos clientes, respectivamente. Aproveite ao máximo seus dados de cookies primários (da Adobe Audience Manager*) assim que os prospetos forem autenticados e aproveitarem esses insights no Adobe Campaign. <br /> *O Adobe Audience Manager é obrigatório. Para obter mais informações, consulte a <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Compartilhamento de KPI do Campaign para o Analytics<br /> </td> 
   <td> Compartilhe dados de campanha com o Adobe Analytics para medir métricas de marketing por email do Campaign junto a outras iniciativas de marketing e publicidade por meio da conversão, unindo os comportamentos anterior e posterior ao clique.<br /> Acompanhe o desempenho geral diretamente e descubra sinergias com programas externos no Analytics. Aplique seu aprendizado dessa visualização consolidada novamente em suas campanhas; melhorando, em última análise, as taxas de abertura, click-through e conversão, aumentando a receita e o desempenho geral da campanha. <br /> O Adobe Analytics é obrigatório. Para obter mais informações, consulte a <a href="../../integrating/using/about-campaign-analytics-integration.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Canal De Correspondência Direta - Retornar Ao Remetente<br /> </td> 
   <td> Agora são compatíveis trocas de arquivos simples com provedores de Correspondência direta incorporando informações Retornar para o remetente. Esse aprimoramento no canal de correspondência direta permite que os endereços postais correspondentes sejam excluídos de comunicações futuras.<br /> Isso permite que os profissionais de marketing sejam notificados sobre um endereço incorreto e se envolvam com o cliente por meio de outros canais ou para incentivá-los a atualizar seu endereço postal. Isso também reduz o número de dólares de marketing desperdiçados, já que os profissionais de marketing evitam enviar emails para endereços incorretos. <br /> A Correspondência direta está disponível como um canal complementar. Para obter mais informações, consulte a <a href="../../channels/using/return-to-sender.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Geral_

* Correção de um problema que permitia a exportação de qualquer lista de usuários. Agora, somente usuários com **[!UICONTROL Export]** podem.

_Emails, mensagens SMS e correspondência direta_

* Correção de um problema com o **updateDeliveryExecInfo** fluxo de trabalho que define o **Para entregar** indicador para 0 para deliveries de SMS.
* No **Parâmetros avançados** das propriedades do template do delivery, a variável **Roteamento** A lista suspensa agora exibe somente contas externas correspondentes ao tipo de mensagem do template. Por exemplo, um template do delivery de email exibe somente contas externas de email.
* Correção de um problema com o **[!UICONTROL Text]** formato de email preferencial definido para perfis de teste.
* Correção de um problema que resultava em um erro de Javascript no ao selecionar o fuso horário padrão na tela de definição de programação de um delivery.
* Correção de um problema que impedia o aparecimento de armadilhas nos logs de envio.
* Na tela de seleção de modelo do assistente de criação de delivery, os modelos de teste A/B e de acompanhamento agora estão ocultos por padrão. Para obter mais informações, consulte [documentação detalhada](../../channels/using/creating-an-email.md).
* Correção de um problema que permitia que qualquer usuário enviasse deliveries. Agora, somente usuários com **[!UICONTROL Start deliveries]** podem. Para obter mais informações, consulte [documentação detalhada](../../sending/using/confirming-the-send.md).

_Notificações por push_

* Correção de um problema com o **Endpoint de rastreamento de campanha** URL que impediu o relatório.
* Correção de um problema que impedia que o título da notificação por push fosse exibido em dispositivos Android.
* Correção de um problema que impedia que a notificação por push fosse exibida em dispositivos iOS quando a notificação por push continha apenas um título (e nada no corpo da mensagem).
* Correção de um problema que forçava o rastreamento de URLs de anexo de mídia em uma entrega, o que impedia que vídeos e imagens fossem incorporados na entrega. O rastreamento de URLs do tipo mediaAttachmentURL agora é desativado por padrão para notificações por push.

_Relatórios_

* Correção de um problema em que os valores apareciam diferentes entre gráficos e tabela.
* Correção de um problema que exibia valores de notificação por push como valores de email.
* Correção de um problema que mostrava valores como desconhecidos quando um delivery era criado fora de uma campanha.
* Correção de um problema que mostrava dados de relatório de SMS como dados de aplicativo móvel.

_Workflows_

* Agora é possível filtrar logs de fluxo de trabalho (período e pesquisa de texto). Para obter mais informações, consulte [documentação detalhada](../../automating/using/monitoring-workflow-execution.md).
* Agora há uma opção nos deliveries do fluxo de trabalho para desativar a confirmação antes do envio.
* Correção de um problema que impedia a configuração de uma transição de saída no assistente de criação de delivery recorrente.
* Correção de um problema que ocorria ao usar uma atividade de consulta de fluxo de trabalho baseada em um campo de recurso personalizado com uma enumeração que tinha muitos valores

## Versão 17.5 - Maio de 2017 {#release-17-5---may-2017}

**Novos recursos**

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Correspondência direta<br /> </td> 
   <td> Derrote a barreira digital e conecte-se ao mundo físico com o primeiro canal offline da Adobe Campaign Standard, a Correspondência Direta. Esse recurso permite personalizar e gerar o arquivo exigido por provedores de correspondência direta como parte de suas campanhas entre canais. Aproveite a Mala direta para reengajar os clientes ou aprimorar a experiência do cliente com um ponto de contato tátil atraente que leva os clientes até seu aplicativo, site ou loja.<br /> Para obter mais informações, consulte <a href="../../channels/using/about-direct-mail.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email Cco<br /> </td> 
   <td> A Cco de email permite salvar mensagens de email exclusivas enviadas para destinatários individuais, permitindo que a marca arquive essas mensagens. Ao adicionar um endereço de email de CCO a todos os emails, os clientes do Adobe Campaign Standard podem manter uma cópia exata de cada email com esse recurso. Esse é um requisito legal comum para o setor de serviços financeiros e é útil para ajudar os centros de atendimento ao cliente a resolver conflitos em tempo real.<br /> Para obter mais informações, consulte <a href="../../sending/using/archiving.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Atualizações de interface_

* Na barra superior, a variável **[!UICONTROL Timeline]** foi removido e substituído por um link para **[!UICONTROL Programs & Campaigns]** .

_Emails e mensagens SMS_

* Correção de um problema que exibia a cor errada para o **[!UICONTROL Retry in progress]** status do delivery. A cor era cinza em vez de azul.

_Workflows_

* Correção de um problema que ocorria ao alterar a ação para executar em uma **[!UICONTROL Transfer file]** atividade.

_Relatórios_

* A variável **[!UICONTROL Spam]** e **[!UICONTROL Spam rate]** os cálculos de indicadores foram alterados.
* A variável **[!UICONTROL Bounce]** As métricas do foram aprimoradas para obter um resultado mais preciso.

_Notificações por push_

* Correção de um problema que impedia o clique em um evento de push no histórico de marketing de um perfil.
* O uso de notificações por push em workflows foi aprimorado.

## Versão 17.4 - Abril de 2017 {#release-17-4---april-2017}

**Novos recursos**

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Recursos de edição de imagens aprimorados com o SDK do Creative<br /> </td> 
   <td> Agora você tem acesso a um conjunto completo de recursos viabilizados pelo SDK da Creative para aprimorar suas imagens diretamente no editor de conteúdo ao editar emails ou landing pages.<br /> Este recurso não requer a aquisição de soluções de Creative Cloud adicionais.<br /> Para obter mais informações, consulte <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificações por push transacionais<br /> </td> 
   <td> O canal de aplicativo móvel foi adicionado aos recursos de mensagens transacionais do Adobe Campaign. Agora há suporte para três canais para mensagens transacionais: email, SMS e notificações por push.<br /> Para obter mais informações, consulte <a href="../../channels/using/transactional-push-notifications.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificações por push recorrentes<br /> </td> 
   <td> Agora você pode configurar notificações por push recorrentes em um fluxo de trabalho. Você pode usar notificações por push recorrentes em situações em que seus clientes esperam atualizações periódicas, como lembretes semanais para verificar novos conteúdos ou promoções.<br /> Para obter mais informações, consulte <a href="../../automating/using/push-notification-delivery.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Conector S3 (Simple Storage Service) da Amazon<br /> </td> 
   <td> O conector do Serviço de Armazenamento Simples da Amazon (S3) agora pode ser usado para importar ou exportar dados para o Adobe Campaign. Ele pode ser configurado em uma atividade de workflow. A configuração é feita em uma conta externa.<br /> Para obter mais informações, consulte <a href="../../administration/using/external-accounts.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integração do Dreamweaver em tempo real<br /> </td> 
   <td> A integração entre o Adobe Campaign e o Dreamweaver agora está ativa. Agora funciona com a última versão oficial do Dreamweaver (17.0.2).<br /> Requer a instalação da extensão de Integração do Adobe Campaign. Para obter mais informações, consulte esta <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=pt-BR">vídeo</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Platform_

* Correção de um problema de consumo de memória.

_Emails e mensagens SMS_

* Correção de um problema em que o conteúdo não podia ser sincronizado corretamente com as alterações mais recentes ao visualizar uma mensagem.
* Correção de um problema que impedia a criação ou a exclusão de uma regra de processamento de email MX ou Domínio.
* Correção de um problema que impedia o envio de emails com vários aliases.
* Correção de um problema que impedia que logs de entrega de interceptação fossem exibidos nos logs de envio da entrega.
* Correção de um problema que resultava em erro ao exibir os URLs rastreados de um delivery sem nenhum URL em seu conteúdo.
* Correção de um problema que impedia que os atributos de tamanho de uma imagem fossem aplicados corretamente na mensagem enviada.

_Mensagens transacionais_

* O campo rtEventHistoId não é mais exposto como um campo de personalização em um template de mensagem transacional.

_Landing pages_

* Otimizamos o **[!UICONTROL by email]** filtro usado em landing pages para reconciliar novos assinantes com perfis de banco de dados.
* Correção de um problema que exibia entradas de texto livre em vez de caixas de seleção ao usar campos booleanos em uma configuração de formulário.
* Correção de um problema que impedia a geração de miniaturas de páginas de destino.

_Workflows_

* Correção de um erro de exibição ao editar um **[!UICONTROL End]** ou **[!UICONTROL External Signal]** atividade (somente no Safari).
* A mensagem de erro exibida ao editar um **[!UICONTROL Read Audience]** atividade contendo um público-alvo incorreto.
* Correção de um problema que poderia resultar em um erro de SQL ao executar uma atividade de assinatura.

_Integrações_

* Dados de pontos de interesse: correção de um erro que ocorria ao contar assinantes de localização.

_Públicos-alvo e consultas_

* Correção de um problema que impedia o uso de agregações de soma e média em uma coleção no editor de consultas.
* Correção de um problema que impedia que o editor de consultas fosse recarregado após a alteração do recurso do filtro.

_Relatórios_

* Correção de um problema que impedia que as métricas de Taxa de abertura fossem calculadas corretamente ao selecionar várias linhas em uma tabela.
* Correção de um erro que mostrava apenas métricas como valores inteiros. Métricas agora podem ser exibidas com decimais.

_Notificações por push_

* Correção de um problema em que uma mensagem de erro não era exibida ao ser criado um aplicativo Android vinculado a um aplicativo móvel que não tinha sido criado no MCPNS.
* Correção de um problema que permitia a um usuário adicionar sons a uma notificação silenciosa.

## Versão 17.2 - Março de 2017 {#release-17-2---march-2017}

**Novos recursos**

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Relatórios dinâmicos<br /> </td> 
   <td> O Dynamic Reporting oferece uma nova geração de relatórios comerciais totalmente personalizáveis e em tempo real. Com base em tabelas dinâmicas visuais e gráficos, esse recurso permite arrastar e soltar variáveis e dimensões para analisar a eficiência e a eficácia de suas campanhas de marketing. O Dynamic Reporting também permite criar seus próprios relatórios comerciais do zero e salvá-los para uso posterior.<br /> Para obter mais informações, consulte <a href="../../reporting/using/about-dynamic-reports.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integração do Dreamweaver (Labs)<br /> </td> 
   <td> Com a integração do Adobe Campaign e do Dreamweaver, agora você tem um processo integrado para criar campanhas de email com soluções Adobe.<br /> Você pode editar emails do Adobe Campaign no Dreamweaver e sincronizar o conteúdo facilmente entre as duas soluções.<br /> Para a versão inicial, a integração está disponível como um recurso "Labs" e funciona somente com o Dreamweaver Pre Release Beta. Se desejar ativá-la, entre em contato com AC-DW-integration@adobe.com.<br /> Para obter mais informações, consulte esta <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=pt-BR">vídeo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Otimização manual do tempo de envio<br /> </td> 
   <td> Agora é possível definir manualmente um tempo de envio personalizado por recipient, no nível do delivery ou usando um fluxo de trabalho. <br /> Duas novas opções estão disponíveis: <br /> 
    <ul> 
     <li> Todos os recipients recebem a mensagem levando em conta o fuso horário. </li> 
     <li> Cada recipient recebe a mensagem em uma data e hora calculadas definidas por uma fórmula. </li> 
    </ul> Para obter mais informações, consulte a <a href="../../sending/using/optimizing-the-sending-time.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificações por push Novos recursos<br /> </td> 
   <td> O canal de notificação por push foi aprimorado com vários novos recursos:<br /> 
    <ul> 
     <li> Nova interface de criação </li> 
     <li> Notificações silenciosas </li> 
     <li> Push interativo </li> 
     <li> Suporte a conteúdo avançado </li> 
     <li> Calculadora de tamanho da carga útil </li> 
    </ul> Para obter mais informações, consulte a <a href="../../channels/using/about-push-notifications.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fluxos de trabalho: nova atividade de sinal<br /> </td> 
   <td> Acionar um workflow a partir de outro workflow usando o novo <span class="uicontrol">Sinal</span> atividade.<br /> Com a capacidade de iniciar um workflow a partir de outro, agora é possível oferecer suporte a jornadas mais complexas do cliente. É possível monitorar melhor as jornadas do cliente e reagir em caso de problemas.<br /> Várias atividades de workflow foram atualizadas:<br /> 
    <ul> 
     <li> <span class="uicontrol">Fim</span> Atividade: uma nova guia permite que o usuário defina um fluxo de trabalho a ser acionado após a realização dessa atividade. </li> 
     <li> <span class="uicontrol">Atualizar dados</span> activity: use a nova transição de saída vazia para adicionar uma <strong>Fim</strong> atividade que aciona outro workflow. Transições de saída vazias não transferem dados e não consomem espaço desnecessário no sistema </li> 
    </ul> Para obter mais informações, consulte a <a href="../../automating/using/external-signal.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: nova atividade Ler público<br /> </td> 
   <td> Inicie o processo de direcionamento com um público-alvo existente que pode ser facilmente selecionado e refinado em uma atividade.<br /> Para obter mais informações, consulte <a href="../../automating/using/read-audience.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dados de pontos de interesse<br /> </td> 
   <td> Os dados de Pontos de interesse integram o Adobe Campaign ao Adobe Analytics para dispositivos móveis. Uma marca pode coletar dados dos locais móveis dos usuários, chamados de <strong>Pontos de interesse</strong> - quando os usuários abrem o aplicativo da marca. Isso permite que a marca aproveite os workflows do Adobe Campaign para enviar mensagens personalizadas com base nos locais dos usuários. Este canal utiliza o SDK do Mobile Core Service.<br /> Observe que o uso desse recurso exige o Analytics para dispositivos móveis, que é uma solução paga.<br /> Para obter mais informações, consulte <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> REST APIs<br /> </td> 
   <td> Os recursos vinculados em qualquer nível aos recursos de perfis ou serviços agora estão disponíveis na API.<br /> Para obter mais informações, consulte <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Geral_

* Agora é possível adicionar dados de perfil ao exportar logs do delivery.

_Emails e mensagens SMS_

* Correção de um problema que causava a **[!UICONTROL Request confirmation before sending messages]** opção para permanecer selecionada mesmo depois de desmarcá-la e salvar o delivery.
* Correção de um problema que impedia o cancelamento da publicação de emails transacionais.
* Correção de um problema em que o conteúdo não podia ser sincronizado corretamente com as alterações mais recentes antes de visualizar um delivery.

_Landing pages_

* Correção de um erro que impedia a edição de um usuário ao clicar no conteúdo de uma landing page.

_Workflows_

* Correção de um problema que poderia impedir a leitura do conteúdo da transição de rejeição de um **[!UICONTROL Load file]** atividade.
* Correção de um problema que impedia que colunas trocadas fossem consideradas corretamente ao configurar um **[!UICONTROL Load file]** atividade.

## Versão 17.1 – Janeiro de 2017 {#release-17-1---january-2017}

**Novos recursos**

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidade<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Exportação de logs para relatórios externos<br /> </td> 
   <td> Exportar logs, como logs de delivery e rastreamento, para processá-los em seus relatórios preferidos ou nas ferramentas de BI. Você pode usar workflows simples com consultas incrementais para automatizar exportações regulares de novos logs.<br /> Além da disponibilidade de recursos de log do seletor de recursos, foram feitos aprimoramentos no <a href="../../automating/using/incremental-query.md">Query incremental</a> e <a href="../../automating/using/extract-file.md">Extrair arquivo</a> atividades:<br /> 
    <ul> 
     <li> <span class="uicontrol">Query incremental</span> agora permite usar um campo de data para recuperar dados novos ou atualizados. Anteriormente, todos os resultados de execuções anteriores eram excluídos automaticamente, mesmo que fossem atualizados desde a última execução. </li> 
     <li> <span class="uicontrol">Extrair arquivo</span> O agora pode exportar rótulos para valores de enumeração em vez de IDs. </li> 
    </ul> Essas atividades estão disponíveis para administradores com acesso a todas as unidades geográficas e organizacionais.<br /> Para obter mais informações sobre esses requisitos, consulte <a href="../../automating/using/exporting-logs.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Recursos de marketing para mensagens transacionais<br /> </td> 
   <td> Agora os profissionais de marketing podem enviar mensagens transacionais com base nos perfis de marketing do cliente. Isso permite:<br /> 
    <ul> 
     <li> Aplicar regras de tipologia de marketing, como <span class="uicontrol">Endereço na inclui na lista de bloqueios</span> . </li> 
     <li> Incluir o link de unsubscription nas mensagens. </li> 
     <li> Adicionar as mensagens transacionais aos relatórios globais da entrega. </li> 
     <li> Usar as mensagens transacionais na jornada do cliente. </li> 
    </ul> Para obter mais informações, consulte a <a href="../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API de mensagens transacionais<br /> </td> 
   <td> A API de mensagens transacionais agora está disponível, facilitando o uso e o monitoramento:<br /> 
    <ul> 
     <li> Você pode se beneficiar dos recursos de relatório e monitoramento da plataforma Adobe Developer. </li> 
     <li> A autenticação agora é realizada usando a autenticação baseada em token adobe.io em vez do incluir na lista de permissões IP, tornando o processo de segurança mais simples. </li> 
     <li> Todas as APIs agora estão integradas em uma única plataforma, tornando mais simples do que nunca adicionar recursos de mensagens transacionais à sua integração se você já for compatível com a API de perfis e serviços. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Geral_

* A variável **[!UICONTROL Access authorization]** opções retornaram às propriedades da landing page.
* Correção de um problema que fazia com que uma imagem antiga fosse renderizada em vez da imagem correta. Isso ocorria se a imagem de origem tivesse sido atualizada na definição de conteúdo de um delivery ou landing page.
* Correção de um problema que impedia os usuários de editar determinados campos em uma conta externa SFTP existente.
* Correção de vários problemas de interface do usuário. Por exemplo, agora os usuários podem editar atributos de perfil e salvar modificações sem enfrentar problemas com a interface do usuário.

_Emails e mensagens SMS_

* Correção de um problema relacionado a templates do delivery com conteúdo de HTML que contém um

_Notificações por push_

* Correção de um problema que pode ter impedido o postback de um aplicativo para o servidor do Adobe Campaign.
* Correção de um problema que pode ter evitado **[!UICONTROL Play a sound]** e **[!UICONTROL Custom fields]** a ser considerado para o Android.
* Correção de um problema que pode ter causado a adição de um caractere de escape extra a caracteres Unicode usados para Emojis.
* Quando o token de registro de um assinante é adicionado ao incluo na lista de bloqueios, o status correspondente agora é atualizado imediatamente na lista de assinantes do aplicativo no Adobe Campaign.

_Workflows_

* Correção de um problema que pode ter impedido a pré-visualização de consultas em recursos de evento (por exemplo, rtEvent).
* O arquivo de rejeição gerado por um **[!UICONTROL Load file]** A atividade agora pode ser recuperada na transição de saída e processada na próxima atividade. Por exemplo, fazer upload do arquivo rejeitado por meio de um servidor SFTP usando **[!UICONTROL Transfer file]** .
* Correção de um problema que pode ter impedido um usuário de limitar a população de um segmento se **[!UICONTROL Temporary resource]** foi selecionado na **[!UICONTROL General]** guia de **[!UICONTROL Segmentation]** .
* **[!UICONTROL Scheduler]** as atividades não podem mais ser definidas para acionar um workflow mais de uma vez a cada 10 minutos.
* Correção de um problema que pode ter evitado **[!UICONTROL Use common columns]** de trabalhar corretamente em um **[!UICONTROL Union]** atividade.

_Integrações_

* Correção de um problema que pode ter causado um erro ao implantar um acionador de evento no Adobe Campaign. Esse erro ocorria quando os metadados &quot;Probabilidade de retorno em 30 dias&quot; tinham sido adicionados ao acionador de Abandono no Adobe Marketing Cloud.
* Correção de um problema que pode ter feito com que o fluxo de trabalho técnico limpasse o campo Dimension do Target ao importar públicos do serviço principal Pessoas. Consultas subsequentes não puderam recuperar os públicos importados.
* Correção de um problema que pode ter causado a **[!UICONTROL Save audience]** atividade de um workflow a falhar quando a opção **[!UICONTROL Share in Adobe Marketing Cloud]** foi verificado.
