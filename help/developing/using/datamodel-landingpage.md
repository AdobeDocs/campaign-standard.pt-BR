---
title: Página de aterrissagem do modelo de dados
description: Saiba mais sobre o modelo de dados
audience: designing
content-type: reference
topic-tags: editing-sms-and-push-content
context-tags: delivery,smsContent,back
feature: Data Model
role: Developer
level: Experienced
exl-id: bd12a214-5998-4fb9-9f54-0c886067b58b
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '1817'
ht-degree: 7%

---

# landingPage (nms:landingPage)

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
         <td>additionalData</td>
         <td>Dados adicionais</td>
         <td>coleção </td>
         <td> </td>
      </tr>
      <tr>
         <td>additionalLanguages</td>
         <td>Outros idiomas</td>
         <td>Item </td>
         <td> </td>
      </tr>
      <tr>
         <td>allowNonIdentifiedTarget</td>
         <td>Autorizar visitantes não identificados</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>identidade visual (brandingBase)</td>
         <td>Marca</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>builtIn</td>
         <td>Objeto de aplicativo integrado</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>cache</td>
         <td>Cache</td>
         <td>sequência de caracteres </td>
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
         <td>Log "Página de aterrissagem fechada"</td>
         <td>sequência de caracteres </td>
         <td> </td>
      </tr>
      <tr>
         <td>contextResourceType</td>
         <td>ContextResourceType</td>
         <td>sequência de caracteres </td>
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
         <td>sequência de caracteres (64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>defaultLanguage</td>
         <td>Idioma padrão</td>
         <td>enumeração (cadeia de caracteres) (255)</td>
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
               <li>Holandês (Holanda) - nl_NL - nl_NL</li>
               <li>Árabe - ar - ar</li>
               <li>Inglês (Estados Unidos) - en_US - en_US</li>
               <li>Irlandês - ga - ga</li>
               <li>Tcheco - cs - cs</li>
               <li>Estoniano - et - et</li>
               <li>Indonésio - ID - ID</li>
               <li>Espanhol - es - es</li>
               <li>Russo - ru - ru</li>
               <li>Holandês - nl - nl</li>
               <li>Valão - wa - wa</li>
               <li>Português - pt - pt</li>
               <li>Francês (Bélgica) - fr_BE - fr_BE</li>
               <li>Letão - lv - lv</li>
               <li>Lituano - lt - lt</li>
               <li>Tailandês - th - th</li>
               <li>Inglês (Reino Unido) - en_GB - en_GB</li>
               <li>Francês - fr - fr</li>
               <li>Português (Brasil) - pt_BR - pt_BR</li>
               <li>Alemão - de - de</li>
               <li>Dinamarquês - da - da</li>
               <li>Finlandês - fi - fi</li>
               <li>Húngaro - hu - hu</li>
               <li>Sueco (Finlândia) - sv_FI - sv_FI</li>
               <li>Japonês - ja - ja</li>
               <li>Hebraico - ele - ele</li>
               <li>Coreano - ko - ko</li>
               <li>Sueco - sv - sv</li>
               <li>Suécia (Sueco) - sv_SE - sv_SE</li>
               <li>Eslovaco - sk - sk</li>
               <li>Maltês - mt - mt</li>
               <li>Italiano (Suíça) - it_CH - it_CH</li>
               <li>Polonês - pl - pl</li>
               <li>Esloveno - sl - sl</li>
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
         <td>sequência de caracteres (512)</td>
         <td> </td>
      </tr>
      <tr>
         <td>designLanguage</td>
         <td>Idioma de design</td>
         <td>enumeração (cadeia de caracteres) (255)</td>
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
               <li>Holandês (Holanda) - nl_NL - nl_NL</li>
               <li>Árabe - ar - ar</li>
               <li>Inglês (Estados Unidos) - en_US - en_US</li>
               <li>Irlandês - ga - ga</li>
               <li>Tcheco - cs - cs</li>
               <li>Estoniano - et - et</li>
               <li>Indonésio - ID - ID</li>
               <li>Espanhol - es - es</li>
               <li>Russo - ru - ru</li>
               <li>Holandês - nl - nl</li>
               <li>Valão - wa - wa</li>
               <li>Português - pt - pt</li>
               <li>Francês (Bélgica) - fr_BE - fr_BE</li>
               <li>Letão - lv - lv</li>
               <li>Lituano - lt - lt</li>
               <li>Tailandês - th - th</li>
               <li>Inglês (Reino Unido) - en_GB - en_GB</li>
               <li>Francês - fr - fr</li>
               <li>Português (Brasil) - pt_BR - pt_BR</li>
               <li>Alemão - de - de</li>
               <li>Dinamarquês - da - da</li>
               <li>Finlandês - fi - fi</li>
               <li>Húngaro - hu - hu</li>
               <li>Sueco (Finlândia) - sv_FI - sv_FI</li>
               <li>Japonês - ja - ja</li>
               <li>Hebraico - ele - ele</li>
               <li>Coreano - ko - ko</li>
               <li>Sueco - sv - sv</li>
               <li>Suécia (Sueco) - sv_SE - sv_SE</li>
               <li>Eslovaco - sk - sk</li>
               <li>Maltês - mt - mt</li>
               <li>Italiano (Suíça) - it_CH - it_CH</li>
               <li>Polonês - pl - pl</li>
               <li>Esloveno - sl - sl</li>
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
         <td>fim</td>
         <td>Data de expiração</td>
         <td>data </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorContextResourceType</td>
         <td>ErrorContextResourceType</td>
         <td>sequência de caracteres </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorPage</td>
         <td>Página de erro</td>
         <td>Item </td>
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
         <td>inativeUrlRedirection</td>
         <td>URL de redirecionamento</td>
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
         <td>Modelo</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>tarefa</td>
         <td>Processo</td>
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
         <td>rótulo</td>
         <td>Rótulo</td>
         <td>sequência de caracteres (128)</td>
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
         <td>Carregando chave</td>
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
         <td>Status da execução</td>
         <td>enumeração (cadeia de caracteres) (255)</td>
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
         <td>sequência de caracteres (64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>orgUnit (orgUnitBase)</td>
         <td>Entidade organizacional</td>
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
         <td>programa (programBase)</td>
         <td>Programa</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicUrl</td>
         <td>URL público</td>
         <td>sequência de caracteres </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicationDate</td>
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
         <td>Atualizar estratégia</td>
         <td>enumeração (byte) </td>
         <td>
            <ul>
               <li>Atualizar - updateTarget - 1</li>
               <li>Não autorizado - não autorizado - 0</li>
               <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>serviço (serviceBase)</td>
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
               <li>Blacklist - blackList - 3</li>
               <li>Nenhuma ação específica - nenhuma - 0</li>
               <li>Unsubscription - unsubscription - 2</li>
               <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
               <li>Assinatura - assinatura - 1</li>
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
         <td>estado</td>
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
         <td>sequência de caracteres (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>modelo (landingPage)</td>
         <td>Modelo da landing page</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>testUrl</td>
         <td>Testar URL</td>
         <td>sequência de caracteres </td>
         <td> </td>
      </tr>
      <tr>
         <td>miniatura</td>
         <td>Miniatura</td>
         <td>sequência de caracteres (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>fuso horário</td>
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
               <li>Fuso horário do servidor - _server_ - _server_</li>
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
               <li>Padrão - _inherit_ - _inherit_</li>
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
               <li>Fuso horário do banco de dados - _wdbc_ - _wdbc_</li>
               <li>(GMT+06:30) Rangum - Ásia_Rangum - Ásia/Rangum</li>
               <li>(GMT+11:00) Magadan, Ilhas Salomão, Nova Caledônia - Pacífico_Guadalcanal - Pacífico/Guadalcanal</li>
               <li>(GMT+02:00) Cairo - África_Cairo - África/Cairo</li>
               <li>(GMT+05:00) Ecaterimburgo - Ásia_Ecaterimburgo - Ásia/Ecaterimburgo</li>
               <li>(GMT+08:00) Irkoutsk - Ásia_Irkutsk - Ásia/Irkutsk</li>
               <li>(GMT+10:00) Guam, Porto Moresby - Pacífico_Guam - Pacífico/Guam</li>
               <li>(GMT-04:00) Horário Padrão do Atlântico (Canadá) - América_Halifax - América/Halifax</li>
               <li>(GMT) Horário de Greenwich - GMT - GMT</li>
               <li>(GMT-04:00) La Paz - América_La_Paz - América/La_Paz</li>
               <li>Fuso horário do operador - _login_ - _login_</li>
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
         <td>Página de destino</td>
         <td>sequência de caracteres (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingEnabled</td>
         <td>Registrar respostas</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingUrlName</td>
         <td>Nome do URL de rastreamento</td>
         <td>sequência de caracteres </td>
         <td> </td>
      </tr>
      <tr>
         <td>tipo</td>
         <td>Tipo</td>
         <td>enumeração (byte) </td>
         <td>
            <ul>
               <li>Genérico - genérico - 0</li>
               <li>Cancelar assinatura de um serviço - cancelar assinatura - 3</li>
               <li>Lista negra - blacklist - 4</li>
               <li>VALOR INVÁLIDO - __Valor_Inválido__ - __Valor_Inválido__</li>
               <li>Aquisição - aquisição - 1</li>
               <li>Assinatura de um serviço - assinatura - 2</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>uuid</td>
         <td>ID de segurança</td>
         <td>sequência de caracteres </td>
         <td> </td>
      </tr>
      <tr>
         <td>webTrackingEnabled</td>
         <td>Habilitar rastreamento web</td>
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
    <td>estado</td>
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
    <td>sequência de caracteres</td>
    </tr>
</table>

Por status (por estado)

<table>
    <tr>
    <th>Nome</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>estado</td>
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
<td>sequência de caracteres</td>
</tr>
</table>

Incluir páginas de aterrissagem avançadas (com Avançado)

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

Incluir deliveries contínuos de uma lista heterogênea (com Continuous)

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

Presente durante determinado período (por calendário)

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

Publicado durante determinado período (byPlanning)

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
