---
title: DataModel
description: Saiba mais sobre o modelo de dados
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 14%

---


# Audiência (nms:audiência)

## Descrição do objeto

<table>
               <tr>
                  <th>Nome</th>
                  <th>Rótulo</th>
                  <th>Tipo (comprimento)</th>
                  <th>valores de lista discriminada</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>ID do recurso principal</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>aamMappingId</td>
                  <td>ID de mapeamento de Audience Manager</td>
                  <td>string (100)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>amcDataSource (amcDataSourceBase)</td>
                  <td>Fonte de dados da Adobe Experience Cloud (AMC)</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceData</td>
                  <td>Pré-visualização selecionada</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceDataSchema</td>
                  <td>Schema de dados</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceMetadata</td>
                  <td>AudienceMetadata</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>collectLineNumber</td>
                  <td>Usar um número de linha como ID</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>count</td>
                  <td>Contagem</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countDate</td>
                  <td>Data de contagem</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countPreview</td>
                  <td>CountPreview</td>
                  <td>item </td>
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
                  <td>desc</td>
                  <td>Descrição</td>
                  <td>string (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>doNotPersist</td>
                  <td>Não historizar este trabalho</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>errorLimit</td>
                  <td>Erros antes de abortar</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>expirationDate</td>
                  <td>Expira em</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Unidade geográfica</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hasSchema</td>
                  <td>HasSchema</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isAMC</td>
                  <td>audiência Adobe Marketing Cloud</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>É um recurso externo</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>jobLogs</td>
                  <td>Logs</td>
                  <td>coleção </td>
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
                  <td>Unidade organizacional</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cancelFilename</td>
                  <td>Arquivo de rejeição</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sharedAudience</td>
                  <td>Nome da audiência compartilhada</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fonte</td>
                  <td>Fonte</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sourceId</td>
                  <td>Source Id</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>título</td>
                  <td>Público-alvo</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>type</td>
                  <td>Tipo</td>
                  <td>lista discriminada (string) (100)</td>
                  <td>
                     <ul>
                        <li>Query - query - query</li>
                        <li>Lista - lista - lista</li>
                        <li>Arquivo - arquivo - arquivo</li>
                        <li>VALOR INVÁLIDO - __Valor_inválido__ - __Valor_inválido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>where</td>
                  <td>Definição de query</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fluxo de trabalho (fluxo de trabalho)</td>
                  <td>Fluxo de trabalho</td>
                  <td>link </td>
                  <td> </td>
               </tr>
            </table>

## Filtros

Por dimensão do filtro (byFilteringResource)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>filteringResource</td>
    <td>string</td>
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
</table>

Por tipo (byType)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>type</td>
    <td>lista discriminada</td>
    </tr>
    <tr>
    <td>isAMC</td>
    <td>string</td>
    </tr>
</table>