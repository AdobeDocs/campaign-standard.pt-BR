---
title: Fluxos de trabalho técnicos
description: Os fluxos de trabalho técnicos são fluxos de trabalho predefinidos, projetados para lidar com processos técnicos em segundo plano no Adobe Campaign, garantindo o comportamento correto da plataforma.
page-status-flag: nunca ativado
uuid: 6e763dc1-e1d3-4d94-bc0b-ef5b1703d8e5
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: administração
content-type: referência
topic-tags: application-settings
discoiquuid: e9f147bd-6a5b-4b82-b9bb-311e38e22c62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Fluxos de trabalho técnicos{#technical-workflows}

Os fluxos de trabalho técnicos são disponibilizados prontamente com o Adobe Campaign. Fluxos de trabalho técnicos são operações ou trabalhos programados para serem executados regularmente no servidor.

Eles permitem que você realize operações de manutenção no banco de dados, aproveite as informações de rastreamento nas entregas e atualize as ordens de produção provisórias nas entregas.

Os administradores funcionais podem acessar fluxos de trabalho técnicos no **[!UICONTROL Administration > Application settings > Workflows]** menu.

>[!NOTE]
>
>Como administrador funcional, você pode reiniciar ou pausar fluxos de trabalho técnicos e modificar suas propriedades e estrutura.

![](assets/technical_workflows.png)

## Lista de fluxos de trabalho técnicos {#list-of-technical-workflows}

Os fluxos de trabalho técnicos são usados para lidar com processos técnicos e de plano de fundo acionados automaticamente no Adobe Campaign.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Teste</span> A/B <br /> </td> 
   <td> <span class="uicontrol">abTesting</span><br /> </td> 
   <td> Esse fluxo de trabalho analisa os registros de rastreamento de cada variante. No final do período de teste A/B, calcula automaticamente a variante vencedora. Por padrão, ele é iniciado todos os dias.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Cobrança</span><br /> </td> 
   <td> <span class="uicontrol">faturamento</span><br /> </td> 
   <td> Esse fluxo de trabalho envia o relatório de atividade do sistema para o usuário de "cobrança" por email. Por padrão, ele é iniciado automaticamente todos os dias às 01h00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Limpeza</span> do banco de dados <br /> </td> 
   <td> <span class="uicontrol">limpeza</span><br /> </td> 
   <td> Esse fluxo de trabalho é o fluxo de trabalho de manutenção do banco de dados: ele executa diferentes estatísticas e processos e exclui dados obsoletos do banco de dados de acordo com a configuração que foi definida. Por padrão, é iniciado automaticamente todos os dias, às 4h.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Previsão</span><br /> </td> 
   <td> <span class="uicontrol">previsão</span><br /> </td> 
   <td> Esse fluxo de trabalho executa a análise das entregas armazenadas na previsão provisória (criação dos registros provisórios). By default, it is started every day at 1am. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Importar um público</span> compartilhado <br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span><br /> </td> 
   <td> Esse fluxo de trabalho sincroniza os dados de público-alvo da Adobe Experience Cloud importados no Adobe Campaign. Por padrão, ele é iniciado a cada hora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Compartilhamento</span> instantâneo de relatórios <br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span><br /> </td> 
   <td> Esse fluxo de trabalho é iniciado assim que um relatório está programado para ser enviado. Ele converte seu relatório em um arquivo pdf e, em seguida, o envia por email para os destinatários.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Reconciliação de KPIs com o Adobe Analytics</span><br /> </td> 
   <td> <span class="uicontrol">kpiReconciliation</span><br /> </td> 
   <td> Esse fluxo de trabalho obtém os KPIs do serviço de Relatórios uma vez por dia e os reconcilia com os dados do Adobe Analytics. Em seguida, empurra a diferença, se necessário. By default, it is started every day at 4.20am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Gerenciamento de opções</span> NMAC <br /> </td> 
   <td> <span class="uicontrol">mobileAppOptOutMgt</span><br /> </td> 
   <td> Esse fluxo de trabalho atualiza as assinaturas para notificações em dispositivos móveis. Por padrão, ele é iniciado a cada 6 horas entre 1h e meia-noite.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Arquivamento</span> local do centro de mensagens <br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span><br /> </td> 
   <td> Esse fluxo de trabalho arquiva eventos em tempo real em uma tabela histórica. Por padrão, ele é iniciado a cada hora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Agregados</span> de relatório <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span><br /> </td> 
   <td> Esse fluxo de trabalho atualiza os agregados usados nos relatórios. Por padrão, é iniciado automaticamente às 2h00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Compartilhar KPIs com o Adobe Analytics</span><br /> </td> 
   <td> <span class="uicontrol">kpiSharing</span><br /> </td> 
   <td> Esse fluxo de trabalho envia dados KPI a cada 15 minutos do Adobe Campaign Standard para o Adobe Analytics.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Atualizar execução</span> de entrega <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span><br /> </td> 
   <td> Esse fluxo de trabalho atualiza o rastreamento da entrega. Por padrão, ele é iniciado a cada 10 minutos.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Atualizar indicadores</span> de entrega <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span><br /> </td> 
   <td> Esse fluxo de trabalho atualiza os KPIs da entrega (Indicador-chave de desempenho). Por padrão, ele é iniciado a cada hora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Atualizar status</span> do evento <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span><br /> </td> 
   <td> Esse fluxo de trabalho permite que você atribua um status a um evento. <br /> Os seguintes status de evento estão disponíveis: <strong>Pendente</strong>: O evento está em fila. Nenhum template de mensagem foi atribuído a ele.<br /> Entrega <span class="uicontrol">pendente</span> : O evento está na fila, um modelo de mensagem foi atribuído a ele e está sendo processado pela entrega.<br /> <strong>Enviados</strong>: Esse status é copiado dos registros de entrega. Significa que a entrega foi enviada.<br /> <strong>Ignorado pela entrega</strong>: Esse status é copiado dos registros de entrega. Significa que o delivery foi ignorado.<br /> Falha na <strong>entrega</strong>: Esse status é copiado dos registros de entrega. Significa que o delivery falhou.<br /> <span class="uicontrol">Evento não tomado em consideração</span> : Não foi possível vincular o evento a um modelo de mensagem. O evento não será processado.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Atualização para o material de entrega</span><br /> </td> 
   <td> <span class="uicontrol">deliveryUpdate</span><br /> </td> 
   <td> Esse fluxo de trabalho permite criar a lista de regras de qualificação de regras de rejeição, bem como a lista de domínios e MX na plataforma. Esse fluxo de trabalho só funcionará se o HTTPS estiver aberto. Por padrão, é iniciado automaticamente às 2h00.<br /> </td> 
  </tr> 
 </tbody> 
</table>

