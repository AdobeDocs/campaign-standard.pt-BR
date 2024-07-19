---
title: Campanha do modelo de dados
description: Saiba mais sobre o modelo de dados
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: a63fe730-a6b2-4ae0-93da-9f8ee7824c9f
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 36%

---

# Campaign (nms:campaign)

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
                  <td>atividades</td>
                  <td>Atividades</td>
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
                  <td>desc</td>
                  <td>Descrição</td>
                  <td>sequência de caracteres (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>duração</td>
                  <td>Duração da campanha</td>
                  <td>número </td>
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
                  <td>programa (programBase)</td>
                  <td>Programa</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>Relatórios em tempo real</td>
                  <td>Item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>start</td>
                  <td>Data de início</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>status</td>
                  <td>Status</td>
                  <td>enumeração (byte) </td>
                  <td>
                     <ul>
                        <li>Iniciado - iniciado - 1</li>
                        <li>Edição - edição - 0</li>
                        <li>Concluído - concluído - 2</li>
                        <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>template (campanha)</td>
                  <td>Template de campanha</td>
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
                  <td>Campanha</td>
                  <td>sequência de caracteres (255)</td>
                  <td> </td>
               </tr>
            </table>

## Filtros

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
</table>

Por período (byPeriod)

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

Planejado para o período determinado (por Planejamento)

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
