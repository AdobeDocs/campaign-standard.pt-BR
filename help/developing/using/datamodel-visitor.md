---
title: Visitante do modelo de dados
description: Saiba mais sobre o modelo de dados
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 20dafd81-8546-450a-87a0-59a2509efb7a
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 45%

---

# Visitante (nms:visitor)

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
        <td>comentário</td>
        <td>Comentário do referenciador</td>
        <td>sequência de caracteres (255)</td>
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
        <td>Link  </td>
        <td> </td>
    </tr>
    <tr>
        <td>delivery (delivery)</td>
        <td>Entrega</td>
        <td>Link  </td>
        <td> </td>
    </tr>
    <tr>
        <td>deliveryId</td>
        <td>ID da última entrega</td>
        <td>inteiro </td>
        <td> </td>
    </tr>
    <tr>
        <td>desc</td>
        <td>Descrição</td>
        <td>sequência de caracteres (512)</td>
        <td> </td>
    </tr>
    <tr>
        <td>email</td>
        <td>Email</td>
        <td>sequência de caracteres (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>externalId</td>
        <td>ID externa</td>
        <td>sequência de caracteres (64)</td>
        <td> </td>
    </tr>
    <tr>
        <td>firstName</td>
        <td>Nome</td>
        <td>sequência de caracteres (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>forwardUrl</td>
        <td>URL de encaminhamento</td>
        <td>sequência de caracteres (255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>geoUnit (geoUnitBase)</td>
        <td>Unidade geográfica</td>
        <td>Link  </td>
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
        <td>sequência de caracteres (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>modifiedBy (userBase)</td>
        <td>Modificado por</td>
        <td>Link  </td>
        <td> </td>
    </tr>
    <tr>
        <td>orgUnit (orgUnitBase)</td>
        <td>Entidade organizacional</td>
        <td>Link  </td>
        <td> </td>
    </tr>
    <tr>
        <td>origem</td>
        <td>Origem</td>
        <td>enumeração (byte) </td>
        <td>
            <ul>
            <li>Indefinido - indefinido - 0</li>
            <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>recipient (recipient)</td>
        <td>Perfil identificado</td>
        <td>Link  </td>
        <td> </td>
    </tr>
    <tr>
        <td>recipientId</td>
        <td>ID do perfil</td>
        <td>inteiro </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerEmail</td>
        <td>Email do referenciador</td>
        <td>sequência de caracteres (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerFirstName</td>
        <td>Nome do referenciador</td>
        <td>sequência de caracteres (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerId</td>
        <td>ID do referenciador</td>
        <td>inteiro </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerLastName</td>
        <td>Sobrenome do referenciador</td>
        <td>sequência de caracteres (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerRcp (recipient)</td>
        <td>Referenciador</td>
        <td>Link  </td>
        <td> </td>
    </tr>
    <tr>
        <td>título</td>
        <td>Rótulo</td>
        <td>sequência de caracteres (255)</td>
        <td> </td>
    </tr>
</table>

## Filtros

Por sobrenome, nome ou email (byText)</p>

<table>
        <tr>
        <th>Nome</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>texto</td>
        <td>sequência de caracteres</td>
        </tr>
    </table>
