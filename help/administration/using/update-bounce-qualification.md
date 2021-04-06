---
solution: Campaign Standard
product: campaign
title: Atualizar qualificação de devolução após uma interrupção de ISP
description: Saiba como atualizar a qualificação de devolução após uma interrupção do ISP.
audience: delivery
content-type: reference
topic-tags: monitoring-deliveries
hidefromtoc: true
translation-type: tm+mt
source-git-commit: 9edf26fa933e9faedecef3b381cb160230a51668
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 1%

---


# Atualizar qualificação de rejeição após uma interrupção de ISP {#update-bounce-qualification.md}

Se NÃO estiver executando a versão mais recente do Campaign, esta seção pode se aplicar a você. Consulte o representante da Adobe Campaign.

## Contexto

No caso de uma interrupção de um ISP, os emails enviados por meio do Campaign não podem ser entregues com êxito ao recipient: esses emails serão marcados incorretamente como rejeições.

Em dezembro de 2020, um problema global no Gmail resultou em mensagens de email enviadas para endereços de email Gmail válidos serem devolvidas incorretamente como endereços de email inválidos pelos servidores Gmail com a seguinte resposta: *&quot;550-5.1.1 A conta de email que você tentou acessar não existe.&quot;*

O Google declarou que as interrupções e interrupções do Gmail que causaram esse problema começaram em 14 de dezembro às 6:55 e terminaram às 6:09 PM EST em 15 de dezembro. Nossa análise de dados também mostrou um pico muito curto em rejeições de Gmail às 2:06AM EST no dia 16 de dezembro, com a maioria ocorrendo no dia 15 de dezembro entre as 14:00 EST e 18:30 EST.

>[!NOTE]
>
>Você pode verificar o Painel de status do Google Workspace em [esta página](https://www.google.com/appsstatus#hl=en&amp;v=status).


De acordo com a lógica padrão de manipulação de rejeição, o Adobe Campaign adicionou automaticamente esses recipients à lista de quarentena com uma configuração **[!UICONTROL Status]** de **[!UICONTROL Quarantine]**. Para corrigir isso, você precisa atualizar a tabela de quarentena no Campaign localizando e removendo esses recipients ou alterando seus **[!UICONTROL Status]** para **[!UICONTROL Valid]** para que o workflow de limpeza noturna os remova.

Para encontrar os recipients que foram afetados por esse problema do Gmail, ou caso isso aconteça novamente com qualquer outro ISP, consulte as instruções abaixo.

## Processo para atualização

Você precisará executar um query na tabela de quarentena para filtrar todos os recipients do Gmail (ou de outro ISP) que foram potencialmente afetados pela interrupção para que possam ser removidos da lista de quarentena e incluídos em futuros deliveries de email do Campaign.

Com base no período do incidente, abaixo estão as diretrizes recomendadas para essa consulta.

>[!IMPORTANT]
>
>Essas datas/horas são baseadas no fuso horário padrão do leste (EST). Ajuste para o fuso horário da sua instância.

Para instâncias do Campaign com informações de resposta de rejeição SMTP no campo **[!UICONTROL Error text]** da lista de quarentena:

* **O texto de erro (texto de quarentena)** contém &quot;550-5.1.1 A conta de email que você tentou acessar não existe&quot; E o texto de  **Erro (texto de quarentena)** contém &quot;support.google.com&quot; **
* **Atualizar status (@lastModified)** em ou após 14/12/2020 6:55:00
* **Atualizar status (@lastModified)** em ou antes de 16/12/2020 6:00:00

Depois de ter a lista de recipients afetados, você pode defini-los como um status **[!UICONTROL Valid]** para que sejam removidos da lista de quarentena pelo workflow **[!UICONTROL Database cleanup]** ou simplesmente excluí-los da tabela.

**Tópicos relacionados:**
* [Compreender as falhas de delivery](../../sending/using/understanding-delivery-failures.md)
* [Qualificação de email de rejeição](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)

