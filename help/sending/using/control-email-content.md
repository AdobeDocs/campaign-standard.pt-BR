---
title: Controle de conteúdo de email no Adobe Campaign Standard
description: Saiba como melhorar a capacidade de entrega no Adobe Campaign Standard ao editar seu conteúdo de email.
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
source-git-commit: f0580e1ab75d4250bfb1cb801ff08b31b91cdc5a

---


# Controle de conteúdo de email{#control-email-content}

Para melhorar a taxa de entrega de email e garantir que seus emails cheguem aos destinatários, o email deve respeitar um certo número de regras.

* **Nome e endereço** do remetente: O endereço deve identificar explicitamente o remetente. O domínio deve ser de propriedade e registrado no remetente. O registro de domínio não deve ser privatizado.
* **Assunto**: Evite a capitalização e a pontuação excessivas e as palavras frequentemente usadas por spammers ("Win", "Free" etc.).
* **Personalize seu email**: Personalizar o email aumenta as chances de sua mensagem ser aberta.
* **Imagens e texto**: Respeite uma proporção decente de texto/imagem (por exemplo, 60% de texto e 40% de imagens).
* **Cancelar assinatura do link e da página** inicial: O link para cancelar a assinatura é essencial. Deve ser visível e válido e o formulário deve ser funcional.
* **Use as ferramentas** oferecidas pelo Adobe Campaign para otimizar o conteúdo de seu email (análise de entrega, análise antispam).

Para obter informações adicionais sobre edição de conteúdo de email, consulte a visão geral [do](../../designing/using/designing-content-in-adobe-campaign.md) Email Designer e as práticas [recomendadas do design de](../../designing/using/overview.md#content-design-best-practices)mensagem.

## Nome e endereço do remetente {#sender-name}

Determinados ISPs verificam a validade do endereço do remetente (De) antes de aceitar mensagens. Um endereço mal formado pode resultar na sua rejeição pelo servidor de recebimento. É necessário garantir que um endereço correto seja fornecido no nível da instância ou nos cenários usados com mais frequência. Entre em contato com o administrador.

![](assets/delivery_content_edition16.png)

Para obter mais informações, consulte [Personalizar o nome](../../designing/using/personalization.md#personalizing-the-sender)do remetente.

## Linha de assunto {#subject-line}

Ao editar um email, você pode tentar diferentes linhas de assunto e obter uma estimativa de sua taxa de abertura antes de enviá-lo. Para obter mais informações, consulte [Testando a linha de assunto de um email](../../sending/using/testing-subject-line-email.md).

![](assets/predictive_subject_line_example.png)

Para obter mais informações sobre como definir a linha de assunto de um email, consulte [esta seção](../../designing/using/subject-line.md).

## Enviar otimização de tempo {#send-time-optimization}

Para melhorar a taxa de sucesso de suas mensagens, é possível definir manualmente uma hora de envio por destinatário. Cada perfil receberá a mensagem na data e hora especificadas, sempre que possível.

Para obter mais informações, consulte [Otimizar o tempo](../../sending/using/optimizing-the-sending-time.md)de envio.

## Link e formulário de recusa {#opt-out}

Por padrão, quando a mensagem é analisada, uma regra de tipologia verifica se um link de opção de não participação foi incluído e gera um aviso se estiver faltando.

Você deve verificar se o link para opção de não participação funciona corretamente antes de cada vez que enviar. Por exemplo, ao enviar a prova, verifique se o link é válido, se o formulário está on-line e se a validação disso altera o valor das caixas de contato Não estão mais marcadas. Você deve fazer essa verificação sistematicamente, pois o erro humano é sempre possível ao inserir o link ou ao alterar o formulário.

Se for detectado um problema de cancelamento de assinatura após a entrega ser iniciada, ainda será possível realizar uma cancelamento de assinatura manualmente (usando a função de atualização em massa, por exemplo) para os destinatários que clicam no link para opção de não participação, mesmo que não tenham conseguido confirmar sua escolha.

Como regra geral, não tente impedir os destinatários que desejam recusar exigindo que eles preencham campos como seu endereço de email ou nome, por exemplo. A página inicial de cancelamento de assinatura deve ter apenas um botão de validação. Solicitar confirmação adicional não é confiável: um usuário pode ter dois endereços de email redirecionados para a mesma caixa (por exemplo: firstname.lastname@club.com e firstname.lastname@internet-club.com). Se o perfil puder lembrar somente o primeiro endereço e desejar cancelar a inscrição por meio de uma mensagem enviada para o outro, o formulário recusará isso, pois o identificador criptografado e o endereço de email digitado não corresponderão.

## Análise antisspam {#anti-spam-analysis}

O editor de mensagens do Adobe Campaign integra uma análise **** antisspam que permite que você classifique emails para determinar se uma mensagem corre o risco de ser considerada spam pelas ferramentas antisspam usadas após o recebimento. Para obter mais informações, consulte [Visualizar mensagens](../../sending/using/previewing-messages.md).

No editor de conteúdo da mensagem, clique em **[!UICONTROL Preview]**. Uma mensagem avisa se a verificação antisspam detectou um alto risco para essa mensagem. Clique para exibir **[!UICONTROL Anti-spam analysis]** os detalhes.

![](assets/sending_anti-spam_analysis.png)

## Verificando a capacidade de resposta da mensagem {#message-responsiveness}

Antes de enviar sua mensagem, você pode verificar como ela será exibida em dispositivos diferentes. Isso garante que ele será exibido da melhor forma em diversos clientes da Web, emails e dispositivos.

Para permitir isso, o Adobe Campaign captura a renderização e a disponibiliza em um relatório dedicado. Isso permite que você visualize a mensagem enviada nos diferentes contextos em que ela pode ser recebida.

Para obter mais informações, consulte Renderização [por](../../sending/using/email-rendering.md)email.

![](assets/inbox_rendering_report_3.png)
