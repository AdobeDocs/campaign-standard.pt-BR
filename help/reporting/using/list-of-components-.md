---
solution: Campaign Standard
product: campaign
title: 'Lista de componentes '
description: Encontre aqui a lista de todos os componentes disponíveis em     Relatórios dinâmicos, bem como suas definições.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Relatórios
role: Líder
level: Iniciante
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1298'
ht-degree: 3%

---


# Lista de componentes {#list-of-components}

Para saber mais sobre a compatibilidade entre dimensões e métricas, consulte esta [tabela](/help/reporting/using/assets/dynamic_report_compatibility.pdf). Se dois componentes não forem compatíveis, a célula exibirá o valor **None**.

[![imagem](assets/dynamic_report_compatibility.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf?lang=en)

## Dimension {#dimensions}

A tabela abaixo fornece a lista de dimensões usadas nos relatórios e suas definições.

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
   <td> Navegador do qual a mensagem foi aberta ou clicada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Campanha<br /> </td> 
   <td> Rótulo e ID da campanha.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cidade<br /> </td> 
   <td> Cidade registrada no perfil do destinatário.<br /> </td> 
  </tr> 
  <tr> 
   <td> País/região<br /> </td> 
   <td> País registrado no perfil do destinatário.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery<br /> </td> 
   <td> Rótulo e ID do delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dispositivo<br /> </td> 
   <td> Dispositivo do qual a notificação por email/SMS/push foi aberta/exibida/clicada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Motivo da falha<br /> </td> 
   <td> Tipos de erros que causaram devoluções para cada delivery, por exemplo, usuário desconhecido, domínio inválido ou caixa de entrada cheia.<br /> </td> 
  </tr> 
  <tr> 
   <td> Sexo<br /> </td> 
   <td> Gênero do destinatário, como masculino ou feminino. Se o campo de gênero estiver vazio no perfil do recipient, o valor será nenhum.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ações de mensagens no aplicativo<br /> </td> 
   <td> Ações na mensagem no aplicativo entregue, por exemplo, ações no botão 1 ou 2 ou demissões.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tipo de mensagem<br /> </td> 
   <td> Canal usado para o delivery, como email, SMS, notificação por push ou No aplicativo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nome do aplicativo móvel<br /> </td> 
   <td> Nome do aplicativo móvel<br /> </td> 
  </tr> 
  <tr> 
   <td> Plataforma<br /> </td> 
   <td> Plataforma do dispositivo a partir do qual a mensagem foi aberta/visualizada/clicada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Perfil<br /> </td> 
   <td> Reagrupa campos prontos para uso e de perfil personalizados criados durante a extensão do recurso de perfil. Para obter mais informações, consulte esta <a href="../../developing/using/key-steps-to-add-a-resource.md">página</a> ou esta <a href="../../reporting/using/creating-a-custom-profile-dimension.md">exemplo</a>.<br /> Observe que os dados dessa dimensão são recuperados assim que o recurso personalizado vinculado ao campo de perfil é publicado.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push platform<br /> </td> 
   <td> Plataforma do dispositivo do qual a notificação por push foi aberta, como iOS ou Android.<br /> </td> 
  </tr> 
  <tr> 
   <td> Domínio do destinatário<br /> </td> 
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
   <td> Estado registrado no perfil do destinatário.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rastrear URL<br /> </td> 
   <td> URL que foi clicado pelo usuário a partir da mensagem.<br /> </td> 
  </tr> 
  <tr> 
   <td> Categoria de URL de rastreamento<br /> </td> 
   <td> Categoria atribuída ao URL de rastreamento.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rastreamento do rótulo do URL<br /> </td> 
   <td> Rótulo fornecido para o URL, como mirror page, entre em contato conosco ou abra.<br /> </td> 
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

As tabelas abaixo fornecem a lista de métricas usadas nos relatórios e suas definições, dependendo do tipo de delivery.

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
   <td> Em lista de bloqueios<br /> </td> 
   <td> Número de recipients que declararam um email como spam ou lixo eletrônico.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de  Lista de bloqueios<br /> </td> 
   <td> Porcentagem de deliveries marcados na lista de bloqueios.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeições + Erros<br /> </td> 
   <td> Total de erros acumulados durante o delivery e o processamento automático de retorno em relação ao número total de mensagens enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeição + Taxa de erro<br /> </td> 
   <td> Porcentagem de emails que retornaram em comparação ao email enviado.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clique em<br /> </td> 
   <td> Número de vezes que um conteúdo foi clicado em um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Índice de click-through<br /> </td> 
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
   <td> Número total de erros permanentes, como um endereço de email incorreto.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de rejeição permanente<br /> </td> 
   <td> Porcentagem de deliveries que falharam devido a erros permanentes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mirror page<br /> </td> 
   <td> Número de recipients que clicaram no link da mirror page.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de mirror page<br /> </td> 
   <td> Porcentagem de cliques no link da mirror page em comparação ao total de mensagens de delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques na oferta<br /> </td> 
   <td> Número de vezes que uma oferta foi clicada em um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cliques da oferta<br /> </td> 
   <td> Porcentagem de cliques em uma oferta.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abertura<br /> </td> 
   <td> Número de vezes que uma mensagem foi aberta em um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de abertura<br /> </td> 
   <td> Porcentagem de mensagens abertas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Processado/enviado<br /> </td> 
   <td> Número total de envios para o delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarentena<br /> </td> 
   <td> Número de mensagens que retornaram e resultaram na quarentena do endereço.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de quarentena<br /> </td> 
   <td> Porcentagem de quarentenas em comparação às mensagens enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeitada<br /> </td> 
   <td> Número de mensagens classificadas como spam pelos servidores SMTP.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa rejeitada<br /> </td> 
   <td> Porcentagem de mensagens marcadas como rejeitadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeição suave<br /> </td> 
   <td> Número total de erros temporários, como uma caixa de entrada cheia.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de rejeição suave<br /> </td> 
   <td> Porcentagem de deliveries que falharam devido a um motivo temporário.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques exclusivos<br /> </td> 
   <td> Número de recipients que clicaram em um conteúdo em um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aberturas exclusivas<br /> </td> 
   <td> Número de recipients que abriram o delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unsubscription exclusivas<br /> </td> 
   <td> Número de recipients que clicaram no link de unsubscription.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cancelamento de inscrição<br /> </td> 
   <td> Número de unsubscription exclusivas em comparação às mensagens entregues.<br /> </td> 
  </tr> 
  <tr> 
   <td> Inscrições canceladas<br /> </td> 
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
   <td> Rejeição + Taxa de erro<br /> </td> 
   <td> Porcentagem de notificações por push que retornaram em comparação às notificações por push enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clique em<br /> </td> 
   <td> Número de vezes que uma notificação por push foi entregue ao dispositivo e clicada pelo usuário. O usuário deseja exibir a notificação, que será movida para o rastreamento Push Open ou ignorá-la.<br /> </td> 
  </tr> 
  <tr> 
   <td> Índice de click-through<br /> </td> 
   <td> Porcentagem de usuários que interagiram com a notificação por push.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregue<br /> </td> 
   <td> Número de notificações por push enviadas com êxito em relação ao número total de notificações por push enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa entregue<br /> </td> 
   <td> Porcentagem de notificações por push enviadas com êxito.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões<br /> </td> 
   <td> Número de vezes que uma notificação por push foi entregue ao dispositivo e deixou-o intocado no centro de notificações. Na maioria dos casos, o número de impressões deve ser semelhante ao número entregue. Isso garante que o dispositivo recebeu a mensagem e reenviou essas informações para o servidor.<br /> </td> 
  </tr> 
  <tr> 
   <td> Processado/enviado<br /> </td> 
   <td> Número total de notificações por push enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abertura<br /> </td> 
   <td> Número total de notificações por push enviadas ao dispositivo e clicadas pelos usuários, abrindo o aplicativo. Isso é semelhante ao Clique por push, exceto que uma Abertura por push não será acionada se a notificação for descartada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de abertura<br /> </td> 
   <td> Porcentagem de notificações por push abertas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques exclusivos<br /> </td> 
   <td> Número de vezes que um usuário único interage com a notificação por push, por exemplo, cliques na notificação ou no botão.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões exclusivas<br /> </td> 
   <td> Número de impressões por recipient.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aberturas exclusivas<br /> </td> 
   <td> Número de recipients que abriram o delivery.<br /> </td> 
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
   <td> Número total de mensagens no aplicativo entregues ao dispositivo pelo provedor de serviços.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões<br /> </td> 
   <td> Total de mensagens no aplicativo vistas pelos recipients, dependendo se o critério do acionador foi atendido.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques no aplicativo <br /> </td> 
   <td> Número total de recipients que clicaram no Botão 1 ou no Botão 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Índice de click-through no aplicativo<br /> </td> 
   <td> Porcentagem de usuários que clicaram no Botão 1 ou no Botão 2 em comparação a usuários que visualizaram a mensagem.<br /> </td> 
  </tr> 
  <tr> 
   <td> Demissão no aplicativo<br /> </td> 
   <td> Número total de mensagens que os destinatários descartaram clicando no botão Fechar ou descartando automaticamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de desativação no aplicativo<br /> </td> 
   <td> Porcentagem de mensagens no aplicativo que os recipients rejeitaram.<br /> </td> 
  </tr> 
  <tr> 
   <td> Processado/enviado<br /> </td> 
   <td> Número total de mensagens no aplicativo enviadas do Adobe Campaign como parte do processo de delivery enviado.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões exclusivas<br /> </td> 
   <td> Número de impressões por um destinatário exclusivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques únicos no aplicativo<br /> </td> 
   <td> Número de vezes que os destinatários clicaram no Botão 1 ou no Botão 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Despedimentos únicos no aplicativo<br /> </td> 
   <td> Número de vezes em que os recipients rejeitaram uma mensagem no aplicativo.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Segmentos {#segments}

>[!NOTE]
>
>Por padrão, o segmento **[!UICONTROL Exclude proof]** já está selecionado para filtrar os relatórios, mas pode ser alterado se necessário.

A tabela abaixo fornece a lista de segmentos usados nos relatórios e suas definições.

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
   <td> Recipients nascidos de 1946 a 1954.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Boomers 2<br /> </td> 
   <td> Recipients nascidos de 1955 a 1965.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: De 18 a 25<br /> </td> 
   <td> Recipients de 18 a 25 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: De 26 a 30<br /> </td> 
   <td> Recipients de 26 a 30 anos de idade.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: De 31 a 40<br /> </td> 
   <td> Recipients de 31 a 40 anos de idade.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: De 41 a 50<br /> </td> 
   <td> Recipients de 41 a 50 anos de idade.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Geração X<br /> </td> 
   <td> Recipients nascidos de 1966 a 1976.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Geração Y (Milênio)<br /> </td> 
   <td> Recipients nascidos de 1977 a 1994.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Geração Z<br /> </td> 
   <td> Recipients nascidos de 1995 até hoje.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Maior que 50<br /> </td> 
   <td> Recipients com idade superior a 50.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Menos de 25<br /> </td> 
   <td> Recipients com menos de 25 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Menos de 30<br /> </td> 
   <td> Recipients com menos de 30 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Menos de 40<br /> </td> 
   <td> Recipients com menos de 40 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Menos de 50<br /> </td> 
   <td> Recipients com menos de 50 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Geração silenciosa<br /> </td> 
   <td> Recipients nascidos em 1945 ou antes.<br /> </td> 
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

