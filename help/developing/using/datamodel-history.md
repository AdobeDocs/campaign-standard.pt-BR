---
solution: Campaign Standard
product: campaign
title: DataModel
description: Saiba mais sobre o datamodel
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1208'
ht-degree: 6%

---


# Histórico de marketing (nms:history)

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
                  <td>age</td>
                  <td>Idade</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>birthDate</td>
                  <td>Data de nascimento</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blacklist</td>
                  <td>Não mais entrar em contato (por qualquer canal)</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListEmail</td>
                  <td>Não entrar mais em contato por e-mail</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListFax</td>
                  <td>Não entrar mais em contato por fax</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListMobile</td>
                  <td>Não entrar mais em contato por SMS</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPhone</td>
                  <td>Não entrar mais em contato por telefone</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPostalMail</td>
                  <td>Não entrar mais em contato por mala direta</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blacklistPushnotification</td>
                  <td>Não entrar mais em contato por notificação por push</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countBroadLogEvents</td>
                  <td>CountBroadLogEvents</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countSubHistoEvents</td>
                  <td>CountSubHistoEvents</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>país (países)</td>
                  <td>Country</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countryIsoA2</td>
                  <td>Código ISO A2</td>
                  <td>string (2)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>criado</td>
                  <td>Criado</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy (userBase)</td>
                  <td>Criado por</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusHobbieslink (cusHobbies)</td>
                  <td>CusHobbieslink</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusLastTransactionDate</td>
                  <td>Data da Última Transação</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusTransactionslink</td>
                  <td>Transações</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>email</td>
                  <td>Email</td>
                  <td>string (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>eventos</td>
                  <td>Recurso heterogêneo</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fax</td>
                  <td>Fax</td>
                  <td>string (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>firstName</td>
                  <td>Nome</td>
                  <td>string (30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>gender</td>
                  <td>Sexo</td>
                  <td>enumeração (byte) </td>
                  <td>
                     <ul>
                        <li>Não especificado - desconhecido - 0</li>
                        <li>Masculino - Masculino - 1</li>
                        <li>Feminino - 2</li>
                        <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>É recurso externo</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>kpisAndChart</td>
                  <td>KpisAndChart</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>Última modificação</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastName</td>
                  <td>Sobrenome</td>
                  <td>string (50)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>localização</td>
                  <td>Local</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>middleName</td>
                  <td>Nome do meio</td>
                  <td>string (30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>minBroadLogEvents</td>
                  <td>MinBroadLogEvents</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>minSubHistoEvents</td>
                  <td>MinSubHistoEvents</td>
                  <td>data </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>Celular</td>
                  <td>string (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>Modificado por</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>phone</td>
                  <td>Telefone</td>
                  <td>string (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>salutation</td>
                  <td>Título</td>
                  <td>string (20)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink (estado)</td>
                  <td>Estado</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniatura</td>
                  <td>Miniatura</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>timeZone</td>
                  <td>Fuso horário</td>
                  <td>enumeration (string) (64)</td>
                  <td>
                     <ul>
                        <li>(GMT-02:00) Atlântico Central - Atlantic_South_Georgia - Atlantic/South_Georgia</li>
                        <li>(GMT+02:00) Amã - Ásia_Amã - Ásia/Amã</li>
                        <li>(GMT-03:00) Brasi - América_São_Paulo - América/São_Paulo</li>
                        <li>(GMT+06:00) Astana, Daca - Ásia_Daca - Ásia/Daca</li>
                        <li>(GMT+06:00) Novossibirsk - Asia_Novosibirsk - Ásia/Novosibirsk</li>
                        <li>(GMT+02:00) Windhoek - Africa_Windhoek - África/Windhoek</li>
                        <li>(GMT+04:00) Cáucaso, Erevan - Asia_Yerevan - Ásia/Yerevan</li>
                        <li>(GMT-04:00) Manaus - América_Manaus - América/Manaus</li>
                        <li>(GMT+03:30) Teerão - Ásia_Teerão - Ásia/Teerão</li>
                        <li>(GMT+12:00) Auckland, Wellington - Pacific_Auckland - Pacífico/Auckland</li>
                        <li>(GMT+02:00) Jerusalém - Ásia_Jerusalém - Ásia/Jerusalém</li>
                        <li>(GMT+03:00) Moscou, São Petersburgo, Volgograd - Europe_Moscou - Europa/Moscou</li>
                        <li>(GMT+09:30) Adelaïde - Austrália_Adelaide - Austrália/Adelaide</li>
                        <li>(GMT+10:00) Canberra, Melbourne, Sydney - Austrália_Canberra - Austrália/Canberra</li>
                        <li>(GMT+08:00) Perth - Austrália_Perth - Austrália/Perth</li>
                        <li>(GMT+09:00) Yakoutsk - Asia_Yakutsk - Ásia/Yakutsk</li>
                        <li>(GMT-10:00) Havaí - Pacific_Honolulu - Pacific/Honolulu</li>
                        <li>(GMT+04:00) Baku - Asia_Baku - Ásia/Baku</li>
                        <li>(GMT+10:00) Vladivostok - Asia_Vladivostok - Ásia/Vladivostok</li>
                        <li>(GMT+09:00) Seul - Asia_Seul - Ásia/Seul</li>
                        <li>(GMT+01:00) Sarajevo, Skoplje, Sofia, Varsóvia, Zagreb - Europe_Sarajevo - Europa/Sarajevo</li>
                        <li>(GMT+04:00) Abu Dhabi, Muscat - Asia_Muscat - Asia/Muscat</li>
                        <li>(GMT+08:00) Kuala Lumpur, Singapura - Asia_Kuala_Lumpur - Ásia/Kuala_Lumpur</li>
                        <li>(GMT+09:00) Osaka, Sapporo, Tóquio - Ásia_Tóquio - Ásia/Tóquio</li>
                        <li>(GMT+10:00) Brisbane - Austrália_Brisbane - Austrália/Brisbane</li>
                        <li>(GMT+05:30) Sri Lanka - Asia_Colombo - Ásia/Colombo</li>
                        <li>(GMT+02:00) Harare, Pretória - Africa_Harare - África/Harare</li>
                        <li>(GMT+08:00) Oulan-Bator - Asia_Ulan_Bator - Ásia/Ulan_Bator</li>
                        <li>(GMT-02:00) Tempo Médio de Greenwich menos 2 horas - Gmt_m2 - Etc/GMT+2</li>
                        <li>(GMT-03:00) Tempo Médio de Greenwich menos 3 horas - Gmt_m3 - Etc/GMT+3</li>
                        <li>(GMT-01:00) Tempo Médio de Greenwich menos 1 hora - Gmt_m1 - Etc/GMT+1</li>
                        <li>(GMT-06:00) Tempo Médio de Greenwich menos 6 horas - Gmt_m6 - Etc/GMT+6</li>
                        <li>(GMT-07:00) Tempo Médio de Greenwich menos 7 horas - Gmt_m7 - Etc/GMT+7</li>
                        <li>(GMT-04:00) Tempo Médio de Greenwich menos 4 horas - Gmt_m4 - Etc/GMT+4</li>
                        <li>(GMT) Casablanca - Africa_Casablanca - África/Casablanca</li>
                        <li>(GMT+05:30) Kolkata, Chennai, Mumbai, Nova Deli - Asia_Kolkata - Ásia/Calcutá</li>
                        <li>(GMT-11:00) Tempo Médio de Greenwich menos 11 horas - Gmt_m11 - Etc/GMT+11</li>
                        <li>(GMT-09:00) Tempo Médio de Greenwich menos 9 horas - Gmt_m9 - Etc/GMT+9</li>
                        <li>(GMT-03:30) Terra Nova - América_St_Johns - América/St_Johns</li>
                        <li>(GMT+03:00) Tempo Médio de Greenwich mais 3 horas - Gmt_p3 - Etc/GMT-3</li>
                        <li>(GMT-04:30) Caracas - América_Caracas - América/Caracas</li>
                        <li>(GMT+01:00) Amesterdã, Berlim, Berna, Roma, Estocolmo, Viena - Europa_Berlim - Europa/Berlim</li>
                        <li>(GMT-07:00) Chihuahua, La Paz, Mazatlan - América_Chihuahua - América/Chihuahua</li>
                        <li>(GMT+03:00) Nairobi - Africa_Nairobi - África/Nairobi</li>
                        <li>(GMT-04:00) Assunção - América_Assunção - América/Assunção</li>
                        <li>(GMT+03:00) Bagdade - Asia_Bagdade - Ásia/Bagdade</li>
                        <li>(GMT-10:00) Tempo Médio de Greenwich menos 10 horas - Gmt_m10 - Etc/GMT+10</li>
                        <li>(GMT-03:00) Gronelândia - América_Godthab - América/Godthab</li>
                        <li>(GMT+02:00) Damas - Asia_Damascus - Ásia/Damasco</li>
                        <li>(GMT-11:00) Samoa - Pacific_Samoa - Pacífico/Samoa</li>
                        <li>(GMT-05:00) Bogotá, Lima, Quito - América_Bogota - América/Bogotá</li>
                        <li>(GMT+01:00) Bruxelas, Copenhaga, Madrid, Paris - Europa_Paris - Europa/Paris</li>
                        <li>(GMT+08:00) Pequim, Chongqing, Hong Kong, Urumqi - Asia_Shanghai - Ásia/Xangai</li>
                        <li>(GMT+12:00) Fidji - Pacific_Fiji - Pacífico/Fiji</li>
                        <li>(GMT+02:00) Atenas, Istambul, Minsk - Europa_Atenas - Europa/Atenas</li>
                        <li>(GMT+04:00) Tbilissi - Asia_Tbilisi - Ásia/Tbilisi</li>
                        <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
                        <li>(GMT+05:45) Katmandu - Asia_Katmandu - Ásia/Katmandu</li>
                        <li>(GMT-05:00) Indiana (Leste) - América_Indianapolis - América/Indianapolis</li>
                        <li>(GMT-01:00) Ilhas de Cabo Verde - Atlantic_Cape_Verde - Atlantic/Cape_Verde</li>
                        <li>(GMT+04:00) Port Louis - Indian_Maurícia - Índia/Maurícia</li>
                        <li>(GMT+08:00) Taipei - Asia_Taipei - Ásia/Taipei</li>
                        <li>(GMT+06:30) Rangum - Asia_Rangoon - Ásia/Rangum</li>
                        <li>(GMT+11:00) Magadan, Ilhas Salomão, Nova Caledónia - Pacific_Guadalcanal - Pacífico/Guadalcanal</li>
                        <li>(GMT+02:00) Cairo - África_Cairo - África/Cairo</li>
                        <li>(GMT+05:00) Iekaterinburg - Asia_Yekaterinburg - Ásia/Yekaterinburg</li>
                        <li>(GMT+08:00) Irkoutsk - Asia_Irkutsk - Ásia/Irkutsk</li>
                        <li>(GMT+10:00) Guam, Port Moresby - Pacific_Guam - Pacífico/Guam</li>
                        <li>(GMT-04:00) Hora Padrão do Atlântico (Canadá) - América_Halifax - América/Halifax</li>
                        <li>(GMT) Hora média de Greenwich - GMT - GMT</li>
                        <li>Padrão - nenhum - nenhum</li>
                        <li>(GMT-04:00) La Paz - América_La_Paz - América/La_Paz</li>
                        <li>(GMT-06:00) Guadalajara, México, Monterrey - América_México_Cidade - América/México_Cidade</li>
                        <li>(GMT+09:30) Darwin - Austrália_Darwin - Austrália/Darwin</li>
                        <li>(GMT-05:00) Leste (Estados Unidos e Canadá) - América_Nova_York - América/Nova_York</li>
                        <li>(GMT-05:00) Tempo Médio de Greenwich menos 5 horas - Gmt_m5 - Etc/GMT+5</li>
                        <li>(GMT+05:00) Islamabad, Karachi, Tachkent - Asia_Karachi - Ásia/Carachi</li>
                        <li>(GMT+03:00) Koweït, Riade - Asia_Riyadh - Ásia/Riade</li>
                        <li>(GMT-08:00) Tempo Médio de Greenwich menos 8 horas - Gmt_m8 - Etc/GMT+8</li>
                        <li>(GMT-01:00) Açores - Atlântico_Açores - Atlântico/Açores</li>
                        <li>(GMT+07:00) Bangkok, Hanói, Djakarta - Asia_Bangkok - Ásia/Bangkok</li>
                        <li>(GMT) Monróvia - África_Monróvia - África/Monróvia</li>
                        <li>(GMT-09:00) Alasca - America_Anchorage - América/Anchorage</li>
                        <li>(GMT+01:00) Belgrado, Bratislava, Budapeste, Liubliana, Praga - Europe_Belgrado - Europa/Belgrado</li>
                        <li>(GMT) Reykjavik - Atlantic_Reykjavik - Atlantic/Reykjavik</li>
                        <li>(GMT+02:00) Festa - Europa_Bucareste - Europa/Bucareste</li>
                        <li>(GMT+05:00) Tempo Médio de Greenwich mais 5 horas - Gmt_p5 - Etc/GMT-5</li>
                        <li>(GMT+04:00) Tempo Médio de Greenwich mais 4 horas - Gmt_p4 - Etc/GMT-4</li>
                        <li>(GMT+07:00) Tempo Médio de Greenwich mais 7 horas - Gmt_p7 - Etc/GMT-7</li>
                        <li>(GMT+06:00) Tempo Médio de Greenwich mais 6 horas - Gmt_p6 - Etc/GMT-6</li>
                        <li>(GMT+01:00) Tempo Médio de Greenwich mais 1 hora - Gmt_p1 - Etc/GMT-1</li>
                        <li>(GMT-08:00) Pacífico (Estados Unidos e Canadá) - América_Los_Angeles - América/Los_Angeles</li>
                        <li>(GMT+02:00) Tempo Médio de Greenwich mais 2 horas - Gmt_p2 - Etc/GMT-2</li>
                        <li>(GMT+07:00) Krasnoïarsk - Asia_Krasnoyarsk - Ásia/Krasnoyarsk</li>
                        <li>(GMT+09:00) Tempo Médio de Greenwich mais 9 horas - Gmt_p9 - Etc/GMT-9</li>
                        <li>(GMT+08:00) Tempo Médio de Greenwich mais 8 horas - Gmt_p8 - Etc/GMT-8</li>
                        <li>(GMT+10:00) Hobart - Austrália_Hobart - Austrália/Hobart</li>
                        <li>(GMT+13:00) Nuku'alofa - Pacific_Tongatapu - Pacific/Tongatapu</li>
                        <li>(GMT-06:00) América Central - América_Regina - América/Regina</li>
                        <li>(GMT-03:00) Buenos Aires, Cayenne, Fortaleza - America_Buenos_Aires - America/Buenos_Aires</li>
                        <li>(GMT-07:00) Montanhas Rochosas (Estados Unidos e Canadá) - América_Denver - América/Denver</li>
                        <li>(GMT+01:00) África Central - Oeste - África_Luanda - África/Luanda</li>
                        <li>(GMT+02:00) Helsínquia, Kiev, Riga, Sófia, Tallinn, Vilnius - Europe_Helsinki - Europa/Helsínquia</li>
                        <li>(GMT) Hora Média de Greenwich: Dublin, Edimburgo, Lisboa, Londres - Europa_Londres - Europa/Londres</li>
                        <li>(GMT-07:00) Arizona - América_Phoenix - América/Phoenix</li>
                        <li>(GMT+02:00) Beirute - Asia_Beirute - Ásia/Beirute</li>
                        <li>(GMT+04:30) Cabul - Ásia_Cabul - Ásia/Cabul</li>
                        <li>(GMT-06:00) Centro (Estados Unidos e Canadá) - América_Chicago - América/Chicago</li>
                        <li>(GMT+11:00) Tempo Médio de Greenwich mais 11 horas - Gmt_p11 - Etc/GMT-11</li>
                        <li>(GMT+10:00) Tempo Médio de Greenwich mais 10 horas - Gmt_p10 - Etc/GMT-10</li>
                        <li>(GMT+13:00) Tempo Médio de Greenwich mais 13 horas - Gmt_p13 - Etc/GMT-13</li>
                        <li>(GMT+12:00) Tempo Médio de Greenwich mais 12 horas - Gmt_p12 - Etc/GMT-12</li>
                        <li>(GMT-04:00) Santiago - América_Santiago - América/Santiago</li>
                        <li>(GMT-03:00) Montevidéu - America_Montevideo - América/Montevideo</li>
                        <li>(GMT-04:00) Cuiaba - América_Cuiaba - América/Cuiaba</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>título</td>
                  <td>Perfil</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
            </table>

## Filtros

Aniversário (aniversário)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>includeStart</td>
<td>booleano</td>
</tr>
<tr>
<td>previousUnitsValue</td>
<td>integer</td>
</tr>
<tr>
<td>nextUnitsValue</td>
<td>integer</td>
</tr>
<tr>
<td>endDay</td>
<td>data</td>
</tr>
<tr>
<td>precisão</td>
<td>enumeração</td>
</tr>
<tr>
<td>relativeValue</td>
<td>string</td>
</tr>
<tr>
<td>mês</td>
<td>data</td>
</tr>
<tr>
<td>operador</td>
<td>enumeração</td>
</tr>
<tr>
<td>includeEnd</td>
<td>booleano</td>
</tr>
<tr>
<td>endMonth</td>
<td>data</td>
</tr>
<tr>
<td>type</td>
<td>enumeração</td>
</tr>
<tr>
<td>dia</td>
<td>data</td>
</tr>
</table>

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

Por chaves (byKeysProfile)

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

Por nome ou email (byText)

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

Por público-alvo estático (por StaticAudience)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>público-alvo</td>
<td>link</td>
</tr>
</table>

Clicado em (hasClickedDelivery)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>delivery</td>
<td>link</td>
</tr>
</table>

Aberto (hasOpenedDelivery)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>delivery</td>
<td>link</td>
</tr>
</table>

Perfil (perfil)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>perfil</td>
<td>link</td>
</tr>
</table>

Recebido (hasReceivedDelivery)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>delivery</td>
<td>link</td>
</tr>
</table>

Assinantes (assinantes)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>service</td>
<td>link</td>
</tr>
</table>