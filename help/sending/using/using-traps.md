---
solution: Campaign Standard
product: campaign
title: Uso de traps
description: Saiba como usar coberturas em mensagens.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Seed Address
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 2%

---


# Uso de traps {#using-traps}

Ao usar coberturas, a mensagem é enviada para o [perfil de teste](../../audiences/using/managing-test-profiles.md) da mesma forma que é enviada para o público-alvo principal, como um meio de identificar se o arquivo do cliente está sendo usado de forma fraudulenta.

As coberturas foram originalmente projetadas para deliveries de correspondência direta. Eles permitem:

* Verifique se seu provedor de correspondência direta está realmente enviando a comunicação.
* Receba o email ao mesmo tempo e nas mesmas condições que seus clientes.
* Mantenha uma cópia exata do email enviado.
* Verifique se sua lista de clientes não foi usada incorretamente pelo provedor de correspondência direta. Na verdade, se qualquer outra comunicação for enviada para o endereço do seu perfil de teste, o arquivo do cliente pode ter sido usado sem que você saiba. É por isso que o endereço do perfil de teste deve ser usado apenas para essa finalidade.

Para obter mais informações sobre como adicionar traps ao público-alvo de uma correspondência direta, consulte [Adicionar perfis de teste e trap](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles).

Para os outros canais de comunicação, você pode adicionar perfis de teste de trap ao target principal para:

* Verifique se a mensagem foi enviada com êxito.
* Obtenha e mantenha uma cópia exata da sua mensagem.
* Rastreie quando ele foi enviado e recebido.

Para usar um perfil de teste como armadilha, ele deve ser incluído no público da sua mensagem.

>[!NOTE]
>
>Ao contrário dos perfis de teste usados para [provas](../../sending/using/sending-proofs.md) ou [renderização de email](../../sending/using/email-rendering.md), a mensagem é enviada ao mesmo tempo para o público-alvo principal e para os perfis de teste usados como armadilhas.

Ao definir o público de uma mensagem:

1. Na guia **[!UICONTROL Test profiles]** , selecione um perfil de teste. Certifique-se de que ele tenha **[!UICONTROL Trap]** como o uso pretendido.

   ![](assets/trap_select.png)

1. Quando o conteúdo da mensagem estiver pronto, clique no botão **[!UICONTROL Prepare]**. Consulte [Preparando o envio](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >Selecione um target principal. Caso contrário, sua mensagem não poderá ser enviada.

1. Clique no botão **[!UICONTROL Confirm]**. Consulte [Confirmação do envio](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

A mensagem é enviada ao público-alvo principal e ao perfil de teste.

Você pode usar traps ao enviar mensagens transacionais. Nesse caso, o perfil de teste receberá uma mensagem por configuração de evento. Para obter mais informações sobre mensagens transacionais, consulte esta [seção](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>Ao usar um perfil de teste como uma armadilha, para qualquer campo enriquecido em uma mensagem, os dados adicionais correspondentes são coletados aleatoriamente de um perfil direcionado real e atribuídos ao perfil de teste de armadilha. Para obter mais informações sobre enriquecimento, consulte [este exemplo](../../automating/using/enriching-profile-data-file.md).
