---
solution: Campaign Standard
product: campaign
title: Controle de conteúdo de email no Adobe Campaign Standard
description: Saiba como melhorar a capacidade de entrega no Adobe Campaign Standard ao editar seu conteúdo de email.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Avaliação do delivery
role: Profissional
level: Intermediário
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 28%

---


# Controle de conteúdo de e-mail{#control-email-content}

<!--TO KEEP because specific to Campaign-->

Para garantir que seus emails cheguem aos recipients e melhorem a taxa de capacidade de delivery de email, eles devem respeitar várias regras. Caso contrário, o conteúdo de determinadas mensagens pode ser detectado como spam. O Adobe Campaign fornece várias ferramentas para fazer com que o conteúdo esteja em conformidade com essas regras.

Siga os princípios listados abaixo ao criar o conteúdo da sua mensagem:

* [Nome e endereço](#sender-name) do remetente: o endereço deve identificar explicitamente o remetente. O domínio deve ser de propriedade e registrado pelo remetente. O registro de domínio não deve ser privatizado.

   <!--**Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).-->
* [Personalização e otimização](#perso-send-time-optimization) de tempo de envio: personalizar o conteúdo e definir um tempo de envio por recipient aumentam as chances de sua mensagem ser aberta.
* Imagens e texto: respeitar uma proporção decente de texto/imagem (por exemplo, 60% de texto e 40% de imagens).
* [Cancelar ](#opt-out) link de assinatura e landing page: o link unsubscription é essencial. Deve ser visível e válido e o formulário deve ser funcional.
* Visualizar: use as ferramentas oferecidas pelo Adobe Campaign para verificar e otimizar o conteúdo do seu email ([Análise antisspam](#anti-spam-analysis), [Renderização de email](#message-responsiveness)).

Para obter dicas adicionais para otimizar a capacidade de entrega ao projetar conteúdo, consulte o [Guia de práticas recomendadas de capacidade de entrega do Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/content-best-practices-for-optimal-delivery.html).

>[!NOTE]
>
>Para obter mais informações sobre edição de conteúdo de email, consulte a [Visão geral do Designer de email](../../designing/using/designing-content-in-adobe-campaign.md) e as [Práticas recomendadas de design de mensagens](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices).

## Nome e endereço do remetente {#sender-name}

Determinados ISPs verificam a validade do endereço do remetente (**[!UICONTROL From]**) antes de aceitar mensagens. Um endereço mal formado pode resultar na rejeição pelo servidor de recebimento.

![](assets/delivery_content_edition16.png)

Você deve garantir que um endereço correto seja fornecido no nível da instância ou nos cenários usados com mais frequência. Para fazer isso, entre em contato com o administrador.

Para obter mais informações, consulte [Definição do remetente de email de um email](../../designing/using/subject-line.md#email-sender).

## Personalização e otimização de tempo de envio {#perso-send-time-optimization}

Para melhorar a experiência dos recipients e abri-los, o Adobe Campaign permite personalizar suas mensagens. Para obter mais informações, consulte [esta seção](../../designing/using/personalization.md).

Para aumentar a taxa de abertura das mensagens, também é possível definir manualmente uma hora de envio por recipient. Cada perfil receberá a mensagem na data e hora especificadas, sempre que possível. Para obter mais informações, consulte [Otimizando o tempo de envio](../../sending/using/optimizing-the-sending-time.md).

## Link e formulário de opt-out {#opt-out}

Por padrão, quando a mensagem é analisada, uma regra de tipologia verifica se há um link de opt-out e gera um aviso se estiver faltando. Para obter mais informações sobre gerenciamento de links, consulte [esta seção](../../designing/using/links.md).

Você deve verificar se o link de opt-out funciona corretamente antes de cada vez que enviar. Por exemplo, ao [enviar a prova](../../sending/using/sending-proofs.md), verifique se o link é válido, se o formulário está online e se a validação está marcada nas caixas **[!UICONTROL No longer contact]**. Você deve fazer essa verificação sistematicamente, pois sempre é possível que ocorra um erro humano ao inserir o link ou ao alterar o formulário. Para obter mais informações sobre o gerenciamento de aceitação e recusa, consulte [esta seção](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md).

![](assets/optin_landingpage_3.png)

Se for detectado um problema de cancelamento de subscrição após o início do delivery, ainda será possível realizar um cancelamento de subscrição manualmente (usando a função de atualização em massa, por exemplo) para os recipients que clicam no link de opt-out, mesmo que não tenham conseguido confirmar sua escolha.

Como regra geral, você não deve tentar impedir os recipients que desejam recusar exigindo que eles preencham campos como endereço de email ou nome, por exemplo. A landing page de unsubscription deve ter apenas um botão de validação.

Solicitar confirmação adicional não é confiável: um usuário pode ter dois endereços de email redirecionados para a mesma caixa (por exemplo: firstname.lastname@club.com e firstname.lastname@internet-club.com). Se o perfil conseguir lembrar somente o primeiro endereço e desejar cancelar a assinatura por meio de uma mensagem enviada para o outro, o formulário recusará essa ação, pois o identificador criptografado e o endereço de email inserido não corresponderão.

## Análise antisspam {#anti-spam-analysis}

O editor de mensagens de Adobe Campaign do integra uma **Análise antisspam** que permite que você marque emails para determinar se uma mensagem corre o risco de ser considerada spam pelas ferramentas antisspam usadas no recebimento. Para obter mais informações, consulte [Pré-visualização de mensagens](../../sending/using/previewing-messages.md).

No editor de conteúdo da mensagem, clique em **[!UICONTROL Preview]**. Uma mensagem avisa se a verificação antisspam detectou um alto risco para essa mensagem. Clique em **[!UICONTROL Anti-spam analysis]** para visualizar os detalhes.

![](assets/sending_anti-spam_analysis.png)

## Renderização de email {#message-responsiveness}

Antes de enviar sua mensagem, você pode testar sua capacidade de resposta da mensagem, verificando como sua mensagem será exibida em diferentes dispositivos. Isso garante que ele seja exibido de maneira ideal em uma variedade de clientes Web, Webmails e dispositivos.

![](assets/inbox_rendering_report_3.png)

Para permitir isso, o Adobe Campaign captura a renderização e a disponibiliza em um relatório dedicado. Assim, você pré-visualiza a mensagem enviada nos diferentes contextos nos quais ela pode ser recebida.

Para obter mais informações, consulte [Renderização de email](../../sending/using/email-rendering.md).