---
title: Definir o público-alvo correto
seo-title: Definir o público-alvo correto
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d5d9d50474142306457a8c76a24388c3c574791d
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 69%

---


# Definir o público-alvo correto {#define-the-right-audience}

A segmentação de público-alvo é fundamental: crie suas listas cuidadosamente, teste seus emails em clientes de email populares e dispositivos móveis e verifique se suas listas de email estão atualizadas (sem endereços desconhecidos ou obsoletos). Você também pode enviar provas que ajudam a configurar um ciclo de validação completo.

Saiba mais sobre as populações de públicos-alvos [nesta seção](../../audiences/using/selecting-an-audience-in-a-message.md)

## Direcionar o público-alvo correto {#target-the-right-audience}

Quando seu conteúdo estiver pronto, será necessário definir com cuidado quem receberá sua mensagem.

Para que seu delivery seja bem-sucedido, o conteúdo personalizado mais relevante deve ser enviado aos recipients corretos. O Adobe Campaign permite criar o público mais preciso: você pode selecionar os recipients de acordo com a idade, localização, o que compraram, se clicaram em um link em um delivery anterior, etc. Com o Adobe Campaign, também é possível definir perfis de teste, grupos de controle e endereços de seed para verificar se o público-alvo está correto.

## Target mappings {#target-mappings}

By default, delivery templates target **Profiles**. O Adobe Campaign oferece outros target mappings para seus deliveries, que podem ser modificados conforme suas necessidades.

Esses mapeamentos são apresentados [nesta seção](../../automating/using/query.md#targeting-dimensions-and-resources).

Você também pode criar e usar um target mapping personalizado. Para obter mais informações, consulte [esta seção](../../administration/using/target-mappings-in-campaign.md).

## Dados externos {#external-data}

Você pode enviar deliveries para destinatários armazenados em um arquivo externo em vez de salvos no banco de dados. Para fazer isso, projete um fluxo de trabalho para carregar dados no banco de dados a partir de um arquivo e crie uma audiência associada.  Saiba mais [neste caso de uso](../../automating/using/use-case-calling-workflow.md). Consulte também [Chamar um fluxo de trabalho com parâmetros](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Enviar para seus assinantes {#send-to-subscribers}

Para enviar mensagens aos assinantes de um informativo, é possível direcionar diretamente os assinantes para o serviço de informação correspondente. Saiba mais [nesta seção](../../audiences/using/about-subscriptions.md).

**Dica** - você pode criar uma audiência de Lista que público alvo os assinantes para o seu boletim informativo usando um fluxo de trabalho. Você pode selecionar essa audiência em um delivery. Para obter mais informações, consulte [Criação de audiências](../../audiences/using/creating-audiences.md#creating-list-audiences)de lista.

## Provas, perfis de teste e grupos de controle {#proofs-test-control-groups}

Para testar seu delivery, use provas antes de enviar para o público-alvo principal.
Selecione os recipients de prova apropriados, porque eles validam a forma e o conteúdo da mensagem. As etapas para enviar provas são apresentadas [nesta seção](../../sending/using/sending-proofs.md).

Learn more about test profiles [in this section](../../audiences/using/managing-test-profiles.md).

Você pode usar [Grupos de controle](../../sending/using/control-group.md) para medir o impacto de suas campanhas, excluindo uma parte de suas audiências. Poderá então comparar o comportamento da população do público alvo que recebeu a mensagem com o comportamento dos contatos que não foram visados. Com base nos registros de envio, você também pode público alvo um grupo de controle em futuras campanhas.

## Cancelar endereços duplicados {#deduplicate-addresses}

É importante evitar emails duplicados, pois eles podem afetar seu público-alvo:

* A mesma mensagem pode ser enviada mais de uma vez quando um público-alvo é dividido.

* Se um destinatário cancelar a assinatura após receber uma mensagem, seu perfil duplicado ainda receberá mensagens futuras.

O cancelamento da duplicação de endereços protege a reputação de envio e garante um bom gerenciamento de quarentena.

Saiba mais [neste caso de uso](../../automating/using/deduplicating-data-imported-file.md).
