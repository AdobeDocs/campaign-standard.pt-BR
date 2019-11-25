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
source-git-commit: 6263623a5a8999c475255709a7d0150437e68c0b

---


# Visitante (nms:visitor)

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
        <td>ID do recurso principal</td>
        <td>string </td>
        <td> </td>
    </tr>
    <tr>
        <td>comentário</td>
        <td>Comentário do referenciador</td>
        <td>string (255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>created</td>
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
        <td>entrega (entrega)</td>
        <td>Delivery</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>deliveryId</td>
        <td>ID da última entrega</td>
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
        <td>enumeração (byte) </td>
        <td>
            <ul>
            <li>Indefinido - indefinido - 0</li>
            <li>VALOR INVÁLIDO - __Valor_inválido__ - __Valor_inválido__</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>destinatário (destinatário)</td>
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
        <td>Email do referenciador</td>
        <td>string (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerFirstName</td>
        <td>Nome do referenciador</td>
        <td>string (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerId</td>
        <td>ID do referenciador</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerLastName</td>
        <td>Sobrenome do referenciador</td>
        <td>string (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerRcp (destinatário)</td>
        <td>Referenciador</td>
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