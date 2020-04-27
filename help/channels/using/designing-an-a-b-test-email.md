---
title: Criação de um email de teste A/B
description: Descubra a funcionalidade de teste A/B e siga estas etapas para criar um email a partir de um modelo de teste A/B no Adobe Campaign.
page-status-flag: never-activated
uuid: 104f6973-68a7-4692-a90a-a5570a980ec7
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: e249ba70-90d0-43f2-868c-ce9fdc7e642d
context-tags: delivery,abTesting,back;deliveryCreation,wizard;delivery,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# Criação de um email de teste A/B{#designing-an-a-b-test-email}

A funcionalidade de teste A/B no Adobe Campaign permite que você defina duas a três variantes de email. Cada variante é enviada para amostras de população, a fim de determinar qual tem o melhor resultado. Uma vez determinada, a variante vencedora é então enviada para a população restante.

Você pode optar por variar o conteúdo, o assunto ou o remetente do email.

>[!NOTE]
>
>Não é possível realizar testes A/B em emails criados no Adobe Experience Manager.

## Creating an A/B test email {#creating-an-a-b-test-email}

Um teste A/B pode ser criado usando o assistente padrão de criação de email, ao qual uma etapa de configuração de teste A/B é adicionada. A criação de um email padrão é detalhada na seção [Criação de um email](../../channels/using/creating-an-email.md) .

No contexto específico de um teste A/B:

1. Crie um novo e-mail a partir de um dos três modelos específicos de teste A/B, de acordo com o elemento que deseja variar:

   * Teste A/B no remetente
   * Teste A/B sobre conteúdo
   * Teste A/B sobre o assunto
   ![](assets/create_ab_testing.png)

   >[!NOTE]
   >
   >Os modelos de teste A/B e de acompanhamento estão ocultos por padrão. Marque a caixa de teste A/B no lado esquerdo (painel lateral) para **[!UICONTROL Filter]** exibi-los.

1. Defina as propriedades gerais e a audiência do público alvo do email, assim como para um email padrão. Consulte a seção [Criação de audiências](../../audiences/using/creating-audiences.md) .
1. Na quarta etapa do assistente de criação, defina os parâmetros de teste A/B:

   * **[!UICONTROL Number of variants]**: Você pode optar por usar duas ou três variantes. Se você escolher três variantes, essa opção não poderá ser modificada depois que essa etapa for confirmada no assistente.
   * **[!UICONTROL Winning strategy]**: Selecione o critério a ser usado para determinar a variante vencedora.
   * **[!UICONTROL Target breakdown]**: Escolha qual porcentagem do público alvo receberá cada variante. A porcentagem restante receberá a variante vencedora depois de determinada. Os perfis direcionados são selecionados aleatoriamente.
   * **[!UICONTROL Winner sending method]**: Escolha se deseja que a variante vencedora seja enviada automaticamente depois de determinada ou se deseja confirmar manualmente o envio para a população restante.
   * **[!UICONTROL Test duration]**: Especifique a duração do teste. A variante vencedora é determinada automaticamente após essa duração. Você pode escolher manualmente a variante vencedora antes do final do teste no painel de email.

      O teste deve ser de, pelo menos, uma hora para que todos os dados de rastreamento sejam coletados e tidos corretamente em conta para selecionar a variante vencedora.
   ![](assets/ab_parameters.png)

1. Depois que os parâmetros de teste A/B forem definidos, passe para a próxima etapa do assistente e defina o conteúdo do email. Dependendo do modelo escolhido, é possível definir vários assuntos, vários nomes de remetentes ou vários conteúdos diferentes. Use o carrossel para navegar entre as diferentes variantes do elemento. Para obter mais informações, consulte a seção do editor [de](../../designing/using/designing-content-in-adobe-campaign.md) conteúdo.

   ![](assets/create_ab_testing2.png)

1. Confirme a criação do email. O painel de email será exibido.
1. Agende o envio. A data definida indica o start do teste A/B.
1. Verifique os parâmetros de teste A/B exibidos no **[!UICONTROL A/B test parameters]** bloco. Você pode modificá-los até confirmar o envio do teste (etapa 9) selecionando o bloco.

   ![](assets/create_ab_testing3.png)

1. Prepare o envio de email para analisar o público alvo e o número de mensagens a serem enviadas. Consulte a seção [Preparando o envio](../../sending/using/preparing-the-send.md) .
1. Antes de enviar o teste A/B, verifique seu email enviando provas.
1. Após a conclusão da preparação, confirme o envio do teste. Depois de confirmado, os parâmetros de teste A/B não podem ser modificados.

   O teste A/B start na data definida na **[!UICONTROL Schedule]**. É possível rastrear o progresso usando os blocos **[!UICONTROL A/B test]** e **[!UICONTROL Deployment]** .

   Você pode selecionar manualmente a variante vencedora a qualquer momento se desejar reduzir a duração do teste.

   Quando o teste for concluído, uma tabela de resumo será exibida no **[!UICONTROL A/B Test]** bloco e isso permitirá que você visualização os vários indicadores para as diferentes variantes que foram testadas.

1. Se você tiver selecionado **[!UICONTROL Send after confirmation]** como o método de envio, é necessário selecionar manualmente a variante vencedora para que o start a envie para a população restante. Se você tiver selecionado **[!UICONTROL Automatic]**, a variante vencedora será enviada automaticamente para a população restante assim que for determinada pelo sistema.

   >[!NOTE]
   >
   >Se houver um vínculo, a variante vencedora deverá ser selecionada manualmente. Você pode notificar o criador e modificador(es) de email que uma variante foi selecionada ou precisa ser selecionada. Consulte Notificações [de Adobe Campaign](../../administration/using/sending-internal-notifications.md).

Seu email agora está definido e enviado. Você pode acessar seus registros e relatórios para medir o sucesso de sua campanha.

**Tópicos relacionados**:

[Criação de um vídeo de email](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/create-email-from-homepage.html)

## Sobre indicadores de teste A/B {#about-a-b-test-indicators}

No painel de email, vários indicadores estão disponíveis para ajudá-lo a medir seu teste A/B: número de cliques, aberturas, rejeições e assim por diante.

Observe que o **[!UICONTROL Estimated recipient reactivity]** indicador é uma taxa comparando o número de recipient que clicaram com o número de recipient que abriram o email. Por exemplo, se 10 recipient abriram o email e 5 recipient clicaram nele. A taxa de reatividade é de 50%.
