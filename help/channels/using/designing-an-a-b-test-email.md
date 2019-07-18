---
title: Projetar um e-mail de teste A/B
seo-title: Projetar um e-mail de teste A/B
description: Projetar um e-mail de teste A/B
seo-description: Descubra a funcionalidade de teste A/B e siga estas etapas para criar um email a partir de um modelo de teste A/B no Adobe Campaign.
page-status-flag: nunca ativado
uuid: 104 f 6973-68 a 7-4692-a 90 a-a 5570 a 980 ec 7
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: por email
discoiquuid: e 249 ba 70-90 d 0-43 f 2-868 c-ce 9 fdc 7 e 642 d
context-tags: entrega, abtesting, back; Deliverycreation, assistente; entrega, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d50d486ed77cb7989df47133bb49fde3227ae3a5

---


# Designing an A/B test email{#designing-an-a-b-test-email}

A funcionalidade de teste A/B no Adobe Campaign permite que você defina duas a três variantes de email. Cada variação é enviada a amostras de população para determinar que tem o melhor resultado. Depois de determinado, a variante vencedora é enviada para a restante população.

Você pode escolher variar o conteúdo, o assunto ou o remetente do e-mail.

>[!NOTE]
>
>Testes A/B em e-mails criados no Adobe Experience Manager não são possíveis.

## Creating an A/B test email {#creating-an-a-b-test-email}

Um teste A/B pode ser criado usando o assistente padrão de criação de email, ao qual uma etapa de configuração de teste A/B é adicionada. Creating a standard email is detailed in the [Creating an email](../../channels/using/creating-an-email.md) section.

No contexto específico de um teste A/B:

1. Crie um novo email de um dos três modelos A/B específicos, de acordo com o elemento que você deseja variar:

   * Teste A/B no remetente
   * Teste A/B no conteúdo
   * Teste A/B no assunto
   ![](assets/create_ab_testing.png)

   >[!NOTE]
   >
   >Os modelos de teste A/B/B estão ocultos por padrão. Check the A/B test box on the left side ( **[!UICONTROL Filter]** lateral panel) to display them.

1. Defina as propriedades gerais e o público-alvo do email, como para um email padrão. Refer to the [Creating audiences](../../audiences/using/creating-audiences.md) section.
1. Na quarta etapa do assistente de criação, defina os parâmetros de teste A/B:

   * **[!UICONTROL Number of variants]**: Você pode optar por usar duas ou três variantes. Se você escolher três variantes, essa escolha não poderá ser modificada após a confirmação dessa etapa no assistente.
   * **[!UICONTROL Winning strategy]**: Selecione o critério a ser usado para determinar a variante vencedora.
   * **[!UICONTROL Target breakdown]**: Escolha qual porcentagem do destino receberá cada variação. A porcentagem restante receberá a variante vencedora uma vez que ela foi determinada. Os perfis direcionados são selecionados aleatoriamente.
   * **[!UICONTROL Winner sending method]**: Escolha se deseja que a variante vencedora seja enviada automaticamente uma vez que tenha sido determinada ou se você deseja confirmar manualmente o envio para a restante população.
   * **[!UICONTROL Test duration]**: Especifique a duração do teste. A variante vencedora é determinada automaticamente após essa duração. É possível escolher manualmente a variante vencedora antes do final do teste do painel de e-mail.

      O teste deve ter pelo menos uma hora para que todos os dados de rastreamento sejam coletados e devidamente considerados para selecionar a variante vencedora.
   ![](assets/ab_parameters.png)

1. Depois que os parâmetros de teste A/B forem definidos, passe para a próxima etapa do assistente e defina o conteúdo de email. Dependendo do modelo escolhido, você pode definir vários assuntos, vários nomes de remetentes ou vários conteúdos diferentes. Use o carrossel para navegar entre as diferentes variantes do elemento. For more information, consult the [content editor](../../designing/using/about-email-content-design.md) section.

   ![](assets/create_ab_testing2.png)

1. Confirme a criação do email. O painel de e-mail será exibido.
1. Programe o envio. A data definida indica o início do teste A/B.
1. Check the A/B test parameters displayed in the **[!UICONTROL A/B test parameters]** block. É possível modificá-los até confirmar o envio do teste (etapa 9) selecionando o bloco.

   ![](assets/create_ab_testing3.png)

1. Prepare o envio do email para analisar a meta e o número de mensagens a serem enviadas. Consult the [Preparing the send](../../sending/using/preparing-the-send.md) section.
1. Antes de enviar o teste A/B, verifique seu email enviando provas.
1. Após concluir a preparação, confirme o envio do teste. Uma vez confirmado, os parâmetros de teste A/B não podem ser modificados.

   The A/B test starts on the date defined in the **[!UICONTROL Schedule]**.You can track its progress using the **[!UICONTROL A/B test]** and **[!UICONTROL Deployment]** blocks.

   Você pode selecionar manualmente a variante vencedora a qualquer momento se desejar recortar a duração do teste curta.

   Once testing has finished, a summary table is displayed in the **[!UICONTROL A/B Test]** block and this allows you to view the various indicators for the different variants that were tested.

1. If you have selected **[!UICONTROL Send after confirmation]** as the sending method, you have to manually select the winning variant to start sending it to the remaining population. If you have selected **[!UICONTROL Automatic]**, the winning variant is automatically sent to the remaining population as soon as it has been determined by the system.

   >[!NOTE]
   >
   >Se houver um vínculo, a variante vencedora deverá ser selecionada manualmente. Você pode notificar o criador e modificador de e-mail que uma variante foi escolhida ou que precisa ser selecionada. See [Adobe Campaign notifications](../../administration/using/sending-internal-notifications.md).

Seu e-mail agora é definido e enviado. Você pode acessar seus logs e relatórios para medir o sucesso da sua campanha.

**Tópico relacionado**:

[Criação de](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-email-from-homepage-feature-video-use.html) um vídeo por email

## About A/B test indicators {#about-a-b-test-indicators}

No painel de e-mail, vários indicadores estão disponíveis para ajudar a medir o teste A/B: número de cliques, abre, rejeita e assim por diante.

Note that the **[!UICONTROL Estimated recipient reactivity]** indicator is a rate comparing the number of recipients who clicked against the number of recipients who opened the email. Por exemplo, se 10 destinatários abrirem o email e 5 destinatários clicaram nele. A taxa de reatividade é 50%.
