---
title: Envio de provas
description: Saiba como enviar provas.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Proofs
role: User
level: Intermediate
exl-id: 75b64c43-f066-45e7-8d61-95eba8f52b05
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 98%

---

# Envio de provas {#sending-proofs}

## Sobre provas {#about-proofs}

Uma prova é uma mensagem especial com a qual é possível testar um delivery antes de enviá-lo ao público alvo principal. Os destinatários da prova são responsáveis pela aprovação da mensagem (seu conteúdo e formato).

Há dois tipos de destinatários de prova:

* **Perfis de teste** permitem segmentar destinatários adicionais que não correspondam aos critérios de direcionamento definidos.

  Eles podem ser adicionados ao público de uma mensagem para detectar qualquer uso fraudulento do banco de dados do seu destinatário ou para garantir que os emails cheguem às caixas de entrada. Para mais informações, consulte [Gerenciamento de perfis de teste](../../audiences/using/managing-test-profiles.md).

  >[!NOTE]
  >
  >Para enviar uma prova, você precisa incluir os perfis de teste no público da sua mensagem.

* **Perfis de substituição** permitem que você se posicione como um dos perfis segmentados e obtenha uma representação exata da mensagem que o perfil receberá. Para mais informações, consulte [Testar mensagens de email usando perfis segmentados](../../sending/using/testing-messages-using-target.md).

  >[!NOTE]
  >
  >Esse recurso está disponível somente para o canal de email.

## Envio de uma prova {#sending-a-proof}

Para enviar provas, siga estas etapas:

1. Verifique se os destinatários da prova foram configurados:
   * Os **perfis de teste** devem ser incluídos no público da sua mensagem.
   * Os **perfis de substituição** devem ser adicionados assim que a preparação da mensagem tiver sido realizada com êxito (consulte [esta seção](../../sending/using/testing-messages-using-target.md)).

1. Clique no botão **[!UICONTROL Send a test]**.

   ![](assets/bat_select.png)

1. Selecione o tipo de prova que deseja usar:

   * **[!UICONTROL Email rendering]**: selecione essa opção para testar a maneira com que sua mensagem é recebida de acordo com as caixas de entrada segmentadas. Para mais informações, consulte [Renderização de email](../../sending/using/email-rendering.md).
   * **[!UICONTROL Proof]**: selecione essa opção para testar a mensagem antes de enviá-la para o público alvo principal. Os destinatários de prova são responsáveis pela aprovação da entrega, verificando o conteúdo e o formato.
   * **[!UICONTROL Proof + Email rendering]**: essa opção combina as duas opções anteriores.

   ![](assets/bat_select1.png)

   >[!NOTE]
   >
   >A renderização de email está disponível somente com perfis de teste. Se nenhum perfil de teste tiver sido adicionado à mensagem, somente a opção **[!UICONTROL Proof]** estará disponível para seleção.

1. Confirme sua escolha.

   As provas são enviadas para os destinatários que foram configurados.

   ![](assets/bat_select2.png)

1. É possível exibir suas provas na lista suspensa **[!UICONTROL Proofs]**.

   ![](assets/bat_view.png)

1. Selecione uma prova para acessar o resumo. Para um email, se você selecionou a opção **Renderização de email** como o tipo de prova, o ícone **[!UICONTROL Access email rendering]** será exibido à direita do rótulo da prova. Consulte [Renderização de email](../../sending/using/email-rendering.md).

   ![](assets/bat_view2.png)

Dependendo dos comentários das pessoas que recebem a prova, talvez você tenha que modificar o conteúdo da entrega. Após realizar as modificações, é necessário reiniciar a preparação do email e, em seguida, reenviar uma prova. Cada nova prova pode ser acessada usando o botão **[!UICONTROL Show proofs]**.

Você precisa enviar quantas provas forem necessárias até concluir o conteúdo da sua entrega. Finalizada essa etapa, você poderá enviar a entrega para o público alvo principal e fechar o ciclo de aprovação.

## Configuração da linha de assunto da prova {#configuring-proofs-subject-line}

Ao enviar uma prova, a linha de assunto é configurada por padrão com o prefixo **&quot;Prova&quot;**, e também um contador, que indica o número da prova.

![](assets/proof-prefix.png)

Para alterar a linha de assunto padrão a ser usada, siga estas etapas:

1. No painel da mensagem, clique no botão **[!UICONTROL Open properties]**.
1. Na seção **[!UICONTROL Advanced parameters]**, defina o prefixo que você deseja usar por padrão na linha de assunto.

Para ocultar o número da prova na linha de assunto, ative a opção **[!UICONTROL Hide proof prefix counter]**.

>[!NOTE]
>
>Se quiser ocultar o prefixo de prova inteiro, deixe o campo **[!UICONTROL Subject line prefix]** em branco.

![](assets/proof-prefix-configuration.png)

1. Clique em **[!UICONTROL Confirm]**. As configurações serão aplicadas por padrão a todas as provas enviadas para a mensagem selecionada.

**Tópicos relacionados:**

* Vídeo [Envio de teste, preparação e envio de email](../../sending/using/get-started-sending-messages.md#video)
* [Teste de mensagens de email usando perfis direcionados](../../sending/using/testing-messages-using-target.md)
* [Gerenciamento de perfis de teste](../../audiences/using/managing-test-profiles.md)
* [Visualização de mensagens](../../sending/using/previewing-messages.md)
* [Configuração do canal de email](../../administration/using/configuring-email-channel.md)
