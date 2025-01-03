---
title: Definir o público-alvo correto
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Quando seu conteúdo estiver pronto, saiba como definir com cuidado quem receberá sua mensagem.
feature: Deliverability
role: User
level: Intermediate
exl-id: 1e06fd9d-e850-4856-8f7b-b581dbe157df
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 71%

---

# Definir o público correto {#define-the-right-audience}

A segmentação de público-alvo é fundamental: crie suas listas cuidadosamente, teste seus emails em clientes de email populares e dispositivos móveis e verifique se suas listas de email estão atualizadas (sem endereços desconhecidos ou obsoletos). Você também pode enviar provas que ajudam a configurar um ciclo de validação completo.

Saiba mais sobre as populações de públicos-alvos [nesta seção](../../audiences/using/selecting-an-audience-in-a-message.md)

## Direcionar ao público-alvo correto {#target-the-right-audience}

Quando seu conteúdo estiver pronto, será necessário definir com cuidado quem receberá sua mensagem.

Para que sua entrega seja bem-sucedida, o conteúdo personalizado mais relevante deve ser enviado aos destinatários corretos. O Adobe Campaign permite criar o público mais preciso: você pode selecionar os destinatários de acordo com a idade, localização, o que compraram, se clicaram em um link em uma entrega anterior, etc. Com o Adobe Campaign, também é possível definir perfis de teste, grupos de controle e endereços de seed para verificar se o público-alvo está correto.

## Direcionar mapeamentos {#target-mappings}

Por padrão, modelos de entrega têm como alvo **Perfis**. O Adobe Campaign oferece outros target mappings para suas entregas, que podem ser modificados conforme suas necessidades.

Esses mapeamentos são apresentados [nesta seção](../../automating/using/query.md#targeting-dimensions-and-resources).

Você também pode criar e usar um target mapping personalizado. Para obter mais informações, consulte [esta seção](../../administration/using/target-mappings-in-campaign.md).

## Dados externos {#external-data}

Você pode enviar entregas para destinatários armazenados em um arquivo externo em vez de salvos no banco de dados. Para fazer isso, crie um fluxo de trabalho que carregará dados em seu banco de dados a partir de um arquivo e criará um público-alvo associado.  Saiba mais [neste caso de uso](../../automating/using/use-case-calling-workflow.md). Consulte também [Chamada de fluxo de trabalho com parâmetros](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Enviar para os assinantes {#send-to-subscribers}

Para enviar mensagens aos assinantes de um informativo, é possível direcionar diretamente os assinantes para o serviço de informação correspondente. Saiba mais [nesta seção](../../audiences/using/about-subscriptions.md).

**Dica** - Você pode criar um público-alvo do tipo Lista que direcione os assinantes do seu informativo usando um fluxo de trabalho. Em seguida, você pode selecionar esse público-alvo em um delivery. Para obter mais informações, consulte [Criação de públicos-alvo da lista](../../audiences/using/creating-audiences.md#creating-list-audiences).

## Provas, perfis de teste e grupos de controle {#proofs-test-control-groups}

Para testar seu delivery, use provas antes de enviar para o target principal.
Selecione os destinatários de prova apropriados, porque eles validam a forma e o conteúdo da mensagem. As etapas para enviar provas são apresentadas [nesta seção](../../sending/using/sending-proofs.md).

Saiba mais sobre perfis de teste [nesta seção](../../audiences/using/managing-test-profiles.md).

Você pode usar [Grupos de controle](../../sending/using/control-group.md) para medir o impacto de suas campanhas excluindo parte de seus públicos. Portanto você poderá comparar o comportamento do público-alvo que recebeu a mensagem com o comportamento dos contatos não atingidos. Com base nos logs de envio, você também poderá se concentrar em um grupo de controle em campanhas futuras.

## Cancelar endereços duplicados {#deduplicate-addresses}

É importante evitar emails duplicados, pois eles podem afetar seu público-alvo:

* A mesma mensagem pode ser enviada mais de uma vez quando um público-alvo é dividido.

* Se um destinatário cancelar a assinatura após receber uma mensagem, seu perfil duplicado ainda receberá mensagens futuras.

O cancelamento da duplicação de endereços protege a reputação de envio e garante um bom gerenciamento de quarentena.

Saiba mais [neste caso de uso](../../automating/using/deduplicating-data-imported-file.md).
