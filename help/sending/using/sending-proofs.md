---
title: Envio de provas
description: Saiba como enviar provas.
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ff9d0c3ca42606f097a34b1835d285541061e57b

---


# Envio de provas {#sending-proofs}

Uma prova é uma mensagem específica que permite testar uma mensagem antes de enviá-la para o destino principal.

Os destinatários da prova são responsáveis pela aprovação da mensagem (seu conteúdo e formulário). Eles são definidos nos perfis **** de teste. Para obter mais informações, consulte [Gerenciamento de perfis](../../audiences/using/managing-test-profiles.md)de teste.

Para enviar uma prova, os perfis de teste devem ser incluídos no público-alvo da mensagem.

Em uma mensagem:

1. Clique no botão **[!UICONTROL Send a test]**.

   ![](assets/bat_select.png)

1. Selecione o tipo de prova que deseja usar:

   * **[!UICONTROL Email rendering]**: selecione essa opção para testar a forma como sua mensagem é recebida de acordo com as caixas de entrada direcionadas. Para obter mais informações, consulte Renderização [por](../../sending/using/email-rendering.md)email.
   * **[!UICONTROL Proof]**: selecione essa opção para testar a mensagem antes de enviá-la para o destino principal. Os destinatários da prova são responsáveis por aprovar a entrega, verificando tanto seu conteúdo quanto seu formato.
   * **[!UICONTROL Proof + Email rendering]**: essa opção combina as duas opções anteriores.
   ![](assets/bat_select1.png)

1. Confirme sua escolha.

   As provas são enviadas aos perfis de teste.

   ![](assets/bat_select2.png)

1. Você pode exibir suas provas usando a lista **[!UICONTROL Proofs]** suspensa.

   ![](assets/bat_view.png)

1. Selecione uma prova para acessar seu resumo. Para um email, se você selecionou a opção de renderização **de** email como o tipo de prova, o **[!UICONTROL Access email rendering]** ícone será exibido à direita do rótulo de prova. Consulte Renderização [por](../../sending/using/email-rendering.md)email.

   ![](assets/bat_view2.png)

Dependendo dos comentários das pessoas que recebem a prova, você pode ser solicitado a modificar o conteúdo da entrega. Uma vez que as modificações tenham sido feitas, é necessário reiniciar a preparação do email e, em seguida, reenviar uma prova. Cada nova prova pode ser acessada usando o **[!UICONTROL Show proofs]** botão.

É necessário enviar tantas provas quantas forem necessárias até que você tenha concluído o conteúdo de sua entrega. Quando isso estiver concluído, você poderá enviar a entrega para o destino principal e fechar o ciclo de aprovação.

**Tópico relacionado:**

[Envio de um teste, preparação e envio de um vídeo por email](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/sending-test-preparing-sending-email.html)
