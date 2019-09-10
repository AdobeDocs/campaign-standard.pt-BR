---
title: Definição do público-alvo de mala direta
seo-title: Definição do público-alvo de mala direta
description: Definição do público-alvo de mala direta
seo-description: Saiba como definir a meta para sua entrega de mala direta.
page-status-flag: nunca ativado
uuid: f 843 e 368-5 c 07-4 b 53-8943-46 f 7 bf 45 b 62 b
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: direta
discoiquuid: f 993 d 1 b 6-4 b 9 a -4 f 95-81 fc -60 c 126211 bd 2
context-tags: entrega, directmailcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 27447db9ee0dd387c39976c7bd4e157a4b7899b8

---


# Definição do público-alvo de mala direta{#defining-the-direct-mail-audience}

Você pode definir o público-alvo no assistente de criação ou clicando na **seção Público-alvo** do painel de entrega.

![](assets/direct_mail_15.png)

## Definição do destino principal {#defining-the-main-target}

Para mala direta, os perfis direcionados são aqueles que serão incluídos no arquivo de extração que você enviará para o seu provedor de mala direta.

Para cada perfil direcionado, uma nova linha é adicionada no arquivo de extração. A quantidade de informações de perfil incluída para cada destinatário é definida na [tela Definição da tela de extração](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) .

>[!CAUTION]
>
>Verifique se os perfis incluem um endereço postal, pois essas informações são essenciais para o provedor de mala direta. Certifique-se também de marcar a **[!UICONTROL Address specified]** caixa nas informações de seus perfis. Consulte [Recommendations](../../channels/using/about-direct-mail.md#recommendations).

## Adição de perfis de teste e captura {#adding-test-and-trap-profiles}

Adicione perfis de teste para testar seu arquivo com um pequeno número de perfis. Isso permite criar rapidamente uma amostra de arquivo para testar e validar a estrutura antes de preparar o arquivo real. Consulte [Gerenciamento de perfis de teste e envio de testes](../../sending/using/managing-test-profiles-and-sending-proofs.md).

O uso de capturas é essencial para o envio de entregas por email. Eles permitem que você verifique se seu provedor de mala direta está enviando a comunicação e que não está enviando sua lista de clientes para outro provedor. Consulte [Uso de capturas](../../sending/using/managing-test-profiles-and-sending-proofs.md#using-traps).

Para entregas de mala direta, as capturas são adicionadas durante a extração e misturadas no documento de saída. Por padrão, são inseridos na ordem de classificação do arquivo de saída, mas você pode optar por inseri-los no final ou no início do arquivo. Ao definir o público, selecione a opção desejada na **[!UICONTROL Trap insertion mode]** guia.

![](assets/direct_mail_trap_insertion_mode.png)
