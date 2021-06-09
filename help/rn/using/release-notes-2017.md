---
solution: Campaign Standard
product: campaign
title: Notas de versão 2017
description: Essa página lista todas as versões 2017 do Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Visão geral
role: Business Practitioner
level: Beginner
exl-id: 73a1ec49-fcbc-406b-9590-1ad20da9e73b
source-git-commit: df86191b2941a6121a52b2255e19f8b623b64be6
workflow-type: tm+mt
source-wordcount: '4625'
ht-degree: 8%

---

# Notas de versão 2017{#release-notes}

Procurando uma versão específica de 2017 do Adobe Campaign Standard?

Cada versão vem com novos recursos e patches. Clique em uma versão para exibir seu conteúdo.

Visualize as [atualizações de documentação](../../rn/using/documentation-updates.md) mais recentes para o Adobe Campaign Standard. Se estiver procurando uma versão mais recente, consulte esta [página](../../rn/using/release-notes.md).

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
   <td> O Gerenciamento de fadiga permite criar regras de fadiga para gerenciar a comunicação excessiva com perfis. As regras de fadiga são facilmente criadas, mas são extremamente flexíveis com recursos como a contagem de mensagens em vários canais (incluindo mensagens transacionais), contagem de entregas específicas somente ou aplicação de regras a perfis específicos.<br /> Para obter mais informações, consulte a <a href="../../sending/using/fatigue-rules.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Criação de conteúdo: Importar de um URL<br /> </td> 
   <td> Importar de um URL permite recuperar rapidamente seu conteúdo criativo de um site para criar emails para qualquer delivery. Além disso, você pode simplificar seu processo criativo, permitindo que terceiros compartilhem conteúdo diretamente por meio de um URL. O conteúdo importado pode ser usado de forma flexível como parte de um único delivery ou no nível de template, garantindo a consistência da marca em todas as campanhas relacionadas, sejam elas baseadas em fluxo de trabalho ou mensagens transacionais, e incluir testes A/B ou multivariados. A importação de um URL converte e rastreia automaticamente todos os links para monitorar o desempenho do email por meio do Dynamic Reporting.<br /> Para obter mais informações, consulte a <a href="../../designing/using/using-existing-content.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Plataforma_

* Correção de um problema que impedia que arquivos compactados grandes fossem descompactados corretamente.
* A segurança no gerenciamento da marca foi aprimorada. A modificação do nome e endereço do remetente de uma marca agora é reservada para administradores técnicos do Adobe.
* Para melhorar a segurança, o conteúdo gerado pelo usuário (imagens, mirror pages, landing pages etc.) não pode mais ser exibido pelo domínio adobe.com. Agora é obrigatório usar seu próprio domínio para lidar com esses recursos, por meio do uso da identidade visual.
* Correção de um problema de interface ao exibir e filtrar atividades de marketing.
* Correção de um problema que impedia que campos de data de assinatura fossem atualizados com uma chamada de API POST Rest .

_Emails, mensagens SMS e mala direta_

* Correção de um problema que poderia impedir o direcionamento de um público-alvo do tipo lista em uma mensagem, causando a falha da preparação.
* Idiomas ausentes adicionados aos recursos de delivery de email multilíngues.
* A miniatura de conteúdo, exibida no painel do delivery, agora é atualizada automaticamente quando o usuário modifica o conteúdo e salva.
* Correção de um problema relacionado ao fuso horário que impedia a abertura de um delivery.

_Notificações por push_

* Ao configurar o canal de notificação por push, a plataforma do provedor de push para iOS deve ser **apns** e para Android **gcm**.
* Correção de um erro que impedia a adição do aplicativo móvel iOS na interface do Adobe Campaign.
* As notificações por push agora são suportadas em aplicativos móveis do Android habilitados para GCM e FCM.
* Correção de um erro que impedia que o conteúdo fosse salvo ao duplicar um modelo de notificação por push.
* Agora é possível criar ou atualizar um perfil do banco de dados do Adobe Campaign reconciliando os dados dos usuários do aplicativo móvel.
* A Adobe Campaign agora prioriza o processamento das notificações transacionais por push em relação às notificações por push padrão.

_Relatórios_

* Correção de um problema que impedia que as porcentagens de cliques ativos fossem exibidas no conteúdo do email.
* Correção de um problema com a métrica de  de lista de bloqueios que era contada como uma rejeição em vez de uma rejeição.
* Correção de um problema que resultava na exibição de contagens negativas em dados de resumo.
* Correção de um problema que contava perfis no segmento de idade incorreto.
* As fórmulas de cálculo de rejeição temporária e permanente foram alteradas.

