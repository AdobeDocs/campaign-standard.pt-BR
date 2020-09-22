---
title: Melhorando sua reputação com a Adobe Campaign Standard
description: Saiba como melhorar sua reputação com a Adobe Campaign Standard, gerenciando endereços de email e quarentenas de duplicados.
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
source-git-commit: 1b1fb4a0dc0f7881e24e10f8ac171feab2ac8cba
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 70%

---


# Aprimoramento da reputação{#improving-reputation}

Para não esgotar os recipients, exclua endereços de email duplicados do destino. Essa etapa protege a reputação de envio e garante um bom gerenciamento de quarentena. A Adobe Campaign oferta as ferramentas necessárias para implementar essas recomendações e evitar o risco de serem adicionadas à lista de bloqueios pelos ISPs.

Abaixo você encontrará detalhes sobre o gerenciamento de duplicidade e quarentena.

## Duplicidades {#duplicates}

Ter endereços de email duplicados pode ter várias consequências:
* A mesma mensagem é enviada mais de uma vez. Mesmo se o Campaign executar um procedimento de desduplicação por padrão antes de enviar, não há nada que impeça o envio da mesma mensagem por ações diferentes com o mesmo conteúdo quando um target é dividido.
* Solicitações de cancelamento de assinatura não respeitadas. Se um recipient cancelar a inscrição depois de receber uma mensagem, o perfil duplicado ainda será qualificado para mensagens futuras.

Além dessa revisão lateral dos procedimentos de aceitação, essa situação provavelmente levará os usuários a considerar as mensagens como spam e a acionar um procedimento de  lista de bloqueios no ISP.

Você deve ter cuidado especial ao executar operações no banco de dados. Para evitar ao máximo as duplicações, as seguintes ações devem ser realizadas:
* **As importações devem ser meticulosamente configuradas.** Isso é particularmente importante ao escolher a chave de reconciliação.
* **Preste atenção ao modificar endereços de email.** Endereços de email alterados também podem ser uma fonte de duplicidades. Em particular, dois endereços com domínios diferentes podem ser roteados para a mesma caixa de correio, por exemplo, no caso de uma empresa que mudou de nome e manteve o domínio anterior por um determinado período de tempo: joe.doe@amce-co.com e joe.doe@acme-rebranded.com.
* **Preste atenção durante as importações automáticas.** Independentemente de listas ou de outras bases de dados, são elementos a ter em conta na gestão de perfis. O que acontece quando você exclui ou move um perfil em outra partição? Ele pode ser recriado na partição inicial por uma importação automática, por exemplo, quando um pedido de compra é feito.
* **Os perfis devem ser classificados em pastas diferentes.**

Há, contudo, casos em que duplicidades entre as diferentes partições são normais. Por exemplo, ao enviar para terceiros ou entidades de empresas diferentes, é lógico que a mesma pessoa seja um recipient por vários motivos. No entanto, raramente é normal encontrar duplicidades na mesma partição.

## Quarentenas {#quarantines}

O Adobe Campaign gerencia uma lista de endereços em quarentena. Os recipients cujos endereços estão em quarentena são excluídos por padrão durante a análise de delivery: não são direcionados.

Quarantine management is detailed in [this section](../../sending/using/understanding-quarantine-management.md).

Um endereço de email pode ser colocado em quarentena, por exemplo, quando a caixa de entrada estiver cheia ou se o endereço não existir. Em todos os casos, a quarentena corresponde às regras específicas apresentadas na [presente seção](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).
