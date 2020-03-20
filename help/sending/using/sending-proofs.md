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
source-git-commit: f7f90991ed4c7323e3a2f8ac7d38da9ff165ef76

---


# Envio de provas {#sending-proofs}

## Sobre provas {#about-proofs}

Uma prova é uma mensagem específica que permite testar uma mensagem antes de enviá-la para o destino principal. Os destinatários da prova são responsáveis pela aprovação da mensagem (seu conteúdo e formulário).

Há dois tipos de destinatários de prova:

* **Os perfis** de teste permitem direcionar destinatários adicionais que não correspondem aos critérios de definição de metas definidos.

   Eles podem ser adicionados ao público-alvo de uma mensagem para detectar qualquer uso fraudulento do banco de dados do destinatário ou para garantir que os e-mails cheguem às caixas de entrada. Para obter mais informações, consulte [Gerenciamento de perfis](../../audiences/using/managing-test-profiles.md)de teste.

   >[!NOTE]
   >
   >Para enviar uma prova, os perfis de teste devem ser incluídos no público-alvo da sua mensagem.

* **Os perfis** de substituição permitem que você se posicione na posição de um dos perfis direcionados e obtenha uma representação exata da mensagem que o perfil receberá. Para obter mais informações, consulte [Testar mensagens de email usando perfis](../../sending/using/testing-messages-using-target.md)direcionados.

   >[!NOTE]
   >
   >Este recurso está disponível somente para o canal de email.

## Envio de uma prova {#sending-a-proof}

Para enviar provas, siga estas etapas:

1. Verifique se os destinatários das provas foram configurados:
   * **Os perfis** de teste devem ser incluídos no público-alvo da sua mensagem.
   * **Os perfis** de substituição devem ser adicionados assim que a preparação da mensagem for bem-sucedida (consulte [esta seção](../../sending/using/testing-messages-using-target.md)).

1. Clique no botão **[!UICONTROL Send a test]**.

   ![](assets/bat_select.png)

1. Selecione o tipo de prova que deseja usar:

   * **[!UICONTROL Email rendering]**: selecione essa opção para testar a forma como sua mensagem é recebida de acordo com as caixas de entrada direcionadas. Para obter mais informações, consulte Renderização [por](../../sending/using/email-rendering.md)email.
   * **[!UICONTROL Proof]**: selecione essa opção para testar a mensagem antes de enviá-la para o destino principal. Os destinatários da prova são responsáveis por aprovar a entrega, verificando tanto seu conteúdo quanto seu formato.
   * **[!UICONTROL Proof + Email rendering]**: essa opção combina as duas opções anteriores.
   ![](assets/bat_select1.png)

   >[!NOTE]
   >
   >A renderização por email está disponível somente com perfis de teste. Se nenhum perfil de teste tiver sido adicionado à mensagem, somente a **[!UICONTROL Proof]** opção estará disponível para seleção.

1. Confirme sua escolha.

   As provas são enviadas aos destinatários que foram configurados.

   ![](assets/bat_select2.png)

1. Você pode exibir suas provas usando a lista **[!UICONTROL Proofs]** suspensa.

   ![](assets/bat_view.png)

1. Selecione uma prova para acessar seu resumo. Para um email, se você selecionou a opção de renderização **de** email como o tipo de prova, o **[!UICONTROL Access email rendering]** ícone será exibido à direita do rótulo de prova. Consulte Renderização [por](../../sending/using/email-rendering.md)email.

   ![](assets/bat_view2.png)

Dependendo dos comentários das pessoas que recebem a prova, você pode ser solicitado a modificar o conteúdo da entrega. Uma vez que as modificações tenham sido feitas, é necessário reiniciar a preparação do email e, em seguida, reenviar uma prova. Cada nova prova pode ser acessada usando o **[!UICONTROL Show proofs]** botão.

É necessário enviar tantas provas quantas forem necessárias até que você tenha concluído o conteúdo de sua entrega. Quando isso estiver concluído, você poderá enviar a entrega para o destino principal e fechar o ciclo de aprovação.

## Configurar a linha de assunto das provas {#configuring-proofs-subject-line}

Quando uma prova é enviada, sua linha de assunto é configurada por padrão com o prefixo **&quot;Prova&quot;** , bem como um contador que indica o número da prova.

![](assets/proof-prefix.png)

Para alterar a linha de assunto padrão a ser usada, siga estas etapas:

1. No painel de mensagens, clique no **[!UICONTROL Open properties]** botão.
1. Na **[!UICONTROL Advanced parameters]** seção, defina o prefixo que você deseja usar por padrão na linha de assunto.

Para ocultar o número da prova na linha de assunto, ative a **[!UICONTROL Hide proof prefix counter]** opção.

>[!NOTE]
>
>Se desejar ocultar o prefixo de prova inteiro, deixe o **[!UICONTROL Subject line prefix]** campo em branco.

![](assets/proof-prefix-configuration.png)

1. Clique em **[!UICONTROL Confirm]**. As configurações serão aplicadas por padrão a todas as provas enviadas para a mensagem selecionada.

**Tópico relacionado:**

* [Envio de um teste, preparação e envio de um vídeo por email](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/sending-test-preparing-sending-email.html)
* [Testando mensagens de email usando perfis](../../sending/using/testing-messages-using-target.md)direcionados.
* [Gerenciamento de perfis](../../audiences/using/managing-test-profiles.md)de teste.
* [Visualizar mensagens](../../sending/using/previewing-messages.md)
* [Configuração do canal de email](../../administration/using/configuring-email-channel.md)
