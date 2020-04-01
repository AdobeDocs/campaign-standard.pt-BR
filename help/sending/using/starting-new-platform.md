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
source-git-commit: f83cf866f1c9fa53687e6cee26306d33327bd822

---


# Início de uma nova plataforma{#starting-new-platform}

É essencial manter sua reputação de domínio e endereço IP. Aqui estão alguns conselhos para configurar uma nova plataforma.

Começar a enviar emails em uma nova plataforma é uma etapa delicada, pois a plataforma não tem histórico de uso e reputação (quando os IPs de envio nunca foram usados para essa finalidade). Os ISPs desconfiam naturalmente dos endereços IP que nunca foram usados para enviar emails e que, de repente, começam a enviar grandes volumes de tráfego de emails. Na verdade, os remetentes de spam geralmente usam endereços IP &quot;desconhecidos&quot; (ou seja, endereços que nunca foram incluídos na blacklist) para enviar o maior número possível de mensagens antes da detecção.

Não se pode esperar atingir a velocidade operacional em termos de saída no início da fase de produção. Além disso, você não deve tentar enviar mensagens a essa taxa, pois isso pode levar os ISPs a bloquear os endereços de envio e comprometer seriamente o restante da fase de inicialização.

A inicialização de uma plataforma geralmente ocorre ao usar uma lista de endereços pela primeira vez e que podem não ser totalmente qualificados. Se você enviar para endereços inválidos ou para endereços armadilha, isso contribuirá para diminuir a reputação da plataforma.
* If you have a list of invalid addresses, it is in your best interests to import it into the quarantine table (**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** > **[!UICONTROL Addresses]**) before sending for the first times. For more on this, see this [section](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).
* Se, mesmo assim, você quiser requalificar os endereços inválidos, é preferível fazer isso assim que a reputação da plataforma for estabelecida e pouco a pouco para &quot;diluir&quot; o uso de endereços inválidos ao longo do tempo.

Para resumir os princípios a serem seguidos ao iniciar:
* **Delegar um subdomínio** dedicado à Adobe que seja específico para campanhas de email enviadas da Adobe.
* **Importe endereços inválidos/inativos para a tabela** de quarentena (se você tiver essas informações).
* **Limite a taxa de transferência** do delivery (configuração técnica: limitação do número de crianças).
* **Aumente progressivamente os volumes enviados**: não público alvo todo o banco de dados do próprio start, mas adicione uma fração extra da lista sempre que enviar. Isso deve permitir aumentar o volume em cada etapa e reduzir a taxa geral de endereços inválidos.
* **Enviar mensagens regularmente**: até certo ponto, é melhor enviar regularmente campanhas pequenas em vez de esporadicamente.
* **Monitore de perto os relatórios do delivery**: indicadores de erro elevados podem significar que uma configuração técnica está mal configurada.
