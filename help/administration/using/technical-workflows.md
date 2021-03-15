---
solution: Campaign Standard
product: campaign
title: 'Workflows técnicos '
description: Os fluxos de trabalho técnicos são fluxos de trabalho prontos para uso, projetados para lidar com processos técnicos em segundo plano no Adobe Campaign, garantindo o comportamento correto da plataforma.
audience: administration
content-type: reference
topic-tags: application-settings
feature: Configurações de instância
role: Administrador
level: Experienciado
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 96%

---


# Fluxos de trabalho técnicos{#technical-workflows}

Os fluxos de trabalho técnicos são fornecidos prontos para uso com o Adobe Campaign. Eles são operações ou trabalhos programados para serem executados regularmente no servidor.

Eles permitem fazer operações de manutenção no banco de dados, usar as informações de rastreamento nos deliveries e atualizar os trabalhos provisionais nos deliveries.

Os administradores funcionais podem acessar os fluxos de trabalho técnicos no menu **[!UICONTROL Administration > Application settings > Workflows]**.

>[!NOTE]
>
>Como administrador funcional, você pode reiniciar ou pausar os fluxos de trabalho técnicos e modificar as propriedades e a estrutura.

![](assets/technical_workflows.png)

## Lista de fluxos de trabalho técnicos {#list-of-technical-workflows}

Os fluxos de trabalho técnicos são usados para lidar com processos técnicos e em segundo plano acionados automaticamente no Adobe Campaign.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Teste A/B</span> <br /> </td> 
   <td> <span class="uicontrol">abTesting</span> <br /> </td> 
   <td> Este fluxo de trabalho analisa os logs de rastreamento de cada variante. No final do período do Teste A/B, ele calcula automaticamente a variante vencedora. Por padrão, ele é iniciado diariamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Faturamento</span> <br /> </td> 
   <td> <span class="uicontrol">faturamento</span> <br /> </td> 
   <td> Este fluxo de trabalho envia por email o relatório de atividades do sistema para o usuário 'faturamento'. Por padrão, ele é iniciado automaticamente todos os dias às 1:00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Limpeza do banco de dados</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> Este é o fluxo de trabalho de manutenção do banco de dados. Ele executa diferentes estatísticas e processos e exclui dados obsoletos do banco de dados de acordo com a configuração que foi definida. Por padrão, ele é iniciado automaticamente todos os dias às 4:00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Previsão</span> <br /> </td> 
   <td> <span class="uicontrol">previsão</span> <br /> </td> 
   <td> Este fluxo de trabalho executa a análise dos deliveries armazenados na previsão provisional (criação dos logs provisionais). Por padrão, ele é iniciado todos os dias às 1:00. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Importar um público-alvo compartilhado</span> <br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span> <br /> </td> 
   <td> Este fluxo de trabalho sincroniza os dados de públicos-alvo da Adobe Experience Cloud importados no Adobe Campaign. Por padrão, ele é iniciado de hora em hora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Compartilhamento instantâneo de relatório</span> <br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span> <br /> </td> 
   <td> Este fluxo de trabalho é iniciado assim que um relatório é programado para ser enviado. Ele converte o relatório em um arquivo pdf e o envia em um email para os recipients direcionados.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Reconciliação de KPIs com o Adobe Analytics</span> <br /> </td> 
   <td> <span class="uicontrol">kpiReconciliation</span> <br /> </td> 
   <td> Este fluxo de trabalho obtém os KPIs do serviço Reporting uma vez por dia e os reconcilia com os dados do Adobe Analytics. Em seguida, envia por push a diferença, se necessário. Por padrão, ele é iniciado todos os dias às 4:20.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Gerenciamento de recusas do NMAC</span> <br /> </td> 
   <td> <span class="uicontrol">mobileAppOptOutMgt</span> <br /> </td> 
   <td> Este fluxo de trabalho atualiza as unsubscriptions para notificações nos dispositivos móveis. Por padrão, ele é iniciado a cada 6 horas entre 1:00 e meia-noite.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Arquivamento local do centro de mensagens</span> <br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span> <br /> </td> 
   <td> Este fluxo de trabalho arquiva os eventos em tempo real em uma tabela histórica. Por padrão, ele é iniciado de hora em hora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Relatórios de agregados</span> <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span> <br /> </td> 
   <td> Este fluxo de trabalho atualiza as agregações usadas nos relatórios. Por padrão, ele é iniciado automaticamente às 2:00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Compartilhar KPIs com o Adobe Analytics</span> <br /> </td> 
   <td> <span class="uicontrol">kpiSharing</span> <br /> </td> 
   <td> Este fluxo de trabalho envia dados de KPI a cada 15 minutos do Adobe Campaign Standard para o Adobe Analytics.<br /> </td> 
  </tr> 
    </tr> 
   <tr> 
   <td> <span class="uicontrol">Sincronizar com o Launch</span> <br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span> <br /> </td> 
   <td> Este fluxo de trabalho sincroniza as propriedades móveis do Adobe Launch importadas no Adobe Campaign Standard. Ele é iniciado a cada 15 minutos.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Atualizar a execução do delivery</span> <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span> <br /> </td> 
   <td> Este fluxo de trabalho atualiza o rastreamento do delivery. Por padrão, ele é iniciado a cada 10 minutos.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Atualizar os indicadores de delivery</span> <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span> <br /> </td> 
   <td> Este fluxo de trabalho atualiza os KPIs (indicadores principais de desempenho) do delivery. Por padrão, ele é iniciado de hora em hora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Atualizar status do evento</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> Este fluxo de trabalho permite atribuir um status a um evento. Os seguintes status de evento estão disponíveis:<br /> <strong>Pending</strong>: o evento está em uma fila. Nenhum template de mensagem foi atribuído a ele.<br /> <span class="uicontrol">Pending delivery</span>: o evento está na fila, um template de mensagem foi atribuído a ele e ele está sendo processado pelo delivery.<br /> <strong>Sent</strong>: este status é copiado dos logs de delivery. Ele significa que o delivery foi enviado.<br /> <strong>Ignored by the delivery</strong>: este status é copiado dos logs de delivery. Ele significa que o delivery foi ignorado.<br /> <strong>Delivery failed</strong>: este status é copiado dos logs de delivery. Ele significa que o delivery falhou.<br /> <span class="uicontrol">Event not taken into account</span>: não foi possível vincular o evento a um template de mensagem. O evento não será processado.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Atualização para entregabilidade</span><br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span> <br /> </td> 
   <td> Este fluxo de trabalho permite criar a lista de regras de qualificação de email de devolução, bem como a lista de domínios e MXs na plataforma. Ele só funcionará se a porta HTTPS estiver aberta. Por padrão, ele é iniciado automaticamente às 2:00.<br /> </td> 
  </tr> 
 </tbody> 
</table>

