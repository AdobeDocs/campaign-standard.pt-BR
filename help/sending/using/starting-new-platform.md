---
title: Iniciar uma nova plataforma com o Adobe Campaign Standard
description: Saiba como configurar uma nova plataforma, mantendo sua reputação de domínio e endereço IP com o Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 89965d859986b9176de6b6bf96df1fbbb89b5b8f

---


# Iniciar uma nova plataforma{#starting-new-platform}

É essencial manter sua reputação de domínio e endereço IP. Aqui estão alguns conselhos para configurar uma nova plataforma.

Começar a enviar emails em uma nova plataforma é uma etapa sensível, pois a plataforma não tem histórico de uso e reputação (quando os IPs de envio nunca foram usados para essa finalidade). Os ISPs desconfiam naturalmente dos endereços IP que nunca foram usados para enviar emails e que, de repente, começam a enviar grandes volumes de tráfego de emails. Na verdade, os remetentes de spam geralmente usam endereços IP "desconhecidos" (ou seja, endereços que nunca foram adicionados à lista negra) para enviar o maior número possível de mensagens antes da detecção.

Não se pode esperar que a velocidade operacional atinja a produção no início da fase de produção. Além disso, você não deve tentar enviar mensagens a essa taxa, pois isso pode levar os ISPs a bloquear os endereços de envio e comprometer seriamente o restante da fase de inicialização.

A inicialização de uma plataforma geralmente ocorre ao usar uma lista de endereços pela primeira vez e que podem não ser totalmente qualificados. Se você enviar para endereços inválidos ou para endereços de correio telefônico, isso contribuirá para diminuir a reputação da plataforma. Se você tiver uma lista de endereços inválidos, é do seu interesse importá-la para a tabela de quarentena (**[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Quarantines]** &gt; **[!UICONTROL Addresses]**) antes de enviar pela primeira vez. Se, mesmo assim, você quiser requalificar os endereços inválidos, é preferível fazer isso assim que a reputação da plataforma for estabelecida e bit a bit para "diluir" o uso de endereços inválidos ao longo do tempo.

Resumir os princípios a seguir no arranque:
* **Delegar um subdomínio** dedicado à Adobe que seja específico para campanhas de email enviadas da Adobe
* **Importar endereços inválidos/inativos para a tabela** de quarentena (se você tiver essas informações)
* **Limite a taxa de throughput** de entrega (configuração técnica: limitação do número de crianças)
* **Aumente progressivamente os volumes enviados**: não direcione todo o banco de dados desde o início, mas adicione uma fração extra da lista sempre que enviar; isso deve permitir aumentar o volume em cada etapa e reduzir a taxa geral de endereços inválidos
* **Enviar mensagens regularmente**: Em certa medida, é melhor enviar regularmente imagens pequenas em vez de grandes campanhas esporadicamente
* **Monitore de perto os relatórios** de entrega: indicadores de erro elevados podem significar que uma configuração técnica está mal configurada.
