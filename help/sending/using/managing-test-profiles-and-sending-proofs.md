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
source-git-commit: 27447db9ee0dd387c39976c7bd4e157a4b7899b8

---


# Gerenciamento de perfis de teste e envio de testes{#managing-test-profiles-and-sending-proofs}

## Sobre perfis de teste {#about-test-profiles}

Os perfis de teste permitem direcionar destinatários adicionais que não correspondem aos critérios de definição de metas definidos. Elas são adicionadas ao público-alvo de uma mensagem para detectar qualquer uso fraudulento do banco de dados do destinatário ou para garantir que os emails cheguem às caixas de entrada.

Você pode gerenciar seus perfis de teste no menu **[!UICONTROL Profiles & audiences > Test profiles]** avançado.

Um perfil de teste contém informações de contato fictícias ou informações de contato controladas pelo remetente, que podem ser usadas em uma mensagem nos seguintes contextos:

* Para enviar **testes**: a Prova é uma mensagem específica usada para verificar a mensagem antes de enviar a entrega finalizada para os destinatários. Um perfil de teste Prova é responsável pela verificação da entrega, em relação ao seu conteúdo e formato. Consulte [Enviar testes](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).
* Para **renderização por email**: o perfil de teste de renderização por email é usado para verificar a forma como uma mensagem é exibida de acordo com a caixa de entrada de mensagem que a recebe. Por exemplo, webmail, serviço de mensagens, dispositivos móveis etc. Consulte [Renderização de email](../../sending/using/email-rendering.md).

   O uso **de renderização** por email é somente leitura. Os perfis de teste com esse uso estão disponíveis apenas para uso out-of-the-box no Adobe Campaign.

