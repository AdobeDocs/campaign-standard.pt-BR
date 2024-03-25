---
title: Controle de conteúdo de email no Adobe Campaign Standard
description: Saiba como melhorar a capacidade de entrega no Adobe Campaign Standard ao editar seu conteúdo de email.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: debbc70d-4094-44c0-b7cb-c999effda1a6
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 47%

---

# Controle de conteúdo de email{#control-email-content}

<!--TO KEEP because specific to Campaign-->

Para garantir que seus emails cheguem aos destinatários e melhorem a taxa de capacidade de entrega de email, eles devem respeitar várias regras. Caso contrário, o conteúdo de determinadas mensagens pode ser detectado como spam. O Adobe Campaign fornece várias ferramentas para fazer com que o conteúdo esteja em conformidade com essas regras.

Siga os princípios listados abaixo ao criar o conteúdo da mensagem:

* [Nome e endereço do remetente](#sender-name): o endereço deve identificar explicitamente o remetente. O domínio deve ser de propriedade do remetente e registrado por ele. O registro de domínio não deve ser privatizado.
  <!--**Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).-->
* [Personalização e otimização de tempo de envio](#perso-send-time-optimization): personalizar o conteúdo e definir um tempo de envio por recipient aumenta as chances de sua mensagem ser aberta.
* Imagens e texto: respeitar uma proporção adequada de texto/imagem (por exemplo, 60% de texto e 40% de imagens).
* [Link de unsubscription ](#opt-out) e landing page: o link de unsubscription é essencial. Deve ser visível e válido e o formulário deve ser funcional.
* Pré-visualização: use as ferramentas oferecidas pelo Adobe Campaign para verificar e otimizar o conteúdo do seu email ([Análise antisspam](#anti-spam-analysis), [Renderização de email](#message-responsiveness)).

Para obter dicas adicionais para otimizar a capacidade de entrega ao projetar conteúdo, consulte o [Manual de práticas recomendadas de capacidade de entrega da Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/content-best-practices-for-optimal-delivery.html?lang=pt-BR).

>[!NOTE]
>
>Para obter mais informações sobre edição de conteúdo de email, consulte o [Visão geral do Designer de email](../../designing/using/designing-content-in-adobe-campaign.md) e a variável [Práticas recomendadas de design de mensagem](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices).

## Nome e endereço do remetente {#sender-name}

Determinados ISPs verificam a validade do endereço do remetente (**[!UICONTROL From]**) antes de aceitar mensagens. Um endereço formado incorretamente pode resultar na rejeição pelo servidor de recebimento.

![](assets/delivery_content_edition16.png)

Verifique se um endereço correto é fornecido no nível da instância ou nos cenários usados com mais frequência. Para fazer isso, entre em contato com o administrador.

Para obter mais informações, consulte [Definição do remetente de email de um email](../../designing/using/subject-line.md#email-sender).

## Personalização e otimização de tempo de envio {#perso-send-time-optimization}

Para melhorar a experiência dos recipients e fazer com que eles abram seu email, o Adobe Campaign permite personalizar suas mensagens. Para obter mais informações, consulte [esta seção](../../designing/using/personalization.md).

Para aumentar a taxa de abertura das mensagens, também é possível definir manualmente um tempo de envio por recipient. Cada perfil receberá a mensagem na data e hora especificadas, sempre que possível. Para obter mais informações, consulte [Otimização do tempo de envio](../../sending/using/optimizing-the-sending-time.md).

## Formulário e link para opção de não participação {#opt-out}

Por padrão, quando a mensagem é analisada, uma regra de tipologia verifica se há um link de opt-out e gera um aviso se estiver faltando. Para obter mais informações sobre gerenciamento de links, consulte [nesta seção](../../designing/using/links.md).

Você deve verificar se o link de opt-out funciona corretamente antes de cada vez que enviar. Por exemplo, quando [envio da prova](../../sending/using/sending-proofs.md), verifique se o link é válido, se o formulário está online e se a validação verifica o **[!UICONTROL No longer contact]** caixas. Você deve fazer essa verificação sistematicamente, pois sempre é possível que ocorra um erro humano ao inserir o link ou ao alterar o formulário. Para obter mais informações sobre gerenciamento de aceitação e recusa, consulte [nesta seção](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md).

![](assets/optin_landingpage_3.png)

Se for detectado um problema de cancelamento de subscrição após o início da entrega, ainda será possível realizar um cancelamento de subscrição manualmente (usando a função de atualização em massa, por exemplo) para os destinatários que clicam no link de opt-out, mesmo que não tenham conseguido confirmar sua escolha.

Como regra geral, você não deve tentar impedir os recipients que desejam fazer o opt-out exigindo que eles preencham campos como endereço de email ou nome, por exemplo. A landing page de cancelamento de subscrição deve ter apenas um botão de validação.

Solicitar confirmação adicional não é confiável: um usuário pode ter dois endereços de email redirecionados para a mesma caixa (por exemplo: firstname.lastname@club.com e firstname.lastname@internet-club.com). Se o perfil conseguir lembrar somente o primeiro endereço e desejar cancelar a inscrição por meio de uma mensagem enviada para o outro, o formulário recusará essa ação, pois o identificador criptografado e o endereço de email digitado não corresponderão.

## Análise anti-spam {#anti-spam-analysis}

O editor de mensagens da Adobe Campaign integra uma **Análise antisspam** que permite que você marque emails para determinar se uma mensagem corre o risco de ser considerada spam pelas ferramentas antisspam usadas no recebimento. Para obter mais informações, consulte [Pré-visualização de mensagens](../../sending/using/previewing-messages.md).

No editor de conteúdo de mensagens, clique em **[!UICONTROL Preview]**. Uma mensagem avisa se a verificação antisspam detectar um alto risco para essa mensagem. Clique em **[!UICONTROL Anti-spam analysis]** para exibir detalhes.

![](assets/sending_anti-spam_analysis.png)

## Renderização de email {#message-responsiveness}

Antes de enviar a mensagem, você pode testar a capacidade de resposta dela verificando como a mensagem será exibida em diferentes dispositivos. Isso é para garantir que ela seja exibida de maneira ideal em uma variedade de clientes web, emails da web e dispositivos.

![](assets/inbox_rendering_report_3.png)

Para permitir isso, o Adobe Campaign captura a renderização e a disponibiliza em um relatório dedicado. Assim, você pré-visualiza a mensagem enviada nos diferentes contextos nos quais ela pode ser recebida.

Para obter mais informações, consulte [Renderização de email](../../sending/using/email-rendering.md).
