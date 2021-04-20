---
solution: Campaign Standard
product: campaign
title: DataModel
description: Saiba mais sobre o datamodel
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 10%

---


# Delivery (nms:delivery)

## Descrição do objeto

<table>
               <tr>
                  <th>Nome</th>
                  <th>Rótulo</th>
                  <th>Tipo (comprimento)</th>
                  <th>Valores de enumeração</th>
               </tr>
               <tr>
                  <td>FCP</td>
                  <td>Prova</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>ID de recurso principal</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>abTesting</td>
                  <td>Teste A/B</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>avançado</td>
                  <td>Delivery avançado</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>advancedParameters</td>
                  <td>Parâmetros avançados</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>aemContents</td>
                  <td>Conteúdos do Adobe Experience Manager</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMessage</td>
                  <td>Mensagem de aviso</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMode</td>
                  <td>Tipo de aviso</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>anexo</td>
                  <td>Arquivos anexados</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>marca (brandingBase)</td>
                  <td>Marca</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>broadLogs</td>
                  <td>Logs do delivery</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>build</td>
                  <td>Objeto de aplicativo integrado</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>campaign (campaignBase)</td>
                  <td>Campanha</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cmsAccount (extAccountAEMBase)</td>
                  <td>Conta Adobe Experience Manager</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>comandos</td>
                  <td>Comandos</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>conteúdo</td>
                  <td>Conteúdo</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>contentSource</td>
                  <td>Fonte de conteúdo</td>
                  <td>enumeração (byte) </td>
                  <td>
                     <ul>
                        <li>Adobe Experience Manager - aem - 1</li>
                        <li>Adobe Campaign - campanha - 0</li>
                        <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>contextResourceType</td>
                  <td>Tipo de recurso</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>criado</td>
                  <td>Criado</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy (userBase)</td>
                  <td>Criado por</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>deliveryMode</td>
                  <td>Modo de entrega</td>
                  <td>enumeração (byte) </td>
                  <td>
                     <ul>
                        <li>Delivery em massa - em massa - 1</li>
                        <li>Mid-sourcing - midSourcing - 4</li>
                        <li>Descrição - descritiva - 2</li>
                        <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
                        <li>Externo - externo - 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>deliveryProvider (extAccountBase)</td>
                  <td>Roteamento</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>desc</td>
                  <td>Descrição</td>
                  <td>string (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailPreview</td>
                  <td>Visualização de email</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>excludeLogs</td>
                  <td>Logs de exclusão</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>exclusões</td>
                  <td>Causas de exclusão</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>execução</td>
                  <td>Parâmetros de execução do delivery</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>executionType</td>
                  <td>Tipo de execução</td>
                  <td>enumeração (byte) </td>
                  <td>
                     <ul>
                        <li>Exclusivo - uma vez - 0</li>
                        <li>Contínuo - contínuo - 1</li>
                        <li>Centro de mensagens - messageCenter - 2</li>
                        <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>forecastLogs</td>
                  <td>ForecastLog</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Unidade geográfica</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hasAttachments</td>
                  <td>Adicionar arquivos anexados</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ícone</td>
                  <td>Ícone</td>
                  <td>enumeração (byte) </td>
                  <td>
                     <ul>
                        <li>Email transacional - emailLightning - 60</li>
                        <li>Fax - 4</li>
                        <li>Móvel (SMS) - sms - 1</li>
                        <li>Email recorrente - emailRefresh - 30</li>
                        <li>Correspondência direta - papel - 3</li>
                        <li>Telefone - Telefone - 2</li>
                        <li>Outros - outros - 120</li>
                        <li>SMS recorrente - smsRefresh - 31</li>
                        <li>Aplicativo móvel - notificação por push - 40</li>
                        <li>SMS transacional - smsLightning - 61</li>
                        <li>Email - email - 0</li>
                        <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>É recurso externo</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isMaster</td>
                  <td>Principal</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isTemplate</td>
                  <td>Template</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>iterações</td>
                  <td>Deliveries</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trabalho</td>
                  <td>Tarefa</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>jobLogs</td>
                  <td>Logs</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>kpis</td>
                  <td>Indicadores</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>label</td>
                  <td>Rótulo</td>
                  <td>string (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>Última modificação</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>logicalStatus</td>
                  <td>Status de execução</td>
                  <td>enumeration (string) (255)</td>
                  <td>
                     <ul>
                        <li>Em andamento - iniciado - iniciado</li>
                        <li>Edição - edição - edição</li>
                        <li>Concluído - concluído - concluído</li>
                        <li>Aviso - aviso - aviso</li>
                        <li>Errado - erro - erro</li>
                        <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>mailParameters</td>
                  <td>Parâmetros do cabeçalho do email</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>Data</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mapping (deliveryMapping)</td>
                  <td>Target mapping</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>principal (deliveryBase)</td>
                  <td>Instância principal</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>masterKpis</td>
                  <td>Indicadores principais</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>Canal </td>
                  <td>enumeração (byte) </td>
                  <td>
                     <ul>
                        <li>Fax - 4</li>
                        <li>Móvel (SMS) - sms - 1</li>
                        <li>Email - email - 0</li>
                        <li>Telefone - Telefone - 2</li>
                        <li>Correspondência direta - papel - 3</li>
                        <li>Aplicativo móvel - notificação por push - 40</li>
                        <li>Outros - outros - 120</li>
                        <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>Modificado por</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>name</td>
                  <td>ID</td>
                  <td>string (64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>offerManagement</td>
                  <td>Gerenciamento de ofertas</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Unidade organizacional</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>parent (deliveryBase)</td>
                  <td>Delivery pai</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>priority</td>
                  <td>Prioridade do delivery</td>
                  <td>enumeração (byte) </td>
                  <td>
                     <ul>
                        <li>Alta - alta - 20</li>
                        <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
                        <li>Normal - normal - 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>program (programBase)</td>
                  <td>Programa</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>provas</td>
                  <td>Provas</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotificationPreview</td>
                  <td>Visualização da notificação por push</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushnotificationParameters</td>
                  <td>Parâmetros PushNotification</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>Relatórios em tempo real</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>resourceVersion</td>
                  <td>Versão do recurso</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ribbonMessage</td>
                  <td>Mensagem de fita</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cenário</td>
                  <td>Parâmetros do template Delivery</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>programação</td>
                  <td>Programação de delivery</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsParameters</td>
                  <td>Parâmetros de SMS</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsPreview</td>
                  <td>Visualização de SMS</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>state</td>
                  <td>Status</td>
                  <td>enumeração (byte) </td>
                  <td>
                     <ul>
                        <li>Iniciar pendente - startPending - 51</li>
                        <li>Pronto para ser entregue - pronto - 45</li>
                        <li>Tentativa pendente - retryPending - 61</li>
                        <li>Tentativa em andamento - retryInProgress - 62</li>
                        <li>Falha - falha - 87</li>
                        <li>Em andamento - iniciado - 55</li>
                        <li>Direcionamento pendente - targetPrepPending - 11</li>
                        <li>Personalização pendente - messagePrepPending - 21</li>
                        <li>Pausado - pausado - 75</li>
                        <li>Edição - edição - 0</li>
                        <li>Concluído - concluído - 95</li>
                        <li>Contagem em andamento - targetSelection - 12</li>
                        <li>Mensagem finalizada - messageReady - 25</li>
                        <li>Falha na personalização ou contagem - preparationError - 37</li>
                        <li>Parado - cancelado - 85</li>
                        <li>Personalização em andamento - messagePreparation - 22</li>
                        <li>Pronto para Target - targetReady - 15</li>
                        <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
                        <li>Arbitragem em andamento - targetArbitration - 13</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>targets</td>
                  <td>População do target de delivery</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>template (deliveryTemplateSummary)</td>
                  <td>Modelo de delivery</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniatura</td>
                  <td>Miniatura do delivery</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>título</td>
                  <td>Delivery</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>tracking</td>
                  <td>Parâmetros de rastreamento</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingLogs</td>
                  <td>Logs de rastreamento</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingUrls</td>
                  <td>URLs rastreados</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>triggerMessage</td>
                  <td>Parâmetros da mensagem transacional</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>tipologia (typologyBase)</td>
                  <td>Tipologia</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflow (workflowBase)</td>
                  <td>Fluxo de trabalho de direcionamento</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflowStatus</td>
                  <td>Status do workflow</td>
                  <td>enumeration (string) (255)</td>
                  <td>
                     <ul>
                        <li>Em andamento - iniciado - iniciado</li>
                        <li>Edição - edição - edição</li>
                        <li>Concluído - concluído - concluído</li>
                        <li>Aviso - aviso - aviso</li>
                        <li>Errado - erro - erro</li>
                        <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
                     </ul>
                  </td>
               </tr>
            </table>

## Filtros

Por tipo de canal (porCanal)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>canal</td>
    <td>enumeração</td>
    </tr>
</table>

Por tipo de execução (byExecutionType)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>executionType</td>
    <td>enumeração</td>
    </tr>
</table>

Por status lógico (byLogicalStatus)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>state</td>
    <td>enumeração</td>
    </tr>
</table>

Por nome ou rótulo (byText)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>texto</td>
    <td>string</td>
    </tr>
    <tr>
    <td>mc</td>
    <td>string</td>
    </tr>
</table>

Por período (porPeríodo)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>string</td>
    </tr>
</table>

Por período (byStartPeriod)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>data</td>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>string</td>
    </tr>
</table>

Por status de publicação (byPublicationStatus)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>pStatus</td>
    <td>enumeração</td>
    </tr>
</table>

Por status (porEstado)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>state</td>
    <td>enumeração</td>
    </tr>
</table>

Mensagens de acompanhamento (showSegulowup)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>acompanhamento</td>
    <td>booleano</td>
    </tr>
</table>

Incluir deliveries avançados (comAdvanced)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>avançado</td>
    <td>booleano</td>
    </tr>
</table>

Incluir deliveries contínuos de uma lista heterogênea (com Contínuo)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>withContinuous</td>
    <td>booleano</td>
    </tr>
</table>

Incluir provas (com FCP)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>comFCP</td>
    <td>booleano</td>
    </tr>
</table>

Planejado durante o período especificado (byPlanning)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>data</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>data</td>
    </tr>
</table>

Apresentar durante um determinado período (porCalendário)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>data</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>data</td>
    </tr>
</table>

Mostrar pronto para uso (showOob)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>oob</td>
    <td>booleano</td>
    </tr>
</table>