---
title: Notas de versão 2017
description: Esta página lista todas as versões 2017 do Adobe Campaign Standard.
page-status-flag: never-activated
uuid: d73f8186-e309-441b-969d-71d0a1c33cf4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 1cfd9b3b-9b3e-4587-9c46-b6fb02131654
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a34cc1a8848b21ea01b9a20b9deb9be5b5e3895

---


# Notas de versão 2017{#release-notes}

Procurando uma versão específica de 2017 do Adobe Campaign Standard?

Cada versão traz novos recursos e correções. Clique em uma versão para exibir seu conteúdo.

Exiba as atualizações [mais recentes da](../../rn/using/documentation-updates.md) documentação do Adobe Campaign Standard. Se você estiver procurando uma versão mais recente, consulte esta [página](../../rn/using/release-notes.md).

## Versão 17.10 - outubro de 2017 {#release-17-10---october-2017}

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
   <td> O Gerenciamento de fadiga permite que você crie regras de fadiga para gerenciar a comunicação excessiva com perfis. As regras de fadiga são facilmente criadas, mas são extremamente flexíveis com recursos como contagem de mensagens em vários canais (incluindo mensagens transacionais), contagem de entregas específicas apenas ou aplicação de regras a perfis específicos.<br /><a href="../../administration/using/fatigue-rules.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Criação de conteúdo: Importar de um URL<br /> </td> 
   <td> Importar de um URL permite recuperar rapidamente seu conteúdo criativo de um site para criar emails para qualquer entrega. Além disso, você pode simplificar seu processo criativo, permitindo que terceiros compartilhem conteúdo diretamente por meio de um URL. O conteúdo importado pode ser usado de forma flexível como parte de uma única entrega ou no nível do modelo, garantindo a consistência da marca para todas as campanhas relacionadas, sejam elas baseadas em fluxo de trabalho ou mensagens transacionais, e incluam testes A/B ou multivariados. A importação de um URL converte e rastreia automaticamente todos os links para monitorar o desempenho do email por meio do Relatório dinâmico.<br /><a href="../../designing/using/using-existing-content.md#importing-content-from-a-url"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Plataforma_

* Correção de um problema que impedia que arquivos compactados grandes fossem descompactados corretamente.
* A segurança no gerenciamento de marcas foi aprimorada. A modificação do nome e endereço do remetente de uma marca agora está reservada para administradores técnicos da Adobe.
* Para melhorar a segurança, o conteúdo gerado pelo usuário (imagens, páginas espelhadas, páginas de aterrissagem, etc.) não pode mais ser servido pelo domínio adobe.com. Agora é obrigatório usar seu próprio domínio para lidar com esses recursos, por meio do uso da marca.
* Correção de um problema de interface ao exibir e filtrar atividades de marketing.
* Correção de um problema que impedia que campos de datas de assinatura fossem atualizados com uma chamada POST Rest API.

_Emails, mensagens SMS e mala direta_

* Correção de um problema que impedia o direcionamento de um público-alvo do tipo de lista em uma mensagem, fazendo com que a preparação falhasse.
* Idiomas ausentes adicionados aos recursos de entrega de email multilíngues.
* A miniatura do conteúdo, exibida no painel de entrega, agora é atualizada automaticamente quando o usuário modifica o conteúdo e salva.
* Correção de um problema relacionado ao fuso horário que impedia a abertura de uma entrega.

_Notificações por push_

* Ao configurar o canal de notificação por push, a plataforma do provedor de push para iOS deve ser **apns** e para Android **gcm**.
* Correção de um erro que impedia que o aplicativo móvel iOS fosse adicionado na interface do Adobe Campaign.
* As notificações por push agora são suportadas em aplicativos móveis Android habilitados para GCM e FCM.
* Correção de um erro que impedia o conteúdo de ser salvo ao duplicar um modelo de notificação por push.
* Agora é possível criar ou atualizar um perfil do banco de dados do Adobe Campaign reconciliando os dados dos usuários do aplicativo móvel.
* O Adobe Campaign agora prioriza o processamento das notificações por push transacionais em vez das notificações por push padrão.

_Relatórios_

* Correção de um problema que impedia que as porcentagens de cliques ativos fossem exibidas no conteúdo do email.
* Correção de um problema com a métrica da lista negra que era contada como uma rejeição em vez de uma rejeição.
* Correção de um problema que resultava na exibição de contagens negativas em dados de resumo.
* Correção de um problema que contava perfis no segmento de idade errado.
* As fórmulas de cálculo de rejeição flexível e rígida foram alteradas.

