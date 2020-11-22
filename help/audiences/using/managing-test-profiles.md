---
solution: Campaign Standard
product: campaign
title: Gerenciamento de perfis de teste
description: Saiba como gerenciar perfis de teste.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 100%

---


# Gerenciamento de perfis de teste {#managing-test-profiles}

## Sobre perfis de teste {#about-test-profiles}

Os perfis de teste permitem direcionar recipients adicionais que não correspondem aos critérios de direcionamento definidos. Eles são adicionados ao público-alvo de uma mensagem para detectar qualquer uso fraudulento do seu banco de dados de recipients ou para garantir que os emails cheguem às caixas de entrada.

Você pode gerenciar os perfis de teste no menu avançado **[!UICONTROL Profiles & audiences > Test profiles]**.

Um perfil de teste contém informações de contato fictícias, ou informações de contato controladas pelo remetente, que então podem ser usadas em uma mensagem nos seguintes contextos:

* Para enviar **Provas**: a Prova é uma mensagem específica usada para verificar a mensagem antes de enviar o delivery finalizado para os recipients. Um perfil de teste de Prova tem o objetivo de verificar o delivery no que diz respeito ao seu conteúdo e formato. Consulte [Enviar provas](../../sending/using/sending-proofs.md).
* Para **Renderização de email**: o perfil de teste Renderização de email é usado para verificar de que maneira uma mensagem é exibida, de acordo com a caixa de entrada de mensagens que a recebe. Por exemplo, webmail, serviço de mensagens, celular etc. Consulte [Renderização de email](../../sending/using/email-rendering.md).

   O uso da **Renderização de email** é somente leitura. Perfis de teste com esse uso só estão disponíveis para uso imediato no Adobe Campaign.

* Como uma **Trap**: a mensagem é enviada ao perfil de teste da mesma maneira que é enviada ao destino principal. Consulte [Uso de coberturas](../../sending/using/using-traps.md).
* Para **Pré-visualização** de mensagens: um perfil de teste pode ser selecionado ao visualizar uma mensagem para testar os elementos de personalização. Consulte [Pré-visualização de mensagens](/help/sending/using/previewing-messages.md).

![](assets/test_profile.png)

## Criar perfis de teste {#creating-test-profiles}

1. No menu avançado, no logotipo do Adobe Campaign, selecione **Profiles &amp; audiences > Test profiles** para acessar a lista de perfis de teste.

   ![](assets/test_profile_creation_1.png)

1. No painel **[!UICONTROL Test profiles]**, clique em **Create**.

   ![](assets/test_profile_creation_2.png)

1. Insira os dados desse perfil.

   ![](assets/test_profile_creation_3.png)

1. Selecione o uso pretendido para seu perfil de teste.

   ![](assets/test_profile_creation_4.png)

1. Insira os canais de contato **[!UICONTROL Email, Telephone, Mobile, Mobile app]**, bem como o endereço do perfil de teste, se necessário.

   >[!NOTE]
   >
   >Você pode definir um formato do email preferencial: **[!UICONTROL Text]** ou **[!UICONTROL HTML]**.

1. Especifique um tipo de evento e os dados para esse evento se quiser usar esse perfil de teste para testar a personalização de uma mensagem transacional.
1. Clique em **[!UICONTROL Create]** para salvar o perfil de teste.

O perfil de teste será então adicionado à lista de perfis.

**Tópicos relacionados:**

Vídeo [Criar um perfil de teste](https://docs.adobe.com/content/help/pt-BR/campaign-standard-learn/tutorials/profiles-and-audiences/test-profiles.translate.html)

## Editar perfis de teste {#editing-test-profiles}

Para editar um perfil de teste e consultar os dados vinculados a ele ou para modificá-lo:

1. Selecione o perfil de teste que deseja editar clicando na imagem.
1. Consulte ou modifique os campos.

   ![](assets/test_profile_edit.png)

1. Clique em **[!UICONTROL Save]** se tiver inserido as alterações ou selecione o nome do perfil de teste e depois **[!UICONTROL Test profiles]** na seção localizada na parte superior da tela para retornar ao painel de perfis de teste.
