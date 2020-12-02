---
solution: Campaign Standard
product: campaign
title: Notas de versão 2017
description: Essa página lista todas as versões 2017 do Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '4627'
ht-degree: 8%

---


# Notas de versão 2017{#release-notes}

Você está procurando uma versão específica do Adobe Campaign Standard para 2017?

Cada versão traz novos recursos e correções. Clique em uma versão para visualização de seu conteúdo.

Visualização as últimas [atualizações de documentação](../../rn/using/documentation-updates.md) para Adobe Campaign Standard. Se estiver procurando uma versão mais recente, consulte esta [página](../../rn/using/release-notes.md).

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
   <td> O Gerenciamento de fadiga permite que você crie regras de fadiga para gerenciar a comunicação excessiva com perfis. As regras de fadiga são facilmente criadas, mas são extremamente flexíveis com recursos como contagem de mensagens em vários canais (incluindo mensagens transacionais), contagem somente de delivery específicos ou aplicação de regras a perfis específicos.<br /> Para obter mais informações, consulte a <a href="../../sending/using/fatigue-rules.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Criação de conteúdo: Importar de um URL<br /> </td> 
   <td> Importar de um URL permite recuperar rapidamente seu conteúdo criativo de um site para criar emails para qualquer delivery. Além disso, você pode simplificar seu processo criativo, permitindo que terceiros compartilhem conteúdo diretamente por meio de um URL. O conteúdo importado pode ser usado de forma flexível como parte de um único delivery ou no nível do modelo, garantindo a consistência da marca para todas as campanhas relacionadas, sejam elas baseadas em fluxos de trabalho ou mensagens transacionais, e incluir testes A/B ou multivariados. A importação de um URL converte e rastreia automaticamente todos os links para monitorar o desempenho do email por meio do Relatórios dinâmico.<br /> Para obter mais informações, consulte a <a href="../../designing/using/using-existing-content.md#importing-content-from-a-url">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Plataforma_

* Correção de um problema que impedia que arquivos compactados grandes fossem descompactados corretamente.
* A segurança no gerenciamento de marcas foi aprimorada. A modificação do nome e endereço do remetente de uma marca agora está reservada para administradores técnicos do Adobe.
* Para melhorar a segurança, o conteúdo gerado pelo usuário (imagens, mirrores page, landings page etc.) não pode mais ser servido pelo domínio adobe.com. Agora é obrigatório usar seu próprio domínio para lidar com esses recursos, por meio do uso da marca.
* Correção de um problema de interface ao exibir e filtrar atividades de marketing.
* Correção de um problema que impedia que campos de data de subscrição fossem atualizados com uma chamada de API POST Rest.

_Emails, mensagens SMS e mala direta_

* Correção de um problema que impedia o direcionamento de uma audiência de tipo de lista em uma mensagem, fazendo com que a preparação falhasse.
* Idiomas ausentes adicionados aos recursos do delivery de email multilíngue.
* A miniatura do conteúdo, exibida no painel do delivery, agora é atualizada automaticamente quando o usuário modifica o conteúdo e salva.
* Correção de um problema relacionado ao fuso horário que impedia a abertura de um delivery.

_Notificações por push_

* Ao configurar o canal de notificação por push, a plataforma do provedor de push para iOS deve ser **apns** e para Android **gcm**.
* Correção de um erro que impedia que o aplicativo móvel iOS fosse adicionado na interface do Adobe Campaign.
* As notificações por push agora são suportadas em aplicativos móveis Android habilitados para GCM e FCM.
* Correção de um erro que impedia o conteúdo de ser salvo ao duplicar um modelo de notificação por push.
* Agora é possível criar ou atualizar um perfil do banco de dados Adobe Campaign reconciliando os dados dos usuários do aplicativo móvel.
* A Adobe Campaign agora prioriza o processamento das notificações por push transacionais em vez das notificações por push padrão.

_Relatórios_

* Correção de um problema que impedia que as porcentagens de cliques ativos fossem exibidas no conteúdo do email.
* Correção de um problema com a métrica de  lista de bloqueios que era contada como uma rejeição em vez de uma rejeição.
* Correção de um problema que resultava na exibição de contagens negativas em dados de resumo.
* Correção de um problema que contava perfis no segmento de idade errado.
* As fórmulas de cálculo de rejeição flexível e rígida foram alteradas.

_Fluxos de trabalho_

