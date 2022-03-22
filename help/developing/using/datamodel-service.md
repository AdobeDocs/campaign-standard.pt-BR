---
title: Serviço do DataModel
description: Saiba mais sobre o datamodel
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: a326b38f-ca88-4a44-a7c2-b6e34497a364
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 21%

---

# Serviço (nms:service)

## Descrição do objeto

<table>
               <tr>
                  <th>Nome</th>
                  <th>Rótulo</th>
                  <th>Tipo (comprimento)</th>
                  <th>Valores de enumeração</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>ID de recurso principal</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>build</td>
                  <td>Objeto de aplicativo integrado</td>
                  <td>booleano </td>
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
                  <td>cusPrice</td>
                  <td>Preço</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>desc</td>
                  <td>Descrição</td>
                  <td>string (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>end</td>
                  <td>Data final</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Unidade geográfica</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>história</td>
                  <td>Histórico de subscrição</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>É recurso externo</td>
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
                  <td>limitedDuration</td>
                  <td>Duração limitada</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>Data</td>
                  <td>data (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>Canal </td>
                  <td>enumeração (byte) </td>
                  <td>
                     <ul>
                        <li>Mobile (SMS) - sms - 1</li>
                        <li>Email - email - 0</li>
                        <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modo</td>
                  <td>Modo</td>
                  <td>enumeração (byte) </td>
                  <td>
                     <ul>
                        <li>Viral - 1</li>
                        <li>Informativo - boletim informativo - 0</li>
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
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Entidade organizacional</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>publicLabel</td>
                  <td>Etiqueta de serviço</td>
                  <td>string (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>start</td>
                  <td>Data inicial</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subLandingPage (landingPageSubscriptionBase)</td>
                  <td>Página de aterrissagem da assinatura</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenario (deliveryMCTemplateBase)</td>
                  <td>Confirmação de assinatura</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenarioEventType</td>
                  <td>SubScenarioEventType</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>assinaturas</td>
                  <td>Assinaturas</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>targetResource</td>
                  <td>Dimensão de direcionamento</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>template (serviço)</td>
                  <td>Modelo de serviço</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniatura</td>
                  <td>Miniatura</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>título</td>
                  <td>Serviço</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubLandingPage (landingPageUnsubscriptionBase)</td>
                  <td>Página de aterrissagem de cancelamento de assinatura</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubScenario (deliveryMCTemplateBase)</td>
                  <td>Confirmação de cancelamento de assinatura</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubScenarioEventType</td>
                  <td>UnsubScenarioEventType</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>validityDuration</td>
                  <td>Duração da validade</td>
                  <td>número </td>
                  <td> </td>
               </tr>
            </table>

## Filtros

Disponível durante o período especificado (byPlanning)

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
</table>

Por recurso de direcionamento (byTargetResource)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>targetResource</td>
<td>string</td>
</tr>
</table>
