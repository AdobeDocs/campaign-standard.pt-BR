---
solution: Campaign Standard
product: campaign
title: DataModel
description: Saiba mais sobre o datamodel
audience: developing
content-type: reference
feature: Modelo de dados
role: Desenvolvedor
level: Experienciado
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 12%

---


# Evento de assinatura (nms:rtEvent)

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
        <td>ctx</td>
        <td>Contexto do evento</td>
        <td>item </td>
        <td> </td>
    </tr>
    <tr>
        <td>email</td>
        <td>Email</td>
        <td>string (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>emailFormat</td>
        <td>Formato de email</td>
        <td>enumeração (byte) </td>
        <td>
            <ul>
            <li>Texto - texto - 1</li>
            <li>HTML - html - 2</li>
            <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
            <li>Desconhecido - desconhecido - 0</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>eventHistoId</td>
        <td>ID de evento arquivada</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>mobilePhone</td>
        <td>Número do celular</td>
        <td>string (32)</td>
        <td> </td>
    </tr>
    <tr>
        <td>serverUrl</td>
        <td>ServerUrl</td>
        <td>string </td>
        <td> </td>
    </tr>
</table>

## Filtros

Por email (por email)

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

Por status ou tipo (byStatusOrType)

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