---
solution: Campaign Standard
product: campaign
title: DataModel
description: Saiba mais sobre o modelo de dados
audience: developing
content-type: reference
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 13%

---


# Visitante (nms:visitante)

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
        <td>comentário</td>
        <td>Comentário quem indicou</td>
        <td>string (255)</td>
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
        <td>delivery (delivery)</td>
        <td>Delivery</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>deliveryId</td>
        <td>ID do último delivery</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>desc</td>
        <td>Descrição</td>
        <td>string (512)</td>
        <td> </td>
    </tr>
    <tr>
        <td>email</td>
        <td>Email</td>
        <td>string (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>externalId</td>
        <td>ID externa</td>
        <td>string (64)</td>
        <td> </td>
    </tr>
    <tr>
        <td>firstName</td>
        <td>Nome</td>
        <td>string (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>forwardUrl</td>
        <td>URL de encaminhamento</td>
        <td>string (255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>geoUnit (geoUnitBase)</td>
        <td>Unidade geográfica</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastModified</td>
        <td>Última modificação</td>
        <td>date </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastName</td>
        <td>Sobrenome</td>
        <td>string (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>modifiedBy (userBase)</td>
        <td>Modificado por</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>orgUnit (orgUnitBase)</td>
        <td>Unidade organizacional</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>origem</td>
        <td>Origem</td>
        <td>lista discriminada (byte) </td>
        <td>
            <ul>
            <li>Indefinido - indefinido - 0</li>
            <li>VALOR INVÁLIDO - __Valor_inválido__ - __Valor_inválido__</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>recipient (recipient)</td>
        <td>Perfil identificado</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>receiptId</td>
        <td>ID do perfil</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerEmail</td>
        <td>E-mail de quem indicou</td>
        <td>string (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerFirstName</td>
        <td>Nome da quem indicou</td>
        <td>string (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerId</td>
        <td>ID da quem indicou</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerLastName</td>
        <td>sobrenome da quem indicou</td>
        <td>string (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerRcp (recipient)</td>
        <td>Quem indicou</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>título</td>
        <td>Rótulo</td>
        <td>string (255)</td>
        <td> </td>
    </tr>
</table>

## Filtros

Por sobrenome, nome ou email (por texto)</p>

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