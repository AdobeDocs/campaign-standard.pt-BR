---
title: Atualizar qualificação de rejeição após uma interrupção do ISP
description: Saiba como atualizar a qualificação de rejeição após uma interrupção do ISP.
audience: delivery
exl-id: b06e9009-70c7-459f-8a9f-d5b7020d662f
TQID: 'https://experienceleague.adobe.com/PcNbVFzTVJhadANGQ5uogj16VHiaNIf7HVn-7X-EbJA'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 66%
---
# Atualizar qualificação de rejeição após uma interrupção do ISP {#update-bounce-qualification.md}

## Contexto

No caso de uma interrupção de um ISP, os emails enviados por meio do Campaign não podem ser entregues com êxito ao destinatário: esses emails serão marcados incorretamente como rejeições.

Em dezembro de 2020, um problema global no Gmail fez com que mensagens de email enviadas para endereços de email Gmail válidos fossem rejeitadas incorretamente como endereços de email inválidos pelos servidores do Gmail, com a seguinte resposta: *&quot;550-5.1.1 A conta de email que você tentou acessar não existe.&quot;*

A Google declarou que as interrupções e as interrupções do Gmail que causaram esse problema começaram em 14 de dezembro às 6h55 e terminaram às 18h09 EST em 15 de dezembro. Nossa análise de dados também mostrou um pico muito curto de rejeições no Gmail às 2h06 EST no dia 16 de dezembro, com a maioria ocorrendo no dia 15 de dezembro entre 14h EST e 18h30 EST.

>[!NOTE]
>
>Você pode verificar o Painel de status do Google Workspace [nesta página](https://www.google.com/appsstatus#hl=en&v=status).


De acordo com a lógica padrão de manipulação de rejeição, o Adobe Campaign adicionou automaticamente esses destinatários à lista de quarentena com uma configuração **[!UICONTROL Status]** de **[!UICONTROL Quarantine]**. Para corrigir isso, você precisa atualizar a tabela de quarentena no Campaign localizando e removendo esses destinatários ou alterando seus **[!UICONTROL Status]** para **[!UICONTROL Valid]** para que o fluxo de trabalho de limpeza noturna os remova.

Para encontrar os destinatários que foram afetados por esse problema do Gmail, ou caso isso aconteça novamente com qualquer outro ISP, consulte as instruções abaixo.

## Processo para atualização

Você precisará executar uma consulta na tabela de quarentena para filtrar todos os destinatários do Gmail (ou de outro ISP) que foram potencialmente afetados pela interrupção para que possam ser removidos da lista de quarentena e incluídos em futuras entregas de email do Campaign.

Com base no período do incidente, abaixo estão as diretrizes recomendadas para essa consulta.

>[!IMPORTANT]
>
>Essas datas/horas são baseadas no fuso horário padrão do leste (EST). Ajuste para o fuso horário da sua instância.

Para instâncias do Campaign com informações de resposta de rejeição SMTP no campo **[!UICONTROL Error text]** da lista de quarentena:

* **O texto de erro (texto de quarentena)** contém &quot;550-5.1.1 A conta de email que você tentou acessar não existe&quot; E **O texto de erro (texto de quarentena)** contém &quot;support.google.com&quot; **
* **Atualizar status (@lastModified)** em ou após 14/12/2020 6:55:00 AM
* **Atualizar status (@lastModified)** em ou antes de 16/12/2020 6:00:00 AM

Depois de ter a lista de destinatários afetados, você pode defini-los como um status **[!UICONTROL Valid]** para que sejam removidos da lista de quarentena pelo fluxo de trabalho **[!UICONTROL Database cleanup]** ou simplesmente excluí-los da tabela.

**Tópicos relacionados:**

* [Entender as falhas de entrega](../../sending/using/understanding-delivery-failures.md)
* [Qualificação de email de rejeição](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)
