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
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 38%

---


# Controle de conteúdo de e-mail{#control-email-content}

Para melhorar a taxa de delivery de email e garantir que seus emails cheguem aos recipients, o email deve respeitar um determinado número de regras.

* **Nome e endereço** do remetente: O endereço deve identificar explicitamente o remetente. O domínio deve ser de propriedade e registrado pelo remetente. O registro de domínio não deve ser privatizado.
* **Assunto**: Evite capitalização e pontuação excessivas e palavras usadas com frequência por remetentes de spam (&quot;Win&quot;, &quot;Free&quot; etc.).
* **Personalize seu email**: Personalizar o email aumenta as chances de sua mensagem ser aberta.
* **Imagens e texto**: Respeite uma proporção decente de texto/imagem (por exemplo, 60% de texto e 40% de imagens).
* **Link de cancelamento de assinatura e landing page**: O link de cancelamento de subscrição é essencial. Deve ser visível e válido e o formulário deve ser funcional.
* **Use as** ferramentas fornecidas pelo Adobe Campaign para otimizar o conteúdo do seu email (análise de delivery, análise antisspam).

Para obter informações adicionais sobre edição de conteúdo de email, consulte a [Visão geral do Designer de email](../../designing/using/designing-content-in-adobe-campaign.md) e as [Práticas recomendadas de design de mensagens](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices).

## Nome e endereço do remetente {#sender-name}

Determinados ISPs verificam a validade do endereço do remetente (From) antes de aceitar mensagens. Um endereço mal formado pode resultar na rejeição pelo servidor de recebimento. Você deve garantir que um endereço correto seja fornecido no nível da instância ou nos cenários usados com mais frequência. Entre em contato com o administrador.

![](assets/delivery_content_edition16.png)

Para obter mais informações, consulte [Personalização do nome do remetente](../../designing/using/personalization.md#personalizing-the-sender).

## Enviar otimização de tempo {#send-time-optimization}

Para melhorar a taxa de sucesso de suas mensagens, é possível definir manualmente uma hora de envio por recipient. Cada perfil receberá a mensagem na data e hora especificadas, sempre que possível.

Para obter mais informações, consulte [Otimizando o tempo de envio](../../sending/using/optimizing-the-sending-time.md).

## Link e formulário de opt-out {#opt-out}

Por padrão, quando a mensagem é analisada, uma regra de tipologia verifica se há um link de opt-out e gera um aviso se estiver faltando.

Você deve verificar se o link de opt-out funciona corretamente antes de cada vez que enviar. Por exemplo, ao enviar a prova, verifique se o link é válido, se o formulário está online e se a validação altera o valor das caixas No longer contact estão marcadas. Você deve fazer essa verificação sistematicamente, pois sempre é possível que ocorra um erro humano ao inserir o link ou ao alterar o formulário.

Se for detectado um problema de cancelamento de subscrição após o início do delivery, ainda será possível realizar um cancelamento de subscrição manualmente (usando a função de atualização em massa, por exemplo) para os recipients que clicam no link de opt-out, mesmo que não tenham conseguido confirmar sua escolha.

Como regra geral, não tente impedir os recipients que desejam fazer o opt-out exigindo que eles preencham campos como endereço de email ou nome, por exemplo. A landing page de unsubscription deve ter apenas um botão de validação. Solicitar confirmação adicional não é confiável: um usuário pode ter dois endereços de email redirecionados para a mesma caixa (por exemplo: firstname.lastname@club.com e firstname.lastname@internet-club.com). Se o perfil conseguir lembrar somente o primeiro endereço e desejar cancelar a assinatura por meio de uma mensagem enviada para o outro, o formulário recusará essa ação, pois o identificador criptografado e o endereço de email inserido não corresponderão.

## Análise antisspam {#anti-spam-analysis}

O editor de mensagens de Adobe Campaign do integra uma **Análise antisspam** que permite que você marque emails para determinar se uma mensagem corre o risco de ser considerada spam pelas ferramentas antisspam usadas no recebimento. Para obter mais informações, consulte [Pré-visualização de mensagens](../../sending/using/previewing-messages.md).

No editor de conteúdo da mensagem, clique em **[!UICONTROL Preview]**. Uma mensagem avisa se a verificação antisspam detectou um alto risco para essa mensagem. Clique em **[!UICONTROL Anti-spam analysis]** para visualizar os detalhes.

![](assets/sending_anti-spam_analysis.png)

## Verificando a capacidade de resposta da mensagem {#message-responsiveness}

Antes de enviar sua mensagem, você pode verificar como sua mensagem será em diferentes dispositivos. Isso garante que ele seja exibido de maneira ideal em uma variedade de clientes Web, Webmails e dispositivos.

Para permitir isso, o Adobe Campaign captura a renderização e a disponibiliza em um relatório dedicado. Assim, você pré-visualiza a mensagem enviada nos diferentes contextos nos quais ela pode ser recebida.

Para obter mais informações, consulte [Renderização de email](../../sending/using/email-rendering.md).

![](assets/inbox_rendering_report_3.png)
