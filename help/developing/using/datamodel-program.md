---
title: Programa DataModel
description: Saiba mais sobre o datamodel
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: b05dc67a-6447-4d22-99f2-8a14a0ee46d2
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 22%

---

# Programa (nms:program)

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
                  <td>Atividades</td>
                  <td>Atividades</td>
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
                  <td>parent (programBase)</td>
                  <td>Programa pai</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>Relatórios em tempo real</td>
                  <td>item </td>
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
                  <td>modelo (programa)</td>
                  <td>Modelo de programa</td>
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
                  <td>Programa</td>
                  <td>string (255)</td>
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
</table>

Por período (porPeríodo)

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

Incluir subprogramas (comPai)

<table>
        <tr>
        <th>Nome</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>withParent</td>
        <td>booleano</td>
        </tr>
    </table>

Apenas os pais elegíveis (eligibleParents)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>Programa do </td>
    <td>link</td>
    </tr>
</table>

Planejado para o período especificado (byPlanning)

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
