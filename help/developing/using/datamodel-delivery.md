---
title: Entrega do modelo de dados
description: Saiba mais sobre o modelo de dados
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: aea3e72d-8e89-46c7-a796-bf856414c654
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 28%

---

# Delivery (nms:delivery)

## Descrição do objeto

<table>
               <tr>
                  <th>Nome</th>
                  <th>Rótulo</th>
                  <th>Tipo (comprimento)</th>
                  <th>Valores de lista discriminada</th>
               </tr>
               <tr>
                  <td>FCP</td>
                  <td>Prova</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>ID do recurso principal</td>
                  <td>sequência de caracteres </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>abTesting</td>
                  <td>Teste AB</td>
                  <td>Item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>avançado</td>
                  <td>Entrega avançada</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>advancedParameters</td>
                  <td>Parâmetros avançados</td>
                  <td>Item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>aemContents</td>
                  <td>Conteúdo do Adobe Experience Manager</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMessage</td>
                  <td>Mensagem de aviso</td>
                  <td>sequência de caracteres </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMode</td>
                  <td>Tipo de aviso</td>
                  <td>sequência de caracteres </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>anexo</td>
                  <td>Arquivos anexados</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>identidade visual (brandingBase)</td>
                  <td>Marca</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>broadLogs</td>
                  <td>Logs de entrega</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>builtIn</td>
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
                  <td>Conta do Adobe Experience Manager</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>comandos</td>
                  <td>Comandos</td>
                  <td>Item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>conteúdo</td>
                  <td>Conteúdo</td>
                  <td>Item </td>
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
                  <td>sequência de caracteres </td>
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
                        <li>Entrega em massa - em massa - 1</li>
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
                  <td>sequência de caracteres (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailPreview</td>
                  <td>Visualização de email</td>
                  <td>Item </td>
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
                  <td>Causas da exclusão</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>execução</td>
                  <td>Parâmetros de execução da entrega</td>
                  <td>Item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>executionType</td>
                  <td>Tipo de execução</td>
                  <td>enumeração (byte) </td>
                  <td>
                     <ul>
                        <li>Exclusivo - oneTime - 0</li>
                        <li>Contínuo - contínuo - 1</li>
                        <li>Centro de mensagens - messageCenter - 2</li>
                        <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>forecastLogs</td>
                  <td>RegistroDePrevisão</td>
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
                        <li>Fax - fax - 4</li>
                        <li>Móvel (SMS) - sms - 1</li>
                        <li>Email recorrente - emailRefresh - 30</li>
                        <li>Correspondência direta - papel - 3</li>
                        <li>Telefone - telefone - 2</li>
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
                  <td>Modelo</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>iterações</td>
                  <td>Entregas</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>tarefa</td>
                  <td>Processo</td>
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
                  <td>Item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>rótulo</td>
                  <td>Rótulo</td>
                  <td>sequência de caracteres (128)</td>
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
                  <td>Status da execução</td>
                  <td>enumeração (cadeia de caracteres) (255)</td>
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
                  <td>Parâmetros de cabeçalho de email</td>
                  <td>Item </td>
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
                  <td>mestre (deliveryBase)</td>
                  <td>Instância principal</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>masterKpis</td>
                  <td>Indicadores mestres</td>
                  <td>Item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>Canal</td>
                  <td>enumeração (byte) </td>
                  <td>
                     <ul>
                        <li>Fax - fax - 4</li>
                        <li>Móvel (SMS) - sms - 1</li>
                        <li>Email - email - 0</li>
                        <li>Telefone - telefone - 2</li>
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
                  <td>sequência de caracteres (64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>offerManagement</td>
                  <td>Gerenciamento de ofertas</td>
                  <td>Item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Entidade organizacional</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pai (deliveryBase)</td>
                  <td>Entrega principal</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>prioridade</td>
                  <td>Prioridade de entrega</td>
                  <td>enumeração (byte) </td>
                  <td>
                     <ul>
                        <li>Alto - alto - 20</li>
                        <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
                        <li>Normal - normal - 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>programa (programBase)</td>
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
                  <td>Item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushnotificationParameters</td>
                  <td>Parâmetros de PushNotification</td>
                  <td>Item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>Relatórios em tempo real</td>
                  <td>Item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>resourceVersion</td>
                  <td>Versão do recurso</td>
                  <td>sequência de caracteres (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ribbonMessage</td>
                  <td>Mensagem da faixa de opções</td>
                  <td>sequência de caracteres </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cenário</td>
                  <td>Parâmetros do modelo de entrega</td>
                  <td>Item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>agendamento</td>
                  <td>Agendamento de entrega</td>
                  <td>Item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsParameters</td>
                  <td>Parâmetros de SMS</td>
                  <td>Item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsPreview</td>
                  <td>Visualização do SMS</td>
                  <td>Item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>estado</td>
                  <td>Status</td>
                  <td>enumeração (byte) </td>
                  <td>
                     <ul>
                        <li>Início pendente - startPending - 51</li>
                        <li>Pronto para ser entregue - pronto - 45</li>
                        <li>Repetição pendente - retryPending - 61</li>
                        <li>Tentativa em andamento - retryInProgress - 62</li>
                        <li>Com falha - com falha - 87</li>
                        <li>Em andamento - iniciado - 55</li>
                        <li>Direcionamento pendente - targetPrepPending - 11</li>
                        <li>Personalização pendente - messagePrepPending - 21</li>
                        <li>Pausado - pausado - 75</li>
                        <li>Edição - edição - 0</li>
                        <li>Concluído - concluído - 95</li>
                        <li>Contagem em andamento - targetSelection - 12</li>
                        <li>Mensagem finalizada - messageReady - 25</li>
                        <li>Falha na personalização ou na contagem - preparationError - 37</li>
                        <li>Interrompido - cancelado - 85</li>
                        <li>Personalização em andamento - messagePreparation - 22</li>
                        <li>Target pronto - targetReady - 15</li>
                        <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
                        <li>Arbitragem em andamento - targetArbitration - 13</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>targets</td>
                  <td>População do público-alvo da entrega</td>
                  <td>Item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>modelo (deliveryTemplateSummary)</td>
                  <td>Template de entrega</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniatura</td>
                  <td>Miniatura de entrega</td>
                  <td>sequência de caracteres (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>título</td>
                  <td>Entrega</td>
                  <td>sequência de caracteres (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>rastreamento</td>
                  <td>Parâmetros de rastreamento</td>
                  <td>Item </td>
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
                  <td>Item </td>
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
                  <td>Status do fluxo de trabalho</td>
                  <td>enumeração (cadeia de caracteres) (255)</td>
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

Por tipo de canal (byChannel)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>channel</td>
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
    <td>estado</td>
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
    <td>sequência de caracteres</td>
    </tr>
    <tr>
    <td>mc</td>
    <td>sequência de caracteres</td>
    </tr>
</table>

Por período (byPeriod)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>sequência de caracteres</td>
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
    <td>sequência de caracteres</td>
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

Por status (por estado)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>estado</td>
    <td>enumeração</td>
    </tr>
</table>

Mensagens de acompanhamento (showFollowup)

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

Incluir entregas avançadas (com Avançado)

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

Incluir deliveries contínuos de uma lista heterogênea (com Continuous)

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
    <td>withFCP</td>
    <td>booleano</td>
    </tr>
</table>

Planejado durante o período determinado (por Planejamento)

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

Presente durante determinado período (por calendário)

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
    <td>trabalho</td>
    <td>booleano</td>
    </tr>
</table>
