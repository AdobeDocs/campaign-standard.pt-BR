---
title: Fluxos de trabalho técnicos
description: Fluxos de trabalho técnicos são workflows prontos para uso, projetados para lidar com processos técnicos em segundo plano no Adobe Campaign, garantindo o comportamento correto da plataforma.
page-status-flag: never-activated
uuid: 6e763dc1-e1d3-4d94-bc0b-ef5b1703d8e5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: e9f147bd-6a5b-4b82-b9bb-311e38e22c62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b4cbc56973a57cde8af6cefa9ff89c7d29ab7b79

---


# Fluxos de trabalho técnicos{#technical-workflows}

Os Workflows técnicos são fornecidos prontos para uso com Adobe Campaign. Workflows técnicos são operações ou trabalhos programados para serem executados regularmente no servidor.

Eles permitem que você realize operações de manutenção no banco de dados, aproveite as informações de rastreamento nos delivery e atualize as tarefas provisórias nos delivery.

Os administradores funcionais podem acessar workflows técnicos sob o **[!UICONTROL Administration > Application settings > Workflows]** menu.

>[!NOTE]
>
>Como administrador funcional, você pode reiniciar ou pausar workflows técnicos e modificar suas propriedades e estrutura.

![](assets/technical_workflows.png)

## Lista de workflows técnicos {#list-of-technical-workflows}

Os Workflows técnicos são usados para lidar com processos técnicos e de plano de fundo acionados automaticamente no Adobe Campaign.

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
   <td> Esse fluxo de trabalho analisa os logs de rastreamento de cada variante. No final do período de teste A/B, calcula automaticamente a variante vencedora. Por padrão, ele é iniciado todos os dias.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Faturamento</span> <br /> </td> 
   <td> <span class="uicontrol">billing</span> <br /> </td> 
   <td> Esse fluxo de trabalho envia o relatório de atividade do sistema para o usuário de "cobrança" por email. Por padrão, ele é iniciado automaticamente todos os dias às 01h00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Limpeza do banco de dados</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> Esse fluxo de trabalho é o fluxo de trabalho de manutenção do banco de dados: ele executa diferentes estatísticas e processos e exclui dados obsoletos do banco de dados de acordo com a configuração que foi definida. Por padrão, ele é iniciado automaticamente todos os dias, às 4h.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Previsão</span><br /> </td> 
   <td> <span class="uicontrol">forecasting</span> <br /> </td> 
   <td> Esse fluxo de trabalho executa a análise dos delivery armazenados na previsão provisória (criação dos registros provisórios). By default, it is started every day at 1am. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Importar uma audiência</span> compartilhada <br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span> <br /> </td> 
   <td> Esse fluxo de trabalho sincroniza os dados de audiência da Adobe Experience Cloud importados no Adobe Campaign. Por padrão, ele é iniciado a cada hora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Compartilhamento</span> instantâneo de relatórios <br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span><br /> </td> 
   <td> Esse fluxo de trabalho é iniciado assim que um relatório está programado para ser enviado. Ele converte seu relatório em um arquivo pdf e o envia em um email para os recipient direcionados.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Reconciliação de KPIs com o Adobe Analytics</span><br /> </td> 
   <td> <span class="uicontrol">kpiReconciliation</span><br /> </td> 
   <td> Esse fluxo de trabalho obtém os KPIs do serviço de Relatórios uma vez por dia e os reconcilia com os dados do Adobe Analytics. Em seguida, empurra a diferença, se necessário. By default, it is started every day at 4.20am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Gerenciamento de opções</span> NMAC <br /> </td> 
   <td> <span class="uicontrol">mobileAppOptOutMgt</span> <br /> </td> 
   <td> Esse fluxo de trabalho atualiza unsubscription para notificações em dispositivos móveis. Por padrão, ele é iniciado a cada 6 horas entre 1h e meia-noite.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Arquivamento</span> local do centro de mensagens <br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span><br /> </td> 
   <td> Esse fluxo de trabalho arquiva eventos em tempo real em uma tabela histórica. Por padrão, ele é iniciado a cada hora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Relatórios de agregados</span> <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span> <br /> </td> 
   <td> Esse fluxo de trabalho atualiza as agregações usadas nos relatórios. Por padrão, é iniciado automaticamente às 2h00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Compartilhar KPIs com o Adobe Analytics</span><br /> </td> 
   <td> <span class="uicontrol">kpiSharing</span><br /> </td> 
   <td> Esse fluxo de trabalho envia dados KPI a cada 15 minutos do Adobe Campaign Standard para o Adobe Analytics.<br /> </td> 
  </tr> 
    </tr> 
   <tr> 
   <td> <span class="uicontrol">Sincronizar com o Launch</span><br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span><br /> </td> 
   <td> Esse fluxo de trabalho sincroniza as propriedades móveis do Adobe Launch importadas no Adobe Campaign Standard. É iniciado a cada 15 minutos.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Atualizar execução</span> do delivery <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span><br /> </td> 
   <td> Esse fluxo de trabalho atualiza o rastreamento de delivery. Por padrão, ele é iniciado a cada 10 minutos.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Atualizar indicadores</span> de delivery <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span><br /> </td> 
   <td> Esse fluxo de trabalho atualiza os KPIs do delivery (Indicador-chave de desempenho). Por padrão, ele é iniciado a cada hora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Atualizar status do evento</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> Esse fluxo de trabalho permite que você atribua um status a um evento. Os seguintes status de evento estão disponíveis:<br /> <strong>Pendente</strong>: O evento está em fila. Nenhum template de mensagem foi atribuído a ele.<br /> delivery <span class="uicontrol">pendente</span> : O evento está na fila, um modelo de mensagem foi atribuído a ele e está sendo processado pelo delivery.<br /> <strong>Enviados</strong>: Esse status é copiado dos logs do delivery. Significa que o delivery foi enviado.<br /> <strong>Ignorado pelo delivery</strong>: Esse status é copiado dos logs do delivery. Significa que o delivery foi ignorado.<br /> Falha no <strong>Delivery</strong>: Esse status é copiado dos logs do delivery. Significa que o delivery falhou.<br /> <span class="uicontrol">Evento não tomado em consideração</span> : Não foi possível vincular o evento a um modelo de mensagem. O evento não será processado.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Atualização para entregabilidade</span><br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span> <br /> </td> 
   <td> Esse fluxo de trabalho permite criar a lista de regras de qualificação de regras de rejeição, bem como a lista de domínios e MX na plataforma. Esse fluxo de trabalho só funcionará se o HTTPS estiver aberto. Por padrão, é iniciado automaticamente às 2h00.<br /> </td> 
  </tr> 
 </tbody> 
</table>

