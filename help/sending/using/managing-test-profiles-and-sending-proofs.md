---
title: Gerenciamento de perfis de teste e envio de testes
seo-title: Gerenciamento de perfis de teste e envio de testes
description: Gerenciamento de perfis de teste e envio de testes
seo-description: Saiba como gerenciar perfis de teste e testes.
page-status-flag: nunca ativado
uuid: eb 4 d 893 b -3724-4 b 15-9312-1 ec 74784368 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviando
content-type: reference
topic-tags: preparando e testando-messages
discoiquuid: 37320 ec 5-196 c -4260-8156-98932 da 3 e 4 a 5
context-tags: Seedmember, visão geral
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# Managing test profiles and sending proofs{#managing-test-profiles-and-sending-proofs}

## About test profiles {#about-test-profiles}

Os perfis de teste permitem direcionar destinatários adicionais que não correspondem aos critérios de definição de metas definidos. Elas são adicionadas ao público-alvo de uma mensagem para detectar qualquer uso fraudulento do banco de dados do destinatário ou para garantir que os emails cheguem às caixas de entrada.

You can manage your test profiles from the advanced menu **[!UICONTROL Profiles & audiences > Test profiles]**.

Um perfil de teste contém informações de contato fictícias ou informações de contato controladas pelo remetente, que podem ser usadas em uma mensagem nos seguintes contextos:

* For sending **Proofs**: the Proof is a specific message used to check the message before sending the finalized delivery to recipients. Um perfil de teste Prova é responsável pela verificação da entrega, em relação ao seu conteúdo e formato. See [Sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).
* For **Email rendering**: the Email rendering test profile is used to check the way in which a message is displayed according to the message inbox that receives it. Por exemplo, webmail, serviço de mensagens, dispositivos móveis etc. See [Email rendering](../../sending/using/email-rendering.md).

   The **Email rendering** use is read-only. Os perfis de teste com esse uso estão disponíveis apenas para uso out-of-the-box no Adobe Campaign.

* As a **Trap**: the message is sent to the test profile just as it is sent to the main target, as a means to identify whether your client file is being used fraudulently.
* To **Preview** messages: a test profile can be selected when previewing a message to test the personalization elements.

![](assets/test_profile.png)

## Managing test profiles {#managing-test-profiles}

### Creating test profiles {#creating-test-profiles}

1. From the advanced menu, via the Adobe Campaign logo, select **Profiles &amp; audiences &gt; Test profiles** to access the list of test profiles.

   ![](assets/test_profile_creation_1.png)

1. From the **[!UICONTROL Test profiles]** dashboard, click **Create**.

   ![](assets/test_profile_creation_2.png)

1. Insira os dados desse perfil.

   ![](assets/test_profile_creation_3.png)

1. Selecione o uso que pretende para o perfil de teste.

   ![](assets/test_profile_creation_4.png)

1. Enter the contact channels **[!UICONTROL Email, Telephone, Mobile, Mobile app]**, as well as the test profile address if necessary.

   >[!NOTE]
   >
   >You can define a preferred email format: **[!UICONTROL Text]** or **[!UICONTROL HTML]**.

1. Especifique um tipo de evento e os dados para esse evento se desejar usar esse perfil de teste para testar a personalização de uma mensagem transacional.
1. Click **[!UICONTROL Create]** to save the test profile.

O perfil de teste será então adicionado à lista de perfis.

**Tópico relacionado:**

[Criação de um vídeo de perfil](https://helpx.adobe.com/campaign/kt/acs/using/acs-test-profiles-feature-video-use.html) de teste

### Editing test profiles {#editing-test-profiles}

Para editar um perfil de teste e consultar os dados vinculados a ele, ou para modificá-lo:

1. Selecione o perfil de teste que deseja editar clicando em sua imagem.
1. Consulte ou modifique os campos.

   ![](assets/test_profile_edit.png)

1. Click **[!UICONTROL Save]** if you have entered your changes, or select the name of the test profile then **[!UICONTROL Test profiles]** in the section at the top of the screen to go back to the test profiles dashboard.

## Sending proofs {#sending-proofs}

Uma prova é uma mensagem específica que permite testar uma mensagem antes de enviá-la para o destino principal.

Os destinatários da prova são responsáveis pela aprovação da mensagem (seu conteúdo e formulário). They are defined in the **Test profiles**. For more on this, see [Managing test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles).

Para enviar uma prova, os perfis de teste devem ser incluídos no público-alvo da sua mensagem.

Em uma mensagem:

1. Click the **[!UICONTROL Send a test]** button.

   ![](assets/bat_select.png)

1. Selecione o tipo de prova que deseja usar:

   * **[!UICONTROL Email rendering]**: selecione esta opção para testar a maneira como sua mensagem é recebida de acordo com as caixas de entrada direcionadas. For more information, refer to [Email rendering](../../sending/using/email-rendering.md).
   * **[!UICONTROL Proof]**: selecione essa opção para testar a mensagem antes de enviá-la para o destino principal. Os destinatários de prova são responsáveis pela aprovação da entrega, verificando seu conteúdo e seu formato.
   * **[!UICONTROL Proof + Email rendering]**: essa opção combina as duas opções anteriores.
   ![](assets/bat_select1.png)

1. Confirme sua escolha.

   Os testes são enviados para os perfis de teste.

   ![](assets/bat_select2.png)

1. You can view your proofs using the **[!UICONTROL Proofs]** drop-down list.

   ![](assets/bat_view.png)

1. Selecione uma prova para acessar seu resumo. For an email, if you have selected the **Email rendering** option as the proof type, the **[!UICONTROL Access email rendering]** icon is displayed on the right of the proof label. See [Email rendering](../../sending/using/email-rendering.md).

   ![](assets/bat_view2.png)

Dependendo dos comentários das pessoas que recebem a prova, talvez seja necessário modificar o conteúdo da entrega. Depois que as modificações tiverem sido executadas, será necessário reiniciar a preparação de e-mails e enviar uma prova novamente. Each new proof can be accessed using the **[!UICONTROL Show proofs]** button.

É necessário enviar quantos testes forem necessários até que você tenha finalizado o conteúdo da entrega. Assim que isso for feito, você poderá enviar a entrega para o destino principal e fechar o ciclo de aprovação.

**Tópico relacionado:**

[Envio de um teste, preparação e envio](https://helpx.adobe.com/campaign/kt/acs/using/acs-sending-test-preparing-sending-email-feature-video-use.html) de um vídeo por email