* Correção de um problema na atividade **[!UICONTROL Load file]** que resultava em erros após adicionar e remover colunas manualmente na atividade.
* O fluxo de trabalho técnico **[!UICONTROL deliverabilityUpdate]** está agendado para ser executado às 2h00, horário do servidor.
* Correção de um problema de segurança que permitia executar uma exportação de lista sem a função de exportação.
* Correção de um problema com a atividade **[!UICONTROL Reconciliation]**.
* Correção de um problema com o uso de caracteres curinga na atividade **[!UICONTROL File Transfer]**.

_Perfis e públicos_

* Correção de um problema que impedia que uma condição de um query fosse considerada corretamente em alguns casos específicos, resultando em resultados errados.
* Correção de um problema que impedia que perfis fossem acessados se fossem direcionados para uma mensagem que foi preparada, mas nunca enviada e expirada.

_Integrações_

* Correção de um problema que impedia que algumas Fontes de Dados criadas para Acionadores fossem exibidas e selecionadas corretamente.

_Recursos personalizados_

* Correção de um problema que ocorria em telas de lista em que linhas de recursos personalizados podiam ser exibidas sem dados.
* Correção de um problema que impedia que campos de tipo booleano com valor &quot;Falso&quot; fossem exibidos em recursos personalizados.

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
   <td> Biblioteca de modelos de e-mail<br /> </td> 
   <td> Apresentamos dezoito novos modelos responsivos projetados em dois belos temas - Astro e Feather. Esses modelos personalizáveis são agnósticos do setor e estão prontos para serem usados imediatamente. Os modelos incluem conteúdo para uma variedade de casos de uso para que suas campanhas de marketing por email sejam projetadas e entregues de forma mais rápida, eficiente e bonita do que nunca.<br /> Para obter mais informações, consulte a <a href="../../designing/using/using-reusable-content.md#content-templates">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Relatórios dinâmico com dados de Perfil<br /> </td> 
   <td> O Relatórios dinâmico fornece relatórios comerciais totalmente personalizáveis e em tempo real. Com esta versão, uma melhoria poderosa no Dynamic Relatórios adiciona acesso aos dados do perfil, permitindo a análise demográfica por dimensões de perfil, como gênero, cidade, código postal e idade, além de dados funcionais de campanha de email, como abrir e clicar. Com a mesma interface de arrastar e soltar, fácil de usar, determinar como sua campanha de e-mail se comporta em relação aos segmentos de clientes mais importantes é mais fácil do que nunca.<br /> Para obter mais informações, consulte a <a href="../../reporting/using/about-dynamic-reports.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Subscrição em massa com Origem e data<br /> </td> 
   <td> Com esse aprimoramento de Subscrição em massa, agora você pode armazenar informações de subscrição (origem e data) diretamente no banco de dados da Adobe Campaign Standard por meio da atividade do Subscrição no serviço em um fluxo de trabalho.<br /> Para obter mais informações, consulte a <a href="../../automating/using/subscription-services.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Plataforma_

* Alguns clientes precisam aproveitar uma ID da Adobe Campaign Standard, pois não gerenciam uma chave exclusiva para identificar seus próprios registros. Essa ID (**ID ACS**) pode ser exportada, bem como usada como uma chave de reconciliação ao atualizar os dados. Para obter mais informações, consulte a [documentação detalhada](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).
* O protocolo FTP está sendo substituído. Agora você deve usar o SFTP. Para não bloquear implementações existentes, as configurações existentes no FTP ainda funcionarão como antes, mas a opção não será exibida para novas atividades.

_Emails, mensagens SMS e mala direta_

