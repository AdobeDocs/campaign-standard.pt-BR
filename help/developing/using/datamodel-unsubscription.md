---
title: DataModel
description: Saiba mais sobre o datamodel
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 508361d1-6a0b-4476-a058-4162fb3e8d5e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 16%

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
                  <td>Verdadeiro</td>
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
