---
title: DataModel
description: Saiba mais sobre o modelo de dados
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c7e83d7d5130ce93b880e4835e634dad03504ebb

---


# Evento de cancelamento de assinatura (nms:rtEvent)

## Descrição do objeto

<table>
               <tr>
                  <th>Nome</th>
                  <th>Somente leitura</th>
                  <th>Tipo</th>
                  <th>Obrigatório</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>Falso</td>
                  <td>string</td>
                  <td>Falso</td>
               </tr>
               <tr>
                  <td>ctx</td>
                  <td>Falso</td>
                  <td>item</td>
                  <td>Falso</td>
               </tr>
               <tr>
                  <td>email</td>
                  <td>Falso</td>
                  <td>string</td>
                  <td>Falso</td>
               </tr>
               <tr>
                  <td>emailFormat</td>
                  <td>Falso</td>
                  <td>enumeração</td>
                  <td>Falso</td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>Falso</td>
                  <td>string</td>
                  <td>Falso</td>
               </tr>
               <tr>
                  <td>serverUrl</td>
                  <td>True</td>
                  <td>string</td>
                  <td>Falso</td>
               </tr>
            </table>

## Filtros

porEmail

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>email</td>
    <td>string</td>
    </tr>
</table>

byStatusOrType

<table>
        <tr>
        <th>Nome</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>status</td>
        <td>enumeração</td>
        </tr>
        <tr>
        <td>type</td>
        <td>string</td>
        </tr>
    </table>