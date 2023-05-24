---
title: Perfil do modelo de dados
description: Saiba mais sobre o modelo de dados
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 652c22a5-7fff-4d08-9396-f0b292aaca76
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '1249'
ht-degree: 14%

---

# Perfil (nms:recipient)

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
                  <td>idade</td>
                  <td>Idade</td>
                  <td>inteiro </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>appSubscription</td>
                  <td>Assinaturas de um aplicativo</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>birthDate</td>
                  <td>Data de nascimento</td>
                  <td>date </td>
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
                  <td>Não contatar mais por fax</td>
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
                  <td>Não contatar mais por telefone</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPostalMail</td>
                  <td>Não contatar mais por correspondência direta</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPushnotification</td>
                  <td>Não contatar mais por notificação por push</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>país (países)</td>
                  <td>Country</td>
                  <td>Link  </td>
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
                  <td>cryptedId</td>
                  <td>ID criptografada</td>
                  <td>sequência de caracteres </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusHobbieslink (cusHobbies)</td>
                  <td>CusHobbieslink</td>
                  <td>Link  </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusLastTransactionDate</td>
                  <td>Data da última transação</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusTransactionslink</td>
                  <td>Transações</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>domain</td>
                  <td>Domínio de email</td>
                  <td>sequência de caracteres (255)</td>
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
                  <td>emailStatus (addressStatus)</td>
                  <td>Informações sobre o email</td>
                  <td>Link  </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>excludeLogs</td>
                  <td>Logs de exclusão</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>externalId</td>
                  <td>ID do recurso externo</td>
                  <td>string(100) </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fax</td>
                  <td>Fax</td>
                  <td>sequência de caracteres (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>firstName</td>
                  <td>Nome</td>
                  <td>sequência de caracteres (30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>gender</td>
                  <td>Sexo</td>
                  <td>enumeração (byte) </td>
                  <td>
                     <ul>
                        <li>Não especificado - desconhecido - 0</li>
                        <li>Masculino - masculino - 1</li>
                        <li>Feminino - feminino - 2</li>
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
                  <td>localização</td>
                  <td>Localização</td>
                  <td>Item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>logs</td>
                  <td>Logs de entrega</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>middleName</td>
                  <td>Nome do meio</td>
                  <td>sequência de caracteres (30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>Celular</td>
                  <td>sequência de caracteres (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>Modificado por</td>
                  <td>Link  </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>phone</td>
                  <td>Telefone</td>
                  <td>sequência de caracteres (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>places</td>
                  <td>Localizações</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>postalAddress</td>
                  <td>Endereço postal</td>
                  <td>Item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>salutation</td>
                  <td>Título</td>
                  <td>sequência de caracteres (20)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink (estado)</td>
                  <td>Estado</td>
                  <td>Link  </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subHisto</td>
                  <td>Histórico de assinatura</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>assinaturas</td>
                  <td>Assinaturas</td>
                  <td>coleção </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniatura</td>
                  <td>Miniatura</td>
                  <td>sequência de caracteres (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>timeZone</td>
                  <td>Fuso horário</td>
                  <td>enumeração (cadeia de caracteres) (64)</td>
                  <td>
                     <ul>
                        <li>(GMT-02:00) Atlântico Central - Atlântico_Geórgia_do_Sul - Atlântico/Geórgia_do_Sul</li>
                        <li>(GMT+02:00) Amã - Ásia_Amã - Ásia/Amã</li>
                        <li>(GMT-03:00) Brasi - América_São_Paulo - América/São_Paulo</li>
                        <li>(GMT+06:00) Astana, Daca - Ásia_Daca - Ásia/Daca</li>
                        <li>(GMT+06:00) Novossibirsk - Ásia_Novosibirsk - Ásia/Novosibirsk</li>
                        <li>(GMT+02:00) Windhoek - África_Windhoek - África/Windhoek</li>
                        <li>(GMT+04:00) Cáucaso, Erevan - Ásia_Erevan - Ásia/Erevan</li>
                        <li>(GMT-04:00) Manaus - América_Manaus - América/Manaus</li>
                        <li>(GMT+03:30) Teerã - Ásia_Teerã - Ásia/Teerã</li>
                        <li>(GMT+12:00) Auckland, Wellington - Pacific_Auckland - Pacífico/Auckland</li>
                        <li>(GMT+02:00) Jerusalém - Ásia_Jerusalém - Ásia/Jerusalém</li>
                        <li>(GMT+03:00) Moscou, São Petersburgo, Volgogrado - Europa_Moscou - Europa/Moscou</li>
                        <li>(GMT+09:30) Adelaide - Austrália_Adelaide - Austrália/Adelaide</li>
                        <li>(GMT+10:00) Camberra, Melbourne, Sydney - Austrália_Camberra - Austrália/Camberra</li>
                        <li>(GMT+08:00) Perth - Austrália_Perth - Austrália/Perth</li>
                        <li>(GMT+09:00) Yakoutsk - Ásia_Yakutsk - Ásia/Yakutsk</li>
                        <li>(GMT-10:00) Hawai - Pacífico_Honolulu - Pacífico/Honolulu</li>
                        <li>(GMT+04:00) Baku - Ásia_Baku - Ásia/Baku</li>
                        <li>(GMT+10:00) Vladivostok - Ásia_Vladivostok - Ásia/Vladivostok</li>
                        <li>(GMT+09:00) Seul - Ásia_Seul - Ásia/Seul</li>
                        <li>(GMT+01:00) Sarajevo, Skoplje, Sófia, Varsóvia, Zagreb - Europa_Sarajevo - Europa/Sarajevo</li>
                        <li>(GMT+04:00) Abu Dhabi, Muscat - Ásia_Muscat - Ásia/Muscat</li>
                        <li>(GMT+08:00) Kuala Lumpur, Cingapura - Ásia_Kuala_Lumpur - Ásia/Kuala_Lumpur</li>
                        <li>(GMT+09:00) Osaka, Saporo, Tóquio - Ásia_Tóquio - Ásia/Tóquio</li>
                        <li>(GMT+10:00) Brisbane - Austrália_Brisbane - Austrália/Brisbane</li>
                        <li>(GMT+05:30) Sri Jayawardenepura - Ásia_Colombo - Ásia/Colombo</li>
                        <li>(GMT+02:00) Harare, Pretória - África_Harare - África/Harare</li>
                        <li>(GMT+08:00) Oulan-Bator - Ásia_Ulan_Bator - Ásia/Ulan_Bator</li>
                        <li>(GMT-02:00) Horário de Greenwich menos 2 horas - Gmt_m2 - Etc/GMT+2</li>
                        <li>(GMT-03:00) Horário de Greenwich menos 3 horas - Gmt_m3 - Etc/GMT+3</li>
                        <li>(GMT-01:00) Horário de Greenwich menos 1 hora - Gmt_m1 - Etc/GMT+1</li>
                        <li>(GMT-06:00) Horário de Greenwich menos 6 horas - Gmt_m6 - Etc/GMT+6</li>
                        <li>(GMT-07:00) Horário de Greenwich menos 7 horas - Gmt_m7 - Etc/GMT+7</li>
                        <li>(GMT-04:00) Horário de Greenwich menos 4 horas - Gmt_m4 - Etc/GMT+4</li>
                        <li>(GMT) Casablanca - África_Casablanca - África/Casablanca</li>
                        <li>(GMT+05:30) Calcutá, Chennai, Mumbai, Nova Délhi - Ásia_Calcutá - Ásia/Calcutá</li>
                        <li>(GMT-11:00) Horário de Greenwich menos 11 horas - Gmt_m11 - Etc/GMT+11</li>
                        <li>(GMT-09:00) Horário de Greenwich menos 9 horas - Gmt_m9 - Etc/GMT+9</li>
                        <li>(GMT-03:30) Terra Nova - América_St_Johns - América/St_Johns</li>
                        <li>(GMT+03:00) Horário de Greenwich mais 3 horas - Gmt_p3 - Etc/GMT-3</li>
                        <li>(GMT-04:30) Caracas - América_Caracas - América/Caracas</li>
                        <li>(GMT+01:00) Amsterdã, Berlim, Berna, Roma, Estocolmo, Viena - Europa_Berlim - Europa/Berlim</li>
                        <li>(GMT-07:00) Chihuahua, La Paz, Mazatlan - América_Chihuahua - América/Chihuahua</li>
                        <li>(GMT+03:00) Nairóbi - África_Nairóbi - África/Nairóbi</li>
                        <li>(GMT-04:00) Assunção - América_Assunção - América/Assunção</li>
                        <li>(GMT+03:00) Bagdá - Ásia_Bagdá - Ásia/Bagdá</li>
                        <li>(GMT-10:00) Horário de Greenwich menos 10 horas - Gmt_m10 - Etc/GMT+10</li>
                        <li>(GMT-03:00) Groenlândia - América_Godthab - América/Godthab</li>
                        <li>(GMT+02:00) Damas - Ásia_Damasco - Ásia/Damasco</li>
                        <li>(GMT-11:00) Samoa - Samoa do Pacífico - Pacífico/Samoa</li>
                        <li>(GMT-05:00) Bogotá, Lima, Quito - América_Bogota - América/Bogotá</li>
                        <li>(GMT+01:00) Bruxelas, Copenhague, Madri, Paris - Europa_Paris - Europa/Paris</li>
                        <li>(GMT+08:00) Pequim, Chongqing, Hong Kong, Urumqi - Ásia_Xangai - Ásia/Xangai</li>
                        <li>(GMT+12:00) Fidji - Pacífico_Fiji - Pacífico/Fiji</li>
                        <li>(GMT+02:00) Atenas, Istambul, Minsk - Europa_Atenas - Europa/Atenas</li>
                        <li>(GMT+04:00) Tbilissi - Ásia_Tbilisi - Ásia/Tbilisi</li>
                        <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
                        <li>(GMT+05:45) Catmandu - Ásia_Katmandu - Ásia/Katmandu</li>
                        <li>(GMT-05:00) Indiana (Leste) - América_Indianápolis - América/Indianápolis</li>
                        <li>(GMT-01:00) Ilhas de Cabo Verde - Atlântico_Cabo_Verde - Atlântico/Cabo_Verde</li>
                        <li>(GMT+04:00) Port Louis - Índico_Maurício - Índico/Maurício</li>
                        <li>(GMT+08:00) Taipei - Ásia_Taipei - Ásia/Taipei</li>
                        <li>(GMT+06:30) Rangum - Ásia_Rangum - Ásia/Rangum</li>
                        <li>(GMT+11:00) Magadan, Ilhas Salomão, Nova Caledônia - Pacífico_Guadalcanal - Pacífico/Guadalcanal</li>
                        <li>(GMT+02:00) Cairo - África_Cairo - África/Cairo</li>
                        <li>(GMT+05:00) Ecaterimburgo - Ásia_Ecaterimburgo - Ásia/Ecaterimburgo</li>
                        <li>(GMT+08:00) Irkoutsk - Ásia_Irkutsk - Ásia/Irkutsk</li>
                        <li>(GMT+10:00) Guam, Porto Moresby - Pacífico_Guam - Pacífico/Guam</li>
                        <li>(GMT-04:00) Horário Padrão do Atlântico (Canadá) - América_Halifax - América/Halifax</li>
                        <li>(GMT) Horário de Greenwich - GMT - GMT</li>
                        <li>Padrão - nenhum - nenhum</li>
                        <li>(GMT-04:00) La Paz - América_La_Paz - América/La_Paz</li>
                        <li>(GMT-06:00) Guadalajara, México, Monterrey - América_Cidade_do_México - América/Cidade_do_México</li>
                        <li>(GMT+09:30) Darwin - Austrália_Darwin - Austrália/Darwin</li>
                        <li>(GMT-05:00) Leste (Estados Unidos e Canadá) - América_Nova_York - América/Nova_York</li>
                        <li>(GMT-05:00) Horário de Greenwich menos 5 horas - Gmt_m5 - Etc/GMT+5</li>
                        <li>(GMT+05:00) Islamabad, Karachi, Tachkent - Ásia_Karachi - Ásia/Karachi</li>
                        <li>(GMT+03:00) Koweït, Riade - Ásia_Riade - Ásia/Riade</li>
                        <li>(GMT-08:00) Horário de Greenwich menos 8 horas - Gmt_m8 - Etc/GMT+8</li>
                        <li>(GMT-01:00) Açores - Atlântico_Açores - Atlântico/Açores</li>
                        <li>(GMT+07:00) Bangkok, Hanói, Jacarta - Ásia_Bangkok - Ásia/Bangkok</li>
                        <li>(GMT) Monróvia - África_Monróvia - África/Monróvia</li>
                        <li>(GMT-09:00) Alasca - América_Anchorage - América/Anchorage</li>
                        <li>(GMT+01:00) Belgrado, Bratislava, Budapeste, Liubliana, Praga - Europa_Belgrado - Europa/Belgrado</li>
                        <li>(GMT) Reiquiavique - Atlântico_Reiquiavique - Atlântico/Reiquiavique</li>
                        <li>(GMT+02:00) Bucareste - Europa_Bucareste - Europa/Bucareste</li>
                        <li>(GMT+05:00) Horário de Greenwich mais 5 horas - Gmt_p5 - Etc/GMT-5</li>
                        <li>(GMT+04:00) Horário de Greenwich mais 4 horas - Gmt_p4 - Etc/GMT-4</li>
                        <li>(GMT+07:00) Horário de Greenwich mais 7 horas - Gmt_p7 - Etc/GMT-7</li>
                        <li>(GMT+06:00) Horário de Greenwich mais 6 horas - Gmt_p6 - Etc/GMT-6</li>
                        <li>(GMT+01:00) Horário de Greenwich mais 1 hora - Gmt_p1 - Etc/GMT-1</li>
                        <li>(GMT-08:00) Pacífico (Estados Unidos e Canadá) - América_Los_Angeles - América/Los_Angeles</li>
                        <li>(GMT+02:00) Horário de Greenwich mais 2 horas - Gmt_p2 - Etc/GMT-2</li>
                        <li>(GMT+07:00) Krasnoïarsk - Ásia_Krasnoyarsk - Ásia/Krasnoyarsk</li>
                        <li>(GMT+09:00) Horário de Greenwich mais 9 horas - Gmt_p9 - Etc/GMT-9</li>
                        <li>(GMT+08:00) Horário de Greenwich mais 8 horas - Gmt_p8 - Etc/GMT-8</li>
                        <li>(GMT+10:00) Hobart - Austrália_Hobart - Austrália/Hobart</li>
                        <li>(GMT+13:00) Nuku'alofa - Pacífico_Tongatapu - Pacífico/Tongatapu</li>
                        <li>(GMT-06:00) América Central - América_Regina - América/Regina</li>
                        <li>(GMT-03:00) Buenos Aires, Caiena, Fortaleza - América_Buenos_Aires - América/Buenos_Aires</li>
                        <li>(GMT-07:00) Montanhas Rochosas (Estados Unidos e Canadá) - América_Denver - América/Denver</li>
                        <li>(GMT+01:00) África Central - Oeste - África_Luanda - África/Luanda</li>
                        <li>(GMT+02:00) Helsinque, Kiev, Riga, Sófia, Tallinn, Vilnius - Europa_Helsinque - Europa/Helsinque</li>
                        <li>(GMT) Horário de Greenwich: Dublin, Edimburgo, Lisboa, Londres - Europa_Londres - Europa/Londres</li>
                        <li>(GMT-07:00) Arizona - América_Phoenix - América/Phoenix</li>
                        <li>(GMT+02:00) Beirute - Ásia_Beirute - Ásia/Beirute</li>
                        <li>(GMT+04:30) Cabul - Ásia_Cabul - Ásia/Cabul</li>
                        <li>(GMT-06:00) Centro (Estados Unidos e Canadá) - América_Chicago - América/Chicago</li>
                        <li>(GMT+11:00) Horário de Greenwich mais 11 horas - Gmt_p11 - Etc/GMT-11</li>
                        <li>(GMT+10:00) Horário de Greenwich mais 10 horas - Gmt_p10 - Etc/GMT-10</li>
                        <li>(GMT+13:00) Horário de Greenwich mais 13 horas - Gmt_p13 - Etc/GMT-13</li>
                        <li>(GMT+12:00) Horário de Greenwich mais 12 horas - Gmt_p12 - Etc/GMT-12</li>
                        <li>(GMT-04:00) Santiago - América_Santiago - América/Santiago</li>
                        <li>(GMT-03:00) Montevidéu - América_Montevidéu - América/Montevidéu</li>
                        <li>(GMT-04:00) Cuiaba - América_Cuiaba - América/Cuiaba</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>título</td>
                  <td>Perfil</td>
                  <td>sequência de caracteres (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>rastreamento</td>
                  <td>Logs de rastreamento</td>
                  <td>coleção </td>
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
<td>inteiro</td>
</tr>
<tr>
<td>nextUnitsValue</td>
<td>inteiro</td>
</tr>
<tr>
<td>endDay</td>
<td>date</td>
</tr>
<tr>
<td>precision</td>
<td>enumeração</td>
</tr>
<tr>
<td>relativeValue</td>
<td>sequência de caracteres</td>
</tr>
<tr>
<td>mês</td>
<td>date</td>
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
<td>date</td>
</tr>
<tr>
<td>tipo</td>
<td>enumeração</td>
</tr>
<tr>
<td>dia</td>
<td>date</td>
</tr>
</table>

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

Por chaves (byKeysProfile)

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

Por nome ou email (byText)

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

Por público estático (byStaticAudience)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>público-alvo</td>
<td>Link </td>
</tr>
</table>

Clicado (hasClickedDelivery)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>entrega</td>
<td>Link </td>
</tr>
</table>

Aberto (hasOpenedDelivery)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>entrega</td>
<td>Link </td>
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
<td>Link </td>
</tr>
</table>

Recebido (hasReceivedDelivery)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>entrega</td>
<td>Link </td>
</tr>
</table>

Assinantes (assinantes)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>serviço</td>
<td>Link </td>
</tr>
</table>