_Fluxos de trabalho_

* Correção de um problema na **[!UICONTROL Load file]** atividade que resultava em erros após a adição e remoção manual de colunas na atividade.
* O fluxo de trabalho **[!UICONTROL deliverabilityUpdate]** técnico está agendado para ser executado às 2h00, horário do servidor.
* Correção de um problema de segurança que permitia executar uma exportação de lista sem a função de exportação.
* Correção de um problema com a **[!UICONTROL Reconciliation]** atividade.
* Correção de um problema com o uso de caracteres curinga na **[!UICONTROL File Transfer]** atividade.

_Perfis e públicos-alvo_

* Correção de um problema que impedia que uma condição de uma consulta fosse considerada corretamente em alguns casos específicos, resultando em resultados errados.
* Correção de um problema que impedia que perfis fossem acessados se fossem direcionados em uma mensagem preparada, mas nunca enviada e expirada.

_Integrações_

* Correção de um problema que impedia que algumas Fontes de Dados criadas para Acionadores fossem exibidas e selecionadas corretamente.

_Recursos personalizados_

* Correção de um problema que ocorria em telas de lista em que linhas de recursos personalizados podiam ser exibidas sem dados.
* Correção de um problema que impedia que campos de tipo booleano com valor &quot;Falso&quot; fossem exibidos em recursos personalizados.

## Versão 17.9 - setembro de 2017 {#release-17-9---september-2017}

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
   <td> Apresentamos 18 novos modelos responsivos projetados em dois lindos temas: o Astro e o Feather. Esses modelos personalizáveis são agnósticos do setor e estão prontos para serem usados imediatamente. Os modelos incluem conteúdo para uma variedade de casos de uso para que suas campanhas de marketing por email sejam projetadas e entregues de forma mais rápida, eficiente e bonita do que nunca.<br /><a href="../../designing/using/using-reusable-content.md#content-templates"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Relatório dinâmico com dados de perfil<br /> </td> 
   <td> Os Relatórios dinâmicos fornecem relatórios comerciais totalmente personalizáveis e em tempo real. Com esta versão, um aprimoramento poderoso do Relatório dinâmico adiciona acesso aos dados do perfil, permitindo a análise demográfica por dimensões de perfil como gênero, cidade, código postal e idade, além de dados funcionais de campanha por email como abertos e cliques. Com a mesma interface de arrastar e soltar fácil de usar, determinar como sua campanha de email se comporta em relação aos segmentos de clientes mais importantes é mais fácil do que nunca.<br /><a href="../../reporting/using/about-dynamic-reports.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Assinatura em massa com origem e data<br /> </td> 
   <td> Com esse aprimoramento de assinatura em massa, agora você pode armazenar informações de assinatura (origem e data) diretamente no banco de dados do Adobe Campaign Standard por meio da atividade Serviços de assinatura em um fluxo de trabalho.<br /><a href="../../automating/using/subscription-services.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Plataforma_

* Alguns clientes precisam aproveitar uma ID proveniente do Adobe Campaign Standard, pois não gerenciam uma chave exclusiva para identificar seus próprios registros. Essa ID (ID **** ACS) pode ser exportada e usada como uma chave de reconciliação ao atualizar os dados. Para obter mais informações, consulte a [documentação detalhada](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).
* O protocolo FTP está sendo substituído. Agora você deve usar o SFTP. Para não bloquear implementações existentes, as configurações existentes no FTP ainda funcionarão como antes, mas a opção não será exibida para novas atividades.

_Emails, mensagens SMS e mala direta_

