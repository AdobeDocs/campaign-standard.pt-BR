---
title: Evento de assinatura de modelo de dados
description: Saiba mais sobre o modelo de dados
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: cf0fac4e-59fd-4d6e-a411-41361f45938d
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 32%

---

# Evento de assinatura (nms:rtEvent)

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
        <td>ctx</td>
        <td>Contexto do evento</td>
        <td>Item </td>
        <td> </td>
    </tr>
    <tr>
        <td>email</td>
        <td>Email</td>
        <td>sequência de caracteres (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>emailFormat</td>
        <td>Formato do email</td>
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
        <td>ID de evento arquivado</td>
        <td>inteiro </td>
        <td> </td>
    </tr>
    <tr>
        <td>mobilePhone</td>
        <td>Número do celular</td>
        <td>sequência de caracteres (32)</td>
        <td> </td>
    </tr>
    <tr>
        <td>serverUrl</td>
        <td>URLdoServidor</td>
        <td>sequência de caracteres </td>
        <td> </td>
    </tr>
</table>

## Filtros

Por e-mail (byEmail)

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
        <td>tipo</td>
        <td>sequência de caracteres</td>
        </tr>
    </table>