_Fluxos de trabalho_

* Correção de um problema na atividade **[!UICONTROL Load file]** que resultava em erros após a adição e remoção manual de colunas na atividade .
* O workflow técnico **[!UICONTROL deliverabilityUpdate]** agora está agendado para ser executado às 2h, horário do servidor.
* Correção de um problema de segurança que permitia executar uma exportação de lista sem a função de exportação.
* Correção de um problema com a atividade **[!UICONTROL Reconciliation]** .
* Correção de um problema com o uso de caracteres curingas na atividade **[!UICONTROL File Transfer]** .

_Perfis e públicos_

* Correção de um problema que impedia que uma condição de um query fosse considerada corretamente em alguns casos específicos, resultando em resultados incorretos.
* Correção de um problema que impedia que os perfis fossem acessados se fossem direcionados a uma mensagem que foi preparada, mas nunca enviada e expirada.

_Integrações_

* Correção de um problema que impedia que algumas Fontes de dados criadas para os Acionadores fossem exibidas e selecionadas corretamente.

_Recursos personalizados_

* Correção de um problema que ocorria em telas de lista em que linhas de recurso personalizadas podiam ser exibidas sem dados.
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
   <td> Apresentando dezoito novos modelos responsivos projetados em dois lindos temas: o Astro e o Feather. Esses modelos personalizáveis são independentes do setor e estão prontos para serem usados imediatamente. Os modelos incluem conteúdo para uma variedade de casos de uso para que suas campanhas de marketing por email sejam projetadas e entregues de forma mais rápida, eficiente e bonita do que nunca.<br /> Para obter mais informações, consulte a <a href="../../designing/using/using-reusable-content.md#content-templates">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Relatórios dinâmicos com dados de perfil<br /> </td> 
   <td> Os Relatórios dinâmicos fornecem relatórios comerciais totalmente personalizáveis e em tempo real. Com esta versão, um aprimoramento poderoso nos Relatórios dinâmicos adiciona acesso aos dados do perfil, permitindo a análise demográfica por dimensões de perfil, como gênero, cidade, código postal e idade, além de dados funcionais de campanha de email, como aberturas e cliques. Com a mesma interface de arrastar e soltar fácil de usar, determinar o desempenho de sua campanha de email em relação aos segmentos de clientes mais importantes é mais fácil do que nunca.<br /> Para obter mais informações, consulte a <a href="../../reporting/using/about-dynamic-reports.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Assinatura em massa com origem e data<br /> </td> 
   <td> Com essa melhoria na Assinatura em massa, agora é possível armazenar informações de assinatura (origem e data) diretamente no banco de dados do Adobe Campaign Standard por meio da atividade Serviços de assinatura em um workflow.<br /> Para obter mais informações, consulte a <a href="../../automating/using/subscription-services.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Plataforma_

* Alguns clientes precisam aproveitar uma ID proveniente do Adobe Campaign Standard, pois não gerenciam uma chave exclusiva para identificar seus próprios registros. Essa ID (**ACS ID**) pode ser exportada, bem como usada como uma chave de reconciliação ao atualizar os dados. Para obter mais informações, consulte a [documentação detalhada](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).
* O protocolo FTP está sendo substituído. Agora você deve usar SFTP em vez disso. Para não bloquear implementações existentes, as configurações existentes no FTP ainda funcionarão como antes, mas a opção não será exibida para novas atividades.

_Emails, mensagens SMS e mala direta_

