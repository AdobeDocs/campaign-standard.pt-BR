---
title: Evento de assinatura de modelo de dados
description: Saiba mais sobre o modelo de dados
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: cf0fac4e-59fd-4d6e-a411-41361f45938d
TQID: 'https://experienceleague.adobe.com/XssYu0sntbeCRq1uNe6MhztLtISXoJiOefIOnjqIaoQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: a1681cd8-6b2e-4955-9113-33b5f7a22b8c
    internal-label: Data model architecture
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 33%
---
# Evento de Assinatura (nms:rtEvent)

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
