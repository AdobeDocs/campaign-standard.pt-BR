---
title: Verificar antes de enviar
seo-title: Verificar antes de enviar
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b80197491b45cff46273e1a41e3dfb7a939f96c5
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 93%

---


# Executar todas as verificações antes de enviar {#perform-all-checks}

Quando a mensagem estiver pronta, certifique-se de que seu conteúdo está sendo exibido corretamente, em todos os dispositivos, e de que não contém erros, como personalização incorreta ou links quebrados.

Antes de enviar a mensagem, verifique também se os parâmetros e a configuração estão consistentes com o delivery.

## Por que a validação é a chave {#validation-is-key}

Antes de enviar um delivery, você precisa garantir que seus recipients receberão a mensagem que você realmente deseja enviar. Para fazer isso é necessário validar o conteúdo da mensagem e os parâmetros do delivery.

Esta etapa permite detectar e corrigir possíveis erros antes de fazer um delivery ao público-alvo principal.

As etapas para validar um delivery são apresentadas [nesta seção](../../sending/using/get-started-sending-messages.md#prepare-test-send).

## Renderização de email {#email-rendering}

Antes de clicar no botão **[!UICONTROL Send]**, verifique se a sua mensagem será exibida com eficiência em uma variedade de clientes Web, Webmails e dispositivos.

Para permitir isso, o Adobe Campaign captura a renderização e a disponibiliza em um relatório dedicado. Assim, você pré-visualiza a mensagem enviada nos diferentes contextos nos quais ela pode ser recebida.

**Dicas**:

* Você pode visualizar a mensagem enviada nos diferentes contextos nos quais ela pode ser recebida: webmail, serviço de mensagens, celular, etc.

* Os recursos de renderização de e-mail são fundamentais para identificar se suas campanhas de e-mail ultrapassam com êxito os filtros dos principais ISPs (Provedores de serviço de Internet) e serviços de e-mail. Essas ferramentas enviam uma cópia de pré-impressão de um email para uma rede de caixas de entrada de teste, para que você possa ver como a mensagem será exibida ou irá renderizar nesses serviços. Elas também podem incluir relatórios e opções de correção de código que ajudam a identificar e fazer correções rapidamente que melhoram a capacidade de entrega.

Saiba mais [nesta seção](../../sending/using/email-rendering.md).

## Mensagens de prova {#proof-messages}

O envio de provas permite a verificação do link de opção de não participação, a mirror page e quaisquer outros links, validação da mensagem, verificação da exibição das imagens, detecção de possíveis erros, etc. Você também pode verificar seu design e renderização em diferentes dispositivos.

Saiba mais [nesta seção](../../sending/using/sending-proofs.md).

## Configurar deliveries de teste A/B {#a-b-testing-deliveries}

Se você tiver vários conteúdos para um delivery de email, poderá usar o teste A/B para descobrir qual versão terá o maior impacto na população direcionada.

**Dicas**:

* Envie as diferentes versões para alguns dos seus recipients

* Selecione aquela com a maior taxa de sucesso e envie-a para o restante do seu público-alvo

Saiba mais [nesta seção](../../channels/using/designing-an-a-b-test-email.md).
