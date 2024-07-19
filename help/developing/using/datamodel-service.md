---
title: Serviço de modelo de dados
description: Saiba mais sobre o modelo de dados
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: a326b38f-ca88-4a44-a7c2-b6e34497a364
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 39%

---

# Serviço (nms:service)

## Descrição do objeto

<table>
               <tr>
                  <th>Nome</th>
                  <th>Rótulo</th>
                  <th>Tipo (comprimento)</th>
                  <th>Valores de lista discriminada</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>ID do recurso principal</td>
                  <td>sequência de caracteres </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>builtIn</td>
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
                  <td>inteiro </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>desc</td>
                  <td>Descrição</td>
                  <td>sequência de caracteres (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fim</td>
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
                  <td>histórico</td>
                  <td>Histórico de assinatura</td>
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
                  <td>Modelo</td>
                  <td>booleano </td>
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
                  <td>limitDuration</td>
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
                  <td>Canal</td>
                  <td>enumeração (byte) </td>
                  <td>
                     <ul>
                        <li>Móvel (SMS) - sms - 1</li>
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
                        <li>Viral - viral - 1</li>
                        <li>Informativo - informativo - 0</li>
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
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Entidade organizacional</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>publicLabel</td>
                  <td>Rótulo de serviço</td>
                  <td>sequência de caracteres (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>start</td>
                  <td>Data de início</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subLandingPage (landingPageSubscriptionBase)</td>
                  <td>Página de destino da assinatura</td>
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
                  <td>TipoDeEventoSubcenário</td>
                  <td>sequência de caracteres </td>
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
                  <td>sequência de caracteres (255)</td>
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
                  <td>sequência de caracteres (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>título</td>
                  <td>Serviço</td>
                  <td>sequência de caracteres (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubLandingPage (landingPageUnsubscriptionBase)</td>
                  <td>Página de destino do cancelamento de assinatura</td>
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
                  <td>sequência de caracteres </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>validDuration</td>
                  <td>Duração da validade</td>
                  <td>número </td>
                  <td> </td>
               </tr>
            </table>

## Filtros

Disponível durante o período determinado (por Planejamento)

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
</table>

Por recurso de direcionamento (byTargetResource)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>targetResource</td>
<td>sequência de caracteres</td>
</tr>
</table>
