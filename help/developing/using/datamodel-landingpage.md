---
solution: Campaign Standard
product: campaign
title: DataModel
description: Saiba mais sobre o datamodel
audience: designing
content-type: reference
topic-tags: editing-sms-and-push-content
context-tags: delivery,smsContent,back
feature: Modelo de dados
role: Desenvolvedor
level: Experienciado
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1731'
ht-degree: 2%

---


# landingPage (nms:landingPage)

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
         <td>additionalData</td>
         <td>Dados adicionais</td>
         <td>coleção </td>
         <td> </td>
      </tr>
      <tr>
         <td>additionalLanguages</td>
         <td>Outras línguas</td>
         <td>item </td>
         <td> </td>
      </tr>
      <tr>
         <td>allowNonIdentifiedTarget</td>
         <td>Autorizar visitantes não identificados</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>marca (brandingBase)</td>
         <td>Marca</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>build</td>
         <td>Objeto de aplicativo integrado</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>cache</td>
         <td>Cache</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>campaign (campaignBase)</td>
         <td>Campanha</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>closedLog</td>
         <td>Registro de "Landing page closed"</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>contextResourceType</td>
         <td>ContextResourceType</td>
         <td>string </td>
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
         <td>cryptKey</td>
         <td>Chave de criptografia AES</td>
         <td>string (64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>defaultLanguage</td>
         <td>Idioma padrão</td>
         <td>enumeration (string) (255)</td>
         <td>
            <ul>
               <li>Grego - el - el</li>
               <li>Inglês - en - en</li>
               <li>Chinês - zh - zh</li>
               <li>Francês (França) - fr_FR - fr_FR</li>
               <li>Vietnamita - vi - vi</li>
               <li>Português (Portugal) - pt_PT - pt_PT</li>
               <li>Italiano (Itália) - it_IT - it_IT</li>
               <li>Italiano - it - it</li>
               <li>Holandês (Bélgica) - nl_BE - nl_BE</li>
               <li>Norueguês (Noruega) - no_NO - no_NO</li>
               <li>Holandês (Países Baixos) - nl_NL - nl_NL</li>
               <li>Árabe - ar - ar</li>
               <li>Inglês (Estados Unidos) - en_US - en_US</li>
               <li>Irlandês - ga</li>
               <li>Tcheco - cs - cs</li>
               <li>Estoniano - et - et</li>
               <li>Indonésio - id - id</li>
               <li>Espanhol - ES - es</li>
               <li>Russo - RU - RU</li>
               <li>Holandês - nl - nl</li>
               <li>Walloon - wa - wa</li>
               <li>Português - pt - pt</li>
               <li>Francês (Bélgica) - fr_BE - fr_BE</li>
               <li>Letão - lv - lv</li>
               <li>Lituano - lt - lt</li>
               <li>Tailandês - th</li>
               <li>Inglês (Reino Unido) - en_GB - en_GB</li>
               <li>Francês - fr - fr</li>
               <li>Português (Brasil) - pt_BR - pt_BR</li>
               <li>Alemão - de - de</li>
               <li>Dinamarquês - da - da</li>
               <li>Finlandês - fi</li>
               <li>Húngaro - Hu - Hu</li>
               <li>Sueco (Finlândia) - sv_FI - sv_FI</li>
               <li>Japonês - ja - ja</li>
               <li>Hebraico - ele -</li>
               <li>Coreano - ko - ko</li>
               <li>Sueco - sv - sv</li>
               <li>Suécia (Sueco) - sv_SE - sv_SE</li>
               <li>Eslovaco - sk - sk</li>
               <li>Maltês - mt - mt</li>
               <li>Italiano (Suíça) - it_CH - it_CH</li>
               <li>Polonês - pl - pl</li>
               <li>Esloveno - SL</li>
               <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>defaultOrigin (delivery)</td>
         <td>Fonte de tráfego</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>desc</td>
         <td>Descrição</td>
         <td>string (512)</td>
         <td> </td>
      </tr>
      <tr>
         <td>designLanguage</td>
         <td>Idioma de design</td>
         <td>enumeration (string) (255)</td>
         <td>
            <ul>
               <li>Grego - el - el</li>
               <li>Inglês - en - en</li>
               <li>Chinês - zh - zh</li>
               <li>Francês (França) - fr_FR - fr_FR</li>
               <li>Vietnamita - vi - vi</li>
               <li>Português (Portugal) - pt_PT - pt_PT</li>
               <li>Italiano (Itália) - it_IT - it_IT</li>
               <li>Italiano - it - it</li>
               <li>Holandês (Bélgica) - nl_BE - nl_BE</li>
               <li>Norueguês (Noruega) - no_NO - no_NO</li>
               <li>Holandês (Países Baixos) - nl_NL - nl_NL</li>
               <li>Árabe - ar - ar</li>
               <li>Inglês (Estados Unidos) - en_US - en_US</li>
               <li>Irlandês - ga</li>
               <li>Tcheco - cs - cs</li>
               <li>Estoniano - et - et</li>
               <li>Indonésio - id - id</li>
               <li>Espanhol - ES - es</li>
               <li>Russo - RU - RU</li>
               <li>Holandês - nl - nl</li>
               <li>Walloon - wa - wa</li>
               <li>Português - pt - pt</li>
               <li>Francês (Bélgica) - fr_BE - fr_BE</li>
               <li>Letão - lv - lv</li>
               <li>Lituano - lt - lt</li>
               <li>Tailandês - th</li>
               <li>Inglês (Reino Unido) - en_GB - en_GB</li>
               <li>Francês - fr - fr</li>
               <li>Português (Brasil) - pt_BR - pt_BR</li>
               <li>Alemão - de - de</li>
               <li>Dinamarquês - da - da</li>
               <li>Finlandês - fi</li>
               <li>Húngaro - Hu - Hu</li>
               <li>Sueco (Finlândia) - sv_FI - sv_FI</li>
               <li>Japonês - ja - ja</li>
               <li>Hebraico - ele -</li>
               <li>Coreano - ko - ko</li>
               <li>Sueco - sv - sv</li>
               <li>Suécia (Sueco) - sv_SE - sv_SE</li>
               <li>Eslovaco - sk - sk</li>
               <li>Maltês - mt - mt</li>
               <li>Italiano (Suíça) - it_CH - it_CH</li>
               <li>Polonês - pl - pl</li>
               <li>Esloveno - SL</li>
               <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>dynamicService</td>
         <td>Serviço dinâmico</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>end</td>
         <td>Data de expiração</td>
         <td>data </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorContextResourceType</td>
         <td>ErrorContextResourceType</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorPage</td>
         <td>Página de erro</td>
         <td>item </td>
         <td> </td>
      </tr>
      <tr>
         <td>geoUnit (geoUnitBase)</td>
         <td>Unidade geográfica</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>htmlPage</td>
         <td>Páginas</td>
         <td>coleção </td>
         <td> </td>
      </tr>
      <tr>
         <td>identificationByUrlParam</td>
         <td>Identificação por parâmetros de URL</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>inativeUrlRedirect</td>
         <td>Redirecionar URL</td>
         <td>string (4096)</td>
         <td> </td>
      </tr>
      <tr>
         <td>isExternal</td>
         <td>É recurso externo</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>isTemplate</td>
         <td>Template</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>trabalho</td>
         <td>Tarefa</td>
         <td>coleção </td>
         <td> </td>
      </tr>
      <tr>
         <td>jobLogs</td>
         <td>Logs</td>
         <td>coleção </td>
         <td> </td>
      </tr>
      <tr>
         <td>label</td>
         <td>Rótulo</td>
         <td>string (128)</td>
         <td> </td>
      </tr>
      <tr>
         <td>lastModified</td>
         <td>Última modificação</td>
         <td>data </td>
         <td> </td>
      </tr>
      <tr>
         <td>loadingFilter (queryFilterBase)</td>
         <td>Chave de carregamento</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>loadingFilterMapping</td>
         <td>Parâmetros da chave de carregamento</td>
         <td>coleção </td>
         <td> </td>
      </tr>
      <tr>
         <td>logicalStatus</td>
         <td>Status de execução</td>
         <td>enumeration (string) (255)</td>
         <td>
            <ul>
               <li>Em andamento - iniciado - iniciado</li>
               <li>Edição - edição - edição</li>
               <li>Concluído - concluído - concluído</li>
               <li>Aviso - aviso - aviso</li>
               <li>Errado - erro - erro</li>
               <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>messageAction</td>
         <td>Iniciar envio de mensagem</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>messageActionDelivery (deliveryMCTemplateBase)</td>
         <td>Mensagem transacional</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>modifiedBy (userBase)</td>
         <td>Modificado por</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>name</td>
         <td>ID</td>
         <td>string (64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>orgUnit (orgUnitBase)</td>
         <td>Unidade organizacional</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>preenchimento prévio</td>
         <td>Pré-carregar dados do visitante</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>program (programBase)</td>
         <td>Programa</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicUrl</td>
         <td>URL público</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>publishDate</td>
         <td>Data de publicação</td>
         <td>data </td>
         <td> </td>
      </tr>
      <tr>
         <td>reconciliationFilter (queryFilterBase)</td>
         <td>Chave de reconciliação</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>reconciliationFilterMapping</td>
         <td>Parâmetros da chave de reconciliação</td>
         <td>coleção </td>
         <td> </td>
      </tr>
      <tr>
         <td>reconciliationUpdateStrategy</td>
         <td>Estratégia de atualização</td>
         <td>enumeração (byte) </td>
         <td>
            <ul>
               <li>Update - updateTarget - 1</li>
               <li>Não autorizado - não autorizado - 0</li>
               <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>service (serviceBase)</td>
         <td>Serviço de assinatura</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>specificAction</td>
         <td>Ação específica</td>
         <td>enumeração (byte) </td>
         <td>
            <ul>
               <li>Lista Negra - Lista Negra - 3</li>
               <li>Nenhuma ação específica - nenhuma - 0</li>
               <li>Unsubscription - unsubscription - 2</li>
               <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
               <li>Subscrição - subscrição - 1</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>start</td>
         <td>Data de implantação</td>
         <td>data </td>
         <td> </td>
      </tr>
      <tr>
         <td>state</td>
         <td>Status</td>
         <td>enumeração (byte) </td>
         <td>
            <ul>
               <li>Edição - editar - 0</li>
               <li>Falha na publicação - falha - 99</li>
               <li>Fechado - fechado - 20</li>
               <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
               <li>Online - aberto - 10</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>targetResource</td>
         <td>Dimensão de direcionamento</td>
         <td>string (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>modelo (landingPage)</td>
         <td>Modelo de página de aterrissagem</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>testUrl</td>
         <td>URL de teste</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>miniatura</td>
         <td>Miniatura</td>
         <td>string (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>fuso horário</td>
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
               <li>Fuso horário do servidor - _server_ - _server_</li>
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
               <li>Padrão - _herdar_ - _herdar_</li>
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
               <li>Fuso horário do banco de dados - _wdbc_ - _wdbc_</li>
               <li>(GMT+06:30) Rangum - Asia_Rangoon - Ásia/Rangum</li>
               <li>(GMT+11:00) Magadan, Ilhas Salomão, Nova Caledónia - Pacific_Guadalcanal - Pacífico/Guadalcanal</li>
               <li>(GMT+02:00) Cairo - África_Cairo - África/Cairo</li>
               <li>(GMT+05:00) Iekaterinburg - Asia_Yekaterinburg - Ásia/Yekaterinburg</li>
               <li>(GMT+08:00) Irkoutsk - Asia_Irkutsk - Ásia/Irkutsk</li>
               <li>(GMT+10:00) Guam, Port Moresby - Pacific_Guam - Pacífico/Guam</li>
               <li>(GMT-04:00) Hora Padrão do Atlântico (Canadá) - América_Halifax - América/Halifax</li>
               <li>(GMT) Hora média de Greenwich - GMT - GMT</li>
               <li>(GMT-04:00) La Paz - América_La_Paz - América/La_Paz</li>
               <li>Fuso horário do operador - _login_ - _login_</li>
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
         <td>Landing page</td>
         <td>string (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingEnabled</td>
         <td>Rastrear respostas</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingUrlName</td>
         <td>Nome do URL de rastreamento</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>type</td>
         <td>Tipo</td>
         <td>enumeração (byte) </td>
         <td>
            <ul>
               <li>Genérico - genérico - 0</li>
               <li>Unsubscription de um serviço - unsubscription - 3</li>
               <li>Lista Negra - Lista Negra - 4</li>
               <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
               <li>Aquisição - aquisição - 1</li>
               <li>Assinatura de um serviço - assinatura - 2</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>uuid</td>
         <td>ID de segurança</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>webTrackingEnabled</td>
         <td>Ativar o rastreamento Web</td>
         <td>booleano </td>
         <td> </td>
      </tr>
   </table>

## Filtros

Por status lógico (byLogicalStatus)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>state</td>
    <td>enumeração</td>
    </tr>
</table>

Por nome ou rótulo (byText)

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

Por status (porEstado)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>state</td>
    <td>enumeração</td>
    </tr>
</table>

Por recurso de direcionamento (byTargetResource)

<table>
<tr>
<th>Nome</th>
<th>Tipo</th>
</tr>
<tr>
<td>targetResource</td>
<td>string</td>
</tr>
</table>

Incluir páginas de aterrissagem avançadas (comAvançado)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>avançado</td>
    <td>booleano</td>
    </tr>
</table>

Incluir deliveries contínuos de uma lista heterogênea (com Contínuo)

<table>
        <tr>
        <th>Nome</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>withContinuous</td>
        <td>booleano</td>
        </tr>
    </table>

Apresentar durante um determinado período (porCalendário)

<table>
        <tr>
        <th>Nome</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>startDate</td>
        <td>data</td>
        </tr>
        <tr>
        <td>endDate</td>
        <td>data</td>
        </tr>
    </table>

Publicado durante um determinado período (peloPlanning)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>data</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>data</td>
    </tr>
</table>
