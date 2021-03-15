---
solution: Campaign Standard
product: campaign
title: Iniciar uma nova plataforma com o Adobe Campaign Standard
description: Saiba como configurar uma nova plataforma, mantendo a reputação do seu domínio e endereço IP com o Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Avaliação do delivery
role: Profissional
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 55%

---


# Início de uma nova plataforma{#starting-new-platform}

É essencial manter sua reputação de domínio e endereço IP. Estes são alguns conselhos para configurar uma nova plataforma.

Começar a enviar emails em uma nova plataforma é uma etapa delicada, pois a plataforma não tem histórico de uso e reputação (quando os IPs de envio nunca foram usados para essa finalidade). Os ISPs desconfiam naturalmente dos endereços IP que nunca foram usados para enviar emails e que, de repente, começam a enviar grandes volumes de tráfego de emails. Na verdade, os remetentes de spam geralmente usam endereços IP &quot;desconhecidos&quot; (endereços que nunca foram adicionados à  de lista de bloqueios) para enviar o maior número possível de mensagens antes da detecção.

Não se pode esperar atingir a velocidade operacional em termos de saída no início da fase de produção. Além disso, você não deve tentar enviar mensagens a essa taxa, pois isso pode levar os ISPs a bloquear os endereços de envio e comprometer seriamente o restante da fase de inicialização.

A inicialização de uma plataforma geralmente ocorre ao usar uma lista de endereços pela primeira vez e que podem não ser totalmente qualificados. Se você enviar para endereços inválidos ou para endereços armadilha, isso contribuirá para diminuir a reputação da plataforma.
* Se você tiver uma lista de endereços inválidos, é do seu interesse importá-la para a tabela de quarentena (**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** > **[!UICONTROL Addresses]**) antes de enviar pela primeira vez. Para obter mais informações, consulte esta [seção](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).
* Se, mesmo assim, você quiser requalificar os endereços inválidos, é preferível fazer isso assim que a reputação da plataforma for estabelecida e pouco a pouco para &quot;diluir&quot; o uso de endereços inválidos ao longo do tempo.

Para resumir os princípios a serem seguidos ao iniciar:
* **Configure um** subdomínio dedicado para funcionar com o Campaign, específico para campanhas de email enviadas do Adobe.
* **Importe endereços inválidos/inativos para a tabela**  de quarentena (se você tiver essas informações).
* **Limite a** taxa de transferência de delivery (configuração técnica: limitando o número de mtachilds).
* **Aumente progressivamente os volumes enviados**: não direcione todo o banco de dados desde o início, mas adicione uma fração extra da lista sempre que enviar. Isso deve permitir aumentar o volume em cada etapa e reduzir a taxa geral de endereços inválidos.
* **Enviar mensagens regularmente**: até certo ponto, é melhor enviar pouca coisa regularmente do que campanhas grandes esporadicamente.
* **Monitore de perto os relatórios** do delivery: indicadores de erro elevados podem significar que uma configuração técnica está mal configurada.
