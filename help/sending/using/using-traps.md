---
title: Uso de traps
description: Saiba como usar armadilhas em mensagens.
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
source-git-commit: a7c2d444b7d971124b676fa2392b51aab40e5629

---


# Uso de traps {#using-traps}

Ao usar traps, a mensagem é enviada ao perfil [de](../../audiences/using/managing-test-profiles.md) teste da mesma forma que é enviada para o destino principal, como um meio de identificar se o arquivo cliente está sendo usado de forma fraudulenta.

As armadilhas foram originalmente projetadas para entregas de mala direta. Eles permitem que você:

* Verifique se seu provedor de mala direta está realmente enviando a comunicação.
* Receba o email ao mesmo tempo e nas mesmas condições que seus clientes.
* Guarde uma cópia exata do correio enviado.
* Verifique se sua lista de clientes não é usada incorretamente pelo seu provedor de mala direta. Na verdade, se qualquer outra comunicação for enviada para o endereço do seu perfil de teste, seu arquivo cliente pode ter sido usado sem que você saiba. É por isso que o endereço do perfil de teste só deve ser usado para esse fim.

Para obter mais informações sobre como adicionar traps ao público-alvo de uma mala direta, consulte [Adicionar perfis](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)de teste e trapping.

Para outros canais de comunicação, você pode adicionar perfis de teste de armadilha ao seu destino principal para:

* Verifique se sua mensagem foi enviada com êxito.
* Obtenha e guarde uma cópia exata da sua mensagem.
* Rastrear quando foi enviado e recebido.

Para usar um perfil de teste como armadilha, ele deve ser incluído no público-alvo da sua mensagem.

>[!NOTE]
>
>Ao contrário dos perfis de teste usados para [provas](../../sending/using/sending-proofs.md) ou renderização [por](../../sending/using/email-rendering.md)email, a mensagem é enviada ao mesmo tempo para o destino principal e para os perfis de teste usados como armadilhas.

Ao definir o público-alvo de uma mensagem:

1. Na **[!UICONTROL Test profiles]** guia, selecione um perfil de teste. Certifique-se de que tem **[!UICONTROL Trap]** o uso pretendido.

   ![](assets/trap_select.png)

1. Quando o conteúdo da mensagem estiver pronto, clique no **[!UICONTROL Prepare]** botão. See [Preparing the send](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >Certifique-se de selecionar um destino principal. Caso contrário, sua mensagem não poderá ser enviada.

1. Clique no botão **[!UICONTROL Confirm]**. See [Confirming the send](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

A mensagem é enviada para o destino principal e para o perfil de teste.

Você pode usar traps ao enviar mensagens transacionais. Nesse caso, o perfil de teste receberá uma mensagem por configuração de evento. Para obter mais informações sobre mensagens transacionais, consulte esta [seção](../../channels/using/about-transactional-messaging.md).

>[!NOTE]
>
>Ao usar um perfil de teste como armadilha, para qualquer campo enriquecido em uma mensagem, os dados adicionais correspondentes são escolhidos aleatoriamente de um perfil direcionado real e atribuídos ao perfil de teste de armadilha. Para obter mais informações sobre o enriquecimento, consulte [este exemplo](../../automating/using/enrichment.md#example--enriching-profile-data-with-data-contained-in-a-file).