* Agora é possível criar novos critérios de alerta para usá-los em notificações de alerta de delivery. Para obter mais informações, consulte a [documentação detalhada](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* As notificações de alerta do delivery têm um novo design e a experiência do usuário do painel de alertas do delivery foi aprimorada.
* Agora, quando uma conta externa de roteamento é desativada, um aviso é exibido nos delivery afetados (email, SMS e push) e o botão **Pré-visualização** fica oculto nesses delivery.
* Correção de um problema que causava um erro na pré-visualização de um teste A/B no conteúdo de email quando o texto dinâmico era ativado na linha de assunto.

_Mensagens transacionais_

* Agora é possível definir quando você deseja enviar uma mensagem de acompanhamento, por exemplo, 3 dias após o envio de um mensagen transacional. Para obter mais informações, consulte a [documentação detalhada](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).
* Agora é possível definir a data a partir da qual os mensagens transacionais vinculados a um evento devem ser enviados.
* Correção de um problema que causava um erro de SQL ao executar um fluxo de trabalho contendo uma mensagem de acompanhamento após excluir perfis vinculados a eventos recebidos e processados.
* Correção de um erro que impedia a exclusão de um perfil vinculado a um evento.
* Correção de um problema que poderia impedir o redirecionamento de links rastreados de funcionar.
* Correção de um problema que impedia a desativação do rastreamento de determinados links em um email ou mensagem SMS.

_Relatórios_

* O relatório **Cliques ativos** foi melhorado. Além disso, agora é possível exibir cliques ativos de acordo com cada conteúdo condicional que foi definido em um delivery e exibir cliques ativos para cada execução de delivery ou mensagens transacionais recorrentes. Para obter mais informações, consulte a [documentação detalhada](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Correção de um problema que impedia a métrica de quarentena de recuperar dados corretos.
* Um novo período predefinido foi adicionado ao widget de calendário.
* As [métricas de relatório dinâmico](../../reporting/using/indicator-calculation.md) e as [campanhas KPIs](../../sending/using/confirming-the-send.md) (exibidas no painel das mensagens enviadas) foram alinhadas para maior coerência.
* Correção de um problema que resultava em falha de pipeline no debian 7.

_Fluxos de trabalho_

* Correção de um problema que impedia o funcionamento da retenção de arquivos importados.

_Integrações_

* As eVars e eventos agora são compatíveis com a integração do Analytics e da Campanha.
* Ao enviar um email com o conteúdo do carrinho abandonado, o parâmetro de carga para elementos removidos do carrinho agora é opcional.

_Perfis e públicos_

* A Adobe Campaign agora fornece um relatório que exibe o número de perfis ativos. Este relatório é apenas informativo, não tem impacto direto na cobrança. Para obter mais informações, consulte a [documentação detalhada](../../audiences/using/active-profiles.md).
* Correção de um problema que impedia a inscrição de perfis em um serviço ao usar a API Perfis e serviços.

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
   <td> E-mail multilíngue e delivery SMS<br /> </td> 
   <td> Defina e execute delivery de email e SMS multilíngues por meio de um único delivery, com base no idioma preferencial de seus clientes segmentados automaticamente. Relate o desempenho de cada delivery até os níveis de idioma e pessoa.<br /> Cada vez mais empresas enfrentam o desafio de fornecer conteúdo em vários idiomas à medida que crescem em casa e no exterior. Como tal, a simplificação do delivery de mensagens localizado é uma parte essencial de uma estratégia eficaz de comunicação dos clientes para empresas multinacionais; empresas em países com múltiplas línguas; e empresas que desejam personalizar ainda mais seu conteúdo em nível de idioma, independentemente de onde os clientes residam. Para obter mais informações, consulte a <a href="../../channels/using/creating-a-multilingual-email.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificações do Adobe Campaign<br /> </td> 
   <td> Receba notificações relacionadas a atividades importantes do sistema diretamente no Adobe Campaign Standard. Você será notificado, por exemplo, sobre o progresso de seus delivery em andamento ou quando um fluxo de trabalho estiver com erro.<br /> As notificações em tempo real mantêm as partes interessadas relevantes informadas e fornecem aos usuários a capacidade de agir imediata e diretamente nas notificações de atividade no aplicativo. O resultado para as equipes é agilidade avançada, eficiência e execução mais suave do campanha. Para obter mais informações, consulte a <a href="../../administration/using/sending-internal-notifications.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Alertas de delivery<br /> </td> 
   <td> Além de visualizar notificações diretamente no Adobe Campaign Standard, a Adobe Campaign agora também fornece um sistema de alerta por email para acionar alertas por email a usuários ou participantes externos de atividades importantes do sistema. Crie, gerencie e receba painéis e alertas personalizáveis para rastrear sucessos ou falhas de delivery.<br /> Os Alertas de Delivery do Adobe Campaign aumentam a eficiência ao manter todos os usuários envolvidos do Adobe Campaign em uma empresa automaticamente informados sobre o status de execução do delivery, por email e painel. Para obter mais informações, consulte a <a href="../../sending/using/receiving-alerts-when-failures-happen.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> ID declarada criptografada em fontes de dados<br /> </td> 
   <td> Envie acionadores de email e SMS sem precisar de um perfil existente na Campanha usando informações de contato criptografadas (endereço de email ou número de telefone) como uma ID declarada. Como as IDs declaradas criptografadas podem ser decodificadas pela Adobe Campaign Standard, a Campaign agora pode criar novos perfis comercializáveis ao receber audiências de outras soluções Experience Cloud que contenham contatos desconhecidos anteriormente.<br /> Clientes de públicos alvos e prospectos desconhecidos em tempo real por meio de email e SMS para melhorar a fidelidade em sua base de clientes existente e adquirir novos clientes, respectivamente. Aproveite ao máximo seus dados de cookies originais (da Adobe Audience Manager*) uma vez que os prospectos autenticarem e aproveitarem esses insights no Adobe Campaign. <br /> *Adobe Audience Manager é necessário. Para obter mais informações, consulte a <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Compartilhamento de KPI da Campanha para o Analytics<br /> </td> 
   <td> Compartilhe dados de campanha com a Adobe Analytics para medir métricas de marketing por email da Campanha, juntamente com outros esforços de marketing e publicidade por meio da conversão, unificando o comportamento pré e pós-clique.<br /> Acompanhe diretamente o desempenho geral e descubra sinergias com programas externos no Analytics. Aplique seu aprendizado desta visualização consolidada de volta às suas campanhas; melhorando, em última análise, o desempenho aberto, de click-through e taxas de conversão, aumentando a receita e o desempenho geral da campanha. <br /> Adobe Analytics é obrigatório. Para obter mais informações, consulte a <a href="../../integrating/using/about-campaign-analytics-integration.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Canal de mala direta - Retornar ao remetente<br /> </td> 
   <td> Agora há suporte para trocas de arquivos simples com provedores de Mala direta incorporando informações de Retorno ao remetente. Essa melhoria no canal de mala direta permite que endereços postais correspondentes sejam excluídos de futuras comunicações.<br /> Isso permite que os profissionais de marketing sejam notificados de um endereço incorreto e interajam com o cliente por meio de outros canais ou que o incentivem a atualizar seu endereço postal. Isso também reduz o número de dólares de marketing desperdiçados, já que os profissionais de marketing evitam enviar emails para endereços incorretos. <br /> A Mala direta está disponível como um canal complementar. Para obter mais informações, consulte a <a href="../../channels/using/return-to-sender.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Geral_

* Correção de um problema que permitia que qualquer usuário exportasse listas. Agora, somente os usuários com a função **[!UICONTROL Export]** podem fazê-lo.

_Emails, mensagens SMS e mala direta_

* Correção de um problema com o fluxo de trabalho **updateDeliveryExecInfo** que definia o indicador **Entregar** como 0 para delivery SMS.
* Em **Parâmetros avançados** das propriedades do template do delivery, a lista suspensa **Roteamento** agora exibe apenas contas externas correspondentes ao tipo de mensagem do modelo. Por exemplo, um template do delivery de email só exibe contas externas de email.
* Correção de um problema com o formato do email preferencial **[!UICONTROL Text]** definido para perfis de teste.
* Correção de um problema que resultava em um erro de Javascript ao selecionar o fuso horário padrão na tela de definição de agendamento de um delivery.
* Correção de um problema que impedia a exibição de armadilhas nos registros de envio.
* Na tela de seleção de modelo do assistente de criação de delivery, o acompanhamento e os modelos de teste A/B agora estão ocultos por padrão. Para obter mais informações, consulte [documentação detalhada](../../channels/using/creating-an-email.md).
* Correção de um problema que permitia que qualquer usuário enviasse delivery. Agora, somente os usuários com a função **[!UICONTROL Start deliveries]** podem fazê-lo. Para obter mais informações, consulte [documentação detalhada](../../sending/using/confirming-the-send.md).

_Notificações por push_

* Correção de um problema com o URL **Endpoint de rastreamento de Campanha** que impedia o relatórios.
* Correção de um problema que impedia que o título da notificação por push fosse exibido em dispositivos Android.
* Correção de um problema que impedia que a notificação por push fosse exibida em dispositivos iOS quando a notificação por push continha apenas um título (e nada no corpo da mensagem).
* Correção de um problema que forçava o rastreamento de URLs de anexos de mídia em um delivery, impedindo que vídeos e imagens fossem incorporados ao delivery. O rastreamento de URLs do tipo mediaAttachmentURL agora é desativado por padrão para notificações por push.

_Relatórios_

* Correção de um problema em que os valores apareciam diferentes entre gráficos e tabelas.
* Correção de um problema que exibia valores de notificação por push como valores de email.
* Correção de um problema que mostrava valores como desconhecidos quando um delivery era criado fora de uma campanha.
* Correção de um problema que mostrava dados de relatório SMS como dados de aplicativo móvel.

_Fluxos de trabalho_

* Agora é possível filtrar logs de fluxo de trabalho (período de tempo e pesquisa de texto). Para obter mais informações, consulte [documentação detalhada](../../automating/using/monitoring-workflow-execution.md).
* Uma opção agora está disponível em delivery de fluxo de trabalho para desativar a confirmação antes do envio.
* Correção de um problema que impedia a configuração de uma transição de saída no assistente de criação de delivery recorrentes.
* Correção de um problema que ocorria ao usar uma atividade de query de fluxo de trabalho com base em um campo de recurso personalizado com uma lista discriminada com muitos valores

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
   <td> Quebre a barreira digital e conecte-se ao mundo físico com o primeiro canal offline da Adobe Campaign Standard, Mala direta. Esse recurso permite que você personalize e gere o arquivo necessário para provedores de mala direta como parte de suas campanhas entre canais. Aproveite a Mala direta para envolver novamente os clientes ou aprimorar a experiência do cliente com um ponto de contato atraente e tátil, levando os clientes ao seu aplicativo, site ou loja.<br /> Para obter mais informações, consulte a <a href="../../channels/using/about-direct-mail.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email Cco<br /> </td> 
   <td> A Cco de email permite salvar mensagens de email únicas enviadas a recipient individuais, permitindo assim que a marca arquive essas mensagens. Ao adicionar um endereço de email CCO a todos os emails, os clientes da Adobe Campaign Standard podem manter uma cópia exata de cada email com este recurso. Este é um requisito legal comum para o setor de serviços financeiros e é útil para auxiliar os centros de atendimento ao cliente na resolução de conflitos em tempo real.<br /> Para obter mais informações, consulte a <a href="../../sending/using/archiving.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Atualizações da interface_

* Na barra superior, o link **[!UICONTROL Timeline]** foi removido e substituído por um link para **[!UICONTROL Programs & Campaigns]**.

_Emails e mensagens SMS_

* Correção de um problema que exibia a cor errada para o status do delivery **[!UICONTROL Retry in progress]**. A cor era cinza em vez de azul.

_Fluxos de trabalho_

* Correção de um problema que ocorria ao alterar a ação para executar em uma atividade **[!UICONTROL Transfer file]**.

_Relatórios_

* Os cálculos dos indicadores **[!UICONTROL Spam]** e **[!UICONTROL Spam rate]** foram alterados.
* As métricas **[!UICONTROL Bounce]** foram aprimoradas para obter um resultado mais preciso.

_Notificações por push_

* Correção de um problema que impedia que você clicasse em um evento de push em um histórico de marketing.
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
   <td> Recursos aprimorados da edição de imagens com o Creative SDK<br /> </td> 
   <td> Agora você tem acesso a um conjunto completo de recursos capacitados pelo Creative SDK para aprimorar suas imagens diretamente no editor de conteúdo ao editar emails ou landings page.<br /> Esse recurso não exige a aquisição de soluções adicionais de Creative Cloud.<br /> Para obter mais informações, consulte a <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificações por push transacionais<br /> </td> 
   <td> O canal do aplicativo móvel foi adicionado aos recursos de mensagens transacionais da Adobe Campaign. Três canais agora são suportados para mensagens transacionais: email, SMS e notificações por push.<br /> Para obter mais informações, consulte a <a href="../../channels/using/transactional-push-notifications.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificações por push recorrentes<br /> </td> 
   <td> Agora você pode configurar notificações por push recorrentes em um fluxo de trabalho. Você pode usar notificações por push recorrentes em situações em que seus clientes esperam atualizações periódicas, como lembretes semanais, para fazer check-out de novo conteúdo ou promoções.<br /> Para obter mais informações, consulte a <a href="../../automating/using/push-notification-delivery.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Conector do Serviço de Armazenamento Simples (S3) Amazon<br /> </td> 
   <td> O conector do Serviço de Armazenamento Simples (S3) da Amazon agora pode ser usado para importar ou exportar dados para a Adobe Campaign. Ele pode ser configurado em uma atividade de workflow. A configuração é feita em uma conta externa.<br /> Para obter mais informações, consulte a <a href="../../administration/using/external-accounts.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integração ao vivo da Dreamweaver<br /> </td> 
   <td> A integração entre a Adobe Campaign e a Dreamweaver está em execução. Agora, ele funciona com a última versão oficial do Dreamweaver (17.0.2).<br /> Isso requer a instalação da extensão de integração da Adobe Campaign aqui:  <a href="https://adobe.ly/acdw_addon">https://adobe.ly/acdw_</a><br /> çãoPara obter mais informações, consulte este  <a href="https://docs.adobe.com/content/help/pt-BR/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.translate.html">vídeo</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Plataforma_

* Corrigido um problema de consumo de memória.

_Emails e mensagens SMS_

* Correção de um problema em que o conteúdo não podia ser sincronizado corretamente com as alterações mais recentes ao visualizar uma mensagem.
* Correção de um problema que impedia a criação ou exclusão de uma regra de processamento de email MX ou Domínio.
* Correção de um problema que impedia o envio de emails com vários aliases.
* Correção de um problema que impedia a exibição de logs do delivery de captura nos registros de envio do delivery.
* Correção de um problema que resultava em erro ao exibir os URLs acompanhados de um delivery sem URL no conteúdo.
* Correção de um problema que impedia que os atributos de tamanho de uma imagem fossem aplicados corretamente na mensagem enviada.

_Mensagens transacionais_

* O campo rtEventHistoId não é mais exposto como um campo de personalização em um template de mensagem transacional.

_Páginas de aterrissagem_

* Otimizamos o filtro **[!UICONTROL by email]** usado no landing page para reconciliar novos assinantes com perfis de banco de dados.
* Correção de um problema que exibia entradas de texto livre em vez de caixas de seleção ao usar campos booleanos em uma configuração de formulário.
* Correção de um problema que impedia a geração de miniaturas de landing page.

_Fluxos de trabalho_

* Corrigido um erro de exibição ao editar uma atividade **[!UICONTROL End]** ou **[!UICONTROL External Signal]** (somente no Safari).
* A mensagem de erro exibida ao editar uma atividade **[!UICONTROL Read Audience]** contendo uma audiência incorreta foi aprimorada.
* Correção de um problema que resultava em erro de SQL ao executar uma atividade de subscrição.

_Integrações_

* Dados de Pontos de interesse: correção de um erro que ocorria ao contar assinantes de localização.

_Audiências e query_

* Correção de um problema que impedia que agregações de soma e média fossem usadas em uma coleção no editor de query.
* Correção de um problema que impedia que o editor de query fosse recarregado após alterar o recurso do filtro.

_Relatórios_

* Correção de um problema que impedia o cálculo correto das métricas de taxa aberta ao selecionar várias linhas em uma tabela.
* Correção de um erro que exibia somente métricas como valores inteiros. As métricas agora podem ser exibidas com decimais.

_Notificações por push_

* Correção de um problema em que uma mensagem de erro não era exibida ao criar um aplicativo Android vinculado a um aplicativo móvel que falhava ao ser criado no MCPNS.
* Correção de um problema que permitia ao usuário adicionar sons a uma notificação silenciosa.

## Versão 17.2 - março de 2017 {#release-17-2---march-2017}

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
   <td> Relatórios dinâmico<br /> </td> 
   <td> O Relatórios dinâmico oferece uma nova geração de relatórios comerciais em tempo real e totalmente personalizáveis. Com base em tabelas e gráficos pivô dinâmicos visuais, esse recurso permite que você arraste e solte variáveis e dimensões para analisar a eficiência e a eficácia de suas campanhas de marketing. O relatórios dinâmico também permite que você crie seus próprios relatórios de negócios do zero e salve-os para uso posterior.<br /> Para obter mais informações, consulte a <a href="../../reporting/using/about-dynamic-reports.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integração com o Dreamweaver (Labs)<br /> </td> 
   <td> Com a integração entre Adobe Campaign e Dreamweaver, agora você tem um processo integrado para criar campanhas de e-mail com soluções de Adobe.<br /> Você pode editar emails da Adobe Campaign no Dreamweaver e fazer com que o conteúdo seja sincronizado perfeitamente entre ambas as soluções.<br /> Para a versão inicial, a integração está disponível como um recurso "Labs" e funciona somente com o Dreamweaver Pre-Release Beta. Se você quiser ativá-lo, entre em contato com AC-DW-integration@adobe.com.<br /> Para obter mais informações, consulte este  <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">vídeo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Otimização manual do tempo de envio<br /> </td> 
   <td> Agora é possível definir manualmente um tempo de envio personalizado por recipient - no nível do delivery ou usando um fluxo de trabalho. <br /> Duas novas opções estão disponíveis:  <br /> 
    <ul> 
     <li> Todos os recipient recebem a mensagem levando em conta o fuso horário. </li> 
     <li> Cada recipient recebe a mensagem em uma data e hora computadas definidas por uma fórmula. </li> 
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
     <li> Calculadora de tamanho da carga </li> 
    </ul> Para obter mais informações, consulte a <a href="../../channels/using/about-push-notifications.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: nova atividade de sinal<br /> </td> 
   <td> Acione um fluxo de trabalho de outro fluxo de trabalho usando a nova atividade <span class="uicontrol">Signal</span>.<br /> Com a capacidade de start de um fluxo de trabalho de outro, agora você pode oferecer suporte a jornadas de clientes mais complexas. É possível monitorar melhor as viagens do cliente e reagir em caso de problemas.<br /> Várias atividades de fluxo de trabalho foram atualizadas:<br /> 
    <ul> 
     <li> <span class="uicontrol"></span> Endactivity: uma nova guia permite que você especifique um fluxo de trabalho a ser acionado após a execução dessa atividade. </li> 
     <li> <span class="uicontrol">Atualizar </span> atividade de dados: use a nova transição de saída vazia para adicionar uma  <strong></strong> Endactivity que aciona outro fluxo de trabalho. Transições de saída vazias não carregam dados e não consomem espaço desnecessário no sistema </li> 
    </ul> Para obter mais informações, consulte a <a href="../../automating/using/external-signal.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: nova atividade de audiência de leitura<br /> </td> 
   <td> Start seu processo de definição de metas com uma audiência existente que pode ser facilmente selecionada e refinada em uma atividade.<br /> Para obter mais informações, consulte a <a href="../../automating/using/read-audience.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dados de Pontos de interesse<br /> </td> 
   <td> Os dados de Pontos de interesse integram a Adobe Campaign à Adobe Analytics para dispositivos móveis. Uma marca pode coletar dados dos locais móveis dos usuários - chamados <strong>Pontos de interesse</strong> - quando os usuários abrem o aplicativo da marca. Isso permite que a marca utilize workflows Adobe Campaign para enviar mensagens personalizadas com base na localização dos usuários. Esse canal aproveita o SDK do serviço principal do Mobile.<br /> Observe que o uso desse recurso exige o Analytics para dispositivos móveis, que é uma solução paga.<br /> Para obter mais informações, consulte a <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> REST APIs<br /> </td> 
   <td> Os recursos vinculados em qualquer nível aos perfis ou aos recursos de serviços agora estão disponíveis na API.<br /> Para obter mais informações, consulte a <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Geral_

* Agora é possível adicionar dados de perfil ao exportar logs do delivery.

_Emails e mensagens SMS_

* Corrigido um problema que fazia com que a opção **[!UICONTROL Request confirmation before sending messages]** permanecesse selecionada mesmo depois de desmarcá-la e salvar o delivery.
* Correção de um problema que poderia impedir a publicação de emails transacionais.
* Correção de um problema em que o conteúdo não podia ser sincronizado corretamente com as alterações mais recentes antes da visualização de um delivery.

_Páginas de aterrissagem_

* Correção de um erro que impedia um usuário de editar ao clicar no conteúdo de uma landing page.

_Fluxos de trabalho_

* Correção de um problema que impedia a leitura do conteúdo da transição de rejeição de uma atividade **[!UICONTROL Load file]**.
* Correção de um problema que impedia que colunas trocadas fossem levadas em conta corretamente ao configurar uma atividade **[!UICONTROL Load file]**.

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
   <td> Exportação de log para relatórios externo<br /> </td> 
   <td> Exporte logs como delivery e logs de rastreamento para processá-los nas ferramentas preferidas do relatórios ou BI. Você pode usar workflows simples com query incrementais para automatizar exportações regulares de novos logs.<br /> Além da disponibilidade dos recursos de log do seletor de recursos, foram feitos aprimoramentos na  <a href="../../automating/using/incremental-query.md">consulta </a> incremental e nas atividades de  <a href="../../automating/using/extract-file.md">arquivo </a> Extract:<br /> 
    <ul> 
     <li> <span class="uicontrol">A </span> consulta incremental agora permite que você use um campo de data para recuperar dados novos ou atualizados. Anteriormente, todos os resultados de execuções anteriores eram excluídos automaticamente, mesmo se fossem atualizados desde a última execução. </li> 
     <li> <span class="uicontrol">Extrair </span> arquivo agora pode exportar rótulos para valores de lista discriminada em vez de IDs. </li> 
    </ul> Essas atividades estão disponíveis para administradores com acesso a todas as unidades geográficas e organizacionais.<br /> Para obter mais informações sobre como exportar registros, consulte a documentação <a href="../../automating/using/exporting-logs.md"> </a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Recursos de marketing para mensagens transacionais<br /> </td> 
   <td> Os profissionais de marketing agora podem enviar mensagens transacionais com base em perfis de marketing do cliente. Isso permite que eles:<br /> 
    <ul> 
     <li> Aplique regras de tipologia de marketing como <span class="uicontrol">Endereço na lista de bloqueios</span>. </li> 
     <li> Incluir o link de unsubscription nas mensagens. </li> 
     <li> Adicionar as mensagens transacionais aos relatórios globais do delivery. </li> 
     <li> Usar as mensagens transacionais na jornada do cliente. </li> 
    </ul> Para obter mais informações, consulte a <a href="../../channels/using/profile-transactional-messages.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API de mensagens transacionais<br /> </td> 
   <td> A API de mensagens transacionais agora está disponível por meio de <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>, facilitando o uso e o monitoramento:<br /> 
    <ul> 
     <li> Você pode se beneficiar do relatórios da plataforma adobe.io e dos recursos de monitoramento. </li> 
     <li> A autenticação agora é realizada usando a autenticação baseada em token adobe.io em vez de incluir na lista de permissões IP, tornando o processo de segurança mais simples. </li> 
     <li> Todas as APIs agora estão integradas em uma única plataforma, tornando mais simples do que nunca adicionar recursos de mensagens transacionais à sua integração se você já oferecer suporte à API de Perfis e serviços. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Geral_

* As opções **[!UICONTROL Access authorization]** retornaram às propriedades da landing page.
* Correção de um problema que resultava na renderização de uma imagem antiga em vez da imagem correta. Isso ocorria se a imagem de origem tivesse sido atualizada na definição de conteúdo de um delivery ou landing page.
* Correção de um problema que impedia os usuários de editar determinados campos em uma conta externa SFTP existente.
* Correção de vários problemas de interface do usuário. Por exemplo, os usuários agora podem editar atributos de perfil e salvar modificações sem enfrentar problemas com a interface do usuário.

_Emails e mensagens SMS_

* Correção de um problema relacionado a templates do delivery com conteúdo HTML que contém um

_Notificações por push_

* Correção de um problema que pode ter impedido o postback de um aplicativo para o servidor Adobe Campaign.
* Correção de um problema que pode ter impedido **[!UICONTROL Play a sound]** e **[!UICONTROL Custom fields]** a ser considerado para Android.
* Correção de um problema que resultava na adição de um caractere de escape extra a caracteres Unicode usados para Emojis.
* Quando o token de registro de um assinante é adicionado à lista de bloqueios, o status correspondente agora é imediatamente atualizado na lista de assinantes do aplicativo no Adobe Campaign.

_Fluxos de trabalho_

* Correção de um problema que pode ter impedido pré-visualizações de query em recursos de evento (por exemplo, rtEvent).
* O arquivo de rejeição gerado por uma atividade **[!UICONTROL Load file]** agora pode ser recuperado em sua transição de saída e processado na próxima atividade. Por exemplo, carregue o arquivo de rejeição por meio de um servidor SFTP usando **[!UICONTROL Transfer file]** .
* Correção de um problema que poderia ter impedido um usuário de limitar a população de um segmento se **[!UICONTROL Temporary resource]** fosse selecionado na guia **[!UICONTROL General]** de **[!UICONTROL Segmentation]**.
* **[!UICONTROL Scheduler]** As atividades não podem mais ser definidas para acionar um fluxo de trabalho mais de uma vez a cada 10 minutos.
* Correção de um problema que pode ter impedido **[!UICONTROL Use common columns]** de funcionar corretamente em uma atividade **[!UICONTROL Union]**.

_Integrações_

* Correção de um problema que pode ter causado um erro ao implantar um acionador de evento no Adobe Campaign. Esse erro ocorria quando os metadados &quot;Probabilidade de retorno em 30 dias&quot; eram adicionados ao acionador de Abandono no Adobe Marketing Cloud.
* Correção de um problema que pode ter feito com que o fluxo de trabalho técnico limpe o campo Dimension do Público alvo ao importar audiências do serviço principal de Pessoas. Os query subsequentes não puderam recuperar as audiências importadas.
* Correção de um problema que resultava na falha da atividade **[!UICONTROL Save audience]** de um fluxo de trabalho quando a opção **[!UICONTROL Share in Adobe Marketing Cloud]** era marcada.

