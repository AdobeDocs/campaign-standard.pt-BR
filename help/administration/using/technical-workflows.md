---
title: Fluxos de trabalho técnicos
seo-title: Fluxos de trabalho técnicos
description: Fluxos de trabalho técnicos
seo-description: Fluxos de trabalho técnicos são fluxos de trabalho prontos para uso projetados para lidar com processos técnicos de fundo no Adobe Campaign, garantindo o comportamento correto da plataforma.
page-status-flag: nunca ativado
uuid: 6 e 763 dc 1-e 1 d 3-4 d 94-bc 0 b-ef 5 b 1703 d 8 e 5
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: e 9 f 147 bd -6 a 5 b -4 b 82-b 9 bb -311 e 38 e 22 c 62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2541b6dadd005c74d6bb737a0e3692e63a5b85db

---


# Technical workflows{#technical-workflows}

Fluxos de trabalho técnicos são fornecidos prontamente com o Adobe Campaign. Fluxos de trabalho técnicos são operações ou tarefas programadas para serem executadas regularmente no servidor.

Eles permitem realizar operações de manutenção no banco de dados, aproveitar as informações de rastreamento nas entregas e atualizar as tarefas provisórias nas entregas.

Functional administrators can access technical workflows under the **[!UICONTROL Administration > Application settings > Workflows]** menu.

>[!NOTE]
>
>Como administrador funcional, você pode reiniciar ou pausar fluxos de trabalho técnicos e modificar suas propriedades e estruturas.

![](assets/technical_workflows.png)

## List of technical workflows {#list-of-technical-workflows}

Fluxos de trabalho técnicos são usados para lidar com processos de plano de fundo e técnicos acionados automaticamente no Adobe Campaign.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Rótulo</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Teste A/B</span><br /> </td> 
   <td> <span class="uicontrol">Abtesting</span><br /> </td> 
   <td> Esse fluxo de trabalho analisa os registros de rastreamento de cada variação. No final do período de teste A/B, calcula automaticamente a variante vencedora. By default, it is started every day.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Faturamento</span><br /> </td> 
   <td> <span class="uicontrol">faturamento</span><br /> </td> 
   <td> Esse fluxo de trabalho envia o relatório de atividade do sistema para o usuário "faturamento" por e-mail. By default, it is automatically started every day at 1am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Limpeza do banco de dados</span><br /> </td> 
   <td> <span class="uicontrol">limpeza</span><br /> </td> 
   <td> Esse fluxo de trabalho é o fluxo de trabalho de manutenção do banco de dados: ele executa estatísticas e processos diferentes e exclui dados obsoletos do banco de dados de acordo com a configuração que foi definida. By default, it is automatically started every day 4am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Previsão</span><br /> </td> 
   <td> <span class="uicontrol">previsão</span><br /> </td> 
   <td> Esse fluxo de trabalho executa a análise das entregas armazenadas na previsão provisória (criação dos logs provisórios). By default, it is started every day at 1am. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Importar um público compartilhado</span><br /> </td> 
   <td> <span class="uicontrol">Importsharedaudience</span><br /> </td> 
   <td> Esse fluxo de trabalho sincroniza os dados de público-alvo da Adobe Experience Cloud importados no Adobe Campaign. By default, it is started every hour.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Compartilhamento de relatório instantâneo</span><br /> </td> 
   <td> <span class="uicontrol">Reportsendingnow</span><br /> </td> 
   <td> Esse fluxo de trabalho é iniciado assim que um relatório está programado para ser enviado. It converts your report into a pdf file then sends it in an email to the targeted recipients.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Reconciliação kpis com o Adobe Analytics</span><br /> </td> 
   <td> <span class="uicontrol">Kpireconciliation</span><br /> </td> 
   <td> Esse fluxo de trabalho busca os kpis do serviço de relatório uma vez por dia e os reconcilia com os dados do Adobe Analytics. Em seguida, ela envia a diferença se necessário. By default, it is started every day at 4.20am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Gerenciamento de opções NMAC</span><br /> </td> 
   <td> <span class="uicontrol">Mobileappoptoutmgt</span><br /> </td> 
   <td> Esse fluxo de trabalho atualiza cancelamentos de assinaturas para notificações em dispositivos móveis. By default, it is started every 6 hours between 1am and midnight.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Arquivamento local da Central de mensagens</span><br /> </td> 
   <td> <span class="uicontrol">Mcsynch_ local</span><br /> </td> 
   <td> Esse fluxo de trabalho arquiva eventos em tempo real em uma tabela histórica. By default, it is started every hour.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Agregar agregados</span><br /> </td> 
   <td> <span class="uicontrol">Reportingagregados</span><br /> </td> 
   <td> Esse fluxo de trabalho atualiza os agregados usados nos relatórios. By default, it is automatically started at 2am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Compartilhar kpis com o Adobe Analytics</span><br /> </td> 
   <td> <span class="uicontrol">Kpisharing</span><br /> </td> 
   <td> This workflow pushes KPI data every 15 minutes from Adobe Campaign Standard to Adobe Analytics.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Atualizar execução de entrega</span><br /> </td> 
   <td> <span class="uicontrol">Updatedeliveryexecinfo</span><br /> </td> 
   <td> Esse fluxo de trabalho atualiza o rastreamento da entrega. By default, it is started every 10 minutes.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Atualizar indicadores de entrega</span><br /> </td> 
   <td> <span class="uicontrol">Updatedeliveryindicadores</span><br /> </td> 
   <td> Esse fluxo de trabalho atualiza os kpis da entrega (Indicador-chave de desempenho). By default, it is started every hour.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Atualizar status do evento</span><br /> </td> 
   <td> <span class="uicontrol">Updateeventsstatus</span><br /> </td> 
   <td> Esse fluxo de trabalho permite atribuir um status a um evento. The following event statuses are available:<br /> <strong>Pending</strong>: The event is in a queue. Nenhum modelo de mensagem foi atribuído a ele ainda.<br /><span class="uicontrol">Entrega</span> pendente: O evento está na fila, um modelo de mensagem foi atribuído a ela e está sendo processado pela entrega.<br /><strong>Enviado</strong>: Esse status é copiado dos registros de entrega. Isso significa que a entrega foi enviada.<br /><strong>Ignorado pela entrega</strong>: Esse status é copiado dos registros de entrega. Isso significa que a entrega foi ignorada.<br /><strong>Falha na entrega</strong>: Esse status é copiado dos registros de entrega. Isso significa que a entrega falhou.<br /><span class="uicontrol">Evento não levado em conta</span> : O evento não pode ser vinculado a um modelo de mensagem. The event will not be processed.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Atualização para disponibilização</span><br /> </td> 
   <td> <span class="uicontrol">Deliverabilityupdate</span><br /> </td> 
   <td> Esse fluxo de trabalho permite criar a lista de regras de qualificação de regras, bem como a lista de domínios e MX na plataforma. Esse fluxo de trabalho funciona apenas se o HTTPS estiver aberto. By default, it is automatically started at 2am.<br /> </td> 
  </tr> 
 </tbody> 
</table>