* Agora é possível criar novos critérios de alerta para usá-los nas notificações de alerta de delivery. Para obter mais informações, consulte a [documentação detalhada](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* As notificações de alerta de delivery têm um novo design e a experiência do usuário do painel de alertas de delivery foi aprimorada.
* Agora, quando uma conta externa de roteamento é desativada, um aviso é exibido nos deliveries afetados (email, SMS e push) e o botão **Preview** fica oculto nesses deliveries.
* Correção de um problema que causava um erro na visualização de um teste A/B no conteúdo do email quando o texto dinâmico era ativado na linha de assunto.

_Mensagens transacionais_

* Agora é possível definir quando você deseja enviar uma mensagem de acompanhamento, por exemplo, 3 dias após o envio de uma mensagem transacional. Para obter mais informações, consulte a [documentação detalhada](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).
* Agora é possível definir a data a partir de quando as mensagens transacionais vinculadas a um evento devem ser enviadas.
* Correção de um problema que causava um erro de SQL ao executar um workflow contendo uma mensagem de acompanhamento após excluir perfis vinculados a eventos recebidos e processados.
* Correção de um erro que impedia a exclusão de um perfil vinculado a um evento.
* Correção de um problema que impedia o funcionamento do redirecionamento de links rastreados.
* Correção de um problema que impedia a desativação do rastreamento de determinados links em um email ou mensagem SMS.

_Relatórios_

* O relatório **Hot clicks** foi aprimorado. Além disso, agora é possível exibir cliques ativos de acordo com cada conteúdo condicional definido em um delivery e exibir cliques ativos para cada execução de deliveries recorrentes ou mensagens transacionais. Para obter mais informações, consulte a [documentação detalhada](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Correção de um problema que impedia que a métrica de quarentena recuperasse os dados corretos.
* Um novo período predefinido foi adicionado ao widget de calendário.
* As [métricas de relatório dinâmico](../../reporting/using/indicator-calculation.md) e os KPIs [das campanhas](../../sending/using/confirming-the-send.md) (exibidos no painel de mensagens enviadas) foram alinhados para maior coerência.
* Correção de um problema que resultava em falha de pipeline no debian 7.

_Fluxos de trabalho_

* Correção de um problema que impedia o funcionamento da retenção de arquivos importada.

_Integrações_

* Agora, as eVars e os eventos são compatíveis com a integração do Analytics &amp; Campaign.
* Ao enviar um email com o conteúdo do carrinho abandonado, o parâmetro de carga para elementos removidos do carrinho agora é opcional.

_Perfis e públicos_

* O Adobe Campaign agora fornece um relatório que exibe o número de perfis ativos. Este relatório é apenas informativo, não tem impacto direto na cobrança. Para obter mais informações, consulte a [documentação detalhada](../../audiences/using/active-profiles.md).
* Correção de um problema que impedia a assinatura de perfis em um serviço ao usar a API de Perfis e Serviços.

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
   <td> Deliveries multilíngue de email e SMS<br /> </td> 
   <td> Defina e execute entregas de emails e SMS multilíngues por meio de um único delivery com base no idioma preferencial dos clientes segmentados automaticamente. Relate o desempenho de cada delivery até os níveis de idioma e pessoa.<br /> Cada vez mais empresas enfrentam o desafio de fornecer conteúdo em vários idiomas à medida que crescem internamente e no exterior. Como tal, a simplificação do fornecimento de mensagens localizadas é uma parte fundamental de uma estratégia eficaz de comunicação com os clientes para empresas multinacionais; Empresas em países com múltiplas línguas; e empresas que desejam personalizar ainda mais o conteúdo no nível da linguagem, independentemente de onde os clientes residem. Para obter mais informações, consulte a <a href="../../channels/using/creating-a-multilingual-email.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificações do Adobe Campaign<br /> </td> 
   <td> Receba notificações sobre atividades importantes do sistema diretamente no Adobe Campaign Standard. Você será notificado, por exemplo, sobre o progresso dos deliveries em andamento ou quando um workflow estiver com erro.<br /> As notificações em tempo real mantêm os participantes relevantes informados e fornecem aos usuários a capacidade de agir imediata e diretamente nas notificações de atividades dentro do aplicativo. O resultado para as equipes é agilidade avançada, eficiência e execução mais suave de campanhas. Para obter mais informações, consulte a <a href="../../administration/using/sending-internal-notifications.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Alertas de entrega<br /> </td> 
   <td> Além de visualizar as notificações diretamente no Adobe Campaign Standard, o Adobe Campaign agora também oferece um sistema de alerta por email para acionar alertas de email a usuários ou participantes externos de atividades importantes do sistema. Crie, gerencie e receba alertas e painéis personalizáveis para acompanhar sucessos ou falhas do delivery.<br /> Os Alertas de envio do Adobe Campaign aumentam a eficiência, mantendo todos os usuários do Adobe Campaign envolvidos em uma empresa informados automaticamente sobre o status de execução da entrega, por email e pelo painel. Para obter mais informações, consulte a <a href="../../sending/using/receiving-alerts-when-failures-happen.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> ID declarada criptografada em fontes de dados<br /> </td> 
   <td> Envie acionadores de email e SMS sem precisar de um perfil existente no Campaign usando informações de contato criptografadas (endereço de email ou número de telefone) como uma ID declarada. Como as IDs declaradas criptografadas podem ser decodificadas pelo Adobe Campaign Standard, o Campaign agora pode criar novos perfis comercializáveis ao receber públicos-alvo de outras soluções do Experience Cloud que contenham contatos anteriormente desconhecidos.<br /> Direcione clientes e prospetos desconhecidos em tempo real por meio de email e SMS para melhorar a fidelidade de sua base de clientes existente e adquirir novos clientes, respectivamente. Aproveite ao máximo seus dados de cookies primários (do Adobe Audience Manager*) uma vez que os prospetos autenticarem e aproveitarem esses insights no Adobe Campaign. <br /> *Adobe Audience Manager é necessário. Para obter mais informações, consulte a <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Compartilhamento de KPI do Campaign para o Analytics<br /> </td> 
   <td> Compartilhe dados de campanha com o Adobe Analytics para medir métricas de marketing por email do Campaign junto a outros esforços de marketing e publicidade por meio da conversão, unindo os comportamentos anterior e posterior ao clique.<br /> Acompanhe diretamente o desempenho geral e descubra sinergias com programas externos no Analytics. Aplique seu aprendizado com essa exibição consolidada novamente em suas campanhas; por fim, melhorando as taxas de abertura, click-through e conversão, aumentando a receita e o desempenho geral da campanha. <br /> O Adobe Analytics é obrigatório. Para obter mais informações, consulte a <a href="../../integrating/using/about-campaign-analytics-integration.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Canal de correspondência direta - Retornar ao remetente<br /> </td> 
   <td> Agora são compatíveis trocas de arquivos simples com provedores de Correspondência direta incorporando informações Retornar para o remetente. Esse aprimoramento no canal Correspondência direta permite que endereços postais correspondentes sejam excluídos de comunicações futuras.<br /> Isso permite que os profissionais de marketing sejam notificados sobre um endereço incorreto e interajam com o cliente por meio de outros canais ou o incentivem a atualizar seu endereço postal. Isso também reduz o número de gastos com marketing, pois os profissionais de marketing evitam enviar emails para endereços incorretos. <br /> A Correspondência direta está disponível como um canal complementar. Para obter mais informações, consulte a <a href="../../channels/using/return-to-sender.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Geral_

* Correção de um problema que permitia qualquer usuário exportar listas. Agora, somente os usuários com a função **[!UICONTROL Export]** podem.

_Emails, mensagens SMS e mala direta_

* Correção de um problema com o workflow **updateDeliveryExecInfo** que definia o indicador **To deliver** como 0 para deliveries de SMS.
* No **Advanced parameters** das propriedades do template de delivery, a lista suspensa **Routing** agora exibe somente as contas externas correspondentes ao tipo de mensagem do template. Por exemplo, um template do delivery de email exibe somente contas externas de email.
* Correção de um problema com o formato de email preferencial **[!UICONTROL Text]** definido para perfis de teste.
* Correção de um problema que resultava em erro de Javascript no ao selecionar o fuso horário padrão na tela de definição de agendamento de um delivery.
* Correção de um problema que impedia a exibição de coberturas nos logs de envio.
* Na tela de seleção de modelo do assistente de criação de delivery, os modelos de teste A/B e de acompanhamento agora estão ocultos por padrão. Para obter mais informações, consulte a [documentação detalhada](../../channels/using/creating-an-email.md).
* Correção de um problema que permitia a qualquer usuário enviar deliveries. Agora, somente os usuários com a função **[!UICONTROL Start deliveries]** podem. Para obter mais informações, consulte a [documentação detalhada](../../sending/using/confirming-the-send.md).

_Notificações por push_

* Correção de um problema com o URL **Campaign Tracking Endpoint** que impedia a criação de relatórios.
* Correção de um problema que impedia que o título da notificação por push fosse exibido em dispositivos Android.
* Correção de um problema que impedia a exibição da notificação por push em dispositivos iOS quando a notificação por push continha apenas um título (e nada no corpo da mensagem).
* Correção de um problema que forçava o rastreamento de URLs de anexos de mídia em um delivery, o que impedia que vídeos e imagens fossem incorporados ao delivery. O rastreamento de URLs do tipo mediaAttachmentURL agora é desativado por padrão para notificações por push.

_Relatórios_

* Correção de um problema em que os valores pareciam diferentes entre gráficos e tabela.
* Correção de um problema que exibia valores de notificação por push como valores de email.
* Correção de um problema que mostrava valores como desconhecidos quando um delivery era criado fora de uma campanha.
* Correção de um problema que mostrava dados de relatório de SMS como dados de aplicativo móvel.

_Fluxos de trabalho_

* Agora é possível filtrar logs de fluxo de trabalho (período e pesquisa de texto). Para obter mais informações, consulte a [documentação detalhada](../../automating/using/monitoring-workflow-execution.md).
* Uma opção agora está disponível nos deliveries do workflow para desativar a confirmação antes do envio.
* Correção de um problema que impedia a configuração de uma transição de saída no assistente de criação de delivery recorrente.
* Correção de um problema que ocorria ao usar uma atividade de query de workflow com base em um campo de recurso personalizado com uma enumeração que tinha muitos valores

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
   <td> Quebre a barreira digital e conecte-se ao mundo físico com o primeiro canal offline da Adobe Campaign Standard, Mala direta. Esse recurso permite personalizar e gerar o arquivo exigido por provedores de correspondência direta como parte de suas campanhas entre canais. Aproveite a Mala direta para engajar novamente os clientes ou aprimorar a experiência deles com um ponto de contato atraente e tátil, direcionando os clientes para seu aplicativo, site ou loja.<br /> Para obter mais informações, consulte a <a href="../../channels/using/about-direct-mail.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> CCO de email<br /> </td> 
   <td> A Cco de email permite salvar mensagens de email exclusivas enviadas para destinatários individuais, permitindo que a marca arquive essas mensagens. Ao adicionar um endereço de email CCO a todos os emails, os clientes do Adobe Campaign Standard podem manter uma cópia exata de cada email com esse recurso. Trata-se de um requisito legal comum para o setor dos serviços financeiros e é útil para ajudar os centros de atendimento ao cliente na resolução de conflitos em tempo real.<br /> Para obter mais informações, consulte a <a href="../../sending/using/archiving.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Atualizações da interface_

* Na barra superior, o link **[!UICONTROL Timeline]** foi removido e substituído por um link para **[!UICONTROL Programs & Campaigns]** .

_Emails e mensagens SMS_

* Correção de um problema que exibia a cor errada para o status de delivery **[!UICONTROL Retry in progress]**. A cor era cinza em vez de azul.

_Fluxos de trabalho_

* Correção de um problema que ocorria ao alterar a ação para executar em uma atividade **[!UICONTROL Transfer file]** .

_Relatórios_

* Os cálculos dos indicadores **[!UICONTROL Spam]** e **[!UICONTROL Spam rate]** foram alterados.
* As métricas **[!UICONTROL Bounce]** foram aprimoradas para obter um resultado mais preciso.

_Notificações por push_

* Correção de um problema que impedia o usuário de clicar em um evento de push no histórico de marketing de um perfil.
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
   <td> Recursos aprimorados de edição de imagens com o Creative SDK<br /> </td> 
   <td> Agora você tem acesso a um conjunto completo de recursos fornecidos pelo Creative SDK para aprimorar suas imagens diretamente no editor de conteúdo ao editar emails ou landing pages.<br /> Esse recurso não requer a aquisição de soluções Creative Cloud adicionais.<br /> Para obter mais informações, consulte a <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificações por push transacionais<br /> </td> 
   <td> O canal de aplicativo móvel foi adicionado aos recursos de mensagens transacionais do Adobe Campaign. Três canais agora são compatíveis com mensagens transacionais: notificações por email, SMS e push.<br /> Para obter mais informações, consulte a <a href="../../channels/using/transactional-push-notifications.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificações por push recorrentes<br /> </td> 
   <td> Agora você pode configurar notificações por push recorrentes em um workflow. Você pode usar notificações por push recorrentes em situações em que seus clientes esperam atualizações periódicas, como lembretes semanais, para verificar novos conteúdos ou promoções.<br /> Para obter mais informações, consulte a <a href="../../automating/using/push-notification-delivery.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Conector S3 (Simple Storage Service) da Amazon<br /> </td> 
   <td> O conector do Serviço de Armazenamento Simples da Amazon (S3) agora pode ser usado para importar ou exportar dados para o Adobe Campaign. Ele pode ser configurado em uma atividade de workflow. A configuração é feita em uma conta externa.<br /> Para obter mais informações, consulte a <a href="../../administration/using/external-accounts.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integração do Dreamweaver ao vivo<br /> </td> 
   <td> A integração entre o Adobe Campaign e o Dreamweaver está ativa. Agora funciona com a última versão oficial do Dreamweaver (17.0.2).<br /> Isso requer a instalação da extensão de Integração do Adobe Campaign a partir daqui:  <a href="https://adobe.ly/acdw_addon">https://adobe.ly/acdw_</a><br /> addonPara obter mais informações, consulte este  <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">vídeo</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Plataforma_

* Correção de um problema de consumo de memória.

_Emails e mensagens SMS_

* Correção de um problema em que o conteúdo não podia ser sincronizado corretamente com as alterações mais recentes ao visualizar uma mensagem.
* Correção de um problema que impedia a criação ou exclusão de uma regra de processamento de email MX ou Domain.
* Correção de um problema que impedia o envio de emails com vários aliases.
* Correção de um problema que impedia que logs de delivery de trap fossem exibidos nos logs de envio do delivery.
* Correção de um problema que resultava em erro ao exibir os URLs rastreados de um delivery sem URL em seu conteúdo.
* Correção de um problema que impedia que os atributos de tamanho de uma imagem fossem aplicados corretamente na mensagem enviada.

_Mensagens transacionais_

* O campo rtEventHistoId não é mais exposto como um campo de personalização em um template de mensagem transacional.

_Páginas de aterrissagem_

* Otimizamos o filtro **[!UICONTROL by email]** usado nas landing pages para reconciliar novos assinantes com perfis de banco de dados.
* Correção de um problema que exibia entradas de texto livre em vez de caixas de seleção ao usar campos booleanos em uma configuração de formulário.
* Correção de um problema que impedia a geração de miniaturas de landing page.

_Fluxos de trabalho_

* Correção de um erro de exibição ao editar uma atividade **[!UICONTROL End]** ou **[!UICONTROL External Signal]** (somente no Safari).
* A mensagem de erro exibida ao editar uma atividade **[!UICONTROL Read Audience]** contendo um público-alvo incorreto foi aprimorada.
* Correção de um problema que poderia levar a um erro de SQL ao executar uma atividade de assinatura.

_Integrações_

* Dados dos pontos de interesse: correção de um erro que ocorria ao contar assinantes de localização.

_Públicos-alvo e consultas_

* Correção de um problema que impedia que agregações de soma e média fossem usadas em uma coleção no editor de consultas.
* Correção de um problema que impedia o recarregamento do editor de consultas após alterar o recurso do filtro.

_Relatórios_

* Correção de um problema que impedia o cálculo correto das métricas de Taxa de abertura ao selecionar várias linhas em uma tabela.
* Correção de um erro que mostrava apenas métricas como valores inteiros. Agora, as métricas podem ser exibidas com decimais.

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
   <td> Relatórios dinâmicos<br /> </td> 
   <td> Os Relatórios dinâmicos fornecem uma nova geração de relatórios comerciais totalmente personalizáveis e em tempo real. Baseado em tabelas dinâmicas visuais e gráficos dinâmicos, esse recurso permite arrastar e soltar variáveis e dimensões para analisar a eficiência e a eficácia de suas campanhas de marketing. Os relatórios dinâmicos também permitem que você crie seus próprios relatórios de negócios do zero e os salve para uso posterior.<br /> Para obter mais informações, consulte a <a href="../../reporting/using/about-dynamic-reports.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integração do Dreamweaver (Labs)<br /> </td> 
   <td> Com a integração Adobe Campaign e Dreamweaver, agora você tem um processo integrado para criar campanhas por email com soluções do Adobe.<br /> Você pode editar emails do Adobe Campaign no Dreamweaver e ter o conteúdo sincronizado facilmente entre as duas soluções.<br /> Na versão inicial, a integração está disponível como um recurso "Labs" e funciona somente com o Dreamweaver Pre-Release Beta. Se quiser ativá-la, entre em contato com AC-DW-integration@adobe.com.<br /> Para obter mais informações, consulte este  <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">vídeo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Otimização manual do tempo de envio<br /> </td> 
   <td> Agora é possível definir manualmente uma hora de envio personalizada por recipient - no nível de delivery ou usando um workflow. <br /> Duas novas opções estão disponíveis:  <br /> 
    <ul> 
     <li> Todos os recipients recebem a mensagem levando em conta o fuso horário. </li> 
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
     <li> Suporte a conteúdo sofisticado </li> 
     <li> Calculadora de tamanho da carga </li> 
    </ul> Para obter mais informações, consulte a <a href="../../channels/using/about-push-notifications.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fluxos de trabalho: nova atividade de sinal<br /> </td> 
   <td> Acione um workflow a partir de outro workflow usando a nova atividade <span class="uicontrol">Signal</span> .<br /> Com a capacidade de iniciar um workflow a partir de outro, agora é possível oferecer suporte a jornadas de clientes mais complexas. É possível monitorar melhor as jornadas do cliente e reagir em caso de problemas.<br /> Várias atividades de workflow foram atualizadas:<br /> 
    <ul> 
     <li> <span class="uicontrol"></span> Endactivity: uma nova guia permite que você especifique um workflow a ser acionado após a execução dessa atividade. </li> 
     <li> <span class="uicontrol">Atualizar </span> atividade de dados: use a nova transição de saída vazia para adicionar uma  <strong></strong> atividade Endactivity que aciona outro workflow. Transições de saída vazias não transferem dados e não consomem espaço desnecessário no sistema </li> 
    </ul> Para obter mais informações, consulte a <a href="../../automating/using/external-signal.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fluxos de trabalho: nova atividade Ler público<br /> </td> 
   <td> Inicie o processo de direcionamento com um público-alvo existente que pode ser facilmente selecionado e refinado em uma atividade.<br /> Para obter mais informações, consulte a <a href="../../automating/using/read-audience.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dados de pontos de interesse<br /> </td> 
   <td> Os dados de pontos de interesse integram o Adobe Campaign ao Adobe Analytics for Mobile. Uma marca pode coletar dados de locais móveis dos usuários - chamados <strong>Pontos de interesse</strong> - quando eles abrem o aplicativo da marca. Isso permite que a marca aproveite os fluxos de trabalho do Adobe Campaign para enviar mensagens personalizadas com base na localização dos usuários. Esse canal utiliza o SDK do serviço principal móvel.<br /> Observe que para usar esse recurso é necessário ter o Analytics for Mobile, que é uma solução paga.<br /> Para obter mais informações, consulte a <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> REST APIs<br /> </td> 
   <td> Os recursos vinculados em qualquer nível aos perfis ou aos recursos de serviços agora estão disponíveis na API.<br /> Para obter mais informações, consulte a <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Geral_

* Agora é possível adicionar dados de perfil ao exportar logs de delivery.

_Emails e mensagens SMS_

* Correção de um problema que fazia com que a opção **[!UICONTROL Request confirmation before sending messages]** permanecesse selecionada mesmo após desmarcá-la e salvar o delivery.
* Correção de um problema que poderia impedir a despublicação de emails transacionais.
* Correção de um problema em que o conteúdo não podia ser sincronizado corretamente com as alterações mais recentes antes de visualizar um delivery.

_Páginas de aterrissagem_

* Correção de um erro que impedia o usuário de editar ao clicar no conteúdo de uma landing page.

_Fluxos de trabalho_

* Correção de um problema que poderia impedir a leitura do conteúdo da transição de rejeição de uma atividade **[!UICONTROL Load file]** .
* Correção de um problema que impedia que colunas trocadas fossem devidamente levadas em conta ao configurar uma atividade **[!UICONTROL Load file]** .

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
   <td> Exportar logs, como logs de delivery e rastreamento, para processá-los em seus relatórios preferidos ou ferramentas de BI. Você pode usar workflows simples com queries incrementais para automatizar exportações regulares de novos logs.<br /> Além da disponibilidade dos recursos de log do seletor de recursos, foram feitos aprimoramentos nas atividades  <a href="../../automating/using/incremental-query.md">Incremental </a> de query e  <a href="../../automating/using/extract-file.md">Extract </a> do arquivo:<br /> 
    <ul> 
     <li> <span class="uicontrol">Agora, o </span> query incremental permite usar um campo de data para recuperar dados novos ou atualizados. Anteriormente, todos os resultados de execuções anteriores eram excluídos automaticamente, mesmo se fossem atualizados desde a última execução. </li> 
     <li> <span class="uicontrol">Extrair </span> arquivo agora pode exportar rótulos para valores de enumeração em vez de IDs. </li> 
    </ul> Essas atividades estão disponíveis para administradores com acesso a todas as unidades geográficas e organizacionais.<br /> Para obter mais informações sobre exportação de logs, consulte a documentação  <a href="../../automating/using/exporting-logs.md">detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Recursos de marketing para mensagens transacionais<br /> </td> 
   <td> Os profissionais de marketing agora podem enviar mensagens transacionais com base nos perfis de marketing do cliente. Isso permite:<br /> 
    <ul> 
     <li> Aplique regras de tipologia de marketing, como <span class="uicontrol">Endereço na lista de bloqueios</span> . </li> 
     <li> Incluir o link de unsubscription nas mensagens. </li> 
     <li> Adicionar as mensagens transacionais aos relatórios globais do delivery. </li> 
     <li> Usar as mensagens transacionais na jornada do cliente. </li> 
    </ul> Para obter mais informações, consulte a <a href="../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API de mensagens transacionais<br /> </td> 
   <td> A API de mensagens transacionais agora está disponível por meio de <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>, facilitando o uso e o monitoramento:<br /> 
    <ul> 
     <li> Você pode se beneficiar dos recursos de monitoramento e emissão de relatórios da plataforma adobe.io. </li> 
     <li> A autenticação agora é realizada usando a autenticação baseada em token adobe.io em vez do  de IP incluir na lista de permissões, tornando o processo de segurança mais simples. </li> 
     <li> Todas as APIs agora são integradas em uma única plataforma, tornando mais simples do que nunca adicionar recursos de mensagens transacionais à integração, se você já oferecer suporte à API de Perfil e Serviços. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Geral_

* As opções **[!UICONTROL Access authorization]** retornaram às propriedades da landing page.
* Correção de um problema que poderia ter causado a renderização de uma imagem antiga em vez da imagem correta. Isso ocorria se a imagem de origem tivesse sido atualizada na definição de conteúdo de um delivery ou landing page.
* Correção de um problema que impedia os usuários de editar determinados campos em uma conta externa SFTP existente.
* Correção de vários problemas da interface do usuário do . Por exemplo, os usuários agora podem editar atributos de perfil e salvar modificações sem ter problemas com a interface do usuário.

_Emails e mensagens SMS_

* Correção de um problema relacionado aos templates do delivery com conteúdo HTML que contém um

_Notificações por push_

* Correção de um problema que pode ter impedido o postback de um aplicativo para o servidor do Adobe Campaign.
* Correção de um problema que poderia ter impedido **[!UICONTROL Play a sound]** e **[!UICONTROL Custom fields]** de serem considerados para o Android.
* Correção de um problema que poderia ter feito com que um caractere de escape extra fosse adicionado aos caracteres Unicode usados para Emojis.
* Quando um token de registro de um assinante é adicionado à  de lista de bloqueios, o status correspondente agora é atualizado imediatamente na lista de assinantes do aplicativo no Adobe Campaign.

_Fluxos de trabalho_

* Correção de um problema que poderia ter impedido visualizações de consultas em recursos de evento (por exemplo, rtEvent).
* O arquivo de rejeição gerado por uma atividade **[!UICONTROL Load file]** agora pode ser recuperado na transição de saída e processado na próxima atividade. Por exemplo, carregue o arquivo de rejeição por meio de um servidor SFTP usando **[!UICONTROL Transfer file]** .
* Correção de um problema que poderia ter impedido um usuário de limitar a população de um segmento se **[!UICONTROL Temporary resource]** fosse selecionado na guia **[!UICONTROL General]** de **[!UICONTROL Segmentation]** .
* **[!UICONTROL Scheduler]** As atividades do não podem mais ser definidas para acionar um workflow mais de uma vez a cada 10 minutos.
* Correção de um problema que poderia ter impedido **[!UICONTROL Use common columns]** de funcionar corretamente em uma atividade **[!UICONTROL Union]** .

_Integrações_

* Correção de um problema que poderia ter causado um erro ao implantar um acionador de evento no Adobe Campaign. Esse erro ocorria quando os metadados &quot;Probabilidade de retorno em 30 dias&quot; eram adicionados ao acionador de Abandono no Adobe Marketing Cloud.
* Correção de um problema que poderia ter causado a limpeza do workflow técnico no campo Dimension do Target ao importar públicos do serviço principal Pessoas . As consultas subsequentes não conseguiram recuperar os públicos importados.
* Correção de um problema que poderia causar falha na atividade **[!UICONTROL Save audience]** de um workflow quando a opção **[!UICONTROL Share in Adobe Marketing Cloud]** era marcada.
