---
title: Melhorando sua reputação com o Adobe Campaign Standard
description: Saiba como melhorar sua reputação com o Adobe Campaign Standard gerenciando endereços de email e quarentena duplicados.
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
source-git-commit: 44049443f8028ed26089ee0d49944ebac6a62111

---


# Melhorando sua reputação{#improving-reputation}

Para evitar esgotar seus destinatários, exclua endereços de email duplicados do destino. Esta etapa protege a reputação de envio e garante um bom gerenciamento de quarentena. O Adobe Campaign oferece as ferramentas necessárias para implementar essas recomendações e evitar o risco de serem proibidas pelo ISP.

Abaixo você encontrará detalhes sobre o gerenciamento de duplicatas e quarentena.

## Duplicatas {#duplicates}

Ter endereços de email duplicados pode ter várias consequências:
* A mesma mensagem é enviada mais de uma vez. Mesmo se o Campaign executar um procedimento de desduplicação por padrão antes de enviar, não há nada que impeça o envio da mesma mensagem por ações diferentes com o mesmo conteúdo quando um destino é dividido.
* Solicitações de cancelamento de assinatura não respeitadas. Se um destinatário cancelar a inscrição depois de receber uma mensagem, seu perfil duplicado ainda será qualificado para mensagens futuras.

Além desta revisão lateral dos procedimentos de aceitação, esta situação levará os usuários a considerar as mensagens como spam e a acionar um procedimento de lista negra no ISP.

Você deve ter cuidado ao executar operações no banco de dados. Para evitar duplicações tanto quanto possível, devem ser realizadas as seguintes ações:
* **As importações devem ser meticulosamente configuradas.** Isso é particularmente importante ao escolher a chave de reconciliação.
* **Preste atenção ao modificar endereços de email.** Endereços de email alterados também podem ser uma fonte de duplicatas. Em particular, dois endereços com domínios diferentes podem ser roteados para a mesma caixa de correio, por exemplo, no caso de uma empresa que mudou de nome e manteve o domínio anterior por um determinado período de tempo: joe.doe@amce-co.com e joe.doe@acme-rebranded.com.
* **Prestem atenção durante as importações automáticas.** Independentemente de listas ou de outros bancos de dados, eles são elementos a serem considerados ao gerenciar perfis. O que acontece quando você exclui ou move um perfil em outra partição? Ele pode ser recriado na partição inicial por uma importação automática, por exemplo, quando um pedido de compra é feito.
* **Os perfis devem ser classificados em pastas diferentes.**

Há, todos os mesmos, casos em que duplicatas entre as diferentes partições são normais. Por exemplo, ao enviar para terceiros ou entidades de empresas diferentes, é lógico que a mesma pessoa seja um destinatário por motivos diferentes. No entanto, raramente é normal encontrar duplicatas na mesma partição.

## Quarenta {#quarantines}

O Adobe Campaign gerencia uma lista de endereços em quarentena. Os destinatários cujos endereços estão em quarentena são excluídos por padrão durante a análise de entrega: não são visados.

O gerenciamento de quarentena é detalhado na [presente seção](../../sending/using/understanding-quarantine-management.md).

Um endereço de email pode ser colocado em quarentena, por exemplo, quando a caixa de entrada está cheia ou se o endereço não existe. Em todos os casos, a quarentena corresponde às regras específicas apresentadas na [presente seção](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).
