---
title: 'Lista de componentes '
description: Encontre aqui a lista de todos os componentes disponíveis em Relatórios dinâmicos, bem como suas definições.
page-status-flag: never-activated
uuid: a2403806-8df4-4bb1-bac2-2689dc584ae0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: about-reporting
discoiquuid: 17cf126a-7ce1-4e11-bb5e-2bdce01cfded
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b1fb4a0dc0f7881e24e10f8ac171feab2ac8cba
workflow-type: tm+mt
source-wordcount: '1274'
ht-degree: 2%

---


# Lista de componentes {#list-of-components}

Para saber mais sobre a compatibilidade entre dimensões e métricas, consulte esta [tabela](/help/reporting/using/assets/dynamic_report_compatibility.pdf). Se dois componentes não forem compatíveis, a célula exibirá o valor **Nenhum**.

![](assets/dynamic_report_compatibility.png)

## Dimension {#dimensions}

A tabela abaixo fornece a lista das dimensões usadas nos relatórios e suas definições.

<table> 
 <thead> 
  <tr> 
   <th> Dimensão<br /> </th> 
   <th> Definição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Navegador<br /> </td> 
   <td> Navegador no qual a mensagem foi aberta ou clicada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Campanha<br /> </td> 
   <td> Etiqueta e ID da sua campanha.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cidade<br /> </td> 
   <td> Cidade registrada no perfil do recipient.<br /> </td> 
  </tr> 
  <tr> 
   <td> País/região<br /> </td> 
   <td> País registrado no perfil recipient.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery<br /> </td> 
   <td> Rótulo e ID do delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dispositivo<br /> </td> 
   <td> Dispositivo a partir do qual a notificação por email/SMS/push foi aberta/visualizada/clicada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Motivo da falha<br /> </td> 
   <td> Tipos de erros que causaram saltos para cada delivery, por exemplo, usuário desconhecido, domínio inválido ou caixa de correio cheia.<br /> </td> 
  </tr> 
  <tr> 
   <td> Sexo<br /> </td> 
   <td> Gênero do recipient, como masculino ou feminino. Se o campo gênero estiver vazio no perfil, o valor será nenhum.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ações de mensagens no aplicativo<br /> </td> 
   <td> Ações na mensagem no aplicativo fornecida, por exemplo, ações no botão 1 ou 2 ou demissões.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tipo de mensagem<br /> </td> 
   <td> Canal usado para o delivery, como email, SMS, notificação por push ou no aplicativo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nome do aplicativo móvel<br /> </td> 
   <td> Nome do aplicativo móvel<br /> </td> 
  </tr> 
  <tr> 
   <td> Platform<br /> </td> 
   <td> Plataforma do dispositivo a partir do qual a mensagem foi aberta/visualizada/clicada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Perfil<br /> </td> 
   <td> Reagrupa campos predefinidos e perfis personalizados criados durante a extensão do recurso do perfil, para obter mais informações, consulte esta <a href="../../developing/using/key-steps-to-add-a-resource.md">página</a> ou este <a href="../../reporting/using/creating-a-custom-profile-dimension.md">exemplo</a>.<br /> Observe que os dados para essa dimensão são recuperados assim que o recurso personalizado vinculado ao campo do perfil é publicado.<br /> </td> 
  </tr> 
  <tr> 
   <td> Plataforma push<br /> </td> 
   <td> Plataforma do dispositivo a partir do qual a notificação por push foi aberta, como iOS ou Android.<br /> </td> 
  </tr> 
  <tr> 
   <td> domínio do recipient<br /> </td> 
   <td> Domínio usado para abrir o email.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery recorrente<br /> </td> 
   <td> Rótulo e ID do delivery recorrente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Domínio do remetente<br /> </td> 
   <td> Domínio usado para enviar o email.<br /> </td> 
  </tr> 
  <tr> 
   <td> IP do remetente<br /> </td> 
   <td> IP usado para enviar o email.<br /> </td> 
  </tr> 
  <tr> 
   <td> Estado<br /> </td> 
   <td> Estado registrado no perfil.<br /> </td> 
  </tr> 
  <tr> 
   <td> URL de rastreamento<br /> </td> 
   <td> URL clicado pelo usuário na mensagem.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rastreamento da categoria de URL<br /> </td> 
   <td> Categoria atribuída ao URL de rastreamento.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rastreamento do rótulo do URL<br /> </td> 
   <td> Rótulo fornecido ao URL, como mirror page, entre em contato conosco ou abra.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery transacional<br /> </td> 
   <td> Rótulo e ID do delivery transacional.<br /> </td> 
  </tr> 
  <tr> 
   <td> Variante<br /> </td> 
   <td> Variante do email no caso de teste A/B.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Métricas {#metrics}

As tabelas abaixo fornecem a lista das métricas usadas nos relatórios e suas definições, dependendo do tipo de delivery.

### Métricas de email e SMS {#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Métrica<br /> </th> 
   <th> Definição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Na lista de bloqueios<br /> </td> 
   <td> Número de recipient que declararam um email como spam ou lixo eletrônico.<br /> </td> 
  </tr> 
  <tr> 
   <td> lista de bloqueios taxa de<br /> </td> 
   <td> Porcentagem de delivery marcados na lista de bloqueios.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeições + Erros<br /> </td> 
   <td> Total de erros acumulados durante o processamento de retorno automático e delivery em relação ao número total de mensagens enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Salto + Taxa de erro<br /> </td> 
   <td> Porcentagem de emails que retornaram em comparação ao email enviado.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clique em<br /> </td> 
   <td> Número de vezes que um conteúdo foi clicado em um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cliques<br /> </td> 
   <td> Porcentagem de cliques em um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregue<br /> </td> 
   <td> Número de mensagens enviadas com êxito, em relação ao número total de mensagens enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa entregue<br /> </td> 
   <td> Porcentagem de mensagens enviadas com êxito.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeição forçada<br /> </td> 
   <td> O número total de erros permanentes, como um endereço de email incorreto.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de rejeição em disco<br /> </td> 
   <td> Porcentagem de delivery que falharam devido a erros permanentes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mirror page<br /> </td> 
   <td> Número de recipient que clicaram no link do mirror page.<br /> </td> 
  </tr> 
  <tr> 
   <td> taxa de mirror page<br /> </td> 
   <td> Porcentagem de cliques no link do mirror page em comparação ao total de mensagens do delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques na oferta<br /> </td> 
   <td> Número de vezes que uma oferta foi clicada em um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cliques de oferta<br /> </td> 
   <td> Porcentagem de cliques em uma oferta.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abertura<br /> </td> 
   <td> Número de vezes que uma mensagem foi aberta em um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa aberta<br /> </td> 
   <td> Porcentagem de mensagens abertas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Processado/enviado<br /> </td> 
   <td> Número total de envios para o delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarantine<br /> </td> 
   <td> Número de mensagens que retornou e resultaram na quarentena do endereço.<br /> </td> 
  </tr> 
  <tr> 
   <td> taxa de quarentena<br /> </td> 
   <td> Porcentagem de quarentenas em comparação a mensagens enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeitada<br /> </td> 
   <td> Número de mensagens classificadas como spam pelos servidores SMTP.<br /> </td> 
  </tr> 
  <tr> 
   <td> taxa rejeitada<br /> </td> 
   <td> Porcentagem de mensagens marcadas como rejeitadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeição suave<br /> </td> 
   <td> O número total de erros temporários, como uma caixa de entrada completa.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de rejeição suave<br /> </td> 
   <td> Porcentagem de delivery que falharam devido a um motivo temporário.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques únicos<br /> </td> 
   <td> Número de recipient que clicaram em um conteúdo em um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aberturas exclusivas<br /> </td> 
   <td> Número de recipient que abriram o delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cancelamento de inscrição<br /> </td> 
   <td> Porcentagem de unsubscription por recipient em relação às mensagens entregues.<br /> </td> 
  </tr> 
  <tr> 
   <td> Inscrito<br /> </td> 
   <td> Número de cliques no link unsubscription.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Métricas de notificação por push {#push-notification-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Métrica<br /> </th> 
   <th> Definição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Rejeições + Erros<br /> </td> 
   <td> Total de erros acumulados durante o delivery em relação ao número total de mensagens enviadas, por exemplo, erros do MCPNS ou do provedor.<br /> </td> 
  </tr> 
  <tr> 
   <td> Salto + Taxa de erro<br /> </td> 
   <td> Porcentagem de notificações por push que pularam em comparação com as notificações por push enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clique em<br /> </td> 
   <td> Número de vezes que uma notificação por push foi entregue ao dispositivo e clicada pelo usuário. O usuário desejou visualização na notificação, que será movida para o rastreamento Push Open ou ignorará.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cliques<br /> </td> 
   <td> Porcentagem de usuários que interagiram com a notificação por push.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregue<br /> </td> 
   <td> Número de notificações por push enviadas com êxito, em relação ao número total de notificações por push enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa entregue<br /> </td> 
   <td> Porcentagem de notificações por push enviadas com êxito.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões<br /> </td> 
   <td> Número de vezes que uma notificação por push foi entregue ao dispositivo e deixada inalterada no centro de notificações. Na maioria dos casos, o número de impressões deve ser semelhante ao número fornecido. Isso garante que o dispositivo recebeu a mensagem e repassou essas informações para o servidor.<br /> </td> 
  </tr> 
  <tr> 
   <td> Processado/enviado<br /> </td> 
   <td> Número total de notificações por push enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abertura<br /> </td> 
   <td> O número total de notificações por push entregues ao dispositivo e clicadas pelos usuários, abrindo o aplicativo. Isso é semelhante ao clique de push, exceto que a opção Abrir push não será acionada se a notificação for descartada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa aberta<br /> </td> 
   <td> Porcentagem de notificações por push abertas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques únicos<br /> </td> 
   <td> Número de vezes que um usuário único interage com a notificação por push, por exemplo, clica na notificação ou no botão.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões exclusivas<br /> </td> 
   <td> Número de impressões por recipient.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aberturas únicas<br /> </td> 
   <td> Número de recipient que abriram o delivery.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Métricas no aplicativo {#in-app-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Métrica<br /> </th> 
   <th> Definição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Entregue<br /> </td> 
   <td> Número total de mensagens no aplicativo entregues ao dispositivo pelo provedor de serviço.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões<br /> </td> 
   <td> Total de mensagens no aplicativo visualizadas por recipient, dependendo se o critério de disparo foi atendido.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques no aplicativo <br /> </td> 
   <td> Número total de recipient que clicaram no Botão 1 ou no Botão 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cliques no aplicativo<br /> </td> 
   <td> A porcentagem de usuários que clicaram no Botão 1 ou no Botão 2 em comparação aos usuários que viram a mensagem.<br /> </td> 
  </tr> 
  <tr> 
   <td> Demissão no aplicativo<br /> </td> 
   <td> O número total de mensagens que os recipient rejeitaram ao clicar no botão Fechar ou fechar automaticamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de demissão no aplicativo<br /> </td> 
   <td> Porcentagem de mensagens no aplicativo que os recipient rejeitaram.<br /> </td> 
  </tr> 
  <tr> 
   <td> Processado/enviado<br /> </td> 
   <td> O número total de mensagens no aplicativo enviadas da Adobe Campaign como parte do processo de envio do delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões exclusivas<br /> </td> 
   <td> Número de impressões por um recipient exclusivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques únicos no aplicativo<br /> </td> 
   <td> Número de vezes que os recipient clicaram no Botão 1 ou no Botão 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Despedimentos únicos no aplicativo<br /> </td> 
   <td> Número de vezes que os recipient rejeitaram uma mensagem no aplicativo.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Segmentos {#segments}

>[!NOTE]
>
>Por padrão, o **[!UICONTROL Exclude proof]** segmento já está selecionado para filtrar seus relatórios, mas pode ser alterado se necessário.

A tabela abaixo fornece a lista dos segmentos usados nos relatórios e suas definições.

<table> 
 <thead> 
  <tr> 
   <th> Segmento<br /> </th> 
   <th> Definição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Idade: Boomers 1<br /> </td> 
   <td> Recipient nascidos de 1946 a 1954.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Boomers 2<br /> </td> 
   <td> Recipient nascidos de 1955 a 1965.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: De 18 para 25<br /> </td> 
   <td> Recipient de 18 a 25 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: De 26 para 30<br /> </td> 
   <td> Recipient de 26 a 30 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: De 31 para 40<br /> </td> 
   <td> Recipient de 31 a 40 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: De 41 para 50<br /> </td> 
   <td> Recipient de 41 a 50 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Geração X<br /> </td> 
   <td> Recipient nascidos de 1966 a 1976.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Geração Y (geração)<br /> </td> 
   <td> Recipient nascidos de 1977 a 1994.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Geração Z<br /> </td> 
   <td> Recipient nascidos de 1995 a hoje.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Maior que 50<br /> </td> 
   <td> Recipient com mais de 50 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Menos de 25<br /> </td> 
   <td> Recipient com menos de 25 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Menos de 30<br /> </td> 
   <td> Recipient com menos de 30 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Menos de 40<br /> </td> 
   <td> Recipient com menos de 40 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Menos de 50<br /> </td> 
   <td> Recipient com menos de 50 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Geração silenciosa<br /> </td> 
   <td> Recipient nascidos em 1945 ou antes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Todas as visitas<br /> </td> 
   <td> Cada recipient<br /> </td> 
  </tr> 
    <tr> 
   <td> Excluir prova<br /> </td> 
   <td> Excluir provas de seus relatórios<br /> </td> 
  </tr> 
 </tbody> 
</table>