* Agora é possível criar novos critérios de alerta para usá-los em notificações de alerta de entrega. Para obter mais informações, consulte a [documentação detalhada](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* As notificações de aviso de entrega têm um novo design e a experiência do usuário do painel de alertas de entrega foi aprimorada.
* Agora, quando uma conta externa de roteamento é desativada, um aviso é exibido nas entregas impactadas (email, SMS e push) e o botão **Visualizar** fica oculto nessas entregas.
* Correção de um problema que causava um erro na visualização de um teste A/B no conteúdo de email quando o texto dinâmico era ativado na linha de assunto.

_Mensagens transacionais_

* Agora é possível definir quando você deseja enviar uma mensagem de acompanhamento, por exemplo, 3 dias após o envio de uma mensagem transacional. Para obter mais informações, consulte a [documentação detalhada](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).
* Agora é possível definir a data a partir da qual as mensagens transacionais vinculadas a um evento devem ser enviadas.
* Correção de um problema que causava um erro de SQL ao executar um fluxo de trabalho contendo uma mensagem de acompanhamento após excluir perfis vinculados a eventos recebidos e processados.
* Correção de um erro que impedia a exclusão de um perfil vinculado a um evento.
* Correção de um problema que poderia impedir o redirecionamento de links rastreados de funcionar.
* Correção de um problema que impedia a desativação do rastreamento de determinados links em um email ou mensagem SMS.

_Relatórios_

* O relatório de cliques **em** funcionamento foi aprimorado. Além disso, agora é possível exibir cliques ativos de acordo com cada conteúdo condicional que foi definido em uma entrega e exibir cliques ativos para cada execução de entregas recorrentes ou mensagens transacionais. Para obter mais informações, consulte a [documentação detalhada](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Correção de um problema que impedia a métrica de quarentena de recuperar dados corretos.
* Um novo período predefinido foi adicionado ao widget de calendário.
* As métricas [de relatório](../../reporting/using/indicator-calculation.md) dinâmico e os KPIs [das](../../sending/using/confirming-the-send.md) campanhas (exibidos no painel de mensagens enviadas) foram alinhados para maior coerência.
* Correção de um problema que resultava em falha de pipeline no debian 7.

_Fluxos de trabalho_

* Correção de um problema que impedia o funcionamento da retenção de arquivos importados.

_Integrações_

* As eVars e os eventos agora são compatíveis com a integração do Analytics e Campaign.
* Ao enviar um email com o conteúdo do carrinho abandonado, o parâmetro de carga para elementos removidos do carrinho agora é opcional.

_Perfis e públicos-alvo_

* O Adobe Campaign agora fornece um relatório que exibe o número de perfis ativos. Este relatório é apenas informativo, não tem impacto direto na cobrança. Para obter mais informações, consulte a [documentação detalhada](../../audiences/using/active-profiles.md).
* Correção de um problema que impedia a inscrição de perfis em um serviço ao usar a API Perfis e serviços.

## Versão 17.7 - julho de 2017 {#release-17-7---july-2017}

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
   <td> Envios de e-mail multilíngue e SMS<br /> </td> 
   <td> Defina e execute entregas de email e SMS multilíngues por meio de uma única entrega com base no idioma preferencial de seus clientes segmentados automaticamente. Relatório sobre o desempenho de cada entrega até os níveis de idioma e individual.<br /> Cada vez mais empresas enfrentam o desafio de fornecer conteúdo em vários idiomas à medida que crescem em casa e no exterior. Como tal, a simplificação da entrega de mensagens traduzidas é uma parte essencial de uma estratégia eficaz de comunicação dos clientes para as empresas multinacionais; empresas em países com múltiplas línguas; e empresas que desejam personalizar ainda mais seu conteúdo em nível de idioma, independentemente de onde os clientes residam. Para obter mais informações, consulte a <a href="../../channels/using/creating-a-multilingual-email.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificações do Adobe Campaign<br /> </td> 
   <td> Receba notificações sobre atividades importantes do sistema diretamente no Adobe Campaign Standard. Você será notificado, por exemplo, sobre o andamento de suas entregas em andamento ou quando um fluxo de trabalho estiver com erro.<br /> As notificações em tempo real mantêm as partes interessadas relevantes informadas e fornecem aos usuários a capacidade de agir imediata e diretamente nas notificações de atividade de dentro do aplicativo. O resultado para as equipes é agilidade avançada, eficiência e execução mais suave de campanhas. Para obter mais informações, consulte a <a href="../../administration/using/sending-internal-notifications.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Alerta de entrega<br /> </td> 
   <td> Além de visualizar notificações diretamente no Adobe Campaign Standard, o Adobe Campaign agora também fornece um sistema de alerta por email para acionar alertas por email a usuários ou participantes externos de atividades importantes do sistema. Crie, gerencie e receba alertas e painéis personalizáveis para rastrear sucessos ou falhas de entrega.<br /> O Alerta de entrega do Adobe Campaign aumenta a eficiência, mantendo todos os usuários envolvidos do Adobe Campaign em uma empresa automaticamente informados sobre o status de execução da entrega, por email e painel. Para obter mais informações, consulte a <a href="../../sending/using/receiving-alerts-when-failures-happen.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> ID declarada criptografada em fontes de dados<br /> </td> 
   <td> Envie acionadores de email e SMS sem precisar de um perfil existente no Campaign usando informações de contato criptografadas (endereço de email ou número de telefone) como uma ID declarada. Como as IDs declaradas criptografadas podem ser decodificadas pelo Adobe Campaign Standard, o Campaign agora pode criar novos perfis comercializáveis ao receber públicos-alvo de outras soluções da Experience Cloud que contenham contatos desconhecidos anteriormente.<br /> Direcione clientes e clientes potenciais desconhecidos em tempo real por meio de email e SMS para melhorar a fidelidade em sua base de clientes existente e adquirir novos clientes, respectivamente. Aproveite ao máximo seus dados de cookies originais (do Adobe Audience Manager*) uma vez que os prospetos autenticarem e aproveitarem esses insights no Adobe Campaign. <br /> *O Adobe Audience Manager é obrigatório. Para obter mais informações, consulte a <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Compartilhamento de KPI do Campaign para o Analytics<br /> </td> 
   <td> Compartilhe dados de campanha com o Adobe Analytics para medir métricas de marketing por email do Campaign, juntamente com outros esforços de marketing e publicidade por meio da conversão, unificando o comportamento pré e pós-clique.<br /> Acompanhe diretamente o desempenho geral e descubra sinergias com programas externos no Analytics. Aplique seu aprendizado desta exibição consolidada de volta às suas campanhas; melhorando, em última análise, as taxas de conversão, de click-through e de abertura, aumentando a receita e o desempenho geral da campanha. <br /> O Adobe Analytics é obrigatório. Para obter mais informações, consulte a <a href="../../integrating/using/about-campaign-analytics-integration.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Canal de mala direta - Retornar ao remetente<br /> </td> 
   <td> Agora há suporte para trocas de arquivos simples com provedores de Mala direta incorporando informações de Retorno ao remetente. Essa melhoria no canal de Mala direta permite que endereços postais correspondentes sejam excluídos de futuras comunicações.<br /> Isso permite que os profissionais de marketing sejam notificados de um endereço incorreto e interajam com o cliente por meio de outros canais ou que o incentivem a atualizar seu endereço postal. Isso também reduz o número de dólares de marketing desperdiçados, já que os profissionais de marketing evitam enviar emails para endereços incorretos. <br /> A Mala direta está disponível como um canal de expansão. Para obter mais informações, consulte a <a href="../../channels/using/return-to-sender.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Geral_

* Correção de um problema que permitia que qualquer usuário exportasse listas. Agora, somente os usuários com a **[!UICONTROL Export]** função podem fazê-lo.

_Emails, mensagens SMS e mala direta_

* Correção de um problema com o fluxo de trabalho **updateDeliveryExecInfo** que definia o indicador **Para entregar** como 0 para entregas SMS.
* Nos parâmetros **** avançados das propriedades do modelo de entrega, a lista suspensa **Roteamento** agora exibe somente contas externas correspondentes ao tipo de mensagem do modelo. Por exemplo, um modelo de entrega de email exibe somente contas externas de email.
* Correção de um problema com o formato de email **[!UICONTROL Text]** preferencial definido para perfis de teste.
* Correção de um problema que resultava em um erro de Javascript ao selecionar o fuso horário padrão na tela de definição de agendamento de uma entrega.
* Correção de um problema que impedia a exibição de armadilhas nos registros de envio.
* Na tela de seleção de modelo do assistente de criação de entrega, o acompanhamento e os modelos de teste A/B agora estão ocultos por padrão. For more information, refer to the [detailed documention](../../channels/using/creating-an-email.md).
* Correção de um problema que permitia que qualquer usuário enviasse entregas. Agora, somente os usuários com a **[!UICONTROL Start deliveries]** função podem fazê-lo. For more information, refer to the [detailed documention](../../sending/using/confirming-the-send.md).

_Notificações por push_

* Correção de um problema com o URL de Ponto de Extremidade **de Rastreamento de** Campanha que impedia relatórios.
* Correção de um problema que impedia que o título da notificação por push fosse exibido em dispositivos Android.
* Correção de um problema que impedia que a notificação por push fosse exibida em dispositivos iOS quando a notificação por push continha apenas um título (e nada no corpo da mensagem).
* Correção de um problema que fazia com que URLs de anexos de mídia em uma entrega fossem rastreados, o que impedia que vídeos e imagens fossem incorporados na entrega. O rastreamento de URLs do tipo mediaAttachmentURL agora é desativado por padrão para notificações por push.

_Relatórios_

* Correção de um problema em que os valores apareciam diferentes entre gráficos e tabelas.
* Correção de um problema que exibia valores de notificação por push como valores de email.
* Correção de um problema que mostrava valores como desconhecidos quando uma entrega era criada fora de uma campanha.
* Correção de um problema que mostrava dados de relatório SMS como dados de aplicativo móvel.

_Fluxos de trabalho_

* Agora é possível filtrar logs de fluxo de trabalho (período de tempo e pesquisa de texto). For more information, refer to the [detailed documention](../../automating/using/executing-a-workflow.md#monitoring).
* Uma opção agora está disponível em entregas de fluxo de trabalho para desativar a confirmação antes do envio.
* Correção de um problema que impedia a configuração de uma transição de saída no assistente de criação de entrega recorrente.
* Correção de um problema que ocorria ao usar uma atividade de consulta de fluxo de trabalho com base em um campo de recurso personalizado com uma enumeração que tinha muitos valores

## Versão 17.5 - maio de 2017 {#release-17-5---may-2017}

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
   <td> Correio direto<br /> </td> 
   <td> Quebre a barreira digital e conecte-se ao mundo físico com o primeiro canal offline do Adobe Campaign Standard, Mala direta. Esse recurso permite que você personalize e gere o arquivo exigido pelos provedores de mala direta como parte de suas campanhas entre canais. Aproveite a Mala direta para envolver novamente os clientes ou aprimorar a experiência do cliente com um ponto de contato atraente e tátil, levando os clientes ao seu aplicativo, site ou loja.<br /><a href="../../channels/using/about-direct-mail.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cco de email<br /> </td> 
   <td> A Cco de email permite salvar mensagens de email únicas enviadas a destinatários individuais, permitindo assim que a marca arquive essas mensagens. Ao adicionar um endereço de email Cco a todos os emails, os clientes do Adobe Campaign Standard podem manter uma cópia exata de cada email com esse recurso. Este é um requisito legal comum para o setor de serviços financeiros e é útil para auxiliar os centros de atendimento ao cliente na resolução de conflitos em tempo real.<br /><a href="../../sending/using/archiving.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Atualizações da interface_

* Na barra superior, o **[!UICONTROL Timeline]** link foi removido e substituído por um link para **[!UICONTROL Programs & Campaigns]** .

_Emails e mensagens SMS_

* Correção de um problema que exibia a cor errada para o status de **[!UICONTROL Retry in progress]** entrega. A cor era cinza em vez de azul.

_Fluxos de trabalho_

* Correção de um problema que ocorria ao alterar a ação para executar em uma **[!UICONTROL Transfer file]** atividade.

_Relatórios_

* Os cálculos do **[!UICONTROL Spam]** e do **[!UICONTROL Spam rate]** indicador foram alterados.
* As **[!UICONTROL Bounce]** métricas foram aprimoradas para obter um resultado mais preciso.

_Notificações por push_

* Correção de um problema que impedia que você clicasse em um evento de push no histórico de marketing de um perfil.
* O uso de notificações por push em fluxos de trabalho foi aprimorado.

## Versão 17.4 - abril de 2017 {#release-17-4---april-2017}

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
   <td> Agora você tem acesso a um conjunto completo de recursos capacitados pelo Creative SDK para aprimorar suas imagens diretamente no editor de conteúdo ao editar emails ou páginas iniciais.<br /> Esse recurso não exige a aquisição de soluções adicionais da Creative Cloud.<br /><a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificações por push transacionais<br /> </td> 
   <td> O canal do aplicativo móvel foi adicionado aos recursos de mensagens transacionais do Adobe Campaign. Três canais agora são suportados para mensagens transacionais: email, SMS e notificações por push.<br /><a href="../../channels/using/transactional-push-notifications.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificações por push recorrentes<br /> </td> 
   <td> Agora você pode configurar notificações por push recorrentes em um fluxo de trabalho. Você pode usar notificações por push recorrentes em situações em que seus clientes esperam atualizações periódicas, como lembretes semanais, para fazer check-out de novo conteúdo ou promoções.<br /><a href="../../automating/using/push-notification-delivery.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Conector do Amazon Simple Storage Service (S3)<br /> </td> 
   <td> O conector do Amazon Simple Storage Service (S3) agora pode ser usado para importar ou exportar dados para o Adobe Campaign. Ele pode ser configurado em uma atividade 
                de workflow. A configuração é feita em uma conta externa.<br /><a href="../../administration/using/external-accounts.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integração do Dreamweaver ativa<br /> </td> 
   <td> A integração entre o Adobe Campaign e o Dreamweaver está agora disponível. Agora funciona com a última versão oficial do Dreamweaver (17.0.2).<br /> Isso requer a instalação da extensão de Integração do Adobe Campaign daqui: <a href="https://adobe.ly/acdw_addon">https://adobe.ly/acdw_addon</a><br /> Para obter mais informações, consulte este <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">vídeo</a>.<br /> </td> 
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
* Correção de um problema que impedia a exibição de registros de entrega de armadilhas nos registros de envio da entrega.
* Correção de um problema que resultava em erro ao exibir os URLs acompanhados de uma entrega sem URL no conteúdo.
* Correção de um problema que impedia que os atributos de tamanho de uma imagem fossem aplicados corretamente na mensagem enviada.

_Mensagens transacionais_

* O campo rtEventHistoId não é mais exposto como um campo de personalização em um modelo de mensagem transacional.

_Páginas de aterrissagem_

* Otimizamos o **[!UICONTROL by email]** filtro usado nas páginas de aterrissagem para reconciliar novos assinantes com perfis de banco de dados.
* Correção de um problema que exibia entradas de texto livre em vez de caixas de seleção ao usar campos booleanos em uma configuração de formulário.
* Correção de um problema que impedia a geração de miniaturas de página inicial.

_Fluxos de trabalho_

* Corrigido um erro de exibição ao editar uma atividade **[!UICONTROL End]** ou **[!UICONTROL External Signal]** (somente no Safari).
* A mensagem de erro exibida ao editar uma **[!UICONTROL Read Audience]** atividade que contém um público-alvo incorreto foi aprimorada.
* Correção de um problema que resultava em erro de SQL ao executar uma atividade de assinatura.

_Integrações_

* Dados de Pontos de interesse: correção de um erro que ocorria ao contar assinantes de localização.

_Públicos-alvo e consultas_

* Correção de um problema que impedia que agregados de soma e média fossem usados em uma coleção no editor de consulta.
* Correção de um problema que impedia que o editor de consultas fosse recarregado após alterar o recurso do filtro.

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
   <td> Relatório dinâmico<br /> </td> 
   <td> Os Relatórios dinâmicos fornecem uma nova geração de relatórios de negócios totalmente personalizáveis e em tempo real. Com base em tabelas e gráficos dinâmicos visuais, esse recurso permite que você arraste e solte variáveis e dimensões para analisar a eficiência e a eficácia de suas campanhas de marketing. Os relatórios dinâmicos também permitem que você crie seus próprios relatórios de negócios do zero e os salve para uso posterior.<br /><a href="../../reporting/using/about-dynamic-reports.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integração do Dreamweaver (Labs)<br /> </td> 
   <td> Com a integração do Adobe Campaign e do Dreamweaver, agora você tem um processo integrado para criar campanhas por email com as soluções da Adobe.<br /> Você pode editar emails do Adobe Campaign no Dreamweaver e ter o conteúdo sincronizado perfeitamente entre as duas soluções.<br /> Para a versão inicial, a integração está disponível como um recurso "Labs" e funciona somente com o pré-lançamento Beta do Dreamweaver. Se você quiser ativá-lo, entre em contato com AC-DW-integration@adobe.com.<br /> Para obter mais informações, consulte este <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">vídeo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Otimização do tempo de envio manual<br /> </td> 
   <td> Agora é possível definir manualmente uma hora de envio personalizada por destinatário - no nível de entrega ou usando um fluxo de trabalho. <br /> Duas novas opções estão disponíveis: <br /> 
    <ul> 
     <li> Todos os destinatários recebem a mensagem levando em conta o fuso horário. </li> 
     <li> Cada destinatário recebe a mensagem em uma data e hora computadas definidas por uma fórmula. </li> 
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
   <td> Fluxos de trabalho: nova atividade Sinal<br /> </td> 
   <td> Acionar um fluxo de trabalho de outro fluxo de trabalho usando a nova atividade <span class="uicontrol">Sinal</span> .<br /> Com a capacidade de iniciar um fluxo de trabalho a partir de outro, agora você pode oferecer suporte a jornadas de clientes mais complexas. É possível monitorar melhor as viagens do cliente e reagir em caso de problemas.<br /> Várias atividades de fluxo de trabalho foram atualizadas:<br /> 
    <ul> 
     <li> <span class="uicontrol">Atividade final</span> : uma nova guia permite que você especifique um fluxo de trabalho a ser acionado após a execução dessa atividade. </li> 
     <li> <span class="uicontrol">Atualizar atividade de dados</span> : use a nova transição de saída vazia para adicionar uma atividade <strong>End</strong> que aciona outro fluxo de trabalho. Transições de saída vazias não transmitem dados e não consomem espaço desnecessário no sistema </li> 
    </ul> Para obter mais informações, consulte a <a href="../../automating/using/external-signal.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fluxos de trabalho: nova atividade Ler público-alvo<br /> </td> 
   <td> Inicie o processo de definição de metas com um público-alvo existente que você pode selecionar e refinar facilmente em uma atividade.<br /><a href="../../automating/using/read-audience.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dados de Pontos de interesse<br /> </td> 
   <td> Os dados de Pontos de interesse integram o Adobe Campaign ao Adobe Analytics para dispositivos móveis. Uma marca pode coletar dados dos locais móveis dos usuários - chamados de <strong>Pontos de interesse</strong> - quando eles abrem o aplicativo da marca. Isso permite que a marca aproveite os fluxos de trabalho do Adobe Campaign para enviar mensagens personalizadas com base nos locais dos usuários. Esse canal utiliza o SDK do serviço principal do Mobile.<br /> Observe que o uso desse recurso exige o Analytics para dispositivos móveis, que é uma solução paga.<br /><a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> REST APIs<br /> </td> 
   <td> Os recursos vinculados em qualquer nível aos perfis ou aos recursos de serviços agora estão disponíveis na API.<br /><a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension"> Para obter mais informações, consulte a documentação detalhada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Geral_

* Agora é possível adicionar dados de perfil ao exportar registros de entrega.

_Emails e mensagens SMS_

* Corrigido um problema que fazia com que a opção **[!UICONTROL Request confirmation before sending messages]** permanecesse selecionada mesmo depois de desmarcá-la e salvar a entrega.
* Correção de um problema que poderia impedir a publicação de emails transacionais.
* Correção de um problema em que o conteúdo não podia ser sincronizado corretamente com as alterações mais recentes antes de visualizar uma entrega.

_Páginas de aterrissagem_

* Correção de um erro que impedia um usuário de editar ao clicar no conteúdo de uma página inicial.

_Fluxos de trabalho_

* Correção de um problema que impedia a leitura do conteúdo da transição de rejeição de uma **[!UICONTROL Load file]** atividade.
* Correção de um problema que impedia que colunas trocadas fossem levadas em conta corretamente ao configurar uma **[!UICONTROL Load file]** atividade.

## Versão 17.1 - Janeiro de 2017 {#release-17-1---january-2017}

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
   <td> Exportação de log para relatórios externos<br /> </td> 
   <td> Exporte logs como registros de entrega e rastreamento para processá-los nas ferramentas de relatório ou BI preferidas. Você pode usar fluxos de trabalho simples com consultas incrementais para automatizar exportações regulares de novos logs.<br /> Além da disponibilidade dos recursos de log do seletor de recursos, foram feitos aprimoramentos nas atividades de consulta <a href="../../automating/using/incremental-query.md"></a> incremental e arquivo <a href="../../automating/using/extract-file.md"></a> Extract:<br /> 
    <ul> 
     <li> <span class="uicontrol">A consulta</span> incremental agora permite usar um campo de data para recuperar dados novos ou atualizados. Anteriormente, todos os resultados de execuções anteriores eram excluídos automaticamente, mesmo se fossem atualizados desde a última execução. </li> 
     <li> <span class="uicontrol">O arquivo</span> Extract agora pode exportar rótulos para valores de enumeração em vez de IDs. </li> 
    </ul> Essas atividades estão disponíveis para administradores com acesso a todas as unidades geográficas e organizacionais.<br /> Para obter mais informações sobre como exportar registros, consulte a documentação <a href="../../automating/using/exporting-logs.md"></a>detalhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Capacidades de marketing para mensagens transacionais<br /> </td> 
   <td> Os profissionais de marketing agora podem enviar mensagens transacionais com base nos perfis de marketing do cliente. Isso permite que eles:<br /> 
    <ul> 
     <li> Aplique regras de tipologia de marketing, como endereço <span class="uicontrol">da lista</span> negra. </li> 
     <li> Inclua o link de cancelamento de assinatura nas mensagens. </li> 
     <li> Adicione as mensagens transacionais ao relatório de entrega global. </li> 
     <li> Aproveite as mensagens transacionais na jornada do cliente. </li> 
    </ul> Para obter mais informações, consulte a <a href="../../channels/using/profile-transactional-messages.md">documentação detalhada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API de mensagens transacionais<br /> </td> 
   <td> A API de mensagens transacionais agora está disponível por meio do <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>, facilitando o uso e o monitoramento:<br /> 
    <ul> 
     <li> Você pode se beneficiar dos recursos de relatório e monitoramento da plataforma adobe.io. </li> 
     <li> A autenticação agora é realizada usando a autenticação baseada em token adobe.io em vez da lista de permissões de IP, tornando o processo de segurança mais simples. </li> 
     <li> Todas as APIs agora estão integradas em uma única plataforma, tornando mais simples do que nunca adicionar recursos de mensagens transacionais à sua integração se você já oferecer suporte à API de perfil e serviços. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Correções**

_Geral_

* As **[!UICONTROL Access authorization]** opções retornaram às propriedades da página inicial.
* Correção de um problema que resultava na renderização de uma imagem antiga em vez da imagem correta. Isso ocorria se a imagem de origem tivesse sido atualizada na definição de conteúdo de uma página de entrega ou de aterrissagem.
* Correção de um problema que impedia os usuários de editar determinados campos em uma conta externa SFTP existente.
* Correção de vários problemas de interface do usuário. Por exemplo, os usuários agora podem editar atributos de perfil e salvar modificações sem enfrentar problemas com a interface do usuário.

_Emails e mensagens SMS_

* Correção de um problema relacionado aos modelos de entrega com conteúdo HTML que contém um

_Notificações por push_

* Correção de um problema que pode ter impedido o postback de um aplicativo para o servidor do Adobe Campaign.
* Correção de um problema que pode ter impedido **[!UICONTROL Play a sound]** e **[!UICONTROL Custom fields]** sido considerado para Android.
* Correção de um problema que resultava na adição de um caractere de escape extra a caracteres Unicode usados para Emojis.
* Quando o token de registro de um assinante é bloqueado, o status correspondente agora é atualizado imediatamente na lista de assinantes do aplicativo no Adobe Campaign.

_Fluxos de trabalho_

* Correção de um problema que pode ter impedido visualizações de consultas em recursos de evento (por exemplo, rtEvent).
* O arquivo de rejeição gerado por uma **[!UICONTROL Load file]** atividade agora pode ser recuperado em sua transição de saída e processado na próxima atividade. Por exemplo, carregue o arquivo de rejeição por meio de um servidor SFTP usando **[!UICONTROL Transfer file]** .
* Correção de um problema que poderia ter impedido um usuário de limitar a população de um segmento se **[!UICONTROL Temporary resource]** fosse selecionado na guia **[!UICONTROL General]** de **[!UICONTROL Segmentation]** .
* **[!UICONTROL Scheduler]** atividades não podem mais ser definidas para acionar um fluxo de trabalho mais de uma vez a cada 10 minutos.
* Correção de um problema que pode ter impedido **[!UICONTROL Use common columns]** o funcionamento correto em uma **[!UICONTROL Union]** atividade.

_Integrações_

* Correção de um problema que pode ter causado um erro ao implantar um acionador de evento no Adobe Campaign. Esse erro ocorria quando os metadados &quot;Probabilidade de retornar em 30 dias&quot; eram adicionados ao acionador de Abandono na Adobe Marketing Cloud.
* Correção de um problema que pode ter feito com que o fluxo de trabalho técnico limpe o campo Dimensão de destino ao importar públicos-alvo do serviço principal de Pessoas. As consultas subsequentes não puderam recuperar os públicos importados.
* Correção de um problema que resultava em falha da **[!UICONTROL Save audience]** atividade de um fluxo de trabalho quando a opção **[!UICONTROL Share in Adobe Marketing Cloud]** era marcada.

