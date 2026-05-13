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
TQID: https://experienceleague.adobe.com/1dwRaqZSGzlWwOv6ftIpV5V3poCwN3hzdRrQdk0WQsE
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
subfeature_v2:
  - id: d3b34fea-a110-482f-adb2-aae8d686bac8
  - id: ede6e1ec-9279-415e-b828-a09735018d48
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 458
ht-degree: 2%

---

# Utilização de traps {#using-traps}

Ao usar coberturas, a mensagem é enviada para o [perfil de teste](../../audiences/using/managing-test-profiles.md) da mesma forma que é enviada para o público alvo principal, como um meio de identificar se o arquivo do cliente está sendo usado de forma fraudulenta.

As coberturas foram originalmente projetadas para entregas de correspondência direta. Eles permitem:

* Verifique se o provedor de correspondência direta está realmente enviando a comunicação.
* Receba o email ao mesmo tempo e nas mesmas condições que seus clientes.
* Manter uma cópia exata do email enviado.
* Verifique se a lista de clientes não foi usada incorretamente pelo provedor de correspondência direta. Na verdade, se qualquer outra comunicação for enviada para o endereço do seu perfil de teste, o arquivo do cliente pode ter sido usado sem o seu conhecimento. É por isso que o endereço do perfil de teste deve ser usado somente para essa finalidade.

Para obter mais informações sobre como adicionar interceptações ao público de correspondência direta, consulte [Adicionar perfis de teste e interceptação](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles).

Para os outros canais de comunicação, você pode adicionar perfis de teste de trap ao público alvo principal para:

* Verifique se a mensagem foi enviada com êxito.
* Obtenha e guarde uma cópia exata da sua mensagem.
* Rastrear quando foi enviado e recebido.

Para usar um perfil de teste como interceptação, ele deve ser incluído no público-alvo da sua mensagem.

>[!NOTE]
>
>Ao contrário dos perfis de teste usados para [provas](../../sending/using/sending-proofs.md) ou [renderização de email](../../sending/using/email-rendering.md), a mensagem é enviada ao mesmo tempo para o destino principal e para os perfis de teste usados como armadilhas.

Ao definir o público de uma mensagem:

1. Na guia **[!UICONTROL Test profiles]**, selecione um perfil de teste. Verifique se ele tem **[!UICONTROL Trap]** como o uso pretendido.

   ![](assets/trap_select.png)

1. Quando o conteúdo da mensagem estiver pronto, clique no botão **[!UICONTROL Prepare]**. Consulte [Preparando o envio](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >Verifique se você selecionou um público alvo principal. Caso contrário, sua mensagem não poderá ser enviada.

1. Clique no botão **[!UICONTROL Confirm]**. Consulte [Confirmação do envio](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

A mensagem é enviada para o público-alvo principal e para o perfil de teste.

Você pode usar coberturas ao enviar mensagens transacionais. Nesse caso, o perfil de teste receberá uma mensagem por configuração de evento. Para obter mais informações sobre mensagens transacionais, consulte esta [seção](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>Ao usar um perfil de teste como trap, os campos enriquecidos em uma mensagem terão seus dados adicionais correspondentes selecionados aleatoriamente de um perfil direcionado real e atribuídos ao perfil de teste de trap. No entanto, esteja ciente de que, se o perfil direcionado real for excluído devido a regras de tipologia aplicadas durante a primeira preparação da mensagem, a preparação do delivery falhará. Essa falha ocorre porque os valores de campo enriquecidos não podem ser substituídos pelo perfil de cobertura. Consequentemente, as regras de tipologia de exclusão podem não se aplicar corretamente aos recipients reais.
>
>Para evitar essa situação, evite usar perfis de teste de trap simultaneamente com regras de filtragem ou fadiga na tipologia transacional. Saiba mais sobre enriquecimento. Para obter mais informações sobre enriquecimento, consulte [este exemplo](../../automating/using/enriching-profile-data-file.md).
