---
title: Utilização de traps
description: Saiba como usar coberturas em mensagens.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Seed Address
role: User
level: Intermediate
exl-id: 0482a946-35b1-426f-8505-42adcd1c3bbb
source-git-commit: ee3ab5304e80ea098f7e172f6b3f4af4324e8eb4
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 2%

---

# Utilização de traps {#using-traps}

Ao usar coberturas, a mensagem é enviada para o [perfil de teste](../../audiences/using/managing-test-profiles.md) da mesma forma que é enviado para o target principal, como um meio de identificar se o arquivo do cliente está sendo usado de forma fraudulenta.

As coberturas foram originalmente projetadas para entregas de correspondência direta. Eles permitem:

* Verifique se o provedor de correspondência direta está realmente enviando a comunicação.
* Receba o email ao mesmo tempo e nas mesmas condições que seus clientes.
* Manter uma cópia exata do email enviado.
* Verifique se a lista de clientes não foi usada incorretamente pelo provedor de correspondência direta. Na verdade, se qualquer outra comunicação for enviada para o endereço do seu perfil de teste, o arquivo do cliente pode ter sido usado sem o seu conhecimento. É por isso que o endereço do perfil de teste deve ser usado somente para essa finalidade.

Para obter mais informações sobre como adicionar armadilhas ao público de correspondência direta, consulte [Adicionar perfis de teste e cobertura](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles).

Para os outros canais de comunicação, você pode adicionar perfis de teste de trap ao público alvo principal para:

* Verifique se a mensagem foi enviada com êxito.
* Obtenha e guarde uma cópia exata da sua mensagem.
* Rastrear quando foi enviado e recebido.

Para usar um perfil de teste como interceptação, ele deve ser incluído no público-alvo da sua mensagem.

>[!NOTE]
>
>Ao contrário dos perfis de teste usados para [provas](../../sending/using/sending-proofs.md) ou [renderização de email](../../sending/using/email-rendering.md), a mensagem é enviada ao mesmo tempo para o público-alvo principal e para os perfis de teste usados como armadilhas.

Ao definir o público de uma mensagem:

1. No **[!UICONTROL Test profiles]** selecione um perfil de teste. Verifique se ele **[!UICONTROL Trap]** como a utilização prevista.

   ![](assets/trap_select.png)

1. Quando o conteúdo da mensagem estiver pronto, clique no link **[!UICONTROL Prepare]** botão. Consulte [Preparação do envio](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >Verifique se você selecionou um público alvo principal. Caso contrário, sua mensagem não poderá ser enviada.

1. Clique no botão **[!UICONTROL Confirm]**. Consulte [Confirmação do envio](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

A mensagem é enviada para o público-alvo principal e para o perfil de teste.

Você pode usar coberturas ao enviar mensagens transacionais. Nesse caso, o perfil de teste receberá uma mensagem por configuração de evento. Para obter mais informações, consulte esta [seção](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>Ao usar um perfil de teste como trap, os campos enriquecidos em uma mensagem terão seus dados adicionais correspondentes selecionados aleatoriamente de um perfil direcionado real e atribuídos ao perfil de teste de trap. No entanto, esteja ciente de que, se o perfil direcionado real for excluído devido a regras de tipologia aplicadas durante a primeira preparação da mensagem, a preparação do delivery falhará. Essa falha ocorre porque os valores de campo enriquecidos não podem ser substituídos pelo perfil de cobertura. Consequentemente, as regras de tipologia de exclusão podem não se aplicar corretamente aos recipients reais.
>
>Para evitar essa situação, evite usar perfis de teste de trap simultaneamente com regras de filtragem ou fadiga na tipologia transacional. Saiba mais sobre enriquecimento. Para obter mais informações sobre enriquecimento, consulte [este exemplo](../../automating/using/enriching-profile-data-file.md).
