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
source-git-commit: f78e101b8abea3640ad93db6ff53243a42e07086

---


# Lista de componentes {#list-of-components}

Para saber mais sobre a compatibilidade entre dimensões e métricas, consulte esta [tabela](/help/reporting/using/assets/dynamic_report_compatibility.pdf). Se dois componentes não forem compatíveis, a célula exibirá o valor **Nenhum**.

![](assets/dynamic_report_compatibility.png)

## Dimensões {#dimensions}

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
   <td> Navegador no qual a mensagem foi aberta ou clicada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Campanha<br /> </td> 
   <td> Rótulo e ID da sua campanha.<br /> </td> 
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
   <td> Rótulo e ID da entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dispositivo<br /> </td> 
   <td> Dispositivo a partir do qual a notificação por email/SMS/push foi aberta/visualizada/clicada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Motivo da falha<br /> </td> 
   <td> Tipos de erros que causaram saltos para cada entrega, por exemplo, usuário desconhecido, domínio inválido ou caixa de correio cheia.<br /> </td> 
  </tr> 
  <tr> 
   <td> Sexo<br /> </td> 
   <td> Gênero do destinatário, como masculino ou feminino. Se o campo gênero estiver vazio no perfil do destinatário, o valor será nenhum.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ações de mensagens no aplicativo<br /> </td> 
   <td> Ações na mensagem no aplicativo fornecida, por exemplo, ações no botão 1 ou 2 ou demissões.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tipo de mensagem<br /> </td> 
   <td> Canal usado para a entrega, como email, SMS, notificação por push ou no aplicativo.<br /> </td> 
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
   <td> Profiles<br /> </td> 
   <td> Reagrupa campos predefinidos e de perfil personalizados criados durante a extensão do recurso de perfil, para obter mais informações, consulte esta <a href="../../developing/using/key-steps-to-add-a-resource.md">página</a> ou este <a href="../../reporting/using/creating-a-custom-profile-dimension.md">exemplo</a>.<br /> Observe que os dados para essa dimensão são recuperados assim que o recurso personalizado vinculado ao campo de perfil é publicado.<br /> </td> 
  </tr> 
  <tr> 
   <td> Plataforma push<br /> </td> 
   <td> Plataforma do dispositivo a partir do qual a notificação por push foi aberta, como iOS ou Android.<br /> </td> 
  </tr> 
  <tr> 
   <td> Domínio do destinatário<br /> </td> 
   <td> Domínio usado para abrir o email.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery recorrente<br /> </td> 
   <td> Rótulo e ID da entrega recorrente.<br /> </td> 
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
   <td> URL de rastreamento<br /> </td> 
   <td> URL clicado pelo usuário na mensagem.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rastrear categoria de URL<br /> </td> 
   <td> Categoria atribuída ao URL de rastreamento.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rastreamento do rótulo do URL<br /> </td> 
   <td> Rótulo fornecido ao URL, como página espelhada, entre em contato conosco ou abra.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega transacional<br /> </td> 
   <td> Rótulo e ID da entrega transacional.<br /> </td> 
  </tr> 
  <tr> 
   <td> Variante<br /> </td> 
   <td> Variante do email no caso de teste A/B.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Métricas {#metrics}

As tabelas abaixo fornecem a lista de métricas usadas nos relatórios e suas definições, dependendo do tipo de entrega.

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
   <td> Lista negra<br /> </td> 
   <td> Número de destinatários que declararam um email como spam ou lixo eletrônico.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa da lista negra<br /> </td> 
   <td> Percentagem de entregas marcadas como proibidas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeições + Erros<br /> </td> 
   <td> Total de erros acumulados durante a entrega e o processamento automático de retorno em relação ao número total de mensagens enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Salto + Taxa de erro<br /> </td> 
   <td> Porcentagem de emails que retornaram em comparação ao email enviado.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clique em<br /> </td> 
   <td> Número de vezes que um conteúdo foi clicado em uma entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cliques<br /> </td> 
   <td> Porcentagem de cliques em uma entrega.<br /> </td> 
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
   <td> Porcentagem de entregas que falharam devido a erros permanentes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Página de espelhamento<br /> </td> 
   <td> Número de destinatários que clicaram no link da página espelhada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de páginas espelhadas<br /> </td> 
   <td> Porcentagem de cliques no link da página espelhada em comparação ao total de mensagens de entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques na oferta<br /> </td> 
   <td> Número de vezes que uma oferta foi clicada em uma entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cliques da oferta<br /> </td> 
   <td> Porcentagem de cliques em uma oferta.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abertura<br /> </td> 
   <td> Número de vezes que uma mensagem foi aberta em uma entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa aberta<br /> </td> 
   <td> Porcentagem de mensagens abertas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Processado/enviado<br /> </td> 
   <td> O número total de envios para a entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarentena<br /> </td> 
   <td> Número de mensagens que retornou e resultaram na quarentena do endereço.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de quarentena<br /> </td> 
   <td> Porcentagem de quarentena em comparação a mensagens enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeitada<br /> </td> 
   <td> Número de mensagens classificadas como spam pelos servidores SMTP.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de rejeição<br /> </td> 
   <td> Porcentagem de mensagens marcadas como rejeitadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rejeição suave<br /> </td> 
   <td> Número total de erros temporários, como uma caixa de entrada completa.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de rejeição suave<br /> </td> 
   <td> Porcentagem de entregas que falharam devido a um motivo temporário.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques únicos<br /> </td> 
   <td> Número de destinatários que clicaram em um conteúdo em uma entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aberturas exclusivas<br /> </td> 
   <td> Número de destinatários que abriram a entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cancelamento de inscrição<br /> </td> 
   <td> Porcentagem de cancelamentos de assinaturas por destinatário em comparação às mensagens entregues.<br /> </td> 
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
   <td> Total de erros acumulados durante a entrega em relação ao número total de mensagens enviadas, por exemplo, erros do MCPNS ou do provedor.<br /> </td> 
  </tr> 
  <tr> 
   <td> Salto + Taxa de erro<br /> </td> 
   <td> Porcentagem de notificações por push que pularam em comparação a notificações por push enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clique em<br /> </td> 
   <td> Número de vezes que uma notificação por push foi entregue ao dispositivo e clicada pelo usuário. O usuário deseja exibir a notificação, que será movida para o rastreamento Push Open ou ignorá-la.<br /> </td> 
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
   <td> Clique único<br /> </td> 
   <td> Número de vezes que um usuário único interage com a notificação por push, por exemplo, clica na notificação ou botão.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões exclusivas<br /> </td> 
   <td> Número de impressões por destinatário.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aberturas únicas<br /> </td> 
   <td> Número de destinatários que abriram a entrega.<br /> </td> 
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
   <td> Total de mensagens no aplicativo vistas pelos destinatários, dependendo se o critério de disparo foi atendido.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques no aplicativo <br /> </td> 
   <td> Número total de destinatários que clicaram no Botão 1 ou no Botão 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de cliques no aplicativo<br /> </td> 
   <td> A porcentagem de usuários que clicaram no Botão 1 ou no Botão 2 em comparação aos usuários que viram a mensagem.<br /> </td> 
  </tr> 
  <tr> 
   <td> Demissão no aplicativo<br /> </td> 
   <td> O número total de mensagens que os destinatários dispensaram ao clicar no botão Fechar ou fechar automaticamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taxa de demissão no aplicativo<br /> </td> 
   <td> Porcentagem de mensagens no aplicativo que os destinatários rejeitaram.<br /> </td> 
  </tr> 
  <tr> 
   <td> Processado/enviado<br /> </td> 
   <td> O número total de mensagens no aplicativo enviadas do Adobe Campaign como parte do processo de entrega enviada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressões exclusivas<br /> </td> 
   <td> Número de impressões de um destinatário único.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cliques únicos no aplicativo<br /> </td> 
   <td> Número de vezes que os destinatários clicaram no Botão 1 ou no Botão 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Despedimentos únicos no aplicativo<br /> </td> 
   <td> Número de vezes que os destinatários rejeitaram uma mensagem no aplicativo.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Segmentos {#segments}

>[!NOTE]
>
>Por padrão, o **[!UICONTROL Exclude proof]** segmento já está selecionado para filtrar seus relatórios, mas pode ser alterado se necessário.

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
   <td> Destinatários nascidos de 1946 a 1954.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Boomers 2<br /> </td> 
   <td> Destinatários nascidos de 1955 a 1965.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: De 18 para 25<br /> </td> 
   <td> Destinatários de 18 a 25 anos de idade.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: De 26 para 30<br /> </td> 
   <td> Destinatários de 26 a 30 anos de idade.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: De 31 para 40<br /> </td> 
   <td> Destinatários de 31 a 40 anos de idade.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: De 41 para 50<br /> </td> 
   <td> Destinatários de 41 a 50 anos de idade.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Geração X<br /> </td> 
   <td> Destinatários nascidos de 1966 a 1976.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Geração Y (geração)<br /> </td> 
   <td> Destinatários nascidos de 1977 a 1994.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Geração Z<br /> </td> 
   <td> Destinatários nascidos de 1995 a hoje.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Maior que 50<br /> </td> 
   <td> Destinatários com idade superior a 50 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Menos de 25<br /> </td> 
   <td> Destinatários com menos de 25 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Menos de 30<br /> </td> 
   <td> Destinatários com idade inferior a 30 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Menos de 40<br /> </td> 
   <td> Destinatários com menos de 40 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Menos de 50<br /> </td> 
   <td> Destinatários com menos de 50 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Idade: Geração silenciosa<br /> </td> 
   <td> Destinatários nascidos em 1945 ou antes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Todas as visitas<br /> </td> 
   <td> Cada destinatário<br /> </td> 
  </tr> 
    <tr> 
   <td> Excluir prova<br /> </td> 
   <td> Excluir provas de seus relatórios<br /> </td> 
  </tr> 
 </tbody> 
</table>

