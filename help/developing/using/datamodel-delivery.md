---
solution: Campaign Standard
product: campaign
title: DataModel
description: Saiba mais sobre o modelo de dados
audience: developing
content-type: reference
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 10%

---


# Delivery (nms:delivery)

## Descrição do objeto

<table>
               <tr>
                  <th>Nome</th>
                  <th>Rótulo</th>
                  <th>Tipo (comprimento)</th>
                  <th>valores de lista discriminada</th>
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
                  <td>advanced</td>
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
                  <td>Conteúdo do Adobe Experience Manager</td>
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
                  <td>ligação</td>
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
                  <td>wideLogs</td>
                  <td>Logs do delivery</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>buildIn</td>
                  <td>Objeto de aplicativo incorporado</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>campanha (campaignBase)</td>
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
                  <td>Fonte do conteúdo</td>
                  <td>lista discriminada (byte) </td>
                  <td>
                     <ul>
                        <li>Adobe Experience Manager - aem - 1</li>
                        <li>Adobe Campaign - campanha - 0</li>
                        <li>VALOR INVÁLIDO - __Valor_inválido__ - __Valor_inválido__</li>
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
                  <td>date </td>
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
                  <td>modo delivery</td>
                  <td>lista discriminada (byte) </td>
                  <td>
                     <ul>
                        <li>Delivery em massa - em massa - 1</li>
                        <li>Mid-sourcing - midSourcing - 4</li>
                        <li>Descrição - descritiva - 2</li>
                        <li>VALOR INVÁLIDO - __Valor_inválido__ - __Valor_inválido__</li>
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
                  <td>Pré-visualização de email</td>
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
                  <td>executeType</td>
                  <td>Tipo de execução</td>
                  <td>lista discriminada (byte) </td>
                  <td>
                     <ul>
                        <li>Único - uma vez - 0</li>
                        <li>Contínuo - contínuo - 1</li>
                        <li>Centro de mensagens - messageCenter - 2</li>
                        <li>VALOR INVÁLIDO - __Valor_inválido__ - __Valor_inválido__</li>
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
                  <td>lista discriminada (byte) </td>
                  <td>
                     <ul>
                        <li>Email transacional - emailLightning - 60</li>
                        <li>Fax - Fax - 4</li>
                        <li>Móvel (SMS) - sms - 1</li>
                        <li>Email recorrente - emailRefresh - 30</li>
                        <li>Mala direta - papel - 3</li>
                        <li>Telefone - telefone - 2</li>
                        <li>Outros - outros - 120</li>
                        <li>SMS recorrente - smsRefresh - 31</li>
                        <li>Aplicativo móvel - pushNotification - 40</li>
                        <li>SMS transacional - smsLightning - 61</li>
                        <li>Email - email - 0</li>
                        <li>VALOR INVÁLIDO - __Valor_inválido__ - __Valor_inválido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>É um recurso externo</td>
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
                  <td>Trabalho</td>
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
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>logicalStatus</td>
                  <td>Status de execução</td>
                  <td>lista discriminada (string) (255)</td>
                  <td>
                     <ul>
                        <li>Em andamento - iniciado - iniciado</li>
                        <li>Edição - edição - edição</li>
                        <li>Concluído - concluído - concluído</li>
                        <li>Aviso - aviso - aviso</li>
                        <li>Errado - erro - erro</li>
                        <li>VALOR INVÁLIDO - __Valor_inválido__ - __Valor_inválido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>mailParameters</td>
                  <td>Parâmetros de cabeçalho de email</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>Data</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mapeamento (deliveryMapping)</td>
                  <td>Target mapping</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>principal (deliveryBase)</td>
                  <td>instância principal</td>
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
                  <td>lista discriminada (byte) </td>
                  <td>
                     <ul>
                        <li>Fax - Fax - 4</li>
                        <li>Móvel (SMS) - sms - 1</li>
                        <li>Email - email - 0</li>
                        <li>Telefone - telefone - 2</li>
                        <li>Mala direta - papel - 3</li>
                        <li>Aplicativo móvel - pushNotification - 40</li>
                        <li>Outros - outros - 120</li>
                        <li>VALOR INVÁLIDO - __Valor_inválido__ - __Valor_inválido__</li>
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
                  <td>prioridade</td>
                  <td>Prioridade do delivery</td>
                  <td>lista discriminada (byte) </td>
                  <td>
                     <ul>
                        <li>Alto - alto - 20</li>
                        <li>VALOR INVÁLIDO - __Valor_inválido__ - __Valor_inválido__</li>
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
                  <td>Pré-visualização de notificação por push</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushnotificationParameters</td>
                  <td>Parâmetros de PushNotification</td>
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
                  <td>Mensagem de faixa</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cenário</td>
                  <td>Parâmetros do template do delivery</td>
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
                  <td>Parâmetros SMS</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsPreview</td>
                  <td>PRÉ-VISUALIZAÇÃO SMS</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>estado</td>
                  <td>Status</td>
                  <td>lista discriminada (byte) </td>
                  <td>
                     <ul>
                        <li>Start pendente - startWait - 51</li>
                        <li>Pronto para ser entregue - pronto - 45</li>
                        <li>Tentativa pendente - nova tentativa pendente - 61</li>
                        <li>Tentar novamente em andamento - tentarEmAndamento - 62</li>
                        <li>Falha - falha - 87</li>
                        <li>Em andamento - iniciado - 55</li>
                        <li>Definição de metas pendente - targetPrepCurrent - 11</li>
                        <li>Personalização pendente - messagePrepCurrent - 21</li>
                        <li>Pausado - pausado - 75</li>
                        <li>Edição - edição - 0</li>
                        <li>Concluído - concluído - 95</li>
                        <li>Contagem em andamento - targetSelection - 12</li>
                        <li>Mensagem finalizada - messageReady - 25</li>
                        <li>Falha na personalização ou contagem - prepareError - 37</li>
                        <li>Parado - cancelado - 85</li>
                        <li>Personalização em andamento - messagePreparação - 22</li>
                        <li>Pronto para público alvo - targetReady - 15</li>
                        <li>VALOR INVÁLIDO - __Valor_inválido__ - __Valor_inválido__</li>
                        <li>Arbitragem em curso - targetArbitration - 13</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>públicos alvos</td>
                  <td>População de públicos alvos delivery</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>template (deliveryTemplateSummary)</td>
                  <td>Template do delivery</td>
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
                  <td>rastreamento</td>
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
                  <td>URLs acompanhados</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>triggerMessage</td>
                  <td>Parâmetros do mensagen transacional</td>
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
                  <td>Fluxo de trabalho de definição de metas</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflowStatus</td>
                  <td>Status do fluxo de trabalho</td>
                  <td>lista discriminada (string) (255)</td>
                  <td>
                     <ul>
                        <li>Em andamento - iniciado - iniciado</li>
                        <li>Edição - edição - edição</li>
                        <li>Concluído - concluído - concluído</li>
                        <li>Aviso - aviso - aviso</li>
                        <li>Errado - erro - erro</li>
                        <li>VALOR INVÁLIDO - __Valor_inválido__ - __Valor_inválido__</li>
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
    <td>canal</td>
    <td>lista discriminada</td>
    </tr>
</table>

Por tipo de execução (byExecutionType)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>executeType</td>
    <td>lista discriminada</td>
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
    <td>lista discriminada</td>
    </tr>
</table>

Por nome ou rótulo (por texto)

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

Por período (por período)

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

Por período (porStartPeriod)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>string</td>
    </tr>
</table>

Por status de publicação (byPublishingStatus)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>pStatus</td>
    <td>lista discriminada</td>
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
    <td>lista discriminada</td>
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

Incluir delivery avançados (comAdvanced)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>advanced</td>
    <td>booleano</td>
    </tr>
</table>

Incluir delivery contínuos de uma lista heterogênea (comContínuo)

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

Planejado durante o período especificado (pelo Planning)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>

Presente durante determinado período (porCalendar)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>

Mostrar predefinido (showOob)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>bobajada</td>
    <td>booleano</td>
    </tr>
</table>