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


# Visitante (nms:visitor)

## Descrição do objeto

    &lt;table&gt;
    &lt;tr&gt;
    &lt;th&gt;Nome&lt;/th&gt;
    &lt;th&gt;Rótulo&lt;/th&gt;
    &lt;th&gt;Tipo (comprimento)&lt;/th&gt;
    &lt;th&gt;Valores de enumeração&lt;/th&gt;
    &lt;/tr&gt;
    &lt;tr&gt;
    &lt;td&gt;PKey&lt;/td&gt;
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    &lt;td&gt;ID de recurso principal&lt;/td&gt;cadeia de caracteres &lt;/td&gt;t&gt; &lt;/td&gt;Comentário do referenciador&lt;/td&gt;&lt;/td&gt;Cadeia de caracteres (255)&lt;/td&gt;Comentário&lt;/td&gt;Comentário do referenciador&lt;/td&gt;&gt; &lt;/td&gt;Comentário&lt;/td&gt;Criado&lt;/td&gt;Criado&gt;&lt;/td&gt;Criado &lt;td&lt;td&gt; data &lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;td&gt;criadoBy (userBase)&lt;/td&gt;Criado por&lt;/td&gt;link &lt;/td&gt;td&gt;&gt; &lt;/td&gt; &lt;/td&gt; &lt;/td&gt;Entrega &lt;/tr&gt;&lt;td&gt;entrega (entrega)&lt;/td&gt;&lt;/td&gt;Entrega&lt;/td&gt;link &lt;/td&gt;link &lt;/td&gt;&gt; &lt;/td&gt;&lt;/td&gt;tr&gt;&lt;td&gt;deliveryId&lt;/td&gt;&lt;td&gt;ID da última entrega&lt;/td&gt;&lt;/td&gt;integer &lt;/td&gt;&gt; &lt;/td&gt;t&gt;ID /tr&gt;&lt;td&gt;desc&lt;/td&gt;Descrição&lt;/td&gt;Descrição&lt;/td&gt;&lt;td&gt;cadeia de caracteres (512)&lt;/td&gt;&gt; &lt;/td&gt;&lt;/tr&gt;&gt;cadeia de caracteres (12) 8)&lt;/td&gt;&lt;/td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;td&gt;externalId&lt;/td&gt;ID Externo&lt;/td&gt;cadeia de caracteres (64)&lt;/td&gt; &lt;/td&gt; &lt;/td&gt;td&gt; &lt;/td&gt;Relatório&lt;/tr&gt;&gt;Nome&lt;td&gt;Nome&lt;/td&gt;first&gt; &lt;td&gt;Nome&lt;/td&gt;cadeia de caracteres (30)&lt;/td&gt;&gt; &lt;/td&gt;&lt;/tr&gt;&lt;td&gt;Url&lt;/td&gt;ForwardUrl&lt;/td&gt;Url&lt;/td&gt;Encaminhar url&lt;/td&gt;cadeia de caracteres (255)&lt;/td&gt;&lt;td&gt; td&gt;&lt;/tr&gt;&lt;td&gt;GeoUnit (geoUnitBase)&lt;/td&gt;Unidade geográfica&lt;/td&gt;Ligação &lt;/td&gt;Ligação &lt;/td&gt;Ligação&gt; &lt;/td&gt; &lt;/td&gt;&lt;/tr&gt;tr&gt;&lt;td&gt;lastModified&lt;/td&gt;foi modificada pela última vez&lt;/td&gt;Última modificação&gt;&lt;td&gt;data &lt;/td&gt;Data&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;td&gt;lastName&lt;/td&gt;Nome&lt;/td&gt;Sobrenome&lt;/td&gt;Nome&lt;/td&gt;&gt;(50)&lt;/td&gt;td&gt; &lt;/td&gt; &lt;/td&gt;td&gt;sequência de caracteres modificadaBy. userBase)&lt;/td&gt;&lt;td&gt;Modificado por&lt;/td&gt;link &lt;/td&gt;link &lt;/td&gt;d&gt; &lt;/td&gt;&lt;td&gt;orgUnit (orgUnitBase)&lt;/td&gt;unidade organizacional&lt;/td&gt;Unidade organizacional&lt;/td&gt;&gt;&lt;td&gt;link &lt;/td&gt;&gt; &lt;/td&gt;&lt;/tr&gt;&lt;td&gt;origem&lt;/td&gt;Origem&lt;/td&gt;Origem&lt;/td&gt;&gt;enumeração (byte) &lt;/td&gt;&lt;td&gt;Não definido - não definido - 0&lt;/li&gt;&gt;VALOR INVÁLIDO - __Valor_Inválido___ - __Inválido value__&lt;/li&gt;&lt;/ul&gt;&lt;/d&gt;&lt;tr&gt;Destinatário)&lt;/td&gt;Destinatário (destinatário)&lt;/td&gt;Perfil identificado&lt;/td&gt;Ligação &lt;/td&gt;Ligação &lt;/td&gt;Ligação&gt; &lt;/td&gt;&lt;/tr&gt;td&lt;td&gt;Destinatário&lt;td&gt;Id&lt;/td&gt;td&gt;ID do perfil&lt;/td&gt;&lt;td&gt;integer &lt;/td&gt;inteiro &lt;/td&gt;&gt; &lt;/td&gt;&lt;td&gt;referrerEmail&lt;/td&gt;E-mail do referenciador&lt;/td&gt;cadeia de caracteres (128)&lt;/td&gt;&gt; &lt;/td&gt;t&lt; /tr&gt;&lt;td&gt;referenciadorNomeNome&lt;/td&gt;NomeDoReferenciador&lt;/td&gt;Nome próprio&lt;/td&gt;cadeia de caracteres (30)&lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;referenciadorId&lt;/td&gt;ID do Referenciador&lt;/td&gt;ID do Referenciador&lt; /td&gt;&lt;td&gt;número inteiro &lt;/td&gt;&gt; &lt;/td&gt;&lt;/tr&gt;&lt;td&gt;referenciadorSobrenome&lt;/td&gt;Nome do sobrenome do referenciador&lt;/td&gt;cadeia de caracteres (50)&lt;/td&gt;&gt; &lt;/td&gt;&lt;/tr&gt; tr&gt;&lt;td&gt;referrerRcp (destinatário)&lt;/td&gt;Referenciador&lt;/td&gt;Ligação &lt;/td&gt;Ligação &lt;/td&gt;&gt; &lt;/td&gt;&lt;/tr&gt;&lt;td&gt;título&lt;/td&gt;Etiqueta&lt;/td&gt;Rótulo (255) (cadeia de caracteres)&lt;/td&gt;&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;Tabela&gt;

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