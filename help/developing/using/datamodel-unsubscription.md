---
title: Evento de Cancelamento de Assinatura de Modelo de Dados
description: Saiba mais sobre o modelo de dados
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 508361d1-6a0b-4476-a058-4162fb3e8d5e
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 58%

---

# Evento de cancelamento de subscrição (nms:rtEvent)

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
                  <td>sequência de caracteres</td>
                  <td>Falso</td>
               </tr>
               <tr>
                  <td>ctx</td>
                  <td>Falso</td>
                  <td>Item</td>
                  <td>Falso</td>
               </tr>
               <tr>
                  <td>email</td>
                  <td>Falso</td>
                  <td>sequência de caracteres</td>
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
                  <td>sequência de caracteres</td>
                  <td>Falso</td>
               </tr>
               <tr>
                  <td>serverUrl</td>
                  <td>Verdadeiro</td>
                  <td>sequência de caracteres</td>
                  <td>Falso</td>
               </tr>
            </table>

## Filtros

byEmail

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>email</td>
    <td>sequência de caracteres</td>
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
        <td>tipo</td>
        <td>sequência de caracteres</td>
        </tr>
    </table>
