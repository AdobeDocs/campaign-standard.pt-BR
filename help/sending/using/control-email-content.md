---
solution: Campaign Standard
product: campaign
title: Controle de conteúdo de email no Adobe Campaign Standard
description: Saiba como melhorar a capacidade de entrega no Adobe Campaign Standard ao editar seu conteúdo de email.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 35%

---


# Controle de conteúdo de e-mail{#control-email-content}

Para melhorar a taxa de entrega de e-mails e garantir que seus e-mails cheguem aos seus recipient, o e-mail deve respeitar um certo número de regras.

* **Nome e endereço** do remetente: O endereço deve identificar explicitamente o remetente. O domínio deve ser de propriedade e registrado no remetente. O registro de domínio não deve ser privatizado.
* **Assunto**: Evite a capitalização e a pontuação excessivas e as palavras frequentemente usadas por spammers (&quot;Win&quot;, &quot;Free&quot; etc.).
* **Personalize seu email**: Personalizar o email aumenta as chances de sua mensagem ser aberta.
* **Imagens e texto**: Respeite uma proporção decente de texto/imagem (por exemplo, 60% de texto e 40% de imagens).
* **Unsubscription e landing page**: O link de unsubscription é essencial. Deve ser visível e válido e o formulário deve ser funcional.
* **Use as ferramentas** oferecidas pela Adobe Campaign para otimizar o conteúdo de seu email (análise do delivery, análise antisspam).

Para obter informações adicionais sobre edição de conteúdo de email, consulte a visão geral [do](../../designing/using/designing-content-in-adobe-campaign.md) Email Designer e as práticas [recomendadas do design de](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices)mensagem.

## Nome e endereço do remetente {#sender-name}

Determinados ISPs verificam a validade do endereço do remetente (From) antes de aceitar mensagens. Um endereço mal formado pode resultar na rejeição pelo servidor de recebimento. É necessário garantir que um endereço correto seja fornecido no nível da instância ou nos cenários usados com mais frequência. Entre em contato com o administrador.

![](assets/delivery_content_edition16.png)

Para obter mais informações, consulte [Personalizar o nome](../../designing/using/personalization.md#personalizing-the-sender)do remetente.

## Linha de assunto {#subject-line}

Ao editar um email, você pode tentar diferentes linhas de assunto e obter uma estimativa de sua taxa de abertura antes de enviá-lo. Para obter mais informações, consulte [Testando a linha de assunto de um email](../../sending/using/testing-subject-line-email.md).

![](assets/predictive_subject_line_example.png)

Para obter mais informações sobre como definir a linha de assunto de um email, consulte [esta seção](../../designing/using/subject-line.md).

## Send time optimization {#send-time-optimization}

Para melhorar a taxa de sucesso de suas mensagens, é possível definir manualmente um tempo de envio por recipient. Cada perfil receberá a mensagem na data e hora especificadas, sempre que possível.

Para obter mais informações, consulte [Otimizar o tempo](../../sending/using/optimizing-the-sending-time.md)de envio.

## Link e formulário de opt-out {#opt-out}

Por padrão, quando a mensagem é analisada, uma regra de tipologia verifica se há um link de opt-out e gera um aviso se estiver faltando.

Você deve verificar se o link de opt-out funciona corretamente antes de cada vez que enviar. Por exemplo, ao enviar a prova, verifique se o link é válido, se o formulário está on-line e se a validação altera o valor das caixas de contato Não é mais marcada. Você deve fazer essa verificação sistematicamente, pois sempre é possível que ocorra um erro humano ao inserir o link ou ao alterar o formulário.

Se for detectado um problema de cancelamento de subscrição após o início do delivery, ainda será possível realizar um cancelamento de subscrição manualmente (usando a função de atualização em massa, por exemplo) para os recipients que clicam no link de opt-out, mesmo que não tenham conseguido confirmar sua escolha.

Como regra geral, não tente impedir os recipients que desejam fazer o opt-out exigindo que eles preencham campos como endereço de email ou nome, por exemplo. A landing page da unsubscription deve ter apenas um botão de validação. Solicitar confirmação adicional não é confiável: um usuário pode ter dois endereços de email redirecionados para a mesma caixa (por exemplo: firstname.lastname@club.com e firstname.lastname@internet-club.com). Se o perfil conseguir lembrar somente o primeiro endereço e desejar cancelar a inscrição por meio de uma mensagem enviada para o outro, o formulário recusará essa inscrição, pois o identificador criptografado e o endereço de email digitado não corresponderão.

## Análise antisspam {#anti-spam-analysis}

O editor de mensagens da Adobe Campaign integra uma análise **** antisspam que permite que você classifique emails para determinar se uma mensagem corre o risco de ser considerada spam pelas ferramentas antisspam usadas no recebimento. For more on this, see [Previewing messages](../../sending/using/previewing-messages.md).

No editor de conteúdo da mensagem, clique em **[!UICONTROL Preview]**. Uma mensagem avisa se a verificação antisspam detectou um alto risco para essa mensagem. Clique **[!UICONTROL Anti-spam analysis]** para obter detalhes sobre a visualização.

![](assets/sending_anti-spam_analysis.png)

## Verificando a capacidade de resposta da mensagem {#message-responsiveness}

Antes de enviar sua mensagem, você pode verificar como ela será exibida em dispositivos diferentes. Isso garante que ele será exibido da melhor forma em diversos clientes da Web, emails e dispositivos.

Para permitir isso, o Adobe Campaign captura a renderização e a disponibiliza em um relatório dedicado. Assim, você pré-visualiza a mensagem enviada nos diferentes contextos nos quais ela pode ser recebida.

Para obter mais informações, consulte [Renderização de email](../../sending/using/email-rendering.md).

![](assets/inbox_rendering_report_3.png)