* Como **uma captura**: a mensagem é enviada para o perfil de teste assim que é enviada para o destino principal. Consulte [Uso de capturas](../../sending/using/managing-test-profiles-and-sending-proofs.md#using-traps).
* Para **visualizar** mensagens: um perfil de teste pode ser selecionado ao visualizar uma mensagem para testar os elementos de personalização. Consulte [Visualizar mensagens](/help/sending/using/previewing-messages.md).

![](assets/test_profile.png)

## Gerenciamento de perfis de teste {#managing-test-profiles}

### Criação de perfis de teste {#creating-test-profiles}

1. No menu avançado, por meio do logotipo do Adobe Campaign, selecione **Perfis e públicos-alvo &gt; Testar perfis** para acessar a lista de perfis de teste.

   ![](assets/test_profile_creation_1.png)

1. No **[!UICONTROL Test profiles]** painel, clique **em Criar**.

   ![](assets/test_profile_creation_2.png)

1. Insira os dados desse perfil.

   ![](assets/test_profile_creation_3.png)

1. Selecione o uso que pretende para o perfil de teste.

   ![](assets/test_profile_creation_4.png)

1. Insira os canais **[!UICONTROL Email, Telephone, Mobile, Mobile app]** de contato, assim como o endereço do perfil de teste, se necessário.

   >[!NOTE]
   >
   >É possível definir um formato de email preferencial: **[!UICONTROL Text]** ou **[!UICONTROL HTML]**.

1. Especifique um tipo de evento e os dados para esse evento se desejar usar esse perfil de teste para testar a personalização de uma mensagem transacional.
1. Clique **[!UICONTROL Create]** em para salvar o perfil de teste.

O perfil de teste será então adicionado à lista de perfis.

**Tópico relacionado:**

[Criação de um vídeo de perfil](https://helpx.adobe.com/campaign/kt/acs/using/acs-test-profiles-feature-video-use.html) de teste

### Edição de perfis de teste {#editing-test-profiles}

Para editar um perfil de teste e consultar os dados vinculados a ele, ou para modificá-lo:

1. Selecione o perfil de teste que deseja editar clicando em sua imagem.
1. Consulte ou modifique os campos.

   ![](assets/test_profile_edit.png)

1. Clique **[!UICONTROL Save]** em se tiver inserido suas alterações ou selecione o nome do perfil de teste em seguida **[!UICONTROL Test profiles]** na seção na parte superior da tela para retornar ao painel de perfis de teste.

## Envio de testes {#sending-proofs}

Uma prova é uma mensagem específica que permite testar uma mensagem antes de enviá-la para o destino principal.

Os destinatários da prova são responsáveis pela aprovação da mensagem (seu conteúdo e formulário). Eles são definidos nos perfis **de teste**. Para saber mais sobre isso, consulte [Gerenciamento de perfis de teste](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles).

Para enviar uma prova, os perfis de teste devem ser incluídos no público-alvo da sua mensagem.

Em uma mensagem:

1. Clique no **[!UICONTROL Send a test]** botão.

   ![](assets/bat_select.png)

1. Selecione o tipo de prova que deseja usar:

   * **[!UICONTROL Email rendering]**: selecione esta opção para testar a maneira como sua mensagem é recebida de acordo com as caixas de entrada direcionadas. Para obter mais informações, consulte Renderização [de email](../../sending/using/email-rendering.md).
   * **[!UICONTROL Proof]**: selecione essa opção para testar a mensagem antes de enviá-la para o destino principal. Os destinatários de prova são responsáveis pela aprovação da entrega, verificando seu conteúdo e seu formato.
   * **[!UICONTROL Proof + Email rendering]**: essa opção combina as duas opções anteriores.
   ![](assets/bat_select1.png)

1. Confirme sua escolha.

   Os testes são enviados para os perfis de teste.

   ![](assets/bat_select2.png)

1. Você pode exibir seus testes usando a **[!UICONTROL Proofs]** lista suspensa.

   ![](assets/bat_view.png)

1. Selecione uma prova para acessar seu resumo. Para um email, se você tiver selecionado **a opção de renderização** por email como o tipo de prova, o **[!UICONTROL Access email rendering]** ícone será exibido à direita do rótulo de prova. Consulte [Renderização de email](../../sending/using/email-rendering.md).

   ![](assets/bat_view2.png)

Dependendo dos comentários das pessoas que recebem a prova, talvez seja necessário modificar o conteúdo da entrega. Depois que as modificações tiverem sido executadas, será necessário reiniciar a preparação de e-mails e enviar uma prova novamente. Cada nova prova pode ser acessada usando o **[!UICONTROL Show proofs]** botão.

É necessário enviar quantos testes forem necessários até que você tenha finalizado o conteúdo da entrega. Assim que isso for feito, você poderá enviar a entrega para o destino principal e fechar o ciclo de aprovação.

**Tópico relacionado:**

[Envio de um teste, preparação e envio](https://helpx.adobe.com/campaign/kt/acs/using/acs-sending-test-preparing-sending-email-feature-video-use.html) de um vídeo por email

## Uso de capturas {#using-traps}

Ao usar trappings, a mensagem é enviada para o perfil de teste assim que é enviada para o destino principal, como um meio de identificar se o arquivo cliente está sendo usado fraudulentemente.

Originalmente, os trappings foram projetados para entregas de mala direta. Permitem:
* Verifique se o seu provedor de mala direta está enviando a comunicação.
* Receba o email ao mesmo tempo e nas mesmas condições dos clientes.
* Mantenha uma cópia exata do email enviado.
* Verifique se sua lista de clientes não é usada indevidamente pelo seu provedor de mala direta. Na verdade, se qualquer outra comunicação for enviada para o endereço do seu perfil de teste, seu arquivo cliente pode ter sido usado sem seu conhecimento. Esse o motivo pelo qual o endereço do perfil de teste só deve ser usado para essa finalidade.

Para obter mais informações sobre como adicionar capturas ao público-alvo de um mala direta, consulte [Adicionar perfis de teste e de trapping](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles).

Para os outros canais de comunicação, você pode adicionar perfis de teste de captura à meta principal para:
* Verifique se a mensagem foi enviada com êxito.
* Obtenha e mantenha uma cópia exata da sua mensagem.
* Rastreie quando foi enviado e recebido.

Para usar um perfil de teste como trapping, ele deve ser incluído no público-alvo da sua mensagem.

>[!NOTE]
>
>Ao contrário de perfis de teste usados para [provas](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) ou [renderização por email](../../sending/using/email-rendering.md), a mensagem é enviada ao mesmo tempo para o destino principal e para os perfis de teste usados como capturas.

Ao definir o público-alvo de uma mensagem:

1. Na **[!UICONTROL Test profiles]** guia, selecione um perfil de teste. Verifique se ela tem **[!UICONTROL Trap]** o uso pretendido.

   ![](assets/trap_select.png)

1. Quando o conteúdo da mensagem estiver pronto, clique no **[!UICONTROL Prepare]** botão. Consulte [Preparação do envio](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >Selecione um destino principal. Caso contrário, a mensagem não poderá ser enviada.

1. Clique no **[!UICONTROL Confirm]** botão. Consulte [Confirmação do envio](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

A mensagem é enviada para o destino principal e para o perfil de teste.

>[!NOTE]
>
>Ao usar um perfil de teste como captura, para qualquer campo enriquecido em uma mensagem, os dados adicionais correspondentes são escolhidos aleatoriamente de um perfil direcionado real e atribuído ao perfil de teste de captura. Para obter mais informações sobre enriquecimento, consulte [este exemplo](../../automating/using/enrichment.md#example--enriching-profile-data-with-data-contained-in-a-file).
