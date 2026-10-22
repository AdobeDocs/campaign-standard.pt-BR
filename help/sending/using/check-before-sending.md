---
title: Verificar antes de enviar
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: true
description: Quando a mensagem estiver pronta, saiba como executar todas as verificações antes de enviar
feature: Deliverability
role: User
level: Intermediate
exl-id: dfc5fc00-87aa-4d22-ad7c-cc0ba1ee21be
TQID: 'https://experienceleague.adobe.com/3qM5opRzD4u8HV5PALkfERzsLnWx1AsLuaDs8frG-Ic'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: 63876777-85c3-57e1-a2da-81f02956c63c
    internal-label: Deliverability
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 90%
---
# Executar todas as verificações antes de enviar {#perform-all-checks}

Quando a mensagem estiver pronta, certifique-se de que seu conteúdo está sendo exibido corretamente, em todos os dispositivos, e de que não contém erros, como personalização incorreta ou links quebrados.

Antes de enviar a mensagem, verifique também se os parâmetros e a configuração estão consistentes com a entrega.

## Importância da validação {#validation-is-key}

Antes de enviar uma entrega, você precisa garantir que seus destinatários receberão a mensagem que você realmente deseja enviar. Para fazer isso é necessário validar o conteúdo da mensagem e os parâmetros da entrega.

Esta etapa permite detectar e corrigir possíveis erros antes de fazer uma entrega ao público-alvo principal.

As etapas para validar uma entrega são apresentadas [nesta seção](../../sending/using/get-started-sending-messages.md#prepare-test-send).

## Renderização de email {#email-rendering}

Antes de clicar no botão **[!UICONTROL Send]**, verifique se a sua mensagem será exibida com eficiência em uma variedade de clientes Web, Webmails e dispositivos.

Para permitir isso, o Adobe Campaign captura a renderização e a disponibiliza em um relatório dedicado. Assim, você pré-visualiza a mensagem enviada nos diferentes contextos nos quais ela pode ser recebida.

**Dicas**:

* Você pode visualizar a mensagem enviada nos diferentes contextos nos quais ela pode ser recebida: webmail, serviço de mensagens, celular, etc.

* Os recursos de renderização de email são cruciais para identificar se suas campanhas de email terão êxito em atravessar os filtros dos principais ISPs (Provedores de serviço de internet) e serviços de webmail. Essas ferramentas enviam uma cópia de pré-impressão de um email para uma rede de caixas de entrada de teste, para que você possa ver como a mensagem será exibida ou irá renderizar nesses serviços. Elas também podem incluir relatórios e opções de correção de código que ajudam a identificar e fazer correções rapidamente que melhoram a capacidade de entrega.

Saiba mais [nesta seção](../../sending/using/email-rendering.md).

## Mensagens de prova {#proof-messages}

O envio de provas permite verificar o link de opção de não participação, a mirror page e quaisquer outros links, validar a mensagem, verificar a exibição das imagens, detectar possíveis erros etc. Você também pode verificar o seu design e a renderização em diferentes dispositivos.

Saiba mais [nesta seção](../../sending/using/sending-proofs.md).

## Configurar entregas de teste A/B {#a-b-testing-deliveries}

Se você tiver vários conteúdos para uma entrega de email, poderá usar o teste A/B para descobrir qual versão terá o maior impacto na população direcionada.

**Dicas**:

* Envie as diferentes versões para alguns dos seus destinatários

* Selecione aquela com a maior taxa de sucesso e envie-a para o restante do seu público-alvo

Saiba mais [nesta seção](../../channels/using/designing-an-a-b-test-email.md).
